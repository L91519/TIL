# Retrofit

This is a open source which helps us in http parsing.

Actually I was only focusing on Aquery because this also can handle http connection and even easier... XD but very soon I realized that retrofit is really necessary.

Retrofit depends on OkHttp so though there isn't slient abstaction, we can still make client by using OkHttp Client.

I really didn't wanted to know more about Retrofit but I had to if I wanted to make my project in better way and I'll list down some reasons.

+ Easier to handle errors. (In Aquery, certain error are not able to catch : 수정 예정)
+ Get data and use parsing library to handle it in the way that request is up to.
+ When done connecting with server, request will be sent in the way that server is parsing to android.
+ Http connection must be systemetically handled about whether network connection to server is on or not, and this open source handles this problem.


Before using this method, INTERNET permissino in manifest should be written.

And another important thing about retrofit is that it depends on many other libraries. Such as GSon and OkHttp3. So for you to understand all the method, it's better for you to know all of them... (At least for me Retrofit depending on other libraries made many difficulties.)

## Package retrofit2

### Interface

#### Annotation 

+ @GET
+ @Path
+ @Query

#### Call\<T>

 calls Retrofit method which sends request to server and returns a response.

\<T> : Successful response body type.

### Class

#### Retrofit.Builder

Build new Retrofit.

public Retrofit build() : Create Retrofit

#### Retrofit

public\<T\> create (Class\<T> service) : create an implemention of the API endpoints defined by service interface.

## Retrofit Ex1 (Android)

https://github.com/fs-opensource/android-retrofit-video

Here is the example of a program which uses retrofit.

This works with ListView widget, but here, I am only gonna explain about 'Main Activity' and client interface

### Client Interface

It's only written : 

```java
@Get("/users/{user}/repos")
Call<List<GitHubRepo>> reposForUsers(@Path("user")String user);
```

+ @Path("user") : Since the request is dynamic, by using '@Path' annotation, replace a name in url segment.


+ reposForUsers : Name of the method.
+ List\<GitHubRepo\> : Responded body type.

### Main Activity

```java
Call<T>.enqueue
```

+ Asynchronously send the request and notiy callback method.

```java
GitHubClient client = retrofit.create(GitHubClient.class);
```

+ Implements interface

```java
Retrofit.Builder builder = new Retrofit.Builder().baseUrl().addConvertedFactory();
```

+ addConvertedFactory : Add converter factory for serialization and deserialization of objects.
+ Converter.Factory : 
  + Parament type in addConvertedFactory
  + Convert object to and from their representation in HTTP. (HTTP에서 표현과 객체를 변환한다.) In fact I don't really understand this sentence but I guess this means that when we have a object in java source, we can convert it suitable to http by using this method.

## Retrofit Ex2 (Kotlin)

```kotlin
@GET("serch/{searchType}.json")
fun funName(@Path("param1" param1: String, @Query("param2") param2: String): Call<Model>)
```



# Reference

+ https://square.github.io/retrofit/2.x/retrofit/index.html?retrofit2/http/Path.html
  + https://github.com/fs-opensource/android-retrofit-video	