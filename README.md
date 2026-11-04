
# Ex.No:3 Design an android application Send SMS using Intent.


## AIM:

To create and design an android application Send SMS using Intent using Android Studio.

## EQUIPMENTS REQUIRED:

Android Studio(Latest Version)

## ALGORITHM:

Step 1: Open Android Stdio and then click on File -> New -> New project.

Step 2: Then type the Application name as smsintent and click Next. 

Step 3: Then select the Minimum SDK as shown below and click Next.

Step 4: Then select the Empty Activity and click Next. Finally click Finish.

Step 5: Design layout in activity_main.xml.

Step 6: Send SMS and Display details give in MainActivity file.

Step 7: Save and run the application.

## PROGRAM:
```

Program to create and design an android application Send SMS using Intent.
Developed by: MOHANA PRIYA R
Register Number:  212224220065

```

## activity_main.xml
```
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    android:id="@+id/main"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <TextView
        android:id="@+id/textView"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Send SMS"
        android:textSize="34sp"
        app:layout_constraintBottom_toTopOf="@+id/btnSendSMS"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.054" />

    <EditText
        android:id="@+id/etPhone"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:ems="10"
        android:inputType="text"
        android:text="Enter Number"
        app:layout_constraintBottom_toTopOf="@+id/etMessage"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.079"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.805" />

    <EditText
        android:id="@+id/etMessage"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginBottom="492dp"
        android:ems="10"
        android:inputType="text"
        android:text="Enter Message"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.079"
        app:layout_constraintStart_toStartOf="parent" />

    <Button
        android:id="@+id/btnSendSMS"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginBottom="184dp"
        android:text="Send SMS"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent" />
</androidx.constraintlayout.widget.ConstraintLayout>
```

## MainActivity.java
```
package com.example.sms;

import android.content.Intent;
import android.net.Uri;
import android.os.Bundle;
import android.widget.Button;
import android.widget.EditText;

import androidx.activity.EdgeToEdge;
import androidx.appcompat.app.AppCompatActivity;
import androidx.core.graphics.Insets;
import androidx.core.view.ViewCompat;
import androidx.core.view.WindowInsetsCompat;

public class MainActivity extends AppCompatActivity {
    EditText etPhone, etMessage;
    Button btnSendSMS;
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        etPhone = findViewById(R.id.etPhone);
        etMessage = findViewById(R.id.etMessage);
        btnSendSMS = findViewById(R.id.btnSendSMS);

        btnSendSMS.setOnClickListener(v -> {
            String phoneNumber = etPhone.getText().toString().trim();
            String message = etMessage.getText().toString().trim();
            Intent intent = new Intent(Intent.ACTION_SENDTO);
            intent.setData(Uri.parse("smsto:" + phoneNumber));
            intent.putExtra("sms_body",message);
            startActivity(intent);
        });
    }
}
```

## OUTPUT

<img width="1920" height="1200" alt="Screenshot (154)" src="https://github.com/user-attachments/assets/2fc0b9c1-f8da-49c9-ab7a-1c108bddb479" />

<img width="1920" height="1200" alt="Screenshot (157)" src="https://github.com/user-attachments/assets/53926ed4-81d0-4f6a-926e-7c1ef589bebd" />



## RESULT
Thus a Simple Android Application create and design an android application Send SMS using Intent using Android Studio is developed and executed successfully.
