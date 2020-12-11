# TuriCreate

Quick Links: [Installation](#supported-platforms) | [Documentation](#documentation) | [WWDC 2019](https://developer.apple.com/videos/play/wwdc2019/420/) |  [WWDC 2018](https://developer.apple.com/videos/play/wwdc2018/712/)

[![Build Status](https://travis-ci.com/apple/turicreate.svg?branch=master)](#)
[![PyPI Release](https://img.shields.io/pypi/v/turicreate.svg)](#)
[![Python Versions](https://img.shields.io/pypi/pyversions/turicreate.svg)](#)

[<img align="right" src="https://docs-assets.developer.apple.com/turicreate/turi-dog.svg" alt="Turi Create" width="100">](#)

# Turi Create 

Check out talks at [WWDC 2019](https://developer.apple.com/videos/play/wwdc2019/420/) and at [WWDC 2018](https://developer.apple.com/videos/play/wwdc2018/712/)!

Turi Create simplifies the development of custom machine learning models. You
don't have to be a machine learning expert to add recommendations, object
detection, image classification, image similarity or activity classification to
your app.

* **Easy-to-use:** Focus on tasks instead of algorithms
* **Visual:** Built-in, streaming visualizations to explore your data
* **Flexible:** Supports text, images, audio, video and sensor data
* **Fast and Scalable:** Work with large datasets on a single machine
* **Ready To Deploy:** Export models to Core ML for use in iOS, macOS, watchOS, and tvOS apps

With Turi Create, you can accomplish many common ML tasks:

| ML Task                 | Description                      |
|:------------------------:|:--------------------------------:|
| [Recommender](https://apple.github.io/turicreate/docs/userguide/recommender/)             | Personalize choices for users    |
| [Image Classification](https://apple.github.io/turicreate/docs/userguide/image_classifier/)    | Label images                     |
| [Drawing Classification](https://apple.github.io/turicreate/docs/userguide/drawing_classifier)  | Recognize Pencil/Touch Drawings and Gestures                     |
| [Sound Classification](https://apple.github.io/turicreate/docs/userguide/sound_classifier)  | Classify sounds                     |
| [Object Detection](https://apple.github.io/turicreate/docs/userguide/object_detection/)        | Recognize objects within images  |
| [One Shot Object Detection](https://apple.github.io/turicreate/docs/userguide/one_shot_object_detection/)    | Recognize 2D objects within images using a single example  |
| [Style Transfer](https://apple.github.io/turicreate/docs/userguide/style_transfer/)        | Stylize images |
| [Activity Classification](https://apple.github.io/turicreate/docs/userguide/activity_classifier/) | Detect an activity using sensors |
| [Image Similarity](https://apple.github.io/turicreate/docs/userguide/image_similarity/)        | Find similar images              |
| [Classifiers](https://apple.github.io/turicreate/docs/userguide/supervised-learning/classifier.html)             | Predict a label           |
| [Regression](https://apple.github.io/turicreate/docs/userguide/supervised-learning/regression.html)              | Predict numeric values           |
| [Clustering](https://apple.github.io/turicreate/docs/userguide/clustering/)              | Group similar datapoints together|
| [Text Classifier](https://apple.github.io/turicreate/docs/userguide/text_classifier/)         | Analyze sentiment of messages    |


Example: Image classifier with a few lines of code
--------------------------------------------------

If you want your app to recognize specific objects in images, you can build your own model with just a few lines of code:

```python
import turicreate as tc

# Load data 
data = tc.SFrame('photoLabel.sframe')

# Create a model
model = tc.image_classifier.create(data, target='photoLabel')

# Make predictions
predictions = model.predict(data)

# Export to Core ML
model.export_coreml('MyClassifier.mlmodel')
```
 
It's easy to use the resulting model in an [iOS application](https://developer.apple.com/documentation/vision/classifying_images_with_vision_and_core_ml):

<p align="center"><img src="https://docs-assets.developer.apple.com/published/a2c37bce1f/689f61a6-1087-4112-99d9-bbfb326e3138.png" alt="Turi Create" width="600"></p>

Supported Platforms
-------------------

Turi Create supports:

* macOS 10.12+
* Linux (with glibc 2.10+)
* Windows 10 (via WSL)

System Requirements
-------------------

Turi Create requires:

* Python 2.7, 3.5, 3.6, 3.7, 3.8
* x86\_64 architecture
* At least 4 GB of RAM



We recommend using virtualenv to use, install, or build Turi Create. 

```shell
pip install virtualenv
```

The method for installing *Turi Create* follows the
[standard python package installation steps](https://packaging.python.org/installing/).
To create and activate a Python virtual environment called `venv` follow these steps:

```shell
# Create a Python virtual environment
cd ~
virtualenv venv

# Activate your virtual environment
source ~/venv/bin/activate
```
Alternatively, if you are using [Anaconda](https://www.anaconda.com/what-is-anaconda/), you may use its virtual environment:
```shell
conda create -n virtual_environment_name anaconda
conda activate virtual_environment_name
```

To install `Turi Create` within your virtual environment:
```shell
(venv) pip install -U turicreate
```

Documentation
-------------

The package [User Guide](https://apple.github.io/turicreate/docs/userguide) and [API Docs](https://apple.github.io/turicreate/docs/api) contain
more details on how to use Turi Create.

GPU Support
-----------

Turi Create **does not require a GPU**, but certain models can be accelerated 9-13x by utilizing a GPU.

| Linux                     | macOS 10.13+         | macOS 10.14+ discrete GPUs, macOS 10.15+ integrated GPUs |
| :-------------------------|:---------------------|:---------------------------------------------------------|
| Activity Classification   | Image Classification | Activity Classification                                  |
| Drawing Classification    | Image Similarity     | Object Detection                                         |
| Image Classification      | Sound Classification | One Shot Object Detection                                |
| Image Similarity          |                      | Style Transfer                                           |
| Object Detection          |                      |                                                          |
| One Shot Object Detection |                      |                                                          |
| Sound Classification      |                      |                                                          |
| Style Transfer            |                      |                                                          |


For more details check https://github.com/apple/turicreate
