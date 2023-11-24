# Project-Intent-Wafha

Nama : Wafha Zahra Mulqiya

NIM : 312210577

Kelas : TI.22.A5

Mata Kuliah : Pemrograman Mobile 1

Tugas :

Buatkanlah :

1. Launcher Splash logo masing-masing Individu 

2. Buatkanlah untuk menampilkan semua project sebelum UTS dengan metode Ekplisit Intent dan

     Implisit Intent:

    a. Project Hallo

    b. Project Count

    c. Project Sianida

    d. Project TwoActivity

    e. Project Set Alarm

 Untuk tampilan Layout Bebas, terima kasih.
 
1. Launcher Splash Logo Pertama, yaitu membuat Launcher Splash Logo atau menampilkan logo / icon saat kita pertama kali membuka aplikasi. Caranya adalah :
 a. Persiapkan gambar terlebih dahulu
 b. Selanjutnya kita klik app, lalu klik res dan setelahnya kita pilih dan klik mipmap
 c. Setelah itu klik kanan pada bagian mipmap , lalu pilih new
 d. Lalu pilih dan klik Image Asset
 e. Lalu ketika sudah terbuka, kita klik bagian Icon Type lalu pilih yang Launcher Icons (Adaptive and Legacy)
 f. Lalu pada bagian Path kita klik logo file lalu kita pilih dan klik file gambar yang telah disiapkan sebelumnya dan klik OK
 g. Lalu untuk ukuran logo / ikon bisa kita atur pada bagian Resize, Jika sudah kita klik Next
 h. Setelah itu kita klik Finish, Maka logo / ikon aplikasi kita akan berubah sesuai gambar yang kita inginkan

Untuk menambahkan file gambar seperti untuk SplashScreen, Background di setiap project kita bisa klik bagian Resource Manager lalu kita klik tanda +. Setelah itu kita pilih dan klik Import Drawables, setelah itu kita pilih dan klik file gambar yang sudah kita siapkan lalu klik OK. Maka gambar akan tersedia di res pada drawable.

Lalu buka backgroundlauncher.xml dan masukkan code ini :
<?xml version="1.0" encoding="utf-8"?>
<layer-list xmlns:android="http://schemas.android.com/apk/res/android">
    <item android:drawable="@color/birumuda"/>
    <item>
        <bitmap
            android:src="@drawable/logo"
            android:gravity="center" />
    </item>
</layer-list>
Untuk Warna bisa kita sesuaikan dengan Logo yang telah kita tambahkan tadi

Lalu, buka themes.xml yang letaknya ada di res/values/themes, dan tambahkan code ini didalam resourcesnya :
<resources xmlns:tools="http://schemas.android.com/tools">
    <!-- Base application theme. -->
    <style name="SplashScreen" parent="Theme.MaterialComponents.DayNight.NoActionBar">
        <item name="android:windowBackground">@drawable/bg2</item>
        <item name="android:statusBarColor">?attr/colorOnPrimary</item>
    </style>
</resources>
Selanjutnya kita buat java class nya agar SplashScreen bisa berjalan, lalu pada SplashScreen.java kita masukkan code dibawah ini :
package com.example.projectwafha;

import android.content.Intent;
import android.os.Bundle;
import android.os.Handler;

import androidx.appcompat.app.AppCompatActivity;

public class SplashScreen extends AppCompatActivity {
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);

        new Handler().postDelayed(new Runnable() {
            @Override
            public void run() {
                startActivity(new Intent(SplashScreen.this, MainActivity.class));
                finish();
            }
        }, 2500);
    }
}
Code di atas digukankan untuk menampilkan SplashScreen, ketika SplashScreen selesai dalam 2.5 detik maka akan langsung berpindah pada tampilan MainActivity.java.

Buka AndroidManifest.xml, dan tambahkan code berikut didalam application :
<activity
            android:name=".SplashScreen"
            android:exported="true"
            android:theme="@style/SplashScreen">
            <intent-filter>
                <action android:name="android.intent.action.MAIN" />
                <category android:name="android.intent.category.LAUNCHER" />
            </intent-filter>
