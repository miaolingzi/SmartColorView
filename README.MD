今天是2017年的第一个工作日，就用这个自定义颜色选择控件来纪念下吧～～

相信做过安卓应用的主题切换、富文本编辑器文字颜色切换、画笔颜色切换等项目，都会遇到关于颜色选择的UI，虽然效果很好实现，比如通过selector的形式就很容易，但是如果项目里面有多处关于颜色选择的UI，只是有一点点差别，
那么我们就得维护多套selector，不能达到复用的效果，因此，我总结几种常见的UI，通过自定义view达到组合及复用的效果。以下列出5中效果图，当然并不局限于这5中效果，通过多种属性的组合，可以实现很多种效果。

效果图：

<img src = "screenshots/Screenshot0.png" width = "540" height="960"/>
<img src = "screenshots/Screenshot1.png" width = "540" height="960"/>
<img src = "screenshots/Screenshot2.png" width = "540" height="960"/>
<img src = "screenshots/Screenshot3.png" width = "540" height="960"/>
<img src = "screenshots/Screenshot4.png" width = "540" height="960"/>
<img src = "screenshots/Screenshot5.png" width = "540" height="960"/>

使用方法：
Grab via maven

```xml
<dependency>
  <groupId>com.smart.colorview</groupId>
  <artifactId>colorview</artifactId>
  <version>1.1.1</version>
</dependency>
```
or gradle

```gradle
dependencies {
    compile 'com.smart.colorview:colorview:1.1.1'
}
```

布局代码：

```xml
<com.smart.colorview.normal.CircleColorView
xmlns:circle="http://schemas.android.com/apk/res-auto"
android:layout_width="wrap_content"
android:layout_height="wrap_content"
circle:circleColor="#9258c2"
circle:innerStrokeDividerWidth="6dp"
circle:innerStrokeWidth="0dp"
circle:innerType="inner"
circle:normalUseOutline="true"
circle:outlineStrokeColor="#9258c2"
circle:outlineStrokeWidth="2dp"
circle:selectUseFrame="false"
circle:selectUseOutline="true"/>
```
java代码：
```java
CircleColorModel circleColorModel = new CircleColorModel();
circleColorModel.setCircleColor(0xff9258c2);
circleColorModel.setSelectUseOutline(true);
circleColorModel.setOutlineStrokeWidth(4);
circleColorModel.setOutlineStrokeColor(0xff9258c2);
circleColorModel.setInnerType(CircleColorView.InnerType.INNER);
circleColorModel.setInnerStrokeWidth(0);
circleColorModel.setInnerStrokeDividerWidth(14);
circleColorModel.setCircleSelected(true);
mCircleColorView.setCircleColorModel(circleColorModel);
```
效果：
<img src="screenshots/xiaoguo1.png"/>
布局代码：
```xml
<com.smart.colorview.normal.RectangleColorView
xmlns:rectangle='http://schemas.android.com/apk/res-auto'
android:layout_width="wrap_content"
android:layout_height="wrap_content"
rectangle:rectOutlineStrokeWidth="0dp"
rectangle:rectShowTick="true"
rectangle:rectTickBackgroundColor="#fadb71"
rectangle:rectTickDirection="rightBottom"
rectangle:rectTickStrokeColor="#ffffff"
rectangle:rectTickStrokeWidth="2dp"
rectangle:rectTickType="auto"
rectangle:rectangleColor="#9258c2"
rectangle:rectangleCornerRadius="8dp"
rectangle:rectangleSelected="true"/>
```
java代码
```java
RectangleColorModel rectangleColorModel = new RectangleColorModel();
rectangleColorModel.setRectangleColor(0xff9258c2);
rectangleColorModel.setRectangleColorRadius(26);
rectangleColorModel.setRectTickStrokeWidth(4);
rectangleColorModel.setRectTickStrokeColor(0xffffffff);
rectangleColorModel.setRectTickBackgroundColor(0xfffadb71);
rectangleColorModel.setTickDirection(RectangleColorView.TickDirection.RIGHT_BOTTOM);
rectangleColorModel.setRectShowTick(true);
rectangleColorModel.setRectSelected(true);
mRectangleColorView.setRectangleColorModel(rectangleColorModel);
```
效果：
<img src="screenshots/xiaoguo2.png"/>

如果喜欢，欢迎star一下，您的star将是我开源路上永久的动力～～
