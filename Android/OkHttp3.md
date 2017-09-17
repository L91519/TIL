# OkHttp3'

This is a library that helps 

## Interceptor

It is of course a important but there is only one class that must be implemented in this class which is intercept(Interceptor.Chain chain) class.

According to square.github.io explaination of interface Interceptor, it is written "Typically interceptors add, remove, and transform header on the request or response." And sadly since I dont's know the exact meaning of response and request, I will just consider it that request is a action that client want from server and response as a reply for client. And that means Interceptor delete or add header according to request and response.

### Response interceptor (Interceptor.Chain chain) 

Throws : IOException

The return type of this class is a another object named Response. Let's also know the details of it XD (written below)

## Interceptor.Chain

This also is a interface class.	

Okay, to be hones, and since I am the only one who is reading and editing this, I will just write down what I think Chiain class do.

It seems to me.... that it is something like context..... I don't really know if I am right but it can make a builder class.

### Response proceed(Request request) throws IOException

Okay here, Response class is also important and I don't yet know what it is.

+) When we add request as parameter, response will be returned. so this class is a  class to get response.

## Request

## Request.Builder

## Response

Finally starting to know about it!! I thought there will be some other method that is really important but it was class about what we got as response. 

There is details bout response such as protocol, messages and etc.

### Dealing with header

+ public List\<String> header(String name)
+ @Nullable
  public String header(String name)
+ @Nullable
  public String header(String name, @Nullable String defaultValue)
+ public Headers headers()

#### Headers

Header field of HTTP message.