</activity>
Selesai sudah kita membuat perintah Launcher Splash Logo, Selanjutnya kita akan ke tahap berikutnya yaitu membuat menu untuk menampilkan semua project yang sudah dibuat pada pertemuan sebelumnya.

2. Menu Utama
Yang kedua, disini kita akan membuat menu utamanya yang akan berjalan setelah SplashScreen Logo. Caranya adalah:

Jika awal pembuatan project kita memilih template Empty Views Activity, maka pada layout otomatis terbuat file activity_main.xml dan pada java akan ada MainActivity.java. Maka langsung saja kita buka activity_main.xml, dan buat code seperti berikut ini:

<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <ImageView
        android:id="@+id/background"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:background="@drawable/bg1"
        android:adjustViewBounds="true"
        android:scaleType="centerCrop"/>

    <TextView
        android:id="@+id/txtJudul"
        android:layout_width="match_parent"
        android:layout_height="68dp"
        android:layout_alignParentTop="true"
        android:layout_alignParentBottom="true"
        android:layout_marginTop="46dp"
        android:layout_marginBottom="569dp"
        android:gravity="center"
        android:scaleType="centerCrop"
        android:text="Please select and click on the project below"
        android:textColor="@color/black"
        android:textSize="25dp"
        android:textStyle="bold" />

    <Button
        android:id="@+id/btnHelloWorld"
        android:layout_width="150dp"
        android:layout_height="60dp"
        android:layout_alignParentStart="true"
        android:layout_alignParentTop="true"
        android:layout_alignParentEnd="true"
        android:layout_marginStart="100dp"
        android:layout_marginTop="200dp"
        android:layout_marginEnd="100dp"
        android:onClick="btnHelloWorld"
        android:background="@color/hijaumuda"
        android:text="Hello World!!!"
        tools:ignore="UsingOnClickInXml"
        android:scaleType="centerCrop"/>

    <Button
        android:id="@+id/btnProjectCount"
        android:layout_width="150dp"
        android:layout_height="60dp"
        android:layout_below="@+id/btnHelloWorld"
        android:layout_alignParentStart="true"
        android:layout_alignParentEnd="true"
        android:layout_marginStart="100dp"
        android:layout_marginTop="20dp"
        android:layout_marginEnd="100dp"
        android:onClick="btnCount"
        android:background="@color/cream"
        android:text="Count"
        tools:ignore="UsingOnClickInXml"
        android:scaleType="centerCrop"/>

    <Button
        android:id="@+id/btnProjectSianida"
        android:layout_width="150dp"
        android:layout_height="60dp"
        android:layout_below="@+id/btnProjectCount"
        android:layout_alignParentStart="true"
        android:layout_alignParentEnd="true"
        android:layout_marginStart="100dp"
        android:layout_marginTop="20dp"
        android:layout_marginEnd="100dp"
        android:onClick="btnSianida"
        android:background="@color/birumuda"
        android:scaleType="centerCrop"
        android:text="Scroll Movie"
        tools:ignore="UsingOnClickInXml" />

    <Button
        android:id="@+id/btnTwoActivity"
        android:layout_width="150dp"
        android:layout_height="60dp"
        android:layout_below="@+id/btnProjectSianida"
        android:layout_alignParentEnd="true"
        android:layout_alignParentStart="true"
        android:layout_marginTop="20dp"
        android:layout_marginEnd="100dp"
        android:layout_marginStart="100dp"
        android:onClick="btnTwoActivity"
        android:background="@color/pink"
        android:text="Two Activity"
        tools:ignore="UsingOnClickInXml"
        android:scaleType="centerCrop"/>

    <Button
        android:id="@+id/btnSetAlarm"
        android:layout_width="150dp"
        android:layout_height="60dp"
        android:layout_below="@+id/btnTwoActivity"
        android:layout_alignParentStart="true"
        android:layout_alignParentEnd="true"
        android:layout_marginStart="100dp"
        android:layout_marginTop="20dp"
        android:layout_marginEnd="100dp"
        android:onClick="btnSetAlarm"
        android:background="@color/purple"
        android:text="Set Alarm"
        tools:ignore="UsingOnClickInXml"
        android:scaleType="centerCrop"/>

</RelativeLayout>

