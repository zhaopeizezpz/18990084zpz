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
