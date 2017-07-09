# findViewById not working when using a class which is not MainActivity

'findViewById()' works only in a activity which is set by setContentView.

So you need a view that contains xml file such as activity_main.

And by using the view that contains xml file, you can use 'findViewById()'.

```java
LayoutInflater inflater = (LayoutInflater) context.getSystemService(Context.LAYOUT_INFLATER_SERVICE);
View v = inflater.inflate(R.layout.activity_main);
View innerView = v.findViewById(R.id.*);
```

In this way, you can use 'findViewById()'!! XD



### LayoutInflater

java.lang.Object

  -> android.view.LayoutInflater

##### What does LayoutInflater do?

+ LayoutInflater returns the resources that is declare in xml to the form of View.
+ make XML file in to instance to it's corresponding View object.



## Context

+ An object that contains comprehensive information.
+ Application that is used as interface that contains the inviroment of current application.



# Reference 

https://developer.android.com/reference/classes.html