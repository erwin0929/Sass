## Sass

强大又稳定的css扩展语言。

1. 引入了变量
   * 可以将多次使用的属性值赋予给某一变量,从而多次使用,变量以$开头,以:为赋值手段  
   例: `$padding-left: 20px;`
2. 新的css嵌套规则
   ```
   #content article h1 { color: #333 }
   #content article p { margin-bottom: 1.4em }
   #content aside { background-color: #EEE }
      ```
      如你所见,重复书写选择器是一件非常恼人的工作,随着嵌套的深入,我们需要一遍又一遍的书写重复的选择器  
      这样的写法既繁琐又不利于维护。  
      所幸的是,机智的Sass很好的避开了这种问题。

   ```
      #content {
          article {
              h1 { color: #333 }
              p { margin-bottom: 1.4em }
          }
          aside { background-color: #EEE }
      }
      ```    
   
3. 父选择器的标识符`&`
  ```
  a{
      color: blue;
      &:hover { color: red }
  }
  ```    
  & 表示的是`a`标签本身,类似于js中的`this`(好奇怪的比喻)
4. 支持文件导入 `@import`
 * css中也有导入功能,不同的是css中的`@import`只有被执行到,浏览器才会去下载,这将导致页面加载速度变慢。  
 Sass与之不同的是,会将样式都归纳到一个css文件中,而无需再次发起下载请求。  
 导入时亦可省略后缀名。  

  ![导入方式](https://www.sass.hk/images/p1.png)

5. 默认变量值
 * 一般情况下，你反复声明一个变量，只有最后一处声明有效且它会覆盖前边的值。例如下  
 
 ```
  $link-color: blue;
  $link-color: red;
  a {
      color: $link-color;
  }
 ```
6. 更多高阶用法如mixin,@extend,@include,不多做介绍了  