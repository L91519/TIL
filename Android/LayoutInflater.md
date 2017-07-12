# LayoutInflater

This is used to make xml file as view object.

Since this can only be used when xml file is complet before runtime, we can't use inflater to a xml file when it's being edited on complie time.

LayoutInflater is mostly used but there also is MenuInflater and etc.

### Process of making inflater

1. Get inflater

   ```java
   LayoutInflater inflater = (LayoutInflater) getSystemServiec(Context.LAYOUT_INFLATER_SERVICE);
   ```

2. Check the type of root view because we need xml to make it as object

   ```java
   LinearLayout linearLayout = (Linearlayout) inflater.inflate(R.layout.inflate_example,null)
   ```

   1. View inflate (int resource, ViewGroup root)
      + resource : id for an xml Layout resource to add
      + root : **optional** view to be the parent and can be null
   2. View inflate (XmlPullParser parser, ViewGroup root)
      Because this method only works on pre-processing of xml files, it's not possible with xml file at runtime.
      + containing the description of the view hierachy
   3. View inflate (XmlPullParser parser, ViewGroup root, boolean attachToRoot)
      - attachToRoot : if true, attach to thr root parameter and if false, root is only used to create the subclass.
   4. View inflate (int resource, ViewGroup root, boolean attahToRoot)

3. Draw the view that is taken

   ```java
   setContentView(linearLayout);
   ```



### References

http://aroundck.tistory.com/39

https://developer.android.com/reference/android/view/LayoutInflater.html