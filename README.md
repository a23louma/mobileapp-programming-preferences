
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

```
```

```
```

```
```

Bilder läggs i samma mapp som markdown-filen.

![](android.png)
