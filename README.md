#酒店价格日历

####基于YUI3开发的价格日历组件

	@name：Y.PriceCalendar
	@requires：['node', 'base-base', 'event-mouseenter']
	
##快速上手

####引入文件

在页面head引入YUI3.x.x种子

`<script src="http://yui.yahooapis.com/3.5.1/build/yui/yui-min.js"></script>`

####配置

```
var config = {
    modules: {
        'price-calendar': {
            fullpath: 'price-calendar.js', //根据项目路径调整
            type    : 'js',
            requires: ['price-calendar-css']
        },
        'price-calendar-css': {
            fullpath: 'price-calendar.css', //根据项目路径调整
            type    : 'css'
        }
    }
};
```

####使用

```
YUI(config).use('price-calendar', function(Y) {
    var oCalendar = new Y.PriceCalendar();    
    //do something
});
```

##配置参数

* ####date

	> **概述**
	> 
	> *(默认值：当前日期) 日历初始日期*
	>
	> **类型**
	>
	> `{Date|String}`
	
* ####data

    > **概述**
	> 
	> *(默认值：null) 酒店房态数据*
	>
	> **类型**
	>
	> `{Object}`
	
	```
	{
    	"2012-05-01": {
    		"price"  : "100",
        	"roomNum": "10"
    	},
    	"2012-05-02": {
        	"price"  : "120",
        	"roomNum": "1"
   	 	},
    	"2012-05-03": {
     	   "price"  : "150",
     	   "roomNum": "25"
    	}
    }
	```
	
* ####count

	> **概述**
	>
	> *(默认值：2) 日历个数*
	>
	> **类型**
	>
	> `{Number}`
	
* ####minDate

	> **概述**
	>
	> *(默认值：null) 允许操作的最小日期*
	>
	> **类型**
	>
	> `{Date|String}`
	
* ####maxDate

	> **概述**
	>
	> *(默认值：null) 允许操作的最大日期*
	>
	> **类型**
	>
	> `{Date|String}`
	
* ####depDate

	> **概述**
	>
	> *(默认值：空) 入住时间*
	>
	> **类型**
	>
	> `{String}`
	
* ####endDate

	> **概述**
	>
	> *(默认值：空) 离店时间*
	>
	> **类型**
	>
	> `{String}`
	
* ####afterDays

	> **概述**
	>
	> *(默认值：0) 等价于设置minDate和maxDate，minDate未设置时取当前日期*
	>
	> **类型**
	>
	> `{Number}`
	
##接口
	
* ####`render()`

	> **概述**
	>
	> *用于设置参数后渲染日历UI*
	>
	> **返回值**
	>
	> *日历对象，可做链式操作*
	
* ####`prevMonth()`

	> **概述**
	>
	> *渲染上月日历UI*
	>
	> **返回值**
	>
	> *日历对象，可做链式操作*
	
* ####`nextMonth()`

	> **概述**
	>
	> *渲染下月日历UI*
	>
	> **返回值**
	>
	> *日历对象，可做链式操作*

##自定义事件

* ####render

	> **概述**
	>
	> *渲染日历UI事件*
	>
	> **示例**
	
	```
	var oCalendar = new Y.PriceCalendar();
    	oCalendar.on('render', function(e) {
        	//do something
    	});
	```

* ####prevmonth

	> **概述**
	>
	> *点击上月按钮事件*
	>
	> **示例**
	
	```
	var oCalendar = new Y.PriceCalendar();
    	oCalendar.on('prevmonth', function(e) {
        	//do something
    	});
	```

* ####nextmonth

	> **概述**
	>
	> *点击下月按钮事件*
	>
	> **示例**
	
	```
	var oCalendar = new Y.PriceCalendar();
    	oCalendar.on('nextmonth', function(e) {
        	//do something
    	});
	```

* ####checkin

	> **概述**
	>
	> *点击入住日期事件*
	>
	> **示例**
	
	```
	var oCalendar = new Y.PriceCalendar();
    	oCalendar.on('checkin', function(e) {
        	//do something
    	});
	```

* ####checkout

	> **概述**
	>
	> *点击离店日期事件*
	>
	> **示例**
	
	```
	var oCalendar = new Y.PriceCalendar();
    	oCalendar.on('checkout', function(e) {
        	//do something
    	});
	```

* ####confirm

	> **概述**
	>
	> *点击确定按钮事件*
	>
	> **示例**
	
	```
	var oCalendar = new Y.PriceCalendar();
    	oCalendar.on('confirm', function(e) {
        	//do something
    	});
	```

* ####cancel

	> **概述**
	>
	> *点击取消按钮事件*
	>
	> **示例**
	
	```
	var oCalendar = new Y.PriceCalendar();
    	oCalendar.on('cancel', function(e) {
        	//do something
    	});
	```

##配置参数改变事件

* ####dateChange

	> **概述**
	>
	> *设置`date`参数触发事件*
	>
	> **示例**
	
	```
	var oCalendar = new Y.PriceCalendar();
    	oCalendar.on('dateChange', function(e) {
        	//do something
    	});
	```

* ####dataChange

	> **概述**
	>
	> *设置`data`参数触发事件*
	>
	> **示例**
	
	```
	var oCalendar = new Y.PriceCalendar();
    	oCalendar.on('dataChange', function(e) {
        	//do something
    	});
	```

* ####countChange

	> **概述**
	>
	> *设置`count`参数触发事件*
	>
	> **示例**
	
	```
	var oCalendar = new Y.PriceCalendar();
    	oCalendar.on('countChange', function(e) {
        	//do something
    	});
	```

* ####minDateChange

	> **概述**
	>
	> *设置`minDate`参数触发事件*
	>
	> **示例**
	
	```
	var oCalendar = new Y.PriceCalendar();
    	oCalendar.on('minDateChange', function(e) {
        	//do something
    	});
	```

* ####maxDateChange

	> **概述**
	>
	> *设置`maxDate`参数触发事件*
	>
	> **示例**
	
	```
	var oCalendar = new Y.PriceCalendar();
    	oCalendar.on('maxDateChange', function(e) {
        	//do something
    	});
	```

* ####depDateChange

	> **概述**
	>
	> *设置`depDate`参数触发事件*
	>
	> **示例**
	
	```
	var oCalendar = new Y.PriceCalendar();
    	oCalendar.on('depDateChange', function(e) {
        	//do something
    	});
	```

* ####endDateChange

	> **概述**
	>
	> *设置`endDate`参数触发事件*
	>
	> **示例**
	
	```
	var oCalendar = new Y.PriceCalendar();
    	oCalendar.on('endDateChange', function(e) {
        	//do something
    	});
	```

* ####afterDaysChange

	> **概述**
	>
	> *设置`afterDays`参数触发事件*
	>
	> **示例**
	
	```
	var oCalendar = new Y.PriceCalendar();
    	oCalendar.on('afterDaysChange', function(e) {
        	//do something
    	});
	```