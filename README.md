# Sass

Sass  是一种 CSS 预处理器，用于增强和扩展 CSS 的功能，它是一种强大的工具，引入了一些功能，是开发人员能够以更抽象和模块化的方式编写 CSS，提高了代码的可读性，从而提高了前端开发的效率和可维护性.开发人员通常使用 Sass来提供其样式编写流程，特别是在大型项目中.

官网： https://sass-lang.com/ 

1. 使用 Sass 的主要群体包括：

**前端工程师**：前端工程师通常需要处理大量的CSS代码，Sass可以帮助他们更高效的管理CSS文件和样式. Sass 的继承和混合等功能可以减少代码的重复，提高代码的可重用性

**响应式设计爱好者**：Sass 支持媒体查询，可以帮助开发人员更轻松地实现响应式设计. 使用 Sass 可以轻松地为不同设备和屏幕尺寸编写特定的 CSS 样式.

**CSS 框架用户**： 许多流行的 CSS 框架(比如Bootstrap) 使用 Sass 作为其默认的预处理器. 对于这些框架的用户来说，了解 Sass 是非常有益的，因为Sass可以帮助他们更好地了解框架的内部工作原理，以及如何定制和扩展这些框架.

**CSS新手**：对于刚刚开始学习CSS的人来说，Sass 可以提供一个更易于学习和使用的起点. Sass 的语法比原始CSS更易于理解和掌握，可以帮助新手更快的掌握CSS的核心概念.

2. Sass可以被广泛的应用在以下的地方和情况：

**网站开发**：Sass 可以用于开发各种类型的网站，从简单的个人博客到大型企业网站和电子商务平台

**Web应用程序**：开发web应用程序时，Sass 可以帮助开发人员更轻松地管理应用程序的样式，以及快速响应用户界面的需求变化

**移动应用程序**：Sass 不仅用于web开发，还可以用于创建移动应用程序的样式

**响应式设计**：Sass 有助于开发响应式网站和应用程序，以确保它们在各种设备上都能够适应并提供一致的用户体验

**内容管理系统(CMS)主题开发**：Sass 可以用于创建各种CMS的主题，以定制外观和风格

**Web框架**：许多Web框架都支持 Sass 作为默认的样式表预处理器

**静态网站生成器**：静态网站生成器通常也支持Sass

**开源项目**：Sass 是一个广泛使用的工具，许多开源项目和社区使用它来管理项目的样式表

3. 使用 Sass 的原因有：

**简单易维护**：Sass 具有简洁，易读的语法，并且支持变量，嵌套，混合等功能，可以帮助开发者更快速，更有效地编写CSS代码，提高代码的可维护性和可重用性

**功能强大**：Sass 包含CSS的所有功能以及一些高级功能，如颜色处理，数学，参数列表等，可以帮助开发者创建出色的样式表

**可定制**：Sass 支持变量和混合等功能，可以帮助开发者定制样式表，以适应不同的项目 需求

**促进团队合作**：Sass 可以帮助开发者在团队中更好的协作，因为样式表是易于共享和重用的，可以减少重复工作和冲突

**提高开发效率**：Sass 的自动压缩，颜色处理等功能可以帮助开发者提高开发效率，减少样式的体积和复杂度

4. 要学好 Sass, 可以按照以下步骤和建议：

**理解基本的CSS**：在学习 Sass 之前，确保你对CSS有基本的了解，包括选择器，属性，值，盒模型等. Sass 是CSS的扩展，因此需要首先掌握CSS的基础知识

**安装Sass**: 需要在计算机上安装Sass，Sass有2个主要的编译器，即Dart Sass 和 Node.js 中的LibSass，可以选择其中一个，并根据官方文档进行安装

**学习Sass语法**：包括如何定义变量，嵌套规则，创建混合和使用继承等功能，阅读官方文档和教程可以帮助掌握这些概念

