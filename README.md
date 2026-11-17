# DEVELOPING-AN-ANDROID-APPLICATION-TO-PERFORM-MATHEMATICAL-OPERATION.-

## AIM:
To develop an android application to perform mathematical operation.

## APPARATUS REQUIRED:
ØComputer
ØAndroid studio software


## THEORY:
The platform uses signed two's complement integer arithmetic with int and long primitive types. The developer should choose the primitive type to ensure that arithmetic operations consistently produce correct results, which in some cases means the operations will not overflow the range of values of the computation. The best practice is to choose the primitive type and algorithm to avoid overflow. In cases where the size is int or long and overflow errors need to be detected, the methods add, subtract multiply, and throw an Arithmetic exception when the results overflow. For other arithmetic operations such as divide, absolute value, increment by one, decrement by one, and negation, overflow occurs only with a specific minimum or maximum value and should be checked against the minimum or maximum as appropriate.



## PROCEDURE:
1. Open Android Studio and then click on File -> New -> New project. 2. Then type the application name as “ex.no.1″ and click Next.
3. Then select the Minimum SDK as shown below and click next. 4. Then select the Empty Activity and click next.
5. Finally click Finish.
6. Click on app -> java -> com.example -> MainActivity.java
7. Now click on Text and type the program, so now the programming part of the main activity is completed.
8. Click on app -> res -> layout -> activity_main.xml.
9. Now click on Text and type the program, so now the designing part of Activity main is also completed.
10. Select the suitable available device to display the output. 11. Now run the application to see the output. 


## PROGRAM:
# MainActivity.kt
```package com.example.simplecalc   // keep the package name Android Studio generated

import android.os.Bundle
import android.widget.Button
import android.widget.EditText
import android.widget.TextView
import androidx.appcompat.app.AppCompatActivity

class MainActivity : AppCompatActivity() {

    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)

        val n1 = findViewById<EditText>(R.id.num1)
        val n2 = findViewById<EditText>(R.id.num2)
        val result = findViewById<TextView>(R.id.result)

        fun calculate(op: Char) {
            val a = n1.text.toString().toDoubleOrNull()
            val b = n2.text.toString().toDoubleOrNull()
            if (a == null || b == null) {
                result.text = "Enter both numbers"
                return
            }
            val answer = when (op) {
                '+' -> a + b
                '-' -> a - b
                '*' -> a * b
                else -> {
                    if (b == 0.0) { result.text = "Cannot divide by 0"; return }
                    a / b
                }
            }
            result.text = "Result: $answer"
        }

        findViewById<Button>(R.id.btnAdd).setOnClickListener { calculate('+') }
        findViewById<Button>(R.id.btnSub).setOnClickListener { calculate('-') }
        findViewById<Button>(R.id.btnMul).setOnClickListener { calculate('*') }
        findViewById<Button>(R.id.btnDiv).setOnClickListener { calculate('/') }
    }
}
```
## Activity_main.xml
```<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:padding="24dp">

    <EditText
        android:id="@+id/num1"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="First number"
        android:inputType="numberDecimal|numberSigned" />

    <EditText
        android:id="@+id/num2"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="Second number"
        android:inputType="numberDecimal|numberSigned" />

    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_marginTop="16dp"
        android:orientation="horizontal">

        <Button android:id="@+id/btnAdd" android:layout_width="0dp"
            android:layout_height="wrap_content" android:layout_weight="1" android:text="+" />
        <Button android:id="@+id/btnSub" android:layout_width="0dp"
            android:layout_height="wrap_content" android:layout_weight="1" android:text="−" />
        <Button android:id="@+id/btnMul" android:layout_width="0dp"
            android:layout_height="wrap_content" android:layout_weight="1" android:text="×" />
        <Button android:id="@+id/btnDiv" android:layout_width="0dp"
            android:layout_height="wrap_content" android:layout_weight="1" android:text="÷" />
    </LinearLayout>

    <TextView
        android:id="@+id/result"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_marginTop="24dp"
        android:text="Result: "
        android:textSize="24sp"
        android:textStyle="bold" />
</LinearLayout>
```


## OUTPUT:
<img width="1917" height="1077" alt="image" src="https://github.com/user-attachments/assets/4a899f9a-fafb-40ae-8cdc-e0cce22e9ef2" />


## RESULT:
Thus, the Android app for basic operations (addition, subtraction, multiplication, and division) is developed and the output is verified.

