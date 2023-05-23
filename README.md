# Mean Teacher for surface defect inspection with long-tailed distributions.

## Abstract
Introducing new products in a production line implies adjusting the defect inspection systems, labeling efforts, or even training an inspection model from scratch that exploiting existing data can mitigate. Thus, semi-supervised learning via knowledge distillation and the Mean Teacher takes advantage of the capability of transferring knowledge from one domain to the other by integrating transfer learning and domain adaptation to assist the target network in getting instance-level features by averaging the model weights instead of label predictions. Performing distillation after training raises the temperature of the final prediction branches until the student model produces an acceptable soft target set. Given the Mean Teacher settings, we select YOLOv7 as the backbone for both networks due to its training and inference times, scalability, and low latency. The consistency loss reduces the domain gap between the source and the mapped-target images by measuring the Euclidean distance between final predictions. StyleGAN-NADA performs the image-to-image translation as part of the domain adaptation strategies. The previous schemes ensure the consistency of both domains and reduce the cross-domain biases related to the model classification and objectness. The introduced weighting factor balances the learning in tailed classes so that the minorities' accuracy does not rely exclusively on data augmentation. The outcomes demonstrated the proposal's effectiveness even over typical supervised transfer learning in datasets with few samples. It redeems lower training times than similar approaches, making it suitable for defect inspection.

**Keywords**: Mean Teacher, Semi-supervised transfer learning, Defect inspection, Domain Adaptation.

## Requirements

You can install the minimum requirements via pip or conda as follows:

**pip**
```
pip install -r requirements.txt
```

**Conda**
```
conda env create -f environment.yml 
conda activate MT-YOLOv7-AOI
```

**Docker**

We suggest to create a shared folder to manage your datasets. For example, ours is called "share" and it is located in the home. You can set the size of such shared folder by adjusting --shm-size.
```
sudo docker pull nvcr.io/nvidia/pytorch:20.12-py3
sudo docker run -v $PWD/share:/opt/share --name MT-YOLOv7-AOI -p 8888:8888 --shm-size 10G --gpus all -it nvcr.io/nvidia/pytorch:20.12-py3
pip install -r requirements.txt
```


## Description

### demo1.ipynb
TBD.

## Implementation details
Our experiments were performed on a PC with an Intel(R) Core(TM) i5-10400F 2.90GHz CPU and an NVIDIA RTX 3060 GPU.

## Additional information about labels

Our datasets contain labels in Chinese, so we decided to translate them into English for research purposes. The chart below shows the changes we made.

| Defects | Original name |
| ------- | ------- |
| white crack | _bailiewen |
| standard chipping | _biaozhunbengque |
| standard crack | _biaozhunliewen |
| chamfer | _daojiao |
| multifaceted | _duocengmian  |
| crystallization | _jiejing |
| contour chipping | _lunkuobengque |
| superficial chipping | _mohubengque |
| ambiguity | _molengliangke |
| plane chipping | _pingmianbengque |
| light inking | _qianmo |
| triangular row | _sanjiaolie |
| bump | _tudian |
| fine cracks | _xixiaoliewen |
| impurities | _zazhi |
| chipping | bengque |
| abnormal chamfer | daojiaoyichang |
| crack | liewen |
| gas hole | qikong |
| stains | wuzi |
