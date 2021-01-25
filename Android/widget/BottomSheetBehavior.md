# Bottom Sheet Behavior

## Content

+ What is Bottom Sheet Behavior
+ Attributes of Bottom Sheet Behavior
+ Problem that I faced
+ Reference

## What is Bottom Sheet Behavior

## Attributes of Bottom Sheet Behavior

## Provlem that I faced

#### What I tried to do

I tried to make a custom Bottom Sheet Behavior. This Bottom Sheet Behavior contains nestedScrollView and when we scroll this to the end, bottom panel shouldn't be covered with bottom navigation bar. 

#### What really happened

When we scroll nestedScrollView to then end, seemed like the view is expanded as much as the full screen size (full screen including bottom navigation)

#### Why this happened

This happened because of the code below.

```kotlin
isFitToContents = false
```



## Reference

+ https://stackoverflow.com/a/59565100