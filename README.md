# Ex.No:4 To create a two screens , first screen will take one number input from user. After click on Factorial button, second screen will open and it should display factorial of the same number using Explicit Intents.


## AIM:

To create a two screens , first screen will take one number input from user. After click on Factorial button, second screen will open and it should display factorial of the same number using Explicit Intents.


## EQUIPMENTS REQUIRED:

Latest Version Android Studio

## ALGORITHM:

```
1. Start Android Studio and create a new project.

2. Create two activities:

   * `MainActivity`
   * `SecondActivity`

3. Design the first screen with:

   * One EditText to enter a number
   * One Button labeled “Factorial”

4. In `MainActivity.java`:

   * Read the number entered by the user
   * Create an Explicit Intent to open `SecondActivity`
   * Pass the entered number using `putExtra()`

5. In `SecondActivity.java`:

   * Receive the number using `getIntent().getIntExtra()`
   * Initialize factorial value as 1
   * Use a loop to calculate factorial of the number

6. Display the factorial result using TextView in the second screen.

7. Add `SecondActivity` entry in `AndroidManifest.xml`.

8. Run the application.

9. Enter a number and click the “Factorial” button.

10. Verify that the second screen displays the factorial result correctly.

```

## PROGRAM:
```
/*
Program to print the text “ExplicitIntent”.
Developed by:Pavithra S
Registeration Number :212223220073
*/
```

## activity_main.xml

```
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:gravity="center"
    android:padding="20dp">

    <EditText
        android:id="@+id/numberInput"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="Enter Number"
        android:inputType="number"/>

    <Button
        android:id="@+id/btnFactorial"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Factorial"
        android:layout_marginTop="20dp"/>
</LinearLayout>

```

## MainActivity.java

```
package com.example.ex2b;
import android.content.Intent;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {

    EditText numberInput;
    Button btnFactorial;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        numberInput = findViewById(R.id.numberInput);
        btnFactorial = findViewById(R.id.btnFactorial);

        btnFactorial.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {

                int number = Integer.parseInt(numberInput.getText().toString());

                Intent intent = new Intent(MainActivity.this, com.example.ex2b.SecondActivity.class);

                intent.putExtra("num", number);

                startActivity(intent);
            }
        });
    }
}
```

## activity_second.xml

```
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:gravity="center"
    android:orientation="vertical">

    <TextView
        android:id="@+id/resultText"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:textSize="24sp"
        android:textStyle="bold"/>
</LinearLayout>
```

## SecondActivity.java
```

package com.example.ex2b;
import android.os.Bundle;
import android.widget.TextView;
import androidx.appcompat.app.AppCompatActivity;

public class SecondActivity extends AppCompatActivity {

    TextView resultText;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_second);

        resultText = findViewById(R.id.resultText);

        int number = getIntent().getIntExtra("num", 0);

        int fact = 1;

        for(int i = 1; i <= number; i++) {
            fact = fact * i;
        }

        resultText.setText("Factorial = " + fact);
    }
}
```

## OUTPUT

<img width="1920" height="1200" alt="image" src="https://github.com/user-attachments/assets/5b2fd772-00cb-4504-a450-635ecc625d10" />
<img width="1920" height="1200" alt="image" src="https://github.com/user-attachments/assets/2c9c39ed-8847-4652-96d9-dcd5d51b4c70" />
<img width="1920" height="1200" alt="image" src="https://github.com/user-attachments/assets/055e28e6-7ae3-448a-a9dd-873e4e79065f" />


## RESULT
Thus a Simple Android Application create a Explicit Intents using Android Studio is developed and executed successfully.


