# 应用视觉设计

- strong 加粗

- u 下划线

- em标签 斜体 用于强调文本

- s标签 删除线

- hr标签 水平线

- rgba设置颜色  a:alpha  透明度

- font-size 字体大小

- box-shadow

- opacity,设置透明度，1为完全不透明 0为完全透明

- text-transform:改变文本的大小写

- font-weight:设置字体粗细

- line-height，设置行间间距

- hover与伪类，伪类是添加到选择器上的选择器，用于选择特定状态的元素

- position:relative

- position:absolute,绝对定位的元素定位参照于最近的祖先元素，脱离文档流，若父元素没有添加定位元素(默认为relative)，则它会继续寻找直到body标签为止。

- position:fixed,相对浏览器窗口定位，特殊的绝对定位，脱离文档流，与绝对定位区别是不会随着屏幕滚动而移动(小广告专用定位方式！可恶！)

- float，脱离文档流，可设置其值为left或right，通常需要设置width属性来指定浮动元素占据的水平空间

- z-index:指定元素堆叠次序

- 元素居中方法一:margin:auto

- hsl(色相，饱和度，亮度)，CSS3引入此方式作为颜色的描述方式，如红色hsl(0,100%,50%)

- 颜色渐变:background: linear-gradient(gradient_direction, color 1, color 2, color 3, ...);

  -  background: linear-gradient(35deg, #CCFFFF, #FFCCCC);

     }

- 通过background:url()可以给页面添加纹理。

- transform:scale(2)，把元素放大两倍

- transform有很多用处，可以调整大小、移动、翻转、旋转。

- transform:skewX(-32deg),使元素沿着x轴倾斜-32度。skewY(24deg),使元素沿着y轴倾斜24度

- ::before,所选元素的第一个子元素，::after,所选元素的最后一个子元素，它们都必须配合content使用，当使用此属性实现形状时，把content的值设置为空字符串即可。

- animation属性控制动画外观，@keyframes控制动画各阶段的变化，animation-name设置动画名称，animation-duration设置动画花费时间。

  - ```css
      #rect {
     animation-name:rainbow;
     animation-duration:4s;
      }
      @keyframes rainbow{
        0%{
          background-color:blue;
        }
        50%{
          background-color:green;
        }
        100%{
          background-color:yellow;
        }
      }
    ```

- animation-fill-mode: forwards;    用于保持动画始终停留在最后一刻。

- animation-iteration-count: 3;  动画循环次数为3。infintie则动画无限循环

- animation-timing-function用来定义动画的速度曲线，如果要描述的动画是一辆车在指定时间内（animation-duration）从 A 运动到 B，那么 animation-timing-function 表述的就是车在运动中的加速和减速等过程。ease(默认值):低速开始，加速，结束前变慢。ease-out:高速开始、低俗结束 ease-in:低速开始，高速结束。linear:动画从头到尾速度相同。

- 贝塞尔曲线(Bezier curves):用于更细致地控制动画的速度曲线。cubic-bezier 函数包含了 1 * 1 网格里的4个点：p0、p1、p2、p3。 其中 p0 和 p3 是固定值，代表曲线的起始点和结束点，坐标值依次为 (0, 0) 和 (1, 1)。 你只需设置另外两点的 x 值和 y 值，设置的这两点确定了曲线的形状从而确定了动画的速度曲线。 在 CSS 里面通过 (x1, y1, x2, y2) 来确定 p1 和 p2。 以下就是 CSS 贝塞尔曲线的例子：

  - animation-timing-function: cubic-bezier(0.25, 0.25, 0.75, 0.75); 此时曲线是一条从原点到(1,1)的直线，即元素速度为线性，效果与linear相同，元素匀速运动。

# 应用无障碍

- alt='',img标签属性，用于当图片无法显示时替代图片，也有利于搜索引擎搜索 对于有标题的图片，依然需要添加 `alt` 文本，因为这样有助于搜索引擎记录图片内容

- `main` 标签用于呈现网页的主体内容，且每个页面应只有一个。`main` 标签也有一个内嵌的特性，以便辅助技术快速定位到页面的主体。 如果你在页面顶部看到过“跳转到主要内容”链接，那么使用 `main` 标签会自动让辅助设备具有这个跳转的功能

- article标签用于独立且完整的内容，section用于对与主题相关的内容进行分组。

- header标签可以为父级标签呈现简介信息或者导航链接，适用于那些在多个页面顶部重复出现的内容。`header` 的语义化特性也可以让辅助工具快速定位到它的内容

- nav标签用于使屏幕阅读器快速识别出页面的导航信息，它呈现页面中的主导航链接。

- footer类似nav，它位置页面底部，用于呈现版权信息或相关文档链接。

- audio，呈现音频内容，支持controls属性用于显示浏览器默认播放、停止和其他控制以及支持键盘功能。

  ```css
      <p>A sound clip of Zersiax's screen reader in action.
      <audio controls>
        <source src='https://s3.amazonaws.com/freecodecamp/screen-reader.mp3' type='audio/mpeg'>
        </source></audio>
      </p>
  ```

- figure与figcaption标签，用于展示可视化信息如图片、图表及其标题

