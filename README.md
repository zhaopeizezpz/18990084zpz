<?xml version="1.0" encoding="utf-8"?>

<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"

    xmlns:app="http://schemas.android.com/apk/res-auto"

    xmlns:tools="http://schemas.android.com/tools"

    android:layout_width="match_parent"

    android:layout_height="match_parent"

    tools:context=".Marquee">



    <!-- 这个是普通的文本视图 -->

    <TextView

        android:id="@+id/tv_msg"

        android:layout_width="match_parent"

        android:layout_height="wrap_content"

        android:layout_marginTop="20dp"

        android:gravity="center"

        android:text="跑马灯效果，点击暂停，再点击恢复"

        app:layout_constraintEnd_toEndOf="parent"

        app:layout_constraintStart_toStartOf="parent"

        app:layout_constraintTop_toTopOf="parent" />



    <!-- 这个是跑马灯滚动的文本视图，ellipsize属性设置为true表示文字从右向左滚动 -->

    <TextView

        android:id="@+id/tv_marquee"

        android:layout_width="match_parent"

        android:layout_height="wrap_content"

        android:layout_marginTop="20dp"

        android:ellipsize="marquee"

        android:focusable="true"

        android:focusableInTouchMode="true"

        android:singleLine="true"

        android:text="18990084赵沛泽！18990084赵沛泽！18990084赵沛泽！18990084赵沛泽！"

        android:textColor="#FF5722"

        android:textSize="17sp"

        app:layout_constraintEnd_toEndOf="parent"

        app:layout_constraintStart_toStartOf="parent"

        app:layout_constraintTop_toBottomOf="@+id/tv_msg" />



</androidx.constraintlayout.widget.ConstraintLayout>















package com.example.chash;

import androidx.appcompat.app.AppCompatActivity;



import android.os.Bundle;

import android.text.method.ScrollingMovementMethod;

import android.view.View;

import android.widget.TextView;



import com.example.chash.util.DateUtil;



public class bbs extends AppCompatActivity implements View.OnClickListener, View.OnLongClickListener {

    private TextView tv_bbs;

    private TextView tv_control;


    @Override

    protected void onCreate(Bundle savedInstanceState) {

        super.onCreate(savedInstanceState);

        setContentView(R.layout.activity_bbs);


        tv_control = findViewById(R.id.tv_control);

        tv_control.setOnClickListener(this);

        tv_control.setOnLongClickListener(this);

        tv_bbs = findViewById(R.id.tv_bbs);

        tv_bbs.setOnClickListener(this);

        tv_bbs.setOnLongClickListener(this);

        // 设置tv_bbs内部文本的移动方式为滚动形式

        tv_bbs.setMovementMethod(new ScrollingMovementMethod());

    }


    private String[] mChatStr = {"你吃饭了吗？", "我没吃饭。",

            "18990084赵沛泽！", "我们去吃饭吧", "我能吃好多",};


    @Override

    public void onClick(View v) {

        if (v.getId() == R.id.tv_control || v.getId() == R.id.tv_bbs) {

            // 生成一个0到4之间的随机数

            int random = (int) (Math.random() * 10) % 5;

            // 拼接聊天的文本内容

            String newStr = String.format("%s\n%s %s",

                    tv_bbs.getText().toString(), DateUtil.getNowTime(), mChatStr[random]);

            // 设置文本视图tv_bbs的文本内容

            tv_bbs.setText(newStr);

        }

    }


    @Override

    public boolean onLongClick(View v) {

        if (v.getId() == R.id.tv_control || v.getId() == R.id.tv_bbs) {

            tv_bbs.setText("");

        }

        return true;

    }
}


