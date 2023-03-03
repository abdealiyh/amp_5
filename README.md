# amp_5


PRACTICAL 5
Aim : Programming UI elements, AppBar, UI Components
[Pract 5A : Calculator Application]
Activity_main.xml  Designing Activity UI

        <?xml version="1.0" encoding="utf-8"?>
        <LinearLayout
        xmlns:android="http://schemas.android.com/apk/res/android"
         xmlns:tools="http://schemas.android.com/tools"
         android:layout_width="match_parent"
         android:layout_height="match_parent"
         xmlns:app="http://schemas.android.com/apk/res-auto"
         android:orientation="vertical">
         <EditText
         android:id="@+id/editTextTextPersonName"
         android:layout_width="match_parent"
         android:layout_height="wrap_content"
         android:ems="10"
         android:inputType="textPersonName"
         android:text="NUMBER 1"
         android:textColor="@color/text"
         android:textSize="20sp" />
         <EditText
         android:id="@+id/editTextTextPersonName2"
         android:layout_width="match_parent"
         android:layout_height="wrap_content"
         android:ems="10"
         android:inputType="textPersonName"
         android:text="NUMBER 2"
         android:textColor="@color/text"
         android:textSize="20sp" />
         <TableLayout
         android:layout_width="match_parent"
         android:layout_height="wrap_content">
         <TableRow>
         <Button
         android:id="@+id/button"
         android:layout_width="200dp"
        android:layout_height="90dp"
         android:backgroundTint="@color/b1"
         android:text="ADD"
         android:textSize="20sp" />
         <Button
         android:id="@+id/button2"
         android:layout_width="207dp"
         android:layout_height="90dp"
         android:backgroundTint="@color/b2"
         android:text="SUB"
         android:textSize="20sp" />
         </TableRow>
         <TableRow>
         <Button
         android:id="@+id/button3"
         android:layout_width="200dp"
         android:layout_height="90dp"
         android:backgroundTint="@color/b3"
        android:text="MUL"
         android:textSize="20sp" />
         <Button
         android:id="@+id/button4"
         android:layout_width="211dp"
        android:layout_height="90dp"
         android:backgroundTint="@color/b4"
         android:text="DIV"
         android:textSize="20sp" />
         </TableRow>
         </TableLayout>
         <Button
         android:id="@+id/button5"
         android:layout_width="match_parent"
         android:layout_height="90dp"
         android:backgroundTint="@color/b5"
         android:text="CLEAR"
         android:textSize="20sp" />
         <TextView
         android:id="@+id/textView2"
         android:layout_width="match_parent"
         android:layout_height="wrap_content"
         android:layout_marginTop="30dp"
         android:fontFamily="@font/orbitron_bold"
         android:text="OUTPUT :"
         android:textSize="24sp"
         android:textStyle="bold" />
        </LinearLayout>

