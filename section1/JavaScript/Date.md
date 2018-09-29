#Date

> 一个保存基于1970年1月1日(世界标准时间)起的毫秒数的对象。


> ps：实例化Date对象时，取的是系统时间到1970年1月1日的毫秒数。



|方法|描述|
| :---: | :---: |
|Date.parse(dateString)|解析一个表示某个日期的字符串，并返回从1970-1-1 00:00:00 UTC 到该日期对象（该日期对象的UTC时间）的毫秒数|
|dateObj.getTime()|返回从1970-1-1 00:00:00 UTC 至今的毫秒数。|
|dateObj.getDate()|返回日期。|
|dateObj.getFullYear()|返回年份。|
|dateObj.getMonth()+1|返回月份(0~11)。|
|dateObj.getDay()|返回星期(0代表星期天)。|
|dateObj.getHours()|返回小时数。|
|dateObj.getMinutes()|返回分钟数。|
|dateObj.getSeconds()|返回秒数。|
|dateObj.getMilliseconds()|返回毫秒数。|