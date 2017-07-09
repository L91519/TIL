# ActionBar 

There are two ways of controlling action bar. 

1. android.app.ActionBar
2. android.support.v7.app.ActionBar

But this both support the same function. So no difference functionally. (why is there's different ActionBar class... isn't this useless..?)

Extending AppCompatActivity is necessary when controlling ActionBar.

## Android.app.ActionBar

First method is supported from Android 3.0(Honeycomb). But honeycomb is only a version for tablet so practically first method is only supported from version4.0

### onCreateOptionsMenu()

A method that is in ActionBarActivity class, that adds item to action bar.

This method already exists in ActionBarActivity so we need to override this method if we want to add item to action bar.

### onCreateOptionSelected()

A method that implements a event when a item that which is added in onCreateOprinoMenu is clicked.

### getSupportedActionBar()

Use this method to get ActionBar object.

```java
ActionBar actionBar = getSupportedActionBar();
actionBar.*;
```

```java
getSupportedActionBar.*;
```

Both can be used.

With this method, setting title, setting background color or image etcetera can be possible. 

## Android.app.ActionBar

This can be used if the complieSdkVersion is over 22.