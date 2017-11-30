# EaselJS

EaselJS是一个用于HTML5中构建高性能交互式2D内容的库。它提供了一个功能丰富的显示列表，允许你操作和动画图形。它还为鼠标和触摸交互事件提供了一个强大的交互式模型。

它非常适合于开发游戏、H5营销页面、数据可视化以及其他高级图形化的体验。它可以很好地运行，或者使用CreateJS组件的其他部分:SoundJS、PreloadJS和TweenJS。

它没有依赖任何框架，并且应该与你喜欢使用的任何框架兼容。

### 例子
```
//在画布画一个正方形
var stage = new createjs.Stage('myCanvas');
var shape = new createjs.Shape();
shape.graphics.beginFill('red').drawRect(0, 0, 120, 120);
stage.addChild(shape);
stage.update();
```

### 雪碧图动画例子
```
var ss = new createjs.SpriteSheet({
	frames: {
		width: 32,
		height: 64,
		numFrames: 19
	},
	animations: {run: [0, 25], jump: [26, 63, "run"]},
	images: ["./assets/runningGrant.png"]
});
	
var sprite = new createjs.Sprite(ss, "run");
sprite.scaleY = sprite.scaleX = 0.4;
stage.addChild(sprite);
	
sprite.on("click", function() { sprite.gotoAndPlay("jump"); });
	
createjs.Ticker.on("tick", stage);
```
### 支持和资源
- 去EaselJS网站找一个或者更多的例子；
- 看文档；
- 在reddit上讨论，分享项目，和其他用户互动；
- 去Stack Overflow提问/回答一些问题；
- 可以在Github上提BUG；
- 有一个谷歌小组讨论和支持；
- 请查看其中的示例和API文档，以获得更详细的信息。

它是由gskinner.com建立的，在麻省理工学院许可下免费发布，这意味着你可以用它来实现几乎任何项目(包括商业项目)。我们在可能的情况下接受赞赏，但这不是要求。

### 所有的类

该API有部分受到Flash显示列表的启发，并且应该更易于为JS和AS3开发人员所选择，更多信息请查看文档。

- DisplayObject 抽象基类的所有显示元素在EaselJS。公开所有显示对象所共有的所有显示属性(ex. x、y、rotation、scaleX、scaleY、skewX、skewY、alpha、shadow等)。
- Stage 显示元素的根级别显示容器。每个时间tick()在舞台上被调用，它将更新并将显示列表渲染到它的相关画布上。
- Container 一个nestable显示容器，它允许你聚合显示对象并将其作为一个组进行操作。
- Bitmap 根据显示属性将图像、视频或画布绘制到画布上。
- Sprite 从sprite表中显示单个帧或动画，并提供用于管理回放和排序的api。
- Shape 在显示列表的上下文中呈现图形对象。
- Graphics 为绘制矢量数据提供了一个易于使用的API。可用于形状，或完全独立。
- Text 在舞台上呈现一行文本。
- BitmapText 使用字母的SpriteSheet呈现文本。
- DOMElement 是一个实验性的显示对象，它允许您管理作为显示列表的一部分的HTML元素。
- Filter 其他过滤器(ex . BlurFilter,ColorMatrixFilter等)扩展的基本过滤器类。

**还有一些助手类包括：**

- Shadow 定义了在显示对象上显示阴影所需要的所有属性。
- Ticker为滴答的阶段实例或其他基于时间的代码提供了一个可pa可用的集中式蜱虫管理器。
- UID 非常简单的类，它提供了全局的、递增的惟一数字id。
- SpriteSheet 封装了与sprite一起使用的sprite表相关的所有数据。
- SpriteSheetUtils 包含使用翻转帧扩展现有的sprite片和提取单个帧的实用方法。
- SpriteSheetBuilder 在运行时从矢量图形构建一个位图SpriteSheet。通过SpriteSheet的性能得到矢量的filesize节省。
- Matrix2D 表示一个3x3仿射变换矩阵。内部用于计算连接转换。
- Rectangle 代表由点(x,y)和(x +宽度，y +高度)定义的矩形。
- Point 表示二维x / y坐标系中的一点。

**目前存在一个WebGL实现，但它是有限的：**

- StageGL 为EaselJS Stage类提供了一个完全支持WebGL管道的替代品。StageGL将绘制大多数基于位图的内容，包括任何缓存的displayobject。
- WebGLInspector 是一个实用程序和助手类，它设计用于与StageGL一起帮助调查和测试性能或显示问题。
