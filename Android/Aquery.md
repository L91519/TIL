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
                    Toast.makeText(aq.getContext(), status.getCode() + ":" + json.toString(), Toast.LENGTH_LONG).show();
                  else{
                      //ajax error, show error code
                      Toast.makeText(aq.getContext(), "Error:" + status.getCode(), Toast.LENGTH_LONG).show();
                  }
              }
          });
  ```

  ​

+ Post

  ```java
  aq.ajax(url, params, JSONObject.class, new AjaxCallback<JSONObject>() {
              @Override
              public void callback(String url, JSONObject json, AjaxStatus status) {
               if(json != null) {
               	//success
               	Toast.makeText(aq.getContext(), status.getCode() + ":" + json.toString(), Toast.LENGTH_LONG).show();
                  } 
                else {
                      Toast.makeText(aq.getContext(), "Error:" + status.getCode(), Toast.LENGTH_LONG).show();
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