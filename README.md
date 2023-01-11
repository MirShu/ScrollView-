# ScrollView-
ScrollView 嵌套 RecyclerView 显示不全

ScrollView嵌套多个元素子view

```
<ScrollView
        android:id="@+id/my_scrollview"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:layout_below="@+id/view_line"
        android:scrollbarSize="3dp"
        android:scrollbarThumbVertical="@drawable/shape_content_scrollbars_style"
        android:layout_marginBottom="50dp"
        android:overScrollMode="never">
  <LinearLayout
        android:id="@+id/ll_title"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:orientation="vertical"
        android:visibility="gone">
  <X5WebView
        android:id="@+id/news_content"
        android:layout_width="match_parent"
        android:layout_height="200dp"
        android:layout_marginTop="@dimen/dp10"
        android:layout_marginBottom="@dimen/dp5" />
    <android.support.v7.widget.RecyclerView
        android:id="@+id/recycerView"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_marginLeft="10dp"
        android:layout_marginTop="@dimen/dp5"
        android:layout_marginRight="10dp" />

 <TextView
        android:id="@+id/tv_created_at"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginTop="15dp"
        android:paddingLeft="10dp"
        android:text="时间"
        android:textColor="@color/color_676767"
        android:textSize="@dimen/sp12"
        android:visibility="gone" />
 </LinearLayout>
 </ScrollView>

```

导致 RecyclerView item显示不全，十条数据只显示八条，滑动也有一点点粘连的感觉不是太流畅。
两张图片对比

![2781551-7cf3a3efda0f0b62](https://user-images.githubusercontent.com/13359093/211714307-2dd43f47-66ab-4dfa-b9b9-f8c91d616b86.png)


# 解决
# 1、使用NestedScrollView替代ScrollView，解决显示不全

```
<android.support.v4.widget.NestedScrollView

....

</android.support.v4.widget.NestedScrollView>

```
能显示全部item 没问题


![2781551-abab3878640eeebf](https://user-images.githubusercontent.com/13359093/211714455-9c51fc3a-38e3-4259-bb37-22ee1e8d5fde.png)

# 2、滑动粘连不太流畅，ScrollView和RecyclerView都有滑动事件，二者起了冲突，禁止掉RecyclerView滑动事件。 代码里面添加一句

```
Recycer.setNestedScrollingEnabled(false);
```
![2781551-3ff5a8a1c67b7a3c](https://user-images.githubusercontent.com/13359093/211714510-6bc304a2-0831-4c69-a246-31d26bc84cda.png)

