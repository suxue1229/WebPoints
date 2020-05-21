IE浏览器版本多，兼容性问题复杂，遇到的问题总结如下：
### 1. flex布局默认的兼容性问题(未完待续)
>(1)父级设置了flex布局后，子元素就算是行内元素很多浏览器可以把它当做inline-block或者block元素来用，可以直接设置它的宽高，但是还是有些浏览器不支持，所以要设置行内元素的宽度，还是手动设置一下它的display为inline-block或者block。IE11、firefox、google会把行内元素默认为inline-block或者block；但IE10不行，需要```display:inline-block```。
>(2) flex: 1
>```flex: 1```是设置```flex-grow```、```flex-shrink```、```flex-basic```属性的简便方式。
在firefox与google中```flex：1```等同于
```css
flex-grow: 1; flex-shrink: 1; flex-basic: 0%;
```
而IE浏览器默认为
```css
flex-grow: 1; flex-shrink: 0; flex-basic: 0px;
```
### 参考链接
- https://github.com/philipwalton/flexbugs
- [Flex 布局在IE浏览器下的糟糕表现](https://www.cnblogs.com/dodocie/p/7137314.html)
### 2.```<meta http-equiv="X-UA-Compatible" content="IE=edge,chrome=1"/>```
>如果当前IE浏览器安装了GCF(Google Chrome Frame)插件，则以chrome内核进行渲染；否则以当前IE浏览器支持的最高版本模式来渲染。其中```IE=edge```表示所有IE8及以上的浏览器按照【自身】最新版本渲染
### 参考链接
- https://segmentfault.com/q/1010000007497458/a-1020000007499079
