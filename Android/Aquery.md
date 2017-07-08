# Aquery

## Necessary Permission

- <uses-permission android:name="android.permission.WRITE_EXTERNAL_STORAGE"/>
- <uses-permission android:name="android.permission.INTERNET" />

In Android Menifest.xml, after application tag

## Aquery.ajax

+ Get

  ```java
  aq.ajax(url, JSONObject.class, new AjaxCallback<JSONObject>(){
              @Override
              public void callback(String url, JSONObject json, AjaxStatus status) {
                  if(json != null){
                    //successful ajax call, show status code and json content 
                  else{
                      //ajax error, show error code
                  }
              }
          });
  ```

+ Post

  ```java
  aq.ajax(url, params, JSONObject.class, new AjaxCallback<JSONObject>() {
              @Override
              public void callback(String url, JSONObject json, AjaxStatus status) {
               if(json != null) {
               	//successfully complete
                  } 
                else {
                  //:(
                  }
              }
          });
  ```

  + params : 
    parameter in ajax method.
    HashMa which contains a jason object structure.
    key as name and value as value.

  ​

  ​