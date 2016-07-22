# Basic CSS Knowledge    

### 小虫



# 基础知识



## HTML5
- 更语义化 (section, article, header, nav, footer, [data-*]) <!-- .element: class="fragment" -->
- 本地存储 (localStorage) <!-- .element: class="fragment" -->
- 设备兼容 (Geolocation, 摄像头, 麦克风) <!-- .element: class="fragment" -->
- 连接 (WebSockets推送消息) <!-- .element: class="fragment" -->
- 网页多媒体 <!-- .element: class="fragment" -->
- 3D、图形及特效 (SVG、Canvas、WebGL、CSS3的3D功能) <!-- .element: class="fragment" -->
- CSS3 <!-- .element: class="fragment" -->


## 盒模型
![Box Model](/images/box-model.png)
- box-sizing: content-box | padding-box | border-box; <!-- .element: class="fragment" -->
- margin叠加原则 <!-- .element: class="fragment" -->


## display
- display: block; 块级元素 <!-- .element: class="fragment" -->
- display: inline; 行级元素 <!-- .element: class="fragment" -->
- display: inline-block; 混合 <!-- .element: class="fragment" -->


## 布局方式
- 普通布局 <!-- .element: class="fragment" -->
- 浮动布局 (float) <!-- .element: class="fragment" -->
- 相对绝对定位布局 (position) <!-- .element: class="fragment" -->


## position
- position: static; <!-- .element: class="fragment" -->
- position: relative; <!-- .element: class="fragment" -->
- position: absolute; <!-- .element: class="fragment" -->
- position: fixed; <!-- .element: class="fragment" -->
- [Example](http://jsfiddle.net/joyzhang/au7evznb/) <!-- .element: class="fragment" -->



## 字体尺寸的各种单位
- px <!-- .element: class="fragment" -->
- em <!-- .element: class="fragment" -->
- rem (root em) <!-- .element: class="fragment" -->
- [Example](http://jsfiddle.net/joyzhang/vga9ncdn/) <!-- .element: class="fragment" -->



## SCSS高级用法


## @if
```SCSS
$type: monster;
p {
  @if $type == ocean {
    color: blue;
  } @else if $type == matador {
    color: red;
  } @else if $type == monster {
    color: green;
  } @else {
    color: black;
  }
}
```


## @for
```SCSS
@for $i from 1 through 3 {
  .item-#{$i} { width: 2em * $i; }
}
```
编译成：<!-- .element: class="fragment" -->
```CSS
.item-1 {
  width: 2em;
}
.item-2 {
  width: 4em;
}
.item-3 {
  width: 6em;
}
```
<!-- .element: class="fragment" -->


## @each
```SCSS
@each $animal in cat, dog, duck {
  .#{$animal}-icon {
    background-image: url('/images/#{$animal}.png');
  }
}
```
编译成：<!-- .element: class="fragment" -->
```CSS
.cat-icon {
  background-image: url('/images/cat.png'); }
.dog-icon {
  background-image: url('/images/dog.png'); }
.duck-icon {
  background-image: url('/images/duck.png'); }
```
<!-- .element: class="fragment" -->


## @mixin
```SCSS
@mixin round($size: 20px) {
  width: #size;
  height: #size;
  border-radius: 50%;
}

.avatar {
  @include round(30px);
}
```



## Retinafy
- font smooth <!-- .element: class="fragment" -->
```CSS
html {
    font-family: "Avenir Next", "Segoe UI", "PingFang SC",
    "Hiragino Sans GB", "Microsoft YaHei", sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;  
}
```
<!-- .element: class="fragment" -->
- image@2x.png <!-- .element: class="fragment" -->
  - background-size <!-- .element: class="fragment" -->
  - image width <!-- .element: class="fragment" -->
- 图标字体 <!-- .element: class="fragment" -->
  - [Fontawesome](http://fontawesome.io/icons/) <!-- .element: class="fragment" -->
  - [Fontello](http://fontello.com/) <!-- .element: class="fragment" -->



## 响应式布局



## Media Query
```SCSS
@media not|only mediatype and (media feature) {
    CSS-Code;
}
```
Mobile First <!-- .element: class="fragment" -->

```SCSS
/* For mobile phones: */
.avatar {
    background-image: url(small.png);
}

@media only screen and (min-width: 768px) {
  .avatar {
    background-image: url(normal.png);
  }
}
```
<!-- .element: class="fragment" -->
不到万不得已不用~ <!-- .element: class="fragment" -->



## 其他
- [:before | :after](https://jsfiddle.net/joyzhang/u24oxpm9/) <!-- .element: class="fragment" -->
- :checked | :disabled | :focus | :hover <!-- .element: class="fragment" -->
- :first-child | :last-child <!-- .element: class="fragment" -->
```SCSS
ul {
    li {
      margin-top: 10px;
      &:first-child {
        margin-top: 0;
      }
    }
}
```
<!-- .element: class="fragment" -->
