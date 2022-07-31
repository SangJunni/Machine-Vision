# Machine-Vision
해당 코드들은 colab 환경에서 진행되었으며 GPU 사용은 Transfer Learning 과 Object Detection 외에는 사용하지 않습니다.  
해당 코드들을 다른 이미지들로 테스트하는 과정에서 시간이 오래 걸릴 경우 이미지 사이즈를 줄이는 것을 권장합니다.  
또한 해당 코드들은 tensorflow 및 keras를 활용하여 코드가 작성되었습니다.  

Camera Calibration
-----------
해당 파트에서는 checkerboard가 찍힌 이미지들을 통해 corner를 검출 한 뒤에 3차원 물체를 생성합니다.
![result2](https://user-images.githubusercontent.com/79644050/182020631-06f38f9a-0616-41b2-b192-78838b4d9558.jpg)
![result8](https://user-images.githubusercontent.com/79644050/182020640-4f1a975f-7ba0-4737-95d3-56f4d086084c.jpg)


Filtering
-----------
해당 파트에서는 average filter, gaussian filter, median filter를 적용하여 결과 확인을 진행하며 이외에도 image sharpening, nosie 생성 등을 진행합니다.
![National_Theater_Scaled](https://user-images.githubusercontent.com/79644050/182020687-6bd5ced3-44a7-4f72-ae54-1b1fc21350c9.jpg)
![National_Theater_Sp025_3](https://user-images.githubusercontent.com/79644050/182020692-727a4855-c871-4484-91f5-e06eccc22132.jpg)
![result3_sharpen10](https://user-images.githubusercontent.com/79644050/182020698-f77e7495-12da-4537-8a5b-a3c0c0493e28.jpg)

Line Fitting
-----------
해당 파트에서는 도로에는 차선을 검출하는 Line fitting을 RANSAC을 기반으로 검출하게 됩니다.
![result5](https://user-images.githubusercontent.com/79644050/182020715-9e7caa0a-ea8c-4131-9068-4d2e1062e5c0.jpg)
![result6](https://user-images.githubusercontent.com/79644050/182020718-22abc718-28c9-49d3-a551-52e3e9d8deb9.jpg)


SIFT & Corner Detector
-----------
코너 검출의 경우 Harris corner detector로 코너를 검출하게 되며 이외에도 SIFT 를 통해 blob을 검출합니다. 이후 blob을 통해 얻은 두 이미지들의 matching을 수행하게 됩니다.

![result1_1](https://user-images.githubusercontent.com/79644050/182020732-2f0d6a82-33ea-4277-a0c6-8b91f8c216f0.jpg)
![result2_1](https://user-images.githubusercontent.com/79644050/182020737-fbd0cfdf-e602-4475-a463-c82b506c085e.jpg)


Homography
-----------
SVD를 활용한 homography를 수행한 뒤에 두 영상을 합치는 과정을 수행하게 됩니다.
![theater](https://user-images.githubusercontent.com/79644050/182020769-b64e20c5-a0aa-4f34-8029-dd35b719b04d.jpg)
![banner](https://user-images.githubusercontent.com/79644050/182020774-7bf73f50-766a-4bbd-a86b-cc594c23146a.jpg)
![result1_3](https://user-images.githubusercontent.com/79644050/182020783-cc1ee26b-fe8f-47d7-928f-add48e61a05c.jpg)

이외에도 SIFT의 blob 검출을 토대로 Image Stitching을 진행합니다.
![sculpture1](https://user-images.githubusercontent.com/79644050/182020797-09c30656-1ef8-4708-9a12-7a2b00aaec54.jpg)
![sculpture2](https://user-images.githubusercontent.com/79644050/182020801-de7c7863-54fb-4e81-a466-62f32a134746.jpg)
![result2_4](https://user-images.githubusercontent.com/79644050/182020789-9dffbc88-6c4f-46f8-81a5-4e4699a102b1.jpg)

Transfer Learning
-----------
Fashion Mnist와 CIFAR10 데이터셋들을 Dense Layer를 통한 학습 외에도, Lenet-5 와 VGG16을 통한 전이학습을 실시합니다.

Object Detection Step by step
-----------
Yolo와 같은 one-stage detector를 직접 모델을 쌓아서 진행합니다.
![image](https://user-images.githubusercontent.com/79644050/182020857-1650f727-f069-4cd6-9ffe-59e9bf095102.png)

