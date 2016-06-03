# AutoCompleteTextView

android 60 lesson
1.AutoCompleteTextView自动完成组件：类似于搜索引擎中输入一个关键字，然后程序自动下拉列出与之相匹配的词的选项.操作上有点类似
                                    Spinner组件,但AutoCompleteTextView只能通过代码来实现适配器.
2.AutoCompleteTextView实例：在res->layout->activity_main.xml中：
  <?xml version="1.0" encoding="utf-8"?>
  <RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
      xmlns:tools="http://schemas.android.com/tools"
      android:layout_width="match_parent"
      android:layout_height="match_parent"
      android:paddingBottom="@dimen/activity_vertical_margin"
      android:paddingLeft="@dimen/activity_horizontal_margin"
      android:paddingRight="@dimen/activity_horizontal_margin"
      android:paddingTop="@dimen/activity_vertical_margin"
      tools:context="com.example.mackerlee.android_60.MainActivity">
  
      <AutoCompleteTextView
          android:id="@+id/autocompleteTextView01"
          android:layout_width="match_parent"
          android:layout_height="wrap_content"
          //--设置输入多少个字符之后程序开始提示匹配，在这是输入2个字符后开始匹配
          android:completionThreshold="2"/>
  </RelativeLayout>
  在app->java->MainActivity.java中：
  package com.example.mackerlee.android_60;

  import android.support.v7.app.AppCompatActivity;
  import android.os.Bundle;
  import android.widget.ArrayAdapter;
  import android.widget.AutoCompleteTextView;
  
  public class MainActivity extends AppCompatActivity {
  
      private AutoCompleteTextView actv;
      private String[] names = {"xslj","zgr","land","zxc","llj"};
      @Override
      protected void onCreate(Bundle savedInstanceState) {
          super.onCreate(savedInstanceState);
          setContentView(R.layout.activity_main);
          actv = (AutoCompleteTextView)findViewById(R.id.autocompleteTextView01);
          //--设置适配器与数组关联
          ArrayAdapter<String> adapter = new ArrayAdapter<String>(this,android.R.layout.simple_dropdown_item_1line,names);
          //--设置适配器与ACTV组件关联
          actv.setAdapter(adapter);
      }
  
  }

  
