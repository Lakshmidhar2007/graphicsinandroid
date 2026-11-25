
# Ex.No:07 Design an application that draws basic graphical primitives on the screen.


## AIM:

To create and design an android application that draws basic graphical primitives on the screen using Android Studio.

## EQUIPMENTS REQUIRED:

Android Studio(Latest Version)

## ALGORITHM:

Step 1: Open Android Stdio and then click on File -> New -> New project.

Step 2: Then type the Application name as “graphical″ and click Next. 

Step 3: Then select the Minimum SDK as shown below and click Next.

Step 4: Then select the Empty Activity and click Next. Finally click Finish.

Step 5: Design layout in activity_main.xml.

Step 6: Draw basic object details give in MainActivity file.

Step 7: Save and run the application.

## PROGRAM:
```
Program to create and design an android application that draws basic graphical primitives on the screen.
Developed by: LAKSHMIDHAR N
Registration Number : 212224230138
```

### Activity_main.xml

```xml
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:padding="12dp"
    android:background="#FFFFFF">

    <!-- Experiment Heading -->
    <TextView
        android:id="@+id/txtHeading"
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:text="EXP-7 Design an application that draws basic graphical primitives on the screen."
        android:textSize="18sp"
        android:textStyle="bold"
        android:textColor="#000000"
        android:gravity="center"
        android:padding="10dp"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintEnd_toEndOf="parent"/>

    <!-- Graphical Primitives Image -->
    <ImageView
        android:id="@+id/imageView1"
        android:layout_width="0dp"
        android:layout_height="0dp"
        android:contentDescription="Graphical primitives"
        android:scaleType="fitXY"
        app:layout_constraintTop_toBottomOf="@id/txtHeading"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintEnd_toEndOf="parent"/>

</androidx.constraintlayout.widget.ConstraintLayout>

```

### MainActivity.java

```java

package com.example.exp7;

import androidx.appcompat.app.AppCompatActivity;
import android.graphics.Bitmap;
import android.graphics.Canvas;
import android.graphics.Color;
import android.graphics.LinearGradient;
import android.graphics.Paint;
import android.graphics.Shader;
import android.graphics.drawable.BitmapDrawable;
import android.os.Bundle;
import android.widget.ImageView;

public class MainActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        Bitmap bg = Bitmap.createBitmap(720, 1280, Bitmap.Config.ARGB_8888);

        ImageView imageView = findViewById(R.id.imageView1);
        imageView.setBackground(new BitmapDrawable(getResources(), bg));

        Canvas canvas = new Canvas(bg);
        canvas.drawColor(Color.LTGRAY);

        Paint paint = new Paint();
        paint.setTextSize(50);

        // Circle
        paint.setColor(Color.BLACK);
        paint.setShader(null);
        canvas.drawText("Circle", 120, 150, paint);

        paint.setShader(new LinearGradient(
                50, 350, 350, 350,
                Color.BLUE, Color.CYAN,
                Shader.TileMode.MIRROR
        ));
        canvas.drawCircle(200, 350, 150, paint);

        // Rectangle
        paint.setShader(null);
        paint.setColor(Color.BLACK);
        canvas.drawText("Rectangle", 420, 150, paint);

        paint.setShader(new LinearGradient(
                400, 200, 650, 700,
                Color.RED, Color.YELLOW,
                Shader.TileMode.MIRROR
        ));
        canvas.drawRect(400, 200, 650, 700, paint);

        // Square
        paint.setShader(null);
        paint.setColor(Color.BLACK);
        canvas.drawText("Square", 120, 800, paint);

        paint.setShader(new LinearGradient(
                50, 850, 350, 1150,
                Color.MAGENTA, Color.rgb(255, 105, 180),
                Shader.TileMode.MIRROR
        ));
        canvas.drawRect(50, 850, 350, 1150, paint);

        // Line
        paint.setShader(null);
        paint.setColor(Color.BLACK);
        paint.setStrokeWidth(0);
        canvas.drawText("Line", 500, 800, paint);

        paint.setStrokeWidth(10);
        paint.setShader(new LinearGradient(
                520, 850, 520, 1150,
                Color.GREEN, Color.BLACK,
                Shader.TileMode.MIRROR
        ));
        canvas.drawLine(520, 850, 520, 1150, paint);
    }
}

```

## OUTPUT

<img width="1917" height="1015" alt="image" src="https://github.com/user-attachments/assets/648f3e6f-9cc6-4b1a-86b8-853699c53979" />



## RESULT
Thus a Simple Android Application to create and design an android application that draws basic graphical primitives on the screen using Android Studio is developed and executed successfully.
