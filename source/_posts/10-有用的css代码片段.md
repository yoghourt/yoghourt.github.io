---
title: "10+有用的css代码片段"
date: 2016-04-07 11:05:31
tags:
---

## 10+有用的css代码片段
**1. 垂直对齐**
```
	position:relative;
	top: 50%;
	-webkit-transform: translateY(-50%);
	-o-transform: translateY(-50%);
	transoform:translateY(-50%);
```
[查看Demo](./demo/verticalCenter.html)

<!---more--->

**2. 只在一侧或者两侧具有投影**
```
	.box-shadow {
	    background-color: #AC92EC;
	    width: 160px;
	    height: 90px;
	    margin-top: -45px;
	    margin-left: -80px;
	    position: absolute;
	    top: 50%;
	    left: 50%;
	}
	.box-shadow:after {
	    content: "";
	    width: 150px;
	    height: 1px;
	    margin-top: 88px;
	    margin-left: -75px;
	    display: block;
	    position: absolute;
	    left: 50%;
	    z-index: -1;
    	-webkit-box-shadow: 0px 0px 8px 2px #000000;
        -moz-box-shadow: 0px 0px 8px 2px #000000;
        box-shadow: 0px 0px 8px 2px #000000;
	}
```
[查看Demo](./demo/shadow.html)

**3. 渐变背景动画效果**
```
	button{
		padding: 15px;
		background-image:liner-grafient(#FC6E51,#FFF);
		background-size:auto 200%;
		background-position:0 100%;
		transition:background-position 0.5s;
	}
	button:hover{
		background-position:0 0;
	}
```
[查看Demo](./demo/bgAnimate.html)

**4. 将文本分成多行**
```
	div{
		-moz-column-count:3;
		-webkit-column-count:3;
		column-count:3;
	}
```
[查看Demo](./demo/multipleColumns.html)

**5. 表格自动宽度**
```
	td{white-space: nowrap}
```
[查看Demo](./demo/tdAutoWidth.html)

**6. 像出版物一样，第一个字变得大些**
```
	p:first-child::first-letter{
	font-family:"papyrus";
	font-size: 28px;
	font-weight: bold;
	}
```
[查看Demo](./demo/biggerFont.html)

**7. 特定浏览器的CSS Hacks的完整列表**
```
	/***** Selector Hacks ******/
	
	/* IE6 and below*/
	* html #uno {color: red}
	
	/* IE7 */
	*:first-child+html #dos {color: red}
	
	/* IE7, FF, Saf, Opera */
	html>body #tres {color: red}
	
	/* IE8, FF, Saf, Opera (Everything but IE 6,7) */
	html>/**/body #cuatro { color: red }
	  
	/* Opera 9.27 and below, safari 2 */
	html:first-child #cinco { color: red }
	  
	/* Safari 2-3 */
	html[xmlns*=""] body:last-child #seis { color: red }
	  
	/* safari 3+, chrome 1+, opera9+, ff 3.5+ */
	body:nth-of-type(1) #siete { color: red }
	  
	/* safari 3+, chrome 1+, opera9+, ff 3.5+ */
	body:first-of-type #ocho {  color: red }
	  
	/* saf3+, chrome1+ */
	@media screen and (-webkit-min-device-pixel-ratio:0) {
	 #diez  { color: red  }
	}
	  
	/* iPhone / mobile webkit */
	@media screen and (max-device-width: 480px) {
	 #veintiseis { color: red  }
	}
	  
	/* Safari 2 - 3.1 */
	html[xmlns*=""]:root #trece  { color: red  }
	  
	/* Safari 2 - 3.1, Opera 9.25 */
	*|html[xmlns*=""] #catorce { color: red  }
	  
	/* Everything but IE6-8 */
	:root *> #quince { color: red  }
	  
	/* IE7 */
	*+html #dieciocho {  color: red }
	  
	/* Firefox only. 1+ */
	#veinticuatro,  x:-moz-any-link  { color: red }
	  
	/* Firefox 3.0+ */
	#veinticinco,  x:-moz-any-link, x:default  { color: red  }
	/***** Attribute Hacks ******/
	  
	/* IE6 */
	#once { _color: blue }
	  
	/* IE6, IE7 */
	#doce { *color: blue; /* or #color: blue */ }
	  
	/* Everything but IE6 */
	#diecisiete { color/**/: blue }
	  
	/* IE6, IE7, IE8 */
	#diecinueve { color: blue\9; }
	  
	/* IE7, IE8 */
	#veinte { color/*\**/: blue\9; }
	  
	/* IE6, IE7 -- acts as an !important */
	#veintesiete { color: blue !ie; } /* string after ! can be anything */
```

**8. 创建模糊文本**
```
	.blurry-text{
		color: transparent;
		text-shadow: 0 0 5px rgba(0,0,0,.5);
	}
```
[查看Demo](./demo/blurryText.html)

**9. 不使用表格实现跨浏览器垂直水平居中图片**

这段代码可以在一个已知宽高的容器内垂直水平居中一个未知大小的图片，这是 IE 的一个hack：
```
	<figure class='logo'>
	    <img class='photo'/>
	</figure>
	
	.logo {
	  display: block;
	  text-align: center;
	  vertical-align: middle;
	  border: 4px solid #dddddd;
	  padding: 4px;
	  height: 74px;
	  width: 74px; 
	}
	.logo *{
	    display: inline-block;
	    height: 100%;
	    vertical-align: middle; 
	}
	    .logo .photo {
	    height: auto;
	    width: auto;
	    max-width: 100%;
	    max-height: 100%; 
	}
```
[查看Demo](./demo/imgHorizontal.html)

**10. 高亮选中的input**
```
	// HTML
	<input id="mycheck1" type="checkbox" />
	<label for="mycheck1">Check box label here</label>
	<br />
	<input id="mycheck2" type="checkbox" checked/>
	<label for="mycheck2">Check box label here</label>
	<br />
	<input id="mycheck3" type="checkbox" />
	<label for="mycheck3">Check box label here</label>
	
	// CSS
	input:checked + label{
	    background: yellow;  
	}	
```