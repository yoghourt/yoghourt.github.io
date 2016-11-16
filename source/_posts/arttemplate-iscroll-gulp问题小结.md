---
title: arttemplate iscroll gulp问题小结
date: 2016-04-19 14:47:08
tags:
---
# 今日问题总结
## 1.arttemplate helper多参数传递
```
	tepmlate.helper('name',function(content,parameter){
        /*
            your code
        */
        return content;
    });
```
简洁语法模式下的调用
```
	{{content | name : parameter}}
```

## 2.iscroll动态加载dom完成后初始化
*若是dom未加载完成即初始化会导致页面内容显示不完全，且页面无法滑动到底部*
思路：在dom最后增加mark dom，设置计时器判断mark dom是否加载完成，如果加载完成再执行iscroll 初始化
```
	function initScroll(){
        intervalTime = setInterval(function (){
            var resultContentH = $("#finish-mark").height();
            if (resultContentH > 0) {  //判断数据加载完成的条件
                console.log("dom动态加载完成！");
                setTimeout(function () {
                    clearInterval(intervalTime);
                    var myScroll = new IScroll("#wrapper",{mouseWheel: true, click: true,tap: true});
                }, 100)
            }
        }, 10);
    };
```
加载dom结尾添加
```
	<div id="finish-mark"></div>
```

## 3.gulp合并文件指定文件顺序
* 使用gulp－order
* 按合并顺序放置或重命名文件
* gulp.src[ a.js , b.js , c.js]