```html

    <figure class="figure">
        <img src="" alt="" class="figure-img img-fluid">
        <figcaption class="figure-caption"></figcaption>
    </figure>

    <figure class="figure">
        <img src="" alt="" class="figure-img img-fluid">
        <figcaption class="figure-caption"></figcaption>
    </figure>

```

# 基本显示

* d-none
* d-inline
* d-block
* d-inline-block

**块级元素：**

1. 独占一行
2. 宽度100%，高度内容决定
3. 可以设置width和height

**行内元素：**

1. 可以与其他元素共用一行
2. 默认宽度和高度由内容决定
3. 高度宽度设置无效

**行内块元素**

	1.  可以和其他元素共用一行
 	2. 默认情况下，宽度和高度由内容决定
 	3. widht和height的设置有效
 	4. img input 等

**表格元素**

* d-table : 表格
* d-table-row ： 表格行
* d-table-cell ：每一个表格的单元格
  * 垂直居中
  * 等高

```html
 <div class="container-fluid myborder" style="height: 90%">
     <div class="row h-100 align-items-center"> 
         <div class="col-4 d-table">
             <span class="d-table-cell myborder">
                 sjkjadfa
                 kjkljkljkl
                 kjkljkljkl
             </span>
             <span class="d-table-cell myborder"  style="vertical-align: middle;">
                 sjkjadfa

             </span>
         </div>
     </div>
</div>
```

![image-20210214203824514](/home/huazhilun/.config/Typora/typora-user-images/image-20210214203824514.png)

# 浮动

* float-left
* float-right
* float-none

浮动最初的目的是图文混排，后来图文混排

	1. 脱离文档流
 	2. 如果在块级元素中，会导致父容器高度失去
 	3. 可以在父元素中添加 clear-fix 类清除浮动

## 用浮动布局





```html
<style>
    .container{
        width:100%;
        margin:0 auto; /*自身水平居中*/
        border:1px solid gree;
    }
    aside{
        float:left;
        width:15%;
        height:200px;
    }
    main{
        float:left;
     	width:780px;
        height:200px;
    }
    footer{
        height:30px;
    }
</style>



<div class="container">
    
    <header>头部</header>
    
</div>
```

# 定位

1. 相对定位：

   1. 相对于自己原来的位置做定位
   2. 原来的位置保留
   3. 可以控制某些行内元素的位置，（margin对行内元素没有效果)

2. 绝对定位：

   1. 相对于父亲元素移动（父亲元素有定位的情况）
   2. 脱离文档流
   3. 如果父亲元素没有定位，会相对于body进行定位

3. 常见场景：居中定位

   ```css
   CSS代码
   position:absolute;
   top: 50%;
   left: 50%;
   transform: translate(-50%,-50%)
   ```

# Flex



## container  (父元素类)

![image-20210214214932100](/home/huazhilun/.config/Typora/typora-user-images/image-20210214214932100.png)

* flex-row
* flex-row-reverse
* flex-column
* flex-column-reverse

### 设置主轴排列

* justify-content-center
* justify-content-start
* justify-content-end
* justify-content-between
* justify-content-around （环绕，图略）

![image-20210214215337455](/home/huazhilun/.config/Typora/typora-user-images/image-20210214215337455.png)

## 设置纵轴

	* align-items-center
	* align-items-start
	* align-items-end
	* align-items-between
	* align-items-around

```html
<span class="d-flex justify-content-center align-items-center">嘿嘿诶i</span>
```

## 子元素类

   #### 交叉轴上的设置 

* align-self-start
* align-self-end
* align-self-center

#### order

* order-0
* order-first
* order-last

#### 元素的伸展

	* flex-grow: 分配剩余空间时所占的份数
	* 默认不伸展

##  字元素的收缩

* flex-shrink 
* 默认等比例收缩

#### 字元素在主轴上的大小：

* flex-basis
* 不能保证数值的大小，还要看优先级和缩放比例



### margin 自动

* mr-auto: 向右推动
* ml-auto：向左推动
* mx-auto：居中嘻嘻



# bootstrap的grid sytem

## container

## container-fluid

以上为两种容器，芜湖

## Gird layout

三级结构：

container/container-fluid ->  row  ->  col

row:占用整个container:

```css
.row{
	display:flex;
	flex-wrap:wrap
    padding-right:-15px;
    padding-left:-15px;
}
/*两个padding是为了抵消container默认的padding*/
```

col:

```css
.col-xxx{
    position:relative;
    width:100%;
    padding-right:15px;
    padding-left:15px;
}

/*relative表明子元素可以使用绝对定位*/

等分布局，似乎没有启用相对定位，需要自己写的样子，
芜湖

.col{
 	flex-basis:0;
    flex-grow: 1; /*等比例分*/
}

内容自适应
.col-auto{
    width:auto;
    flex:0 0 auto;
    max-width:100%   
}

？？？？？？以下忘了，请查阅文档，芜湖

.row-cols-1
.row-cols-2 
.row-cols-3
.row-cols-4
.row-cols-5
.row-cols-6
```

