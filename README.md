## dotlottie-android Support

We're currently working on proper support for the format on Android.

## Using `.lottie` right now

In the meantime, you can use the patched version of `LottieCompositionFactory` 
the [lottie-android](https://github.com/airbnb/lottie-android) library.

Copy or clone the file [DotLottieCompositionFactory.java](./DotLottieCompositionFactory.java)
into your project, and replace instances of `LottieCompositionFactory` with `DotLottieCompositionFactory`


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

* Currently only accepts single animations.
* No support for setting animations in XML yet.