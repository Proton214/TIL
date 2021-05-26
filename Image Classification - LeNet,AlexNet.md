# Image Classification

## - LeNet, AlexNet

이미지 처리 분야 딥러닝 모델 중 CNN의 초기 모델이다. 

MLP(Multi Layer Perceptron)에 의해 XOR 문제가 해결되면서 기술이 발전하게 되었다. 하지만 MLP에도 문제점이 존재하는데 input 값의 변화에 매우 민감하게 반응한다는 점이다. 예를 들어 이미지 파일을 입력했을 때 한 픽셀씩 밀리거나 기울어져도 해당 픽셀의 값에 변화가 발생하기 때문에 output에 영향이 크다. 따라서 픽셀끼리의 모양(특징, 특성)을 파악하여 학습해야 변화하는 input에 대해서도 반응할 수 있다.

이를 보안하기 위해 제안된게 CNN이다. CNN은 크게 특징을 추출하기 위한 단계(Feature extraction), 변화에 영향을 받지 않기 위한 단계(Shift and distortion invariance), 분류기 단계(classification)로 구분된다.

- 특징을 추출하기 위한 단계 -> Receptive Field, Convolution filter
- 변화에 영향을 받지 않기 위한 단계 -> subsampling (max pooling)
- 분류기 단계 -> fully connected output

### AlexNet

conv later, max-pooling layer, dropdout layer 5개, fully connected layer 3개를 가졌다. ReLU 함수를 사용하고, batch stochastic gradient descent, 그리고 대회에 적합하게 1000개의 output classification을 얻을 수 있다. 학습을 90 epochs를 수행하였다.

![img](https://t1.daumcdn.net/cfile/tistory/99FEB93C5C80B5192E)

