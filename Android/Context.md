# Context

While coding BaseActivity I've got a question about the difference between many kinds of contexts. 

Context is abstract class that helps us to use application information.



### BaseContext

Component가 생성될때 Context인 녀석들의 BaseContext

Uses when accessing context in another context.



### ApplicationContext

Application's Singleton Context.

#### When do we NOT Use Application Context

+ Working with GUI
+ Memory Leak 

### ActivityContext

Context that follows activity's lifecycle

~~I think this is what Base Context is.~~

### ContentProvider's getContext

Works like ApplicationContext. 

We can get this context by using getContext() function.





### Reference 

https://mrgamza.tistory.com/197

https://stackoverflow.com/questions/10641144/difference-between-getcontext-getapplicationcontext-getbasecontext-and

