# Image Classification

## - LeNet, AlexNet

이미지 처리 분야 딥러닝 모델 중 CNN의 초기 모델이다. 

MLP(Multi Layer Perceptron)에 의해 XOR 문제가 해결되면서 기술이 발전하게 되었다. 하지만 MLP에도 문제점이 존재하는데 input 값의 변화에 매우 민감하게 반응한다는 점이다. 예를 들어 이미지 파일을 입력했을 때 한 픽셀씩 밀리거나 기울어져도 해당 픽셀의 값에 변화가 발생하기 때문에 output에 영향이 크다. 따라서 픽셀끼리의 모양(특징, 특성)을 파악하여 학습해야 변화하는 input에 대해서도 반응할 수 있다.

이를 보안하기 위해 제안된게 CNN이다. CNN은 크게 특징을 추출하기 위한 단계(Feature extraction), 변화에 영향을 받지 않기 위한 단계(Shift and distortion invariance), 분류기 단계(classification)로 구분된다.

- 특징을 추출하기 위한 단계 -> Receptive Field, Convolution filter
- 변화에 영향을 받지 않기 위한 단계 -> subsampling (max pooling)
- 분류기 단계 -> fully connected output

### AlexNet

conv later, max-pooling layer, dropdout layer 5개, fully connected layer 3개를 가졌다. ReLU 함수를 사용하고, batch stochastic gradient descent, 그리고 대회에 적합하게 1000개의 output classification을 얻을 수 있다. 학습을 90 epochs를 수행하였다. 두 부분으로 구조가 구분되는데, 2개의 GPU를 사용한 병렬구조이기 때문이다. 

![img](https://t1.daumcdn.net/cfile/tistory/99FEB93C5C80B5192E)

AlexNet의 특징으로 GPU 병렬연산을 통해 추가적인 정보 습득 가능, ReLU 함수가 사용되면서 같은 정확도를 유지하면서 Tanh을 사용하는 것보다 6배 빨랐다. 또한 Dropout의 사용을 통해 학습을 하고, Overlapping max pooling 방법을 사용했다. 과적합을 막기 위해 data augmentation이란 방법을 통해 데이터 양을 늘렸다.(mirror image, random crops)

