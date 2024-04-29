
# Rapport

Jag började med att lägga till två objekt i MainActivity, SharedPreferences och SharedPreferences.
Jag lade även till en TextView i OnCreate. Detta gjordes för att kunna läsa data från shared 
preferences. Se koden nedan.
```
    private SharedPreferences myPreferenceRef;
    private SharedPreferences.Editor myPreferenceEditor;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        Toolbar toolbar = findViewById(R.id.toolbar);
        setSupportActionBar(toolbar);

        myPreferenceRef = getPreferences(MODE_PRIVATE);
        myPreferenceEditor = myPreferenceRef.edit();

        TextView prefTextRef=new TextView(this);
        prefTextRef=(TextView)findViewById(R.id.prefText);
        prefTextRef.setText(myPreferenceRef.getString("MyAppPreferenceString", "No preference found."));
    }
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
I activity_second lade jag till en EditText, Button och TextView. Button-texten "save" lades till 
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
    <TextView
        android:layout_below="@+id/prefButton"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:id="@+id/prefText"
        tools:ignore="MissingConstraints" />
```

```
```

Bilder läggs i samma mapp som markdown-filen.

![](android.png)
