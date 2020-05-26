###### tags: `AIA`
# OpenVINO 測試
![](https://i.imgur.com/ZFPD9hu.png)
### 前置任務
1. 安裝OPENVINO
2. 安裝Cmakk
3. 安裝VS_studio
#### 參考連結 https://docs.openvinotoolkit.org/2020.1/_docs_install_guides_installing_openvino_windows.html#usb-myriad

```
# INSTALL_DIR 
C:\Program Files (x86)\IntelSWTools\openvino
```

## 安裝後的測試
### 1. Set the Environment Variables 
>done![](https://i.imgur.com/HVAIFYo.png)
```
cd C:\Program Files (x86)\IntelSWTools\openvino\bin\
setupvars.bat
```

> ####  Note: Model Optimizer 是Intel做的基於python的模型轉換器，轉換後才能Inference 
### 2. Configure the Model Optimizer for all supported frameworks at the same time: 
>done for tensorflow and caffe
```
cd C:\Program Files (x86)\IntelSWTools\openvino\deployment_tools\model_optimizer\install_prerequisites
install_prerequisites.bat
```

#### 意外
![](https://i.imgur.com/ZJVtTwu.png)

### 3. Use Verification Scripts to Verify Your Installation
> done ![](https://i.imgur.com/YldTH2Y.png)

```
cd C:\Program Files (x86)\IntelSWTools\openvino\deployment_tools\demo\
demo_squeezenet_download_convert_run.bat
```

### 4. Run the Inference Pipeline Verification Script
> done ![](https://i.imgur.com/PMxITrZ.jpg)

```
cd C:\Program Files (x86)\IntelSWTools\openvino\deployment_tools\demo\
demo_security_barrier_camera.bat
```

### 5. Run the Image Classification Sample Application
> done for CPU and VPU(stick 2)

CPU
![](https://i.imgur.com/pr4BV9c.png)

VPU(stick 2)
![](https://i.imgur.com/0kSfm2f.png)
```
cd C:\Program Files (x86)\IntelSWTools\openvino\bin
setupvars.bat
cd C:\Users\June\Documents\Intel\OpenVINO\inference_engine_samples_build\intel64\Release

# for CPU:
classification_sample_async.exe -i "C:\Program Files (x86)\IntelSWTools\openvino\deployment_tools\demo\car.png" -m "C:\Users\June\Documents\Intel\OpenVINO\openvino_models\ir\public\squeezenet1.1\FP16\squeezenet1.1.xml" -d CPU

# For VPU (Intel® Movidius™ Neural Compute Stick and Intel® Neural Compute Stick 2):
classification_sample_async.exe -i "C:\Program Files (x86)\IntelSWTools\openvino\deployment_tools\demo\car.png" -m "C:\Users\June\Documents\Intel\OpenVINO\openvino_models\ir\public\squeezenet1.1\FP16\squeezenet1.1.xml" -d MYRIAD
```

## 補充
看起來好像可以轉換自己的tensorflow model來用，測試一下
[--連結在此](https://docs.openvinotoolkit.org/2020.1/_docs_MO_DG_prepare_model_convert_model_Convert_Model_From_TensorFlow.html)
![](https://i.imgur.com/omCpXY6.png)
