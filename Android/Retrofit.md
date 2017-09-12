# Retrofit

This is a open source which helps us in http parsing.

Actually I was only focusing on Aquery because this also can handle http connection and even easier... XD 

I really didn't wanted to know more about Retrofit but I had to if I wanted to make my project in better way and I'll list down some reasons.

+ Easier to handle errors.
+ Get data and use parsing library to handle it in the way that request is up to.
+ When done connecting with server, request will be sent in the way that server is parsing to android.
+ Http connection must be systemetically handled about whether network connection to server is on or not, and this open source handles this problem.



Before using this method, INTERNET permissino in manifest should be written.

## Package retrofit2

### Interface

#### Call<T>

 calls Retrofit method which sends request to server and returns a response.

<T> : Successful response body type.

### Class

#### Retrofit.Builder

Build new Retrofit.

public Retrofit build() : Create Retrofit

#### Retrofit

public <T> create (Class<T> service) : create an implemention of the API endpoints defined by service interface.

