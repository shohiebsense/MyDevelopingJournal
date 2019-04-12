# MyDevelopingJournal
Emm.. yeah.. emm.. hehe :)

Cases

1. Your home app displays Toolbar that can be scrolled, and there is a framelayout contains fragment. This fragment contains viewpagers (yes, multiple viewpager) which are displaying recyclerview. What you are gonna do is you wrapped the framelayoutin the activity inside NestedScrollview. Then in the layout fragment, wrapped entire layout with nestedscrollview again for scrolling those multiple viewpager. Put each viewpager absolute height neither wrap content nor match_parent. 

Like this
> activity_main
```xml
<?xml version="1.0" encoding="utf-8"?>
<android.support.v4.widget.NestedScrollView 
xmlns:android="http://schemas.android.com/apk/res/android"
xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    app:layout_behavior="@string/appbar_scrolling_view_behavior"
    android:fillViewport="true"
    tools:context=".view.page.home.MainActivity"
    tools:showIn="@layout/activity_main">

    <FrameLayout
        android:id="@+id/frameLayout"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        app:layout_behavior="@string/appbar_scrolling_view_behavior" />


</android.support.v4.widget.NestedScrollView>
```
> fragment_main

```xml
<?xml version="1.0" encoding="utf-8"?>
<android.support.v4.widget.NestedScrollView
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:id="@+id/scroll_root"
    android:background="@color/white_light"
    app:layout_behavior="@string/appbar_sc_view_behavior"
    >

        <android.support.constraint.ConstraintLayout
            android:layout_width="match_parent"
            android:layout_height="wrap_content">

        <android.support.design.widget.TabLayout
            android:focusable="true"
            android:focusableInTouchMode="true"
            android:id="@+id/tab_a_b"
            android:layout_width="match_parent"
            android:layout_height="0dp"
            app:layout_constraintTop_toBottomOf="@+id/layout_point"
            app:layout_constraintLeft_toLeftOf="parent"
            app:layout_constraintRight_toRightOf="parent"
            app:tabIndicatorColor="@color/color_tab_indicator"
            app:tabSelectedTextColor="@color/color_tab_text_selected"
            app:tabTextColor="@color/color_tab_text"
            app:tabTextAppearance="@style/AppTheme.TextAppearance.Tab"
            >

            <android.support.design.widget.TabItem
                android:id="@+id/tab_item_a"
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:text="@string/promo" />

            <android.support.design.widget.TabItem
                android:id="@+id/tab_item_b"
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:text="@string/spot" />

        </android.support.design.widget.TabLayout>

        <ScrollableViewPager
            android:id="@+id/pager_a_b"
            android:layout_width="match_parent"
            android:layout_height="400dp"
            app:layout_constraintLeft_toLeftOf="parent"
            app:layout_constraintRight_toRightOf="parent"
            app:layout_constraintTop_toBottomOf="@+id/tab_a_b"
            />

        <android.support.design.widget.TabLayout
            android:focusable="true"
            android:focusableInTouchMode="true"
            android:id="@+id/tab_c_d"
            android:layout_width="match_parent"
            android:layout_height="0dp"
            app:tabIndicatorColor="@color/color_tab_indicator"
            app:tabSelectedTextColor="@color/color_tab_text_selected"
            app:tabTextColor="@color/color_tab_text"
            app:layout_constraintLeft_toLeftOf="parent"
            app:layout_constraintRight_toRightOf="parent"
            app:layout_constraintTop_toBottomOf="@+id/pager_a_b"
            >

            <android.support.design.widget.TabItem
                android:id="@+id/tab_item_b"
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:text="@string/news" />

            <android.support.design.widget.TabItem
                android:id="@+id/tab_item_c"
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:text="@string/event" />

        </android.support.design.widget.TabLayout>

        <ScrollableViewPager
            android:id="@+id/pager_c_d"
            android:layout_width="match_parent"
            android:layout_height="400dp"
            android:nestedScrollingEnabled="true"
            app:layout_constraintLeft_toLeftOf="parent"
            app:layout_constraintRight_toRightOf="parent"
            app:layout_constraintTop_toBottomOf="@+id/tab_home_news_event"
            app:layout_constraintBottom_toBottomOf="parent"
            />


        </android.support.constraint.ConstraintLayout>
</android.support.v4.widget.NestedScrollView>
```

2. Use recyclerview and apply FlexBoxLayoutManager, like when you created items horizontally and wrapped to the width of device.

3. You have to set typeface programmatically to change Input Layout text/hint

4. For applying different colors in text, use foregroundcolorspan
SpanableString(string)
ForegroundColorSpan(
StyleSpan(

5. LRUCache is flexible in terms of data type compared to SharedPreferences, but LRUCache accepts thread safe only.

6. Don't use ListAdapter when it is so many user interactions, user recyclerview.adapter instead. submitlist still has an issue.

7. StartActivityForResult In Stacks
https://medium.com/@douglas.iacovelli/android-send-result-back-through-multiple-activities-finished-or-not-4c2ba9e95112

https://www.google.com/search?client=firefox-b-d&q=FLAG_ACTIVITY_FORWARD_RESULT
FLAG_ACTIVITY_FORWARD_RESULT

8. Look upon this link if your generating signed apk error
https://stackoverflow.com/questions/24098494/error-when-generate-signed-apk/52403664

9. Consider to know the difference between SharedPreference.Editor.apply() and commit(). Commit() does the job immediately.

10. To sync-to not sync strategy:
Using timestamp as flags, store the latest timestamp in SharedPreference
- Using last upload time & last download time. When it's more often to interact.
- Using last update.... if it's less often to interact.. like. Master Data.

https://coderwall.com/p/gt_rfa/simple-data-synchronisation-for-web-mobile-apps-working-offline

- last_update_on
- created_on
- deleted_on

https://dzone.com/articles/how-to-make-mobile-app-work-offline

- sync it using time stamp

https://medium.com/mindorks/to-synk-or-not-to-synk-fcc6e4c56e14

https://github.com/google/iosched

https://github.com/karntrehan/Posts



