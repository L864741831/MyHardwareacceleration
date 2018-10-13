package com.edu.hardwareacceleration.myhardwareacceleration;

import android.support.v7.app.AppCompatActivity;
import android.os.Bundle;

public class MainActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);


        /*
            <!--
    在Android清单文件中，将以下属性添加到 标记以为整个应用程序启用硬件加速
    android：hardwareAccelerated = “true”

    自定义view绘图最好关闭硬件加速

如果您的应用程序在全局启用硬件加速时行为不正常，您也可以针对各个活动控制它。
要在活动级别启用或禁用硬件加速，可以使用android:hardwareAccelerated该元素的属性。
    <activity android:hardwareAccelerated="false" />
    -->

         */


        /*
        技巧和窍门
切换到硬件加速的2D图形可以立即提高性能，但您仍应按照以下建议设计应用程序以有效使用GPU：

减少应用程序中的视图数量
系统必须绘制的视图越多，它就越慢。这也适用于软件渲染管道。减少视图是优化UI的最简单方法之一。

避免透支
不要在彼此之上绘制太多层。
删除任何被其他不透明视图完全遮挡的视图。如果您需要绘制多个彼此叠加的图层，请考虑将它们合并到单个图层中。当前硬件的一个好的经验法则是每帧的屏幕上的像素数不会超过2.5倍（位图计数中的透明像素！）。

不要在绘制方法中创建渲染对象
一个常见的错误是每次调用渲染方法时创建一个新的Paint或新的Path。这会强制垃圾收集器更频繁地运行，并绕过硬件管道中的缓存和优化。

不要经常修改形状
例如，复杂的形状，路径和圆圈使用纹理蒙版进行渲染。每次创建或修改路径时，硬件管道都会创建一个新的掩码，这可能很昂贵。
不要经常修改位图
每次更改位图的内容时，下次绘制时它都会再次作为GPU纹理上载。

小心使用alpha
当您使用setAlpha(),, AlphaAnimation或创建半透明视图时ObjectAnimator，它会在屏幕外缓冲区中呈现，该缓冲区会使所需的填充率加倍。
在非常大的视图上应用alpha时，请考虑将视图的图层类型设置为 LAYER_TYPE_HARDWARE。
         */
    }
}
