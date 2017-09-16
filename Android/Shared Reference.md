# Shared Reference

This is used to save a data which is too simple to be added in database. Means to say SharedReference is used when saving a simple data.

Inserted data is used to be saved as file and before the app is deleted, the data will be kept same.

And because of these reasons, data such as user's id or passwords are inserted in shared reference and expired when deleting the application.

## Procedure

1. Get instance of SharedPreferences with a 'getPreferences()'method .

   ### getPreferences()

   There are two ways of getting instance of SharedPreferences.

   + getPreferences(int mode)
     mode : Operating mode
   + getSharedPreferences(String name, int mode)
     name : Name of certain SharedPreferences
     mode : Operating mode

2. Save data in SharedPreferences

   ### SharedReference.Editor

   Interface used for modifying values in a SharedReferences object.

   When you make a change here you should call commit() method.

   With this Interface, save a data with HashMap type because SharedReference itself saves a data which is structured in key&value way.

## Package SharedReference

### getStringSet

```java
Set<String> getStringSet (String key, Set<String> defValues)
```

Method that searches Set\<String> from preference.

key : Name of the preference to search.

defValues : Value to return when preference doesn't exist.

## Package SharedReference.Editor

### putStringSet

```java
SharedReference.Editor putString(String key, Set<String> values)
```

key : Name of the preferency to edit.

values : New value of the preference.

## Reference

+ Android developer