Main_Activity.java  Writing calculator code

              package com.example.prac5;
              import androidx.appcompat.app.AppCompatActivity;
              import android.view.View;
              import android.widget.*;
              import static android.view.View.*;
              import android.os.Bundle;
              public class MainActivity extends AppCompatActivity {
               EditText t1,t2;
               Button b1,b2,b3,b4,b5;
               TextView tv1;
               int n1=0,n2=0;
               String s1,s2;
               @Override
               protected void onCreate(Bundle savedInstanceState) {
               super.onCreate(savedInstanceState);
               setContentView(R.layout.activity_main);
               t1 = (EditText) findViewById(R.id.et1);
               t2 = (EditText) findViewById(R.id.et2);
               b1 = (Button) findViewById(R.id.btnAdd);
               b2 = (Button) findViewById(R.id.btnSub);
               b3 = (Button) findViewById(R.id.btnMult);
               b4 = (Button) findViewById(R.id.btnDiv);
               b5 = (Button) findViewById(R.id.btnClear);
               tv1 = (TextView) findViewById(R.id.tv1);
               b1.setOnClickListener(new OnClickListener()
               { @Override
               public void onClick(View v)
               {
               try
               {
               String s1 = t1.getText().toString();
               String s2 = t2.getText().toString();
               n1 = Integer.parseInt(s1);
               n2 = Integer.parseInt(s2);
              int sum = n1 + n2;
               tv1.setText("Addition = "+sum);
               }
               catch (NumberFormatException e) { }
               }
               });
               b2.setOnClickListener(new OnClickListener()
               { @Override
               public void onClick(View v)
               {
               try
               {
               String s1 = t1.getText().toString();
               String s2 = t2.getText().toString();
               n1 = Integer.parseInt(s1);
               n2 = Integer.parseInt(s2);
              int sub = n1 - n2;
               tv1.setText("Subtraction = "+sub);
               }
               catch (NumberFormatException e) { }
               }
               });
              b3.setOnClickListener(new OnClickListener()
               { @Override
               public void onClick(View v)
               {
               try
               {
               String s1 = t1.getText().toString();
               String s2 = t2.getText().toString();
               n1 = Integer.parseInt(s1);
               n2 = Integer.parseInt(s2);
              int mul = n1 * n2;
               tv1.setText("Multiplication = "+mul);
               }
               catch (NumberFormatException e) { }
               }
               });
               b4.setOnClickListener(new OnClickListener()
               { @Override
               public void onClick(View v)
               {
               try
               {
               String s1 = t1.getText().toString();
               String s2 = t2.getText().toString();
               n1 = Integer.parseInt(s1);
               n2 = Integer.parseInt(s2);
              int div = n1 / n2;
               tv1.setText("Division = " + div);
               }
               catch (NumberFormatException e) { }
               }
               });
               b5.setOnClickListener(new OnClickListener()
               { @Override
               public void onClick(View v)
               {
               t1.setText(" ");
               t2.setText(" ");
               tv1.setText(" ");
               }
               });
               }
              }



Colors.xml.

        <?xml version="1.0" encoding="utf-8"?>
        <resources>
         <color name="purple_200">#FFBB86FC</color>
         <color name="purple_500">#FF6200EE</color>
         <color name="purple_700">#FF3700B3</color>
         <color name="teal_200">#FF03DAC5</color>
         <color name="teal_700">#FF018786</color>
         <color name="black">#FF000000</color>
         <color name="white">#FFFFFFFF</color>
         <color name="text">#8C8AA8</color>
         <color name="b1">#985F6F</color>
         <color name="b2">#C4BBF2</color>
         <color name="b3">#A6B1E1</color>
         <color name="b4">#4E4C67</color>
         <color name="b5">#4F43E4</color>
         <color name="main">#370617</color>
        </resources>


[Pract 5B : AppBar]

Steps :
1. Create AppBar (Remove the default Action Bar)
a. Go to values themes.xml
b. Change:
<style name="Theme.Prac5_AppBar" 
parent="Theme.MaterialComponents.DayNight.DarkActionBar">
To
<style name="Theme.Prac5_AppBar" 
parent="Theme.MaterialComponents.DayNight.NoActionBar">
2. Add a Toolbar to the activity's layout.
a. Go to resources layout
b. Right click > New > Layout Resource File
c. Set file name as toolbar_layout and set root element as 
androidx.appcompat.widget.Toolbar
d. Click on OK


Toolbar_layout.xml

      <?xml version="1.0" encoding="utf-8"?>
      <androidx.appcompat.widget.Toolbar
       xmlns:android="http://schemas.android.com/apk/res/android"
       xmlns:app="http://schemas.android.com/apk/res-auto"
       android:layout_width="match_parent"
       android:layout_height="?attr/actionBarSize"
       android:background="#8D0801"
       android:theme="@style/ThemeOverlay.AppCompat.Dark.ActionBar"
       app:popupTheme="@style/ThemeOverlay.AppCompat.Light"
       android:id="@+id/t1">
      </androidx.appcompat.widget.Toolbar>
      
      
      

