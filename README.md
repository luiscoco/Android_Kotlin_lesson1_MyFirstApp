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

We also have to set the **button constraints**



## 3. 



