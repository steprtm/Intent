
## TUGAS PEMROGRAMAN MOBILE EXPLICIT & IMPLICIT INTENT
STEPHEN PRATAMA KURNIA

TI.22.A5 312210635

DOSEN PENGAMPUH : Donny Maulana, S.Kom., M.M.S.I.


Hasil Run :

https://github.com/steprtm/Intent/assets/129705802/916018da-74b9-44ec-b165-10eac54f5866


## [MainActivity.java](https://github.com/steprtm/Intent/blob/main/app/src/main/java/com/example/allproject/MainActivity.java) - [activity_main.xml](https://github.com/steprtm/Intent/blob/main/app/src/main/res/layout/activity_main.xml) - [AndroidManifest.xml](https://github.com/steprtm/Intent/blob/main/app/src/main/AndroidManifest.xml)




## AndroidManifest.xml
1.       xml version="1.0" encoding="utf-8"

    Deklarasi XML yang menandakan versi dokumen (1.0) dan pengkodean karakter (UTF-8).

2.      <manifest xmlns:android="http://schemas.android.com/apk/res/android" xmlns:tools="http://schemas.android.com/tools">
Deklarasi berkas manifest Android dengan namespace untuk Android dan tools.

3.      <uses-permission android:name="com.android.alarm.permission.SET_ALARM" />

Menyatakan bahwa aplikasi memerlukan izin untuk mengatur alarm.

4.      <application
        android:allowBackup="true"
        android:dataExtractionRules="@xml/data_extraction_rules"
        android:fullBackupContent="@xml/backup_rules"
        android:icon="@mipmap/ic_launcher"
        android:roundIcon="@mipmap/ic_launcher_round"
        android:supportsRtl="true"
        android:theme="@style/Theme.AllProject"
        tools:targetApi="31">

Mendefinisikan pengaturan utama dan komponen-komponen dari aplikasi Android.
Berbagai atribut seperti android:allowBackup, android:dataExtractionRules, android:fullBackupContent, android:icon, android:roundIcon, android:supportsRtl, android:theme, dan tools:targetApi diatur untuk mengonfigurasi aplikasi.
Deklarasi aktivitas (<activity ...>) di dalam tag <application>:

5.  <activity android:name=".AlarmActivity"
            android:exported="false"/>

        <activity
            android:name=".Two2Activity"
            android:exported="false" />

        <activity
            android:name=".TwoActivity"
            android:exported="false">
        </activity>

        <activity
            android:name=".SianidaActivity"
            android:exported="false" />

        <activity
            android:name=".CountActivity"
            android:exported="false" />

        <activity
            android:name=".HalloActivity"
            android:exported="false" />

        <activity
            android:name=".MainActivity"
            android:exported="true">
        </activity>

        <activity
            android:name=".SplashActivity"
            android:exported="true"
            android:theme="@style/Theme.Design.NoActionBar">
            <intent-filter>
                <action android:name="android.intent.action.MAIN" />
                <category android:name="android.intent.category.LAUNCHER" />
            </intent-filter>
        </activity>

Aktivitas seperti AlarmActivity, Two2Activity, dll., dideklarasikan dengan atribut android:exported yang menunjukkan apakah mereka dapat diakses oleh aplikasi lain ("true" atau "false").

MainActivity ditandai sebagai diekspor, mengindikasikan bahwa aktivitas tersebut dapat digunakan oleh aplikasi lain.

SplashActivity ditetapkan sebagai aktivitas utama (launcher) dengan <intent-filter> yang menentukan aksi utama dan kategori launcher.




## MainActivity.java
1.      package com.example.allproject;
Mendeklarasikan paket (package) dari kelas MainActivity. Kelas ini berada dalam paket com.example.allproject.

2.      import android.content.Intent;
        import android.os.Bundle;
        import android.view.View;
        import android.widget.Button;
        import androidx.appcompat.app.AppCompatActivity;
Mengimpor paket-paket yang diperlukan untuk kelas MainActivity, termasuk kelas Intent, Bundle, View, Button, dan AppCompatActivity.

3.      public class MainActivity extends AppCompatActivity {
Mendeklarasikan kelas MainActivity yang merupakan turunan dari kelas AppCompatActivity.

4.      @Override
protected void onCreate(Bundle savedInstanceState) {
Override metode onCreate yang dipanggil ketika aktivitas (activity) dibuat.

5.      super.onCreate(savedInstanceState);
setContentView(R.layout.activity_main);
Memanggil metode onCreate dari kelas induk dan mengatur tata letak aktivitas menggunakan file XML activity_main.

6.      Button helloButton = findViewById(R.id.HelloButton);
Mencari tombol dengan ID HelloButton dari tata letak dan menyimpannya dalam variabel helloButton.

7.      helloButton.setOnClickListener(new View.OnClickListener() {...});
Menetapkan listener untuk menanggapi klik pada tombol HelloButton. Ketika tombol ditekan, akan dijalankan kodenya dalam blok {...}.

8.      startActivity(new Intent(MainActivity.this, HalloActivity.class));
Memulai aktivitas baru (HalloActivity) ketika tombol HalloButton ditekan.

9.      Button countButton = findViewById(R.id.CountButton);
Mencari tombol dengan ID CountButton dan menyimpannya dalam variabel countButton.

10.     countButton.setOnClickListener(new View.OnClickListener() {...});
Menetapkan listener untuk menanggapi klik pada tombol CountButton. Ketika tombol ditekan, akan dijalankan kodenya dalam blok {...}.

11.     startActivity(new Intent(MainActivity.this, CountActivity.class));
Memulai aktivitas baru (CountActivity) ketika tombol CountButton ditekan.

12.     Button sianidaButton = findViewById(R.id.SianidaButton);
Mencari tombol dengan ID SianidaButton dan menyimpannya dalam variabel sianidaButton.

13.     sianidaButton.setOnClickListener(new View.OnClickListener() {...});
Menetapkan listener untuk menanggapi klik pada tombol SianidaButton. Ketika tombol ditekan, akan dijalankan kodenya dalam blok {...}.

14.     startActivity(new Intent(MainActivity.this, SianidaActivity.class));
Memulai aktivitas baru (SianidaActivity) ketika tombol SianidaButton ditekan.

15.     Button twoButton = findViewById(R.id.TwoButton);
Mencari tombol dengan ID TwoButton dan menyimpannya dalam variabel twoButton.

16.     twoButton.setOnClickListener(new View.OnClickListener() {...});
Menetapkan listener untuk menanggapi klik pada tombol TwoButton. Ketika tombol ditekan, akan dijalankan kodenya dalam blok {...}.

17.     startActivity(new Intent(MainActivity.this, TwoActivity.class));
Memulai aktivitas baru (TwoActivity) ketika tombol TwoButton ditekan.

18.     findViewById(R.id.AlarmButton).setOnClickListener(new View.OnClickListener() {...});
Menetapkan listener untuk menanggapi klik pada tombol dengan ID AlarmButton. Ketika tombol ditekan, akan dijalankan kodenya dalam blok {...}.

19.     private void setAlarm() {...}
Mendeklarasikan metode setAlarm(). Ini adalah metode khusus yang akan dijalankan ketika tombol AlarmButton ditekan.

20.     Intent alarm = new Intent(android.provider.AlarmClock.ACTION_SET_ALARM);
Membuat objek Intent untuk mengatur alarm menggunakan aksi ACTION_SET_ALARM dari penyedia alarm Android.

21.     startActivity(alarm);
Memulai aktivitas untuk mengatur alarm ketika tombol AlarmButton ditekan.
