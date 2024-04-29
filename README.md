
# Rapport

Jag började med att lägga till två objekt i MainActivity, SharedPreferences och SharedPreferences.
Jag lade även till en TextView i OnCreate. Detta gjordes för att kunna läsa data från shared 
preferences. Se koden nedan.
```
        myPreferenceRef = getSharedPreferences( "MyAppPreferenceString" ,MODE_PRIVATE);
        myPreferenceEditor = myPreferenceRef.edit();

        TextView prefTextRef=new TextView(this);
        prefTextRef=(TextView)findViewById(R.id.prefText);
        prefTextRef.setText(myPreferenceRef.getString("MyAppPreferenceString", "No preference found."));
```
Därefter skapade jag en ny activity, SecondActivity, samt tillhörande xml-fil, activity_second. Jag
bort onödig kod i SecondActivity. Se koden nedan.
```
public class SecondActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_second);
    }
}
```
I activity_second lade jag till en EditText och Button. Button-texten "save" lades till 
som en string i strings.xml. Se koden nedan från activity_second.
```
    <EditText
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:id="@+id/settingseditview"
        tools:ignore="MissingConstraints" />
    <Button
        android:text="@string/save"
        android:layout_below="@+id/settingseditview"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:id="@+id/prefButton"
        android:onClick="savePref"
        tools:ignore="MissingConstraints" />
```
Jag skapade ett intent i MainActivity för att kunna öpnna SecondActivity. Jag skapade även en knapp
för att kunna öppna SecondActivity. Se koden nedan.
```
        goToSecondActivityButton = findViewById(R.id.openSecondActivityButton);
        goToSecondActivityButton.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                Intent intent = new Intent(MainActivity.this, SecondActivity.class);
                startActivity(intent);
            }
```
Jag behövde ändra i build.gradle för att detta skulle fungera. Se koden nedan.
```
implementation 'androidx.activity:activity:1.1.0'
```
I activity_main.xml lades en Button samt en TextView till för att kunna visa den sparade texten från
SecondActivity. Se koden nedan.
```
    <TextView
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:id="@+id/prefText"
        tools:ignore="MissingConstraints" />

    <Button
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:id="@+id/openSecondActivityButton"
        tools:ignore="MissingConstraints" />
```

I SecondActivity lade jag deklarerade jag två objekt, SharedPreferences.Editor samt SharedPreferences.
I activity_second.xml och activity_second.xml ändrade jag constraints. 

Bilder läggs i samma mapp som markdown-filen.

![](android.png)
