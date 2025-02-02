# Deep Geometric Distillation Network for Compressive Sensing MRI  

This repository contains the CS-MRI reconstruction pytorch codes for the following paper：  
Xiaohong Fan, Yin Yang, Jianping Zhang*, “Deep Geometric Distillation Network for Compressive Sensing MRI,” 2021 IEEE EMBS International Conference on Biomedical and Health Informatics (BHI), 2021, doi: 10.1109/BHI50953.2021.9508565. [[pdf]](https://ieeexplore.ieee.org/document/9508565) 

Xiaohong Fan, Yin Yang, Jianping Zhang*, “Deep Geometric Distillation Network for Compressive Sensing MRI,” arXiv, 2021. [[pdf]](https://arxiv.org/abs/2107.04943) 

### Abstract
Compressed sensing (CS) is an efficient method to reconstruct MR image from small sampled data in k-space and accelerate the acquisition of MRI. In this work, we propose a novel deep geometric distillation network which combines the merits of model-based and deep learning-based CS-MRI methods, it can be theoretically guaranteed to improve geometric texture details of a linear reconstruction. Firstly, we unfold the model-based CS-MRI optimization problem into two sub-problems that consist of image linear approximation and image geometric compensation. Secondly, geometric compensation sub-problem for distilling lost texture details in approximation stage can be expanded by Taylor expansion to design a geometric distillation module fusing features of different geometric characteristic domains. Additionally, we use a learnable version with adaptive initialization of the step-length parameter, which allows model more flexibility that can lead to convergent smoothly. Numerical experiments verify its superiority over other state-of-the-art CS-MRI reconstruction approaches.

![image](https://user-images.githubusercontent.com/48355877/185526778-ccebef63-1c3f-462f-9566-ab06366a0497.png)   
Fig. 1. The overall architecture of deep geometric distillation network for Compressive Sensing MRI reconstruction

These codes are built on PyTorch and tested on Ubuntu 18.04/20.04 (Python3.x, PyTorch>=0.4) with Intel Xeon CPU E5-2630 and Nvidia Tesla V100 GPU.

### Environment  
```
pytorch <= 1.7.1 (recommend 1.6.0, 1.7.1)
scikit-image <= 0.16.2 (recommend 0.16.1, 0.16.2)
```

### 1.Test CS-MRI  
1.1、Pre-trained models:  
All pre-trained models for our paper are in './model_MRI'.  
1.2、Prepare test data:  
The original test set BrainImages_test is in './data/'.  
1.3、Prepare code:  
Open './Core_MRI-DGDN.py' and change the default run_mode to test in parser (parser.add_argument('--run_mode', type=str, default='test', help='train、test')).  
1.4、Run the test script (Core_MRI-DGDN.py).  
1.5、Check the results in './result/'.

### 2.Train CS-MRI  
2.1、Prepare training data:  
We use the same dataset and training data pairs as ISTA-Net+ for CS-MRI. Due to upload file size limitation, we are unable to upload training data directly. Here we provide a [link](https://pan.baidu.com/s/1ap07Jc3u0biCu8rxjB5wlA?pwd=hph4) to download the dataset for you.  
2.2、Prepare measurement matrix:  
We fix the pseudo radial sampling masks the same as ISTA-Net+. The measurement matrixs are in './sampling_matrix/'.  
2.3、Prepare code:  
Open './Core_MRI-DGDN.py' and change the default run_mode to train in parser (parser.add_argument('--run_mode', type=str, default='train', help='train、test')).  
2.4、Run the train script (Core_MRI-DGDN.py).  
2.5、Check the results in './log_MRI/'.

### Citation  
If you find the code helpful in your resarch or work, please cite the following papers. 
```
@Article{Fan2021,
  author    = {Xiaohong Fan and Yin Yang and Jianping Zhang},
  journal   = {2021 {IEEE} {EMBS} International Conference on Biomedical and Health Informatics ({BHI})},
  title     = {Deep Geometric Distillation Network for Compressive Sensing {MRI}},
  year      = {2021},
  doi       = {10.1109/BHI50953.2021.9508565},
  publisher = {{IEEE}},
}
```

### Acknowledgements  
Thanks to the authors of ISTA-Net+ and FISTA-Net, our codes are adapted from the open source codes of ISTA-Net+ and FISTA-Net.   

### Contact  
The code is provided to support reproducible research. If the code is giving syntax error in your particular python configuration or some files are missing then you may open an issue or directly email me at fanxiaohong@zjnu.edu.cn or fanxiaohong1992@gmail.com or fanxiaohong@smail.xtu.edu.cn
