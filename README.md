# SuperDecoration
[ ![Download](https://api.bintray.com/packages/staticsadhu/android/SuperDecoration/images/download.svg?version=1.0.1) ](https://bintray.com/staticsadhu/android/SuperDecoration/1.0.1/link) [![Build Status](https://travis-ci.org/sh1tge/SuperDecoration.svg?branch=master)](https://travis-ci.org/sh1tge/SuperDecoration)

快速设置`RecyclerView`item间间距, 配合此篇文章食用,味道更佳[戳我](https://www.wecando.cc/article/9)

# 特性
1. 支持`LinearLayoutManager`,`GridLayoutManager`
2. 支持单行或单列情况
3. 支持`reverseLayout==true`情况
4. 支持`GridLayoutManager`设置了`SpanSizeLookup`情况
5. 灵活设置各种间距


# sample截图

| LinearLayoutManager        |     normal GridLayoutManager      | GridLayoutManager with Span and reverseLayout   |
| :-------------: |:-------------:| :-------------:|
|<img src="http://blog.wecando.cc/image/20190701/FplFo6vP5gGbdJg-FRcomOFTc-Vy.png" width="540"/>|<img src="http://blog.wecando.cc/image/20190701/FoJW9iWBej5g7h-w0_c1U_pF-wmm.png" width="540"/>|<img src="http://blog.wecando.cc/image/20190701/FgMJJIIUzWEU7k4TpsezXdbeBMX8.png" width="540"/>|

# 使用实例

1. 引用库

```xml
  // 1.添加jcenter仓库
    allprojects {
        repositories {
           jcenter()
        }
    }
    // 2.添加项目依赖（last-version替换为最新版本号）
    dependencies {
        implementation "cc.wecando:SuperDecoration:${last-version}"
    }
```
2. 使用

```kotlin
        mRvContent.addItemDecoration(
            SuperOffsetDecoration.Builder(layoutManager, this)
                .setPrimaryEdgeSpace(12F) // 设置与orientation同方向,RecyclerView内间距,orientation为vertical时, 表示 paddingTop,paddingBottom
                .setSecondaryEdgeSpace(10F)// 设置与orientation垂直方向,RecyclerView内间距,orientation为vertical时, 表示 paddingLeft,paddingRight
                .setPrimarySpace(8F)// 设置与orientation同方向,ItemView的间距
                .setSecondarySpace(4F)// 设置与orientation垂直方向,ItemView的间距, LinearLayoutManager无效
                .build()
        )

```

# 主要Api

| 名称        |     说明      | 
| :-------------: |:-------------:|
|setPrimaryEdgeSpace|  设置与orientation同方向,RecyclerView内间距|
|setSecondaryEdgeSpace| 设置与orientation垂直方向,RecyclerView内间距|
|setPrimarySpace| 设置与orientation同方向,ItemView的间距|
|setSecondarySpace| 设置与orientation垂直方向,ItemView的间距, LinearLayoutManager无效|
