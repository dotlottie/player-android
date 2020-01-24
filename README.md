## dotlottie-android Support

We're currently working on proper support for the format on Android.

### Using `.lottie` right now

In the meantime, you can start using `.lottie` files in your projects by using the drop-in 
replacement `DotLottieCompositionFactory` instead of `LottieCompositionFactory` provided by
the [lottie-android](https://github.com/airbnb/lottie-android) library.

copy or clone the file [DotLottieCompositionFactory.java](./DotLottieCompositionFactory.java)
into your project, and use it as you would normally use `LottieCompositionFactory`.


```java
DotLottieCompositionFactory.fromRawRes(this, R.raw.lottie_resource)
    .addListener {
        animationView.setComposition(it)
        animationView.playAnimation()
    }
    .addFailureListener {
        it.printStackTrace()
    }
```

#### Caveats

* currently only accepts single animations