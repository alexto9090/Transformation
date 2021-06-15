# Transformation

Glide Transformations
======================
[![Android Arsenal](https://img.shields.io/badge/Android%20Arsenal-glide--transformations-brightgreen.svg?style=flat)](https://android-arsenal.com/details/1/1363)
[![License](https://img.shields.io/badge/license-Apache%202-blue.svg)](https://www.apache.org/licenses/LICENSE-2.0)
[![Maven Central](https://maven-badges.herokuapp.com/maven-central/jp.wasabeef/glide-transformations/badge.svg)](https://search.maven.org/artifact/jp.wasabeef/glide-transformations)

An Android transformation library providing a variety of image transformations for [Glide](https://github.com/bumptech/glide).

Please feel free to use this.


#### Are you using Picasso or Fresco?
[Picasso Transformations](https://github.com/wasabeef/picasso-transformations)  
[Fresco Processors](https://github.com/wasabeef/fresco-processors)

# Demo

### Original Image
<img src="art/demo-org.jpg" width="30%">

### Transformations
<img src="art/demo.gif" width="50%">

# How do I use it?

## Step 1

#### Gradle
```groovy
repositories {
  mavenCentral()
}

dependencies {
  implementation 'jp.wasabeef:glide-transformations:4.3.0'
  // If you want to use the GPU Filters
  implementation 'jp.co.cyberagent.android:gpuimage:2.1.0'
}
```

## Step 2

Set Glide Transform.

```kotlin
Glide.with(this).load(R.drawable.demo)
  .apply(RequestOptions.bitmapTransform(BlurTransformation(25, 3)))
  .into(imageView)
```

## Advanced Step 3

You can set a multiple transformations.

```kotlin
val multi = MultiTransformation<Bitmap>(
  BlurTransformation(25),
  RoundedCornersTransformation(128, 0, CornerType.BOTTOM))))
Glide.with(this).load(R.drawable.demo)
  .apply(RequestOptions.bitmapTransform(multi))
  .into(imageView))
```

## Transformations

### Crop
- `CropTransformation`
- `CropCircleTransformation`
- `CropCircleWithBorderTransformation`
- `CropSquareTransformation`
- `RoundedCornersTransformation`

### Color
- `ColorFilterTransformation`
- `GrayscaleTransformation`

### Blur
- `BlurTransformation`

### Mask
- `MaskTransformation`

### GPU Filter (use [GPUImage](https://github.com/CyberAgent/android-gpuimage))
**Will require add dependencies for GPUImage.**  

- `ToonFilterTransformation`
- `SepiaFilterTransformation`
- `ContrastFilterTransformation`
- `InvertFilterTransformation`
- `PixelationFilterTransformation`
- `SketchFilterTransformation`
- `SwirlFilterTransformation`
- `BrightnessFilterTransformation`
- `KuwaharaFilterTransformation`
- `VignetteFilterTransformation`


Applications using Glide Transformations
---
