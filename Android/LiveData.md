# LiveData

## Content

+ LiveEventExtension
  + toSingleEvent( )

## LiveEventExtension

### toSingleEvent( )

```kotlin
fun <T> LiveData<T>.toSingleEvent(): LiveData<T>
```

##### Why do we use this?

First of all we should know what is the purpose of LiveData. According to Google's introduction Live data came for those reasons.

- UI matching the data status
- No memory leak
- No crash from activity stop
- No need of manual handling lifecycle
- Always up to data
- Proper configuration changes
- Sharing resources

But in some cases these adventages doesn't work and having no way of disabling observing pattern might be a problem. 

```kotlin
val isTrue = LiveData<Boolean>()
isTrue.postValue("isTrue")
==============================================================
vm.isTrue.observe(this, Observer { if(it == true) Log.d("","")})
```

Just like this case when an action should be fired only once, there might be a proble. But by using .toSingleEvent( ) these problem can be solved. This method calls call( ) method instead of initializing the data. 

```kotlin
val singleLiveEvent = liveData.toSingleEvent()
```

##### Where do we use this?

+ toast
+ snackbar
+ navigation

##### Reference 

+ https://proandroiddev.com/livedata-with-single-events-2395dea972a8
+ https://medium.com/androiddevelopers/livedata-with-snackbar-navigation-and-other-events-the-singleliveevent-case-ac2622673150

