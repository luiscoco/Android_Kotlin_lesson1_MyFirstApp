# My First Mobile Application with Android Studio and Kotlin

## 1. How to create a New Project in Android Studio

Run Android Studio and press the **New Project** button 

![image](https://github.com/luiscoco/Android_Kotlin_lesson1_MyFirstApp/assets/32194879/67949dce-16f6-488b-8529-14f93b85fd01)

We select the template option **Empty View Activity** and press the **Next** button

![image](https://github.com/luiscoco/Android_Kotlin_lesson1_MyFirstApp/assets/32194879/43418c3e-6d87-439d-aeac-e6322cfd04c6)

We input the new project data: activity name, package name, save location, language, minimum SDK and build configuration language

We press the **Finish** button

![image](https://github.com/luiscoco/Android_Kotlin_lesson1_MyFirstApp/assets/32194879/61b99a37-33d9-4617-aad0-9b28ac43f640)

Then **Gradle** will configure automatically the project 

**Note**: Please accept to add the Project paths to Microsoft Defender

This is the project folder and files structure

![image](https://github.com/luiscoco/Android_Kotlin_lesson1_MyFirstApp/assets/32194879/6b148b4b-4c6d-4b22-b6e0-f88c3c289951)

## 2.  Design the application User Interface UI

We have to open the file **/res/layout/activity_main.xml**

![image](https://github.com/luiscoco/Android_Kotlin_lesson1_MyFirstApp/assets/32194879/75a2ed19-aab9-4687-9cdd-a550989abc92)

This is the the UI code

**activity_main.xml**

```xml
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:id="@+id/main"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Hello World!"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

</androidx.constraintlayout.widget.ConstraintLayout>
```

We drag and drop a **button** into the **ConstraintLayout** with id **main**

![image](https://github.com/luiscoco/Android_Kotlin_lesson1_MyFirstApp/assets/32194879/625071c0-937a-4500-bf52-b030241b76ed)

We fix the **errors**:

We have to set the **buttons constraints** 

Also we have to **extract the button name to resources**

![image](https://github.com/luiscoco/Android_Kotlin_lesson1_MyFirstApp/assets/32194879/77367ea4-b3f7-4915-a46c-fb4c4c37afa4)

We create a string in resources (**/res/values/strings.xml**) with the **button name**

**/res/values/strings.xml**

```
<resources>
    <string name="app_name">MyFirstApplication</string>
    <string name="button_first">Button</string>
</resources>
```

![image](https://github.com/luiscoco/Android_Kotlin_lesson1_MyFirstApp/assets/32194879/a33ddc0a-9c73-4241-a074-379d704153ce)

We verify also the file **/res/layout/activity_main.xml**

![image](https://github.com/luiscoco/Android_Kotlin_lesson1_MyFirstApp/assets/32194879/41585b08-816e-4787-8101-c29fd871ee36)

We also have to set the **button constraints**

![image](https://github.com/luiscoco/Android_Kotlin_lesson1_MyFirstApp/assets/32194879/2f768d30-d26e-4bdb-a199-246f744ce9eb)

This is the modified UI code

**activity_main.xml**

```xml
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:id="@+id/main"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <TextView
        android:id="@+id/textView"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Hello World!"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

    <Button
        android:id="@+id/button_first"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="@string/button_first"
        android:layout_marginTop="16dp"
        app:layout_constraintTop_toBottomOf="@id/textView"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintEnd_toEndOf="parent" />

</androidx.constraintlayout.widget.ConstraintLayout>
```

## 3. Define the button OnClickListener 

This is the original code

**MainActivity.kt**

```kotlin
package com.example.myfirstapplication

import android.os.Bundle
import androidx.activity.enableEdgeToEdge
import androidx.appcompat.app.AppCompatActivity
import androidx.core.view.ViewCompat
import androidx.core.view.WindowInsetsCompat

class MainActivity : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        enableEdgeToEdge()
        setContentView(R.layout.activity_main)
        ViewCompat.setOnApplyWindowInsetsListener(findViewById(R.id.main)) { v, insets ->
            val systemBars = insets.getInsets(WindowInsetsCompat.Type.systemBars())
            v.setPadding(systemBars.left, systemBars.top, systemBars.right, systemBars.bottom)
            insets
        }
    }
}
```

This is the modified code

**MainActivity.kt**

```kotlin
package com.example.myfirstapplication

import android.os.Bundle
import android.widget.Button
import androidx.activity.enableEdgeToEdge
import androidx.appcompat.app.AlertDialog
import androidx.appcompat.app.AppCompatActivity
import androidx.core.view.ViewCompat
import androidx.core.view.WindowInsetsCompat

class MainActivity : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        enableEdgeToEdge()
        setContentView(R.layout.activity_main)

        // Set up window insets
        ViewCompat.setOnApplyWindowInsetsListener(findViewById(R.id.main)) { v, insets ->
            val systemBars = insets.getInsets(WindowInsetsCompat.Type.systemBars())
            v.setPadding(systemBars.left, systemBars.top, systemBars.right, systemBars.bottom)
            insets
        }

        // Find the button by its ID
        val button = findViewById<Button>(R.id.button_first)

        // Set an OnClickListener on the button
        button.setOnClickListener {
            // Create and show a dialog
            val dialog = AlertDialog.Builder(this)
                .setTitle("Dialog Title")
                .setMessage("This is a simple dialog message.")
                .setPositiveButton("OK") { dialog, _ ->
                    dialog.dismiss()
                }
                .create()
            dialog.show()
        }
    }
}
```

## 4. How to run the application

As a mandatory prerequesite we have to create AVD Android Virtual Device before running the application

See this post: 

Now we can press the **Running Devices** button and then the **Run 'app'**

![image](https://github.com/luiscoco/Android_Kotlin_lesson1_MyFirstApp/assets/32194879/73f7973e-4bf1-42d3-8421-f1b2781db6be)

![image](https://github.com/luiscoco/Android_Kotlin_lesson1_MyFirstApp/assets/32194879/75db0d8c-f53d-4acc-8b2f-b8b1c45295aa)

![image](https://github.com/luiscoco/Android_Kotlin_lesson1_MyFirstApp/assets/32194879/c7cf349e-364a-47ea-9804-f623dfa2b84b)


