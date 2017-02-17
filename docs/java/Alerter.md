

## Alerter

![Alerter](https://github.com/Tapadoo/Alerter/raw/master/documentation/alert_default.gif)

[Lien du Repository](https://github.com/Tapadoo/Alerter)
# Usage

With simplicity in mind, the Alerter employs the builder pattern to facilitate easy integration
into any app.

From an Activity -

```java
Alerter.create(this)
       .setTitle("Alert Title")
       .setText("Alert text...")
       .show();
```

Or from a Fragment -

```java
Alerter.create(getActivity())
       .setTitle("Alert Title")
       .setText("Alert text...")
       .show();
```

# Customisation

### Background Colour

```java
Alerter.create(this)
       .setTitle("Alert Title")
       .setText("Alert text...")
       .setBackgroundColor(R.color.colorAccent)
       .show();
```

![Coloured Alert](./documentation/alert_coloured.gif)

### Icon

```java
Alerter.create(this)
       .setText("Alert text...")
       .setIcon(R.drawable.ic_face)
       .show();
```

![Custom Icon Alert](./documentation/alert_icon.gif)

### On screen duration, in milliseconds

```java
Alerter.create(this)
       .setTitle("Alert Title")
       .setText("Alert text...")
       .setDuration(10000)
       .show();
```

### Without title

```java
Alerter.create(this)
       .setText("Alert text...")
       .show();
```

![Text Only Alert](./documentation/alert_text_only.gif)

### Adding an On Click Listener

```java
 Alerter.create(ExampleActivity.this)
        .setTitle("Alert Title")
        .setText("Alert text...")
        .setDuration(10000)
        .setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                Toast.makeText(ExampleActivity.this, "OnClick Called", Toast.LENGTH_LONG).show();
            }
        })
        .show();
```

![On Click Alert](./documentation/alert_on_click.gif)

### Verbose text

```java
 Alerter.create(ExampleActivity.this)
        .setTitle("Alert Title")
        .setText("The alert scales to accommodate larger bodies of text. " +
                 "The alert scales to accommodate larger bodies of text. " +
                 "The alert scales to accommodate larger bodies of text.")
        .show();
```

![Verbose Alert](./documentation/alert_verbose.gif)

## Gradle

```groovy
dependecies {
    compile 'com.tapadoo.android:alerter:1.0.1'
}
```
