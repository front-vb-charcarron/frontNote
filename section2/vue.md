#vue 基础命令

运行vue

> npm run dev

导出并打包文件

>npm run build

安装package.json的模块和依赖

> npm i

###vue 基于 “依赖收集” 的响应式原理
```
// vue 基于 “依赖收集” 的响应式原理。

let Dep = { // 依赖收集器
    target: null  
};

const defineReactive = (obj, key, val) => {
    let deps = [];
    Object.defineProperty(obj, key, {
        get() {
            console.log(`${key}被读取！`);
            if (Dep.target && deps.indexOf(Dep.target) === -1) { 
                deps.push(Dep.target); // 在读取bgg.weight和bgg.height时把依赖保存起来，也完成了依赖关联。
            }

            return val;
        },
        set(newVal) { 
            console.log(`${key}被修改！`);
            val = newVal;
            deps.forEach(dep => { // 只要bgg.age被修改时，就会触发依赖函数
                dep();
            });
        }
    });
};

// 使对象的属性变得可观测
const observable = obj => {
    Object.keys(obj).forEach(k => {
        defineReactive(obj, k, obj[k]);
    });
    
    return obj;
};

const computed = (val) => {
    console.log(val);
}

const watcher = (obj, key, cb) => {
    const onDepUpdated = () => {
        let val = cb(); // 在这里调用cb时会触发 bgg.age属性的get()
        computed(val);
    };

    Object.defineProperty(obj, key, {
        get() {    
            Dep.target = onDepUpdated;
            let val = cb(); // 在这里调用cb时会触发 bgg.age属性的get()
            Dep.target = null;
            return val;
        },
        set() {
            console.log('计算属性没有set方法');
        }
    });
};

let bgg = observable({
    name: 'bgg',
    age: 18,
});

// 多个依赖观测bgg。
watcher(bgg, 'height', () => bgg.age > 30 ? '身高缩水了' : '身高长高了');
watcher(bgg, 'weight', () => bgg.age > 30 ? '体型变肥了' : '体型变瘦了');

// 触发观测bgg的依赖的get属性，形成依赖关联。
console.log('身高初始值：' + bgg.height);
console.log('体重初始值：' + bgg.weight);

// 改变age值，触发关联age属性的依赖。
bgg.age = 40;



```

[vue响应式原理解析](https://segmentfault.com/a/1190000011153487#articleHeader1)
