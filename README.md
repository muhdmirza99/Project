(This project was made during a deep learning workshop held by a local university.)

# Project
Vehicle Detection and Classification using Nvidia Jetson Nano

# Background
To develop a system that can detect and classify vehicles using image classification. For this project, cars, motorcycles, and lorries were used as datasets. 

# Methodology
1. Dataset Collection
  - Obtain data from Google Images (depends on your scope; datasets are vast available in the Internet)
  - Three datasets: cars, motorcycles, lorries, (most are vehicles from Malaysia)
2. Dataset Annotation
  - Roboflow: Used in various computer vision industries for use cases such as – gas leak detection, plant vs weed detection, aeroplane maintenance, and many more.

![2022-08-02 (7)](https://user-images.githubusercontent.com/103092362/184589591-222bc9b6-d523-475b-a1ab-dd4b47ca1dfe.png)

  - Each datasets was annotated and undergoes preprocessing and augmentation to increase the efficiency of the image classification.

3. Dataset Training
  - Datasets were trained using YoloV5 custom training included in the repository

4. Inference
  - For inference, a video of vehicles are recorded and tested with the trained model.
  
 python detect.py --weights project_1.pt --source 0      # webcam
 
                                           img.jpg  # image
                                           vid.mp4  # video
                                           path/  # directory
                                          'path/*.jpg'  # glob
                                          (https://www.youtube.com/watch?v=tOJpQIgWdpI&t=1s)'  # YouTube
                                          'rtsp://example.com/media.mp4'  # RTSP, RTMP, HTTP stream

# YoloV5 Github
 https://github.com/ultralytics/yolov5
 
 # Setup in Jetson Nano
1. Clone the YoloV5 repo
  - git clone https://github.com/ultralytics/yolov5
  - cd yolov5
  - pip install -r requirements.txt
2. Modify requirements.txt
  - Open YoloV5 directory
  - Open requirements.txt using text editor
  - Comment #torch>=1.7.0 to #torchvision>=0.8.1
3. Install PyTorch
  - git clone --recursive --branch 1.7 http://github.com/pytorch/pytorch
  - cd pytorch
  - python3.8 -m pip install -r requirements.txt
  - python3.8 setup.py install
4. Install torchvision
  - git clone https://github.com/pytorch/vision
  - cd vision
  - git checkout v0.8.0
  - python3 setup.py bdist_wheel
  - python3 -m pip install dist/torchvision-0.8.0a0+291f7e2-cp38-cp38-linux_aarch64.whl
(if you encountered error such as missing file error, try to manually install the package using the terminal: sudo apt-get install <filename>)
 