3. Include this layout to activity_main.xml File.


      <?xml version="1.0" encoding="utf-8"?>
      <LinearLayout
       xmlns:android="http://schemas.android.com/apk/res/android"
       xmlns:app="http://schemas.android.com/apk/res-auto"
       xmlns:tools="http://schemas.android.com/tools"
       android:layout_width="match_parent"
       android:layout_height="match_parent"
       tools:context=".MainActivity"
       android:orientation="vertical">
       <include layout="@layout/toolbar_layout"/>
       <TextView
       android:layout_width="wrap_content"
       android:layout_height="wrap_content"
       android:textSize="20dp"
       android:text="Roll No: A020"/>
      </LinearLayout>
      
      
4. Setting the toolbar as default bar
In the activity's onCreate() method, call the activity's setSupportActionBar() method, 
and pass the activity's toolbar. This method sets the toolbar as the app bar for the 
activity

        public class MainActivity extends AppCompatActivity {
         private Toolbar t2;
         @Override
         protected void onCreate(Bundle savedInstanceState) {
         super.onCreate(savedInstanceState);
         setContentView(R.layout.activity_main);
         t2 = findViewById(R.id.t1);
         setSupportActionBar(t2);
         }


Add menu to appbar
 Right click on res folder > add new android resources file
 Name it app_bar_menu
 Set resource type – menu


App_bar_menu.xml

          <?xml version="1.0" encoding="utf-8"?>
          <menu
           xmlns:android="http://schemas.android.com/apk/res/android"
           xmlns:app="http://schemas.android.com/apk/res-auto" >
           <item
           android:id="@+id/action_search"
           android:title="Search"
           android:icon="@drawable/ic_search"
           app:showAsAction="ifRoom"/>
           <item
           android:id="@+id/action_setting"
           android:title="Setting"
           android:icon="@drawable/ic_setting"
           app:showAsAction="ifRoom"/>
          <item
           android:id="@+id/action_about"
           android:title="About"
           app:showAsAction="never"/>
           <item
           android:id="@+id/action_logout"
           android:title="Logout"
           app:showAsAction="never"/>
          </menu>
          
         
 6. To add this Menu to AppBar(Action Bar)


            package com.example.prac5_b_a020;
            import android.os.Bundle;
            import android.view.Menu;
            import android.view.MenuInflater;
            import android.view.MenuItem;
            import android.widget.Toast;
            import androidx.appcompat.app.AppCompatActivity;
            import androidx.appcompat.widget.Toolbar;
            public class MainActivity extends AppCompatActivity {
             private Toolbar t2;
             @Override
             protected void onCreate(Bundle savedInstanceState) {
             super.onCreate(savedInstanceState);
             setContentView(R.layout.activity_main);
             t2 = findViewById(R.id.t1);
             setSupportActionBar(t2);
             }
             @Override
             public boolean onCreateOptionsMenu(Menu menu) {
             MenuInflater mi = getMenuInflater();
             mi.inflate(R.menu.app_bar_menu, menu);
             return super.onCreateOptionsMenu(menu);
            }
             @Override
             public boolean onOptionsItemSelected(MenuItem item) {
             switch (item.getItemId()) {
             case R.id.action_search:
             Toast.makeText(this, "search menu click",
             Toast.LENGTH_SHORT).show();
             return true;
             case R.id.action_setting:
             Toast.makeText(this, "setting menu click",
             Toast.LENGTH_SHORT).show();
             return true;
             case R.id.action_about:
             Toast.makeText(this, "About menu click",
             Toast.LENGTH_SHORT).show();
             return true;
             case R.id.action_logout:
             Toast.makeText(this, "Logout click",
             Toast.LENGTH_SHORT).show();
             return true;
             default:
             return super.onOptionsItemSelected(item);
             }
             }
            }


7. Add ic_search image and ic_setting image to drawable folder.
