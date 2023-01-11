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
