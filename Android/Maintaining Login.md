# Maintaining Login

If we use CookieStore in android, except for the first time you run certain application and login in it, for every request that is held after will notify that you are the same user and maintin cookie.

But if user restart CookieStore, new cookie will be created so user should login again. And this will let the user login to the application everytime that they run the application.

Here, I'm going to post the way of keeping the same cookie everytime that user runs the app by using Retrofit and OkHttp.

## Cookie and Session

### Session

When Client is first connected to server, JSP or ASP engine gives only ID to client and we call that ID session.

### Cookie

Mechanism that server keeps data from client .

+ Persistend Cookie : Though browser is turned off data being saved but when the limit is over data deleted.
+ Seesion Cookie : Saved in cash, and deleted when server is expired.

So the difference between cookie and session is that sessino saves a data from server and cookie saves data from client.

## Procedure of keeping cookie session



## Reference

http://gun0912.tistory.com/50

http://soul0.tistory.com/106