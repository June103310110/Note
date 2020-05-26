# Pre-work to inference openvino on RPI4B
June, May 2, 2020

#### Update System
```
sudo apt update
sudo apt upgrade
pip install --upgrade pip
sudo apt-get install python-pip python-dev
```

#### Sudo install List (Suggest to follow the sequence)
```
venv of python (venv is okay for me)
sudo apt install libatlas-base-dev
sudo apt-get install cython   #需安裝cython才能裝tensorflow，否則會出錯
```

#### Installed in venv list
>>> Ref
https://medium.com/@yanweiliu/raspberry-pi%E5%AD%B8%E7%BF%92%E7%AD%86%E8%A8%98-%E5%8D%81%E4%BA%8C-%E5%AE%89%E8%A3%9Dtensorflow%E5%92%8Ckeras-cafae0d40770

```
pip install mock
pip install tensorflow
pip install keras
pip install --upgrade opencv_contrib_python (this version is for openvino)
```

>### if you finish settle the environment, the output of tensorflow, keras and openvc will like the output below:
```
>>> tf.__version__
'1.14.0'
>>> import keras as k
Using TensorFlow backend.
>>> k.__version__
'2.3.1'
>>> import cv2
>>> cv2.__version__
'4.3.0-openvino'
```

# openvino installing refine list
- Ref 
https://docs.openvinotoolkit.org/latest/_docs_install_guides_installing_openvino_raspbian.html
#### Description:
The tutorial on intel openvino website is good, but there are some mistake. Maybe they will update later.

#### test picture:
- here is a picture that you can download to test for face-detection or person-detection.
https://imgur.com/a/5TRCW8Y

# error list (2 error)
1. Build the Object Detection Sample:
>#### Refine: 
cmake -DCMAKE_BUILD_TYPE=Release -DCMAKE_CXX_FLAGS="-march=armv7-a" /opt/intel/openvino/deployment_tools/inference_engine/samples/cpp

---

2. model problem, 
- face-detection-adas-0001.bin
- face-detection-adas-0001.xml
These IR files can't work for me. I will meet a error below(error id: Error_0, you can find the error message in the end of this document). But if I use the other facedetection or person detection model it will be fine.
I use the model from this repo, and get the result like the below link show.
https://imgur.com/B0rFaFu

>#### IR files download link:
https://download.01.org/opencv/2019/open_model_zoo/R1/models_bin/face-detection-retail-0004/FP32/

> you can use wget to download the file:
ex: wget https://download.01.org/opencv/2019/open_model_zoo/R1/models_bin/face-detection-retail-0004/FP32/face-detection-retail-0004.bin
 

Error message list:
---
#### Error_0 :
```
terminate called after throwing an instance of 'InferenceEngine::details::InferenceEngineException'
  what():  Check 'input_shape_product.get_length() == shape_size(m_output_shape)' failed at /teamcity/work/scoring_engine_build/releases_2020_2/ngraph/src/ngraph/op/reshape.cpp:100:
While validating node 'v0::Reshape Reshape_971(PriorBox_744[0]:f32{2,3909705728}) -> (dynamic?)':
Product of output shape dimensions does not match product of argument shape dimensions (output shape: Shape{1, 2, 3909705728}, argument shape: {2,3909705728}).
```
