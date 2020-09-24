# Sending Enum or Data Class with Retrofit

## Sending Enum As Query or Path

I've been suffering with sending Enum data with Retrofit. When I send Enum with Retrofit by using @Query or @Path, I had to get the value from it. And it was kind of hessle. So me and my coworker decided to make a converter of Enum class so that we no more have to use value of Enum.

```kotlin
enum class DataType(val value: String) {
		@SerializedName(StringKeySet.firstEnum)
		FIRST_ENUM,
		
		@SerializedName(StringKeySet.sexondEnum)
		SECOND_ENUM;
		
		companion object {
				fun parse(value: String): DataType {
						return when(value) {
								StringKeySet.firsetValue -> FIRST_VALUE
								StringKeySet.secondValue -> SECOND_VALUE
						}
				}
		}
	//used in this way : DataType.value
}
```

And these enum class had to be send as Retrofit's @Query or @Path. But our first thought was to use JsonSerializer and JsonDeserializer. When I searched about this in Google, some people seemed to get through with this way. But maybe they weren't dealing with Retrofit's @Query or @Path (I guess they were dealing with @Body).

What we need here was Converter.Factory( )

```kotlin
class EnumConverterFactory : Converter.Factory() {
  override fun stringConverter(type: Type, annotations: Array<Annotation>, retrofit: Retrofit) Converter<Enum*>, String>? = if(type is Class<*> && type.isEnum) {
    Converter {enum -> 
              enum.javaClass.getField(enum.name.getAnnotation(SerializedName::class.java)?.value)
         }
  	 }
}
```

and put this as retrofit builder's converter factory. By using Converter.Factory, we check if the type is Enum class and if it is, get the serialized name from it. You might be having hard time understancding Converter.Factory( ). Because I did ;D

### Converter.Factory()

Converter is a interface of Retrofit and it contains Facotry as it's abstract class. According to the Converter.java Factory returns as voncerter for converting an HTTP response body to coded type. So we override stringConverter to make a converter returning String.

```java
public @Nullable Converter<?, String> stringConverter(
	Type type, Annotation[] annotations, Retrofit retrofit) {
  return null;
}
```



## JsonSerializer JsonDeserializer

This can be used when we want to send DataClass or Enum as @Body of Retrofit. This is a interface of Gson, so when we want to use this, we have to add class that implements JsonSerializer and JsonDeserializer  to GsonBuilder. Actually the way of using this is well introduced in Gson GitHub. Maybe better checking this in their page.

https://www.javadoc.io/doc/com.google.code.gson/gson/2.8.5/com/google/gson/JsonSerializer.html

https://www.javadoc.io/doc/com.google.code.gson/gson/2.6.2/com/google/gson/JsonDeserializer.html



## Adapter

Last way was using adapter but since I haven't done this yet, I will leave this as TO BE DONE. BYE