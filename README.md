# EaselJS

EaselJS是一个用于HTML5中构建高性能交互式2D内容的库。它提供了一个功能丰富的显示列表，允许你操作和动画图形。它还为鼠标和触摸交互事件提供了一个强大的交互式模型。

它非常适合于开发游戏、H5营销页面、数据可视化以及其他高级图形化的体验。它可以很好地运行，或者使用CreateJS组件的其他部分:SoundJS、PreloadJS和TweenJS。

它没有依赖任何框架，并且应该与你喜欢使用的任何框架兼容。

## 例子
```
//在画布画一个正方形
var stage = new createjs.Stage('myCanvas');
var shape = new createjs.Shape();
shape.graphics.beginFill('red').drawRect(0, 0, 120, 120);
stage.addChild(shape);
stage.update();
```

## 雪碧图动画例子
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
## 支持和资源
- 去EaselJS网站找一个或者更多的例子；
- 看文档；
- 在reddit上讨论，分享项目，和其他用户互动；
- 去Stack Overflow提问/回答一些问题；
- 可以在Github上提BUG；
- 有一个谷歌小组讨论和支持；
- 请查看其中的示例和API文档，以获得更详细的信息。
