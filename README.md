# ViewSnackBarBehavitor


* material design Snackbar 弹出时把布局顶上去的特性（Behavior）

* 在android 源码中，FloatingActionButton中有一个默认的Behavior: `public static class Behavior extends CoordinatorLayout.Behavior<FloatingActionButton>`,来出来FloatingActionButton与SnackBar的联动，这里只是针对FloatingActionButton,但是我们想让自己的View与SnackBar联动需要写自己的Behavior,理论上讲，google只要把`public static class Behavior extends CoordinatorLayout.Behavior<FloatingActionButton>`改成`public static class Behavior extends CoordinatorLayout.Behavior<View>`我们就可以用这个Behavior,但是是FloatingActionButton，我们就用不了了。这里我就把源码拷贝出来自己按上面做了修改而已。





----

####**FloatingActionButton** 与**SnackBar**的效果图

![img1](https://github.com/cocolove2/ViewSnackBarBehavitor/blob/master/screenshot/res_3.gif)


####**ImageView** 与**SnackBar**的效果图

![img2](https://github.com/cocolove2/ViewSnackBarBehavitor/blob/master/screenshot/res_4.gif)

---


###How To Use

* use like this

```
<?xml version="1.0" encoding="utf-8"?>
<android.support.design.widget.CoordinatorLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:fitsSystemWindows="true"
    tools:context="com.viewsnackbarbehavior.MainActivity">
    
<!-- 这里的ImageView可以是任意布局View -->

    <ImageView
        android:id="@+id/img"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_gravity="bottom|end"
        android:padding="16dp"
        android:src="@mipmap/ic_launcher"
        android:visibility="visible"
        app:layout_behavior="com.viewsnackbarbehavior.design_extraction.ViewSnackBarBehavior" />


</android.support.design.widget.CoordinatorLayout>

```