**练习Sass代码**：创建一些小项目或样式表，实际练习是学习的最佳方式

**实际项目中应用**：将学到的Sass知识应用到实际项目中，实际项目经验是最好的老师，可以帮助更好的理解如何在真实环境中使用Sass

## 安装Sass

需要先安装好node

```shell
npm install -g sass
```

sass文件就是普通的文本文件，里面可以直接使用CSS语法

sass的文件后缀名是scss，意思为Sassy CSS

由于浏览器不识别sass，需要将其转换成css，命令如下：

```shell
sass index.scss index.css # 将index.scss转换为index.css
```

- 在编辑器VSCode里安装扩展插件：LiveSassCompiler, 并在settings里加入以下配置：

```json
 "liveSassCompile.settings.formats":[
    {
      "format": "expanded",
      "extensionName": ".css",
      "savePath": "/css",
      "generateMap": false
    }
  ],
```

这样只要点击VSCode下方的"Watch Sass", 就会对当前的scss文件监控并自动完成编译为css

- 在编辑器VSCode里安装扩展插件：SCSS IntelliSense
  
  在编写Sass时，会有代码提示效果

## Partials & @import

在 Sass中，文件名以下划线 _\_ 开头的通常被称为 ”部分文件“ (partial files), 这些部分文件主要用于将样式表拆分多个模块，以便更好的组织和管理代码. 

**variables.scss 和 _\_variables.scss 之间的差异和区别：**

1. 命名约定：
   
   variables.scss 通常用于定义全局变量，而 _\_variables.scss 通常用于组织样式的片段，而不是定义全局变量，但这种区别是约定俗成的，不是绝对的

2. 编译行为：
   
   variables.scss 会被编译成一个独立的 CSS 文件，其中包含全局变量的定义，可以在整个项目中使用
   
   __variables.scss 不会被单独编程成 CSS 文件，它通常被其他 Sass 文件所引入，以共享其中定义的变量

