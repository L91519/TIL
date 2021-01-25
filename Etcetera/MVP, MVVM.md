### Model

Model handles all datas that application uses.

#### Model Example

```kotlin
interface LocalSource{
  fun getData()
}

interface RemoteSource{
  fun getUser()
}

class Repository (val localSourceImpl, val remoteSourceImpl){
  fun getData(){
    localSourceImpl.getData()
  }
  
  fun getUser(){
    remoteSourceImpl.getUser()
  }
}
```

Data is being managed this way.

**When we want use functions in model**

```kotlin
val repo: Repository
repo.getData()
repo.getUser()
```

## MVP

Model View Presenter

#### MVP Example

```kotlin
interface ContractEx{
	interface View {
    fun setUserInfo()
  }
  interface Presenter {
    fun getUserInfo()
  }
}

class ViewEx: ContractEx.View{
  val presneter = PresenterEx(this)
  
  override fun onCreate(){
    presenter.getUserInfo()
  }
  
  override fun setUserInfo(){}
}

class PresenterEx(val view: ViewEx): ContractEx.Presenter{
  override fun getuserInfo() {
    view.setUserInfo()
  }
  
}
```

## MVVM

Model View ViewModel