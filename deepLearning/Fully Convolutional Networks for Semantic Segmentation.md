[![hackmd-github-sync-badge](https://hackmd.io/HYl7IHH6TumyhD5p9p8u6A/badge)](https://hackmd.io/HYl7IHH6TumyhD5p9p8u6A)
###### tags: `AI learning` `Unet ref`

# Fully Convolutional Networks for Semantic Segmentation

https://arxiv.org/abs/1411.4038

## keyword
#### 空間金字塔池化 patial pyramid poolong  

#### Submission history
    From: Jonathan Long [view email]
    [v1] Fri, 14 Nov 2014 20:46:03 UTC (5,641 KB)
    [v2] Sun, 8 Mar 2015 22:16:40 UTC (4,333 KB)

#### 作者
    {jonlong,shelhamer,trevor}@cs.berkeley.edu 加州 柏克萊
- Jonathan Long∗
- Evan Shelhamer
    - [google scholar link](https://scholar.google.com/citations?user=-ltRSM0AAAAJ&hl=zh-TW)
    - caffe/ cudnn 創始人
    - computer vision/ machine learning/ deep learning
- Trevor Darrell
    - [google schalar](https://scholar.google.com/citations?user=bh-uRFMAAAAJ&hl=zh-TW)
    - Computer Vision/ Artificial Intelligence
    - caffe 創始人
    - Long-Term_Recurrent_Convolutional
        - [link](https://arxiv.org/abs/1411.4389)

#### 摘要與介紹
- Fully Convolution, end-to-end, pixels-to-pixels
- 可以輸入任意尺寸
- pixel等級的分類
- 語意分割有一個固有的相應關係
    - 全域資訊可以用來解決類別的預測(What)
    - 局域資訊中包含了物件在哪裡(Where)
- 在神經網路中，deep feature hierarchies同時編碼了位置資訊以及語意(semantics)在Local-to-Global(由深到淺)的金字塔中。
    - FCN所定義的架構會跨越深淺層，將深的、粗糙的語意資訊和淺的、精細的外觀資訊進行結合。
- FCN design and dense prediction tradeoffs
- in-network upsampling and multi-layer combinations

#### Related work
- Sliding window detection
    - Overfeat: Integrated recognition, localization and detection using convolutional networks
        > P. Sermanet, D. Eigen, X. Zhang, M. Mathieu, R. Fergus, and Y. LeCun
- semantic segmentation
    - Recurrent convolutional neural networks for scene labeling
        > P. H. Pinheiro and R. Collobert
- image restoration
    - Restoring an image taken through a window covered with dirt or rain
        > D. Eigen, D. Krishnan, and R. Fergus
- semantic segmentation in hybrid proposal-classifier models
    - Rich feature hierarchies for accurate object detection and semantic segmentation
        > R. Girshick, J. Donahue, T. Darrell, and J. Malik
- 只保留卷積部分以設計特徵萃取器
    - Spatial pyramid pooling in deep convolutional networks for visual recognition 
    > K. He, X. Zhang, S. Ren, and J. Sun 
    - 組合目標和 空間金字塔池化 (spatial pyramid poolong)
    - https://arxiv.org/abs/1406.4729

#### 方法


#### ref
- img classify
    - classification with deep convolutional neural networks
    - Very deep convolutional networks for large-scale image recognition
    - Going deeper with convolutions
- transfer learning 
    - A deep convolutional activation feature for generic visual recognition
    - Visualizing and understanding convolutional networks
- semantic segmentation in hybrid proposal-classifier models
    - Rich feature hierarchies for accurate object detection and semantic segmentation
    - Learning rich features from RGB-D images for object detection and segmentation
    - Simultaneous detection and segmentation
- semantic segmentation
    - Recurrent convolutional neural networks for scene labeling