3. 导入方式：
   
   如果要在 Sass 文件中使用全局变量，可以直接导入 variables.scss，在sass文件中不需要带下划线以及后缀名，例如：@import "variables"
   
   如果要在部分文件中使用部分文件变量，可以导入 __variables.scss，但在sass文件同样也不需要导带下划线以及后缀名，例如仍然是：@import "variables"
   
   ```scss
   // __variables.scss 文件
   /* color变量 */
   $primary:#3299ef;
   $secondary: #1ac886;
   $error: #d32752;
   $info: #f6c31c;
   ```
   
   ```scss
   // index.scss文件里导入部分文件变量
   
   @import 'variables';
   
   button{
     color:#fff;
     border: 0;
     background-color: $primary;
     border-radius: $base-border-radius;
     padding: $base-padding;
   }
   
   a{
     color: $secondary;
   }
   ```
   
   总之，variables.scss 与 __variables.scss 主要区别在于文件名的命名约定和编译行为.
   
   不带下划线的scss文件会被编译成一个独立的css文件，带下划线的scss文件不会被编程成独立的css文件
   
   由于在项目中一般都有index.scss文件会被独立编译为一个css文件, 因此在其他模块的scss的命名最好带下划线，这样编译后就只有一个index.css文件，不会生成很多其他模块的css文件，方便项目样式的管理.
   
   ## 项目的样式结构设置
   
   在项目中，一般会有一个入口样式文件 index.css，对应的sass文件就是index.scss
   
   在这个入口样式文件里，我们会引入其他不同的部分样式文件(partial files), 例如
   
   在index.scss文件里：
   
   ```scss
   // 变量，函数
   @import 'variables';
   
   // 基础样式，布局相关的设置
   @import 'base';
   
   @import 'colors';
   
   // components组件(Card,Button,Input等）的样式
   @import 'components/card'
   
   // Utilities公共样式(padding, margin,border等)
   ```
   
   ## Sass 语法
   
   1. 变量
      
      Sass 允许使用变量，所有变量以`$`开头
      
      ```scss
      $blue : #1875e7;　
      
      div {
      　 color : $blue;
      }
      ```
      
      如果变量需要镶嵌在字符串之中，就必须要写在#{}之中
      
      ```scss
      $side : left;
      
      .rounded {
      　　border-#{$side}-radius: 5px;
      }
      ```
   
   2. 样式嵌套
      
      ```scss
      .card{
        display: block;
        padding: $base-padding;
        border: $base-border-thickness solid #ddd;
        box-shadow: $base-box-shadow;
      
        .card-title {
          font-size: $base-font-size;
          padding-bottom: $base-padding;
          font-weight: bold;
        }
      
        .card-body {
          font-size: $base-font-size;
      
          a {
            text-decoration: underline;
          }
        }
      }
      ```
   
   3. math计算
      
      Sass 有一些标准数学运算符，例如`+`、`-`、`*`、`math.div()`和`%`
      
      - 乘法
        
        ```scss
        /* font-size */
        $base-font-size: 1rem;
        $font-size-sm: $base-font-size * 0.75;
        $font-size-lg: $base-font-size * 1.5;
        $font-size-xl: $base-font-size * 2;
        $font-size-xxl: $base-font-size * 3;
        ```
      
      - 除法
        
        如果需要确保除法操作始终是数学除法，而不是产生 CSS 语法，建议使用 `math.div()`
        
        `math.div()` 是 Sass 中提供的固定的数学除法计算方式。与传统的 `/` 运算符不同，`math.div()` 确保始终执行 **数学除法**，而不会被误认为是 **CSS 除法**
        
        `math.div()` 的特点：
        
        1. 始终执行数学除法：即使在 CSS 属性中使用，也会计算出除法的结果，而不是输出 `/` 符号。无论在哪里使用，它都执行数学上的除法计算。
        2. 清晰明确：开发者不再需要依赖括号来区分数学运算和 CSS 运算，使用 `math.div()` 可以直接明确地执行数学除法。
        
        ```scss
        @use 'sass:math';
        
        $width: math.div(100px, 2); // 50px
        $ratio: math.div(16, 9);    // 1.77777 (无单位)
        ```
        
        ```scss
        @use 'sass:math';
        
        $base-border-radius:20px;
        
        .card{
          display: block;
          width: math.div(600px, 960px) * 100%;
          border-radius: math.div($base-border-radius, 4);
        }
        ```
   
   4. map 对象
      
      Sass 中的map包含键和值对，并且可以轻松地通过相应的键查找值
      
      **map必须用圆括号()括起来, 键值对的键一般是字符串**
      
      **使用：map-get() 调用map里的键值对象**
      
      ```scss
      @use "sass:map";
      $font-weights: (
         "regular": 400, 
         "medium": 500, 
         "bold": 700
      );
      
      @debug map-get($font-weights, "medium"); // 500
      @debug map-get($font-weights, "extra-bold"); // null
      ```
      
      ```scss
      /* color变量 */
      $primary:#3299ef;
      $secondary: #1ac886;
      $error: #d32752;
      $info: #f6c31c;
      $red: #e61919;
      $yellow: #e6e619;
      $green: #19e635;
      $orange: #ffa600;
      $purple: #9900ff;
      $gray: #808080;
      $black: #000;
      $white: #fff; 
      
      // sass map
      $colors:(
        'primary': $primary,
        'secondary': $secondary,
        'error': $error,
        'info': $info,
        'red': $red,
        'yellow': $yellow,
        'green': $green,
        'orange': $orange,
        'purple': $purple,
        'gray': $gray,
        'black': $black,
        'white': $white   
      );
      
      // 使用map
      .wrap {
         background: map-get($colors, 'purple')
      }
      
      @debug map-get($colors, 'gray')
      // 返回布尔值，查询map对象$colors里是否有键名info
      @debug map-has-key($colors, 'info') // true
      @debug map-remove($colors, 'gray')// 删除gray
      @debug map-merge($colors, ('pink': #ffc0cb)) // 添加pink颜色
      ```
      
      PS: 注意 debug时，需要在VSCode编辑器的User区的settings里Live Sass Compile > Settungs : Show Output Window on 的下拉框里的选项Debug
   
   5. each 和 for 循环：@each  @for
      
      ```scss
      $sizes: 40px, 50px, 80px;
      
      @each $size in $sizes {
        .icon-#{$size} {
          font-size: $size;
          height: $size;
          width: $size;
        }
      }
      
      ```
      
      ```scss
      // 和map一起使用each循环
      $icons: (
          "eye": "\f112", 
          "start": "\f12e", 
          "stop": "\f12f"
      );
      
      @each $name, $glyph in $icons {
        .icon-#{$name}:before {
          display: inline-block;
          font-family: "Icon Font";
          content: $glyph;
        }
      }
      
      
      $colors:(
        'primary': $primary,
        'secondary': $secondary,
        'error': $error,
        'info': $info,
        'red': $red,
        'yellow': $yellow,
        'green': $green,
        'orange': $orange,
        'purple': $purple,
        'gray': $gray,
        'black': $black,
        'white': $white   
      );
      
      @each $key, $val in $colors {
        .text-#{$key} {
          color: $val;
        }
        .bg-#{$key} {
          background-color: $val;
        }
      }
      ```
      
      ```scss
      // for循环里使用mix()可实现颜色渐变效果
      @each $key, $val in $colors {
      
        // for 循环
        @for $i from 1 through 6 {
          .text-#{$key}-light-#{$i} {
            color: mix(#fff, $val, $i*10)
          }
          .bg-#{$key}-light-#{$i} {
            background-color: mix(#fff, $val, $i*10)
          }
        }
      
        @for $i from 1 through 6 {
          .text-#{$key}-dark-#{$i} {
            color: mix(#000, $val, $i*10)
          }
          .bg-#{$key}-dark-#{$i} {
            background-color: mix(#000, $val, $i*10)
          }
        }
      }
      ```
   
   6. 条件语句: @if
      
      ```scss
      //如果$val不等于#000且不等于#fff时，才会进行for循环处理
        @if($val != #000 and $val != #fff){
            // for 循环
            @for $i from 1 through 6 {
              .text-#{$key}-light-#{$i} {
                color: mix(#fff, $val, $i*10)
              }
              .bg-#{$key}-light-#{$i} {
                background-color: mix(#fff, $val, $i*10)
              }
            }
      
            @for $i from 1 through 6 {
              .text-#{$key}-dark-#{$i} {
                color: mix(#000, $val, $i*10)
              }
              .bg-#{$key}-dark-#{$i} {
                background-color: mix(#000, $val, $i*10)
              }
            }
        }
      ```
   
   7. 获取父元素: &
      
      一般情况下，`sass`在解开一个嵌套规则时就会把父选择器（`#content`）通过一个空格连接到子选择器的前边（`article`和`aside`）形成（`#content article`和`#content aside`）。这种在CSS里边被称为后代选择器，因为它选择ID为`content`的元素内所有命中选择器`article`和`aside`的元素。但在有些情况下你却不会希望`sass`使用这种后代选择器的方式生成这种连接。
      
      最常见的一种情况是当你为链接之类的元素写`：hover`这种伪类时，你并不希望以后代选择器的方式连接。比如说，下面这种情况`sass`就无法正常工作：
      
      ```scss
      article a {
        color: blue;
        :hover { color: red }
      }
      ```
      
      这意味着`color: red`这条规则将会被应用到选择器`article a :hover`，`article`元素内链接的所有子元素在被`hover`时都会变成红色。这是不正确的！你想把这条规则应用到超链接自身，而后代选择器的方式无法帮你实现。
      
      解决之道为使用一个特殊的`sass`选择器，即父选择器。在使用嵌套规则时，父选择器能对于嵌套规则如何解开提供更好的控制。它就是一个简单的`&`符号，且可以放在任何一个选择器可出现的地方，比如`h1`放在哪，它就可以放在哪。
      
      在为父级选择器添加`：hover`等伪类时，这种方式非常有用:
      
      ```scss
      article a {
        color: blue;
        &:hover { color: red }
      }
      ```
      
      当包含父选择器标识符的嵌套规则被打开时，它不会像后代选择器那样进行拼接，而是`&`被父选择器直接替换：
      
      ```css
      article a { color: blue }
      article a:hover { color: red }
      ```
   
   8. mixin混入: @mixin
      
      mixin混入可以避免大量相同的重复样式代码, 
      
      **通过@include + 需要的样式类名()调用** 
      
      ```scss
      // @mixin 部分是不同元素都需要使用的样式
      @mixin btn($bg-color:#e2e2e2){ // 设置背景颜色的默认值
        text-decoration: none;
            cursor: inline-block;
            border: 0;
            padding: $base-padding $base-padding * 2;
            border-radius: $base-border-radius;
            background-color: $bg-color;
      }
      
      // 设置button的默认样式
      .btn {
         @include btn; // btn后没有圆括号，则会直接调用btn的默认样式
      }
      
      @each $key, $val in $colors {
          .btn-#{$key}{
            @include btn($val); // 调用需要的样式
            &:hover {
              background-color: lighten($val, 4);
            }
          }
          .btn-outlined-#{$key} {
            @include btn(#fff); // 调用需要的样式
            border: $base-border-thickness solid $val;
            &:hover {
              background-color: $val;
            }
          }
      }
      ```
   
   9. function函数: @function + 函数名(){ }, 返回值通过@return返回
      
      ```scss
      //_functions.scss文件里定义函数
      @function light-comp($color){
         $complement: complement($color);
         $light-complement: lighten($complement, 30%);
         @return $light-complement;
      }
      ```
      
      ```scss
      // 在_buttons.scss文件里调用函数
      @each $key, $val in $colors {
          .btn-complement-#{$key} {
            @include btn($val);
            color: light-comp($val); // 调用函数
            &:hover{
              color:$val;
            }
            background-color: light-comp($val); // 调用函数
          }
      }
      ```
   
   10. 媒体查询
       
       ```scss
       // 媒体查询
       $breakpoints:(
         'xs': 0,
         'sm': 480px,
         'md': 720px,
         'lg': 960px,
         'xl': 1200px,
       );
       
       @mixin xs{
         @media(min-width:map-get($breakpoints, 'xs')){
           @content; // 占位符
         }
       }
       
       @mixin sm{
         @media(min-width:map-get($breakpoints, 'sm')){
           @content; // 占位符
         }
       }
       
       @mixin md{
         @media(min-width:map-get($breakpoints, 'md')){
           @content; // 占位符
         }
       }
       
       @mixin lg{
         @media(min-width:map-get($breakpoints, 'lg')){
           @content; // 占位符
         }
       }
       
       @mixin xl{
         @media(min-width:map-get($breakpoints, 'xl')){
           @content; // 占位符
         }
       }
       
       @mixin breakpoint($bp:0){
         @media (min-width:$bp){
           @content;
         }
       }
       
       .responsive-test{
         @include xs {
           color: red;
         }
         @include sm {
           color: green;
         }
         @include md {
           color: blue;
         }
         @include lg {
           color: yellow;
         }
         @include xl {
           color: pink;
         }
         @include breakpoint(1400px){
           color: orange;
         }
       }
       ```
   
   11. 继承: @extend
       
       Sass 允许一个选择器继承另一个选择器
       
       ```scss
       .class1 {
       　　border: 1px solid #ddd;
       }
       
       .class2 {
       　　@extend .class1;
       　 font-size:120%;
       }
       ```
       
       
