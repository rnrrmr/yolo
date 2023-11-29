# yolo
yolo_nas를 활용한 객체 검지


# YOLO 와 YOLO-NAS의 차이점

**YOLO(You Only Look Once)**는 객체 탐지 알고리즘으로, 실시간 객체 탐지에 특화된 딥러닝 기반 알고리즘입니다. YOLO 알고리즘은 이미지를 그리드로 분할하고, 각 그리드 셀에서 객체의 존재 여부와 객체의 경계 상자(bounding box)를 예측합니다. 그 후, 경계 상자에 해당하는 객체를 분류하고, 객체의 경계 상자를 정제하여 최종 결과를 출력합니다. YOLO는 여러 개의 크기와 종류의 객체를 동시에 탐지할 수 있으며, 빠른 처리 속도를 가지고 있어 실시간 환경에서의 객체 탐지에 유리합니다.

**YOLO-NAS(You Only Look Once Neural Architecture Search)**는 YOLO의 Neural Architecture Search(신경망 구조 탐색) 버전입니다. 기존의 YOLO는 사전에 정의된 신경망 구조를 사용했지만, YOLO-NAS는 최적의 신경망 구조를 찾기 위해 Neural Architecture Search를 활용합니다. Neural Architecture Search는 기계 학습을 통해 최적의 신경망 구조를 자동으로 탐색하는 방법입니다. YOLO-NAS는 YOLO와 마찬가지로 객체 탐지를 수행하지만, 탐지 성능을 향상시키기 위해 더욱 최적화된 신경망 구조를 찾아내는 데 중점을 둡니다.

요약하자면, **YOLO는 객체 탐지 알고리즘**이며, 실시간 처리와 다양한 객체의 탐지에 특화되어 있습니다. 반면, **YOLO-NAS는 YOLO의 신경망 구조를 탐색하는 기술인 Neural Architecture Search를 활용**하여 더 나은 성능을 얻기 위해 사용됩니다.


**A new YOLO model has arrived! YOLO-NAS, faster and more accurate than YOLOv5, v6, v7, AND v8** <br>
https://www.kaggle.com/discussions/general/406701 <br><br>
⛴️📡 **YOLO-NAS Ship Detection Aerial Images** 🛰️🛳️ <br>
https://www.kaggle.com/code/harpdeci/yolo-nas-ship-detection-aerial-images<br> <br>
🛰️ 🚁 **YOLO-NAS Find Cars from Aerial Images** 🚗🚙 <br>
https://www.kaggle.com/code/harpdeci/yolo-nas-find-cars-from-aerial-images <br><br>

👨‍💻**Object Detection: YOLO-NAS Model** 🔍 <br>
https://www.kaggle.com/code/lusfernandotorres/object-detection-yolo-nas-model
<br><br>


**What is YOLO-NAS?** <br>
https://roboflow.com/model/yolo-nas


*   How to Train YOLO-NAS
*   YOLO-NAS Training Notebook
*   view on github
*   yolo-nas video guide
*   YOLO-NAS Training on Kaggle

<br>

**Turtle Face YOLO-NAS Train & Predict** <br>
https://www.kaggle.com/code/stpeteishii/turtle-face-yolo-nas-train-predict

<br>

**Human Face YOLO-NAS Train & Predict** <br>
https://www.kaggle.com/code/stpeteishii/human-face-yolo-nas-train-predict

<br>

**Introducing YOLO-NAS: One of The Most Efficient Object Detection Algorithms** <br>
https://medium.com/latinxinai/introducing-yolo-nas-one-of-the-most-efficient-object-detection-algorithm-d24303de542 <br><br>




Deci AI는 신경망 아키텍처 검색 엔진인 AutoNAC를 사용하여 새로운 YOLO-NAS 모델을 만들었습니다. 이 모델은 YOLOv5, YOLOv6, YOLOv7 및 최근 출시된 YOLOv8을 포함하여 속도와 정확도 측면에서 다른 모든 SOTA YOLO를 능가합니다. 이 게시물에서는 이 흥미로운 새 모델을 검토합니다.
YOLO-NAS는 YOLOv8 및 YOLOv7의 동급 버전보다 약 0.5 mAP 포인트 더 정확하고 10-20% 더 빠릅니다

**발전 1: YOLO를 위한 건축 검색**
Deci의 독점 Neural Architecture Search 기술인 AutoNAC™는 YOLO-NAS 모델 생성을 담당했습니다. 이 프레임워크는 주어진 작업과 하드웨어 제약을 고려하여 심층 신경망의 추론 속도와 정확도를 최적화하도록 설계되었습니다. AutoNAC™를 사용하여 Deci는 YOLOv8을 포함하여 SOTA YOLO 모델보다 더 정확하고 빠른 새로운 YOLO 아키텍처를 만들 수 있었습니다.

**발전 2: 학습 후 최적화 준비**
VGG는 매우 유명한 전통적인 CNN 아키텍처입니다. 단순성과 효율성으로 유명합니다. 그러나 속도와 메모리 측면에서 그다지 효율적이지 않습니다. 이 문제를 해결하기 위해 RepVGG가 제안되었습니다. RepVGG는 VGG를 기반으로 하는 단순하면서도 강력한 아키텍처입니다. 속도와 메모리 측면에서 더 효율적으로 설계되었습니다. 재매개변수화를 통해 RepVGG는 다중 분기 아키텍처로 학습된 다음 더 빠른 추론을 위해 단일 분기로 변환될 수 있습니다.
<br>
<br>
RepVGG를 사용하여 YOLO-NAS의 아키텍처는 재매개변수화를 통해 학습 후 최적화할 수 있으며 Post-training Quantization과도 호환됩니다. 이는 프로덕션 배포에 매우 중요한 기능입니다. 이 모델은 완전한 정밀도로 훈련된 다음 추론 속도 및 메모리 사용량에 맞게 최적화될 수 있습니다.

**발전 3: 양자화 인식 훈련**
교육 후 양자화를 통해 사용자는 추론을 위해 매우 효율적인 양자화 정수 모델을 만들 수 있습니다. 그러나 신중한 사후 훈련 보정에도 불구하고 모델 정확도는 허용할 수 없을 정도로 손상될 수 있습니다. 이런 일이 발생하면 훈련 후 보정만으로는 양자화된 정수 모델을 생성하기에 충분하지 않습니다. 대신 양자화 효과를 설명하는 방식으로 모델을 훈련해야 합니다. 훈련 중에 양자화 효과를 모델링할 수 있는 기능이 있으므로 양자화 인식 훈련이 들어오는 곳입니다.
<br>
<br>
양자화 인식 블록과 선택적 양자화를 활용하여 YOLO-NAS는 성능을 최적화하는 아키텍처를 사용합니다. 이 모델의 설계에는 정확도 손실과 대기 시간/처리량 개선 사이의 균형에 따라 특정 계층에서 양자화를 건너뛰는 적응형 양자화가 포함됩니다. 모델이 INT8 양자화 버전으로 변환될 때 YOLO-NAS는 다른 모델에 비해 더 작은 정밀도 저하를 경험하여 S, M 및 L 변형에 대해 각각 0.51, 0.65 및 0.45 포인트의 mAP만 손실합니다. 이것은 양자화 동안 1-2 mAP 포인트의 손실을 경험하는 다른 모델과 대조됩니다. 이러한 혁신적인 기술은 뛰어난 물체 감지 기능과 우수한 성능을 갖춘 아키텍처에 기여합니다.


**발전 4: 훈련 전략**
YOLO-NAS의 훈련 과정은 Preuso-labeled Data, Knowledge Distillation, Distribution Focal Loss와 같은 다양한 기술로 강화되었습니다. 이러한 기술을 사용하면 모델 변형에 따라 25-40 에포크에서 Object365 데이터 세트로 SOTA 사전 훈련된 모델을 생성할 수 있습니다.

Distribution Focal Loss는 상자 예측을 유한 값 집합으로 이산화하여 상자 회귀를 분류 작업으로 활용합니다. 그런 다음 이러한 값에 대한 확률 분포를 예측하고 궁극적으로 가중 합계를 통해 최종 예측으로 변환됩니다.

Knowledge Distillation은 큰 모델에서 작은 모델로 지식을 이전하는 기술입니다. 이 방법을 통해 경량 모델은 데이터 세트에서만이 아니라 대형 모델에서 지식(확률 분포)을 학습하여 더 나은 성능을 얻을 수 있습니다. YOLO-NAS의 경우 학생 모델은 교사 모델의 분류와 DFL 예측 모두에서 학습합니다.

<br><br>



**Try: YOLO-NAS**
Deci AI released super-gradients library - the easy way to use YOLO-NAS. You can try it on your own data and see the results.
```
# 코드로 형식 지정됨
import super_gradients

yolo_nas = super_gradients.training.models.get("yolo_nas_l", pretrained_weights="coco").cuda()
yolo_nas.predict("https://deci-pretrained-models.s3.amazonaws.com/sample_images/beatles-abbeyroad.jpg").show()

```




# Introduction
물체 감지는 기계가 주변 세계를 인식하고 해석하는 방식을 혁신적으로 변화시켰습니다.

이는 컴퓨터 비전에서 중요한 작업으로, 기계가 이미지나 비디오 내에서 물체를 인식하고 찾을 수 있도록 합니다. 수년에 걸쳐 이 기술은 점점 더 강력해지고 정확해졌으며 자율 주행 차량, 안면 인식 시스템 등과 같이 현대 세계를 형성하는 많은 애플리케이션에서 없어서는 안 될 존재가 되었습니다. 개체 감지의 발전을 이끈 핵심 요소 중 하나는 강력한 신경망 아키텍처의 발견입니다. 강력한 신경망 아키텍처의 발견은 객체 감지의 발전을 주도하여 컴퓨터 비전의 기능을 향상시켰습니다.

특히 Faster R-CNN 및 YOLO와 같은 아키텍처는 최신 개체 감지 아키텍처를 형성하는 데 중요한 역할을 했습니다.

You Only Look Once의 약자인 YOLO는 객체 감지에 대한 가장 인기 있고 성공적인 접근 방식 중 하나입니다.

YOLO의 첫 번째 버전은 2016년에 도입되었으며 객체 감지를 단일 회귀 문제로 처리하여 객체 감지 수행 방식을 변경했습니다. 이미지를 그리드로 나누고 경계 상자와 클래스 확률을 동시에 예측했습니다. YOLOv1은 이전의 물체 감지 방법보다 빠르지만 작은 물체를 감지하는 데 한계가 있었고 위치 정확도에 어려움을 겪었습니다. 첫 번째 YOLO 아키텍처가 등장한 이후 여러 YOLO 기반 아키텍처가 개발되었으며, 모두 정확성, 실시간 성능, 에지 장치 및 클라우드에서 객체 감지를 지원하는 것으로 알려져 있습니다.

YOLOv6, YOLOv7 및 YOLOv8은 YOLOv5의 성공을 기반으로 구축된 YOLO 제품군의 최신 최신 모델입니다.

그러나 우리가 이 모든 YOLO를 가지고 있다고 해서 객체 감지를 위한 딥 러닝이 연구의 휴면 영역이라는 것을 의미하지는 않습니다.

새로운 YOLO 기반 아키텍처를 개발하면 기존 한계를 해결하고 딥 러닝의 최신 발전을 통합하여 최첨단(SOTA) 객체 감지를 재정의할 수 있습니다. 작은 물체를 감지하는 능력을 향상시키고, 지역화 정확도를 개선하고, 계산당 성능 비율을 증가시켜 실시간 에지 장치 응용 프로그램에서 모델에 더 쉽게 액세스할 수 있도록 하는 새로운 YOLO 기반 아키텍처를 상상해 보십시오.

정확성과 효율성의 경계를 넓힘으로써 새로운 YOLO 아키텍처는 물체 감지를 위한 벤치마크가 되어 혁신을 주도하고 많은 산업 및 연구 영역에서 새로운 가능성을 열 수 있습니다. 이것이 바로 여기 Deci에서 우리가 한 일입니다.

이 게시물에서는 새로운 아키텍처인 YOLO-NAS를 소개하고자 합니다.
<br><br>


# 요약: YOLO-NAS 아키텍처의 새로운 점은 무엇입니까?


*   QSP 및 QCI 블록을 사용하면 재매개변수화와 8비트 양자화 이점이 결합됩니다. 이러한 블록은 Chu 등이 제안한 접근 방식에 의존합니다. 블록은 학습 후 양자화 중에 정확도 손실을 최소화합니다.
*   Deci의 독점 NAS 기술인 AutoNAC은 블록 유형, 블록 수, 각 단계의 채널 수를 포함하여 단계의 최적 크기와 구조를 결정하는 데 사용되었습니다.
* 모델의 특정 부분을 선택적으로 양자화하여 정보 손실을 줄이고 대기 시간과 정확도의 균형을 맞추는 하이브리드 양자화 방법입니다. 표준 양자화는 모든 모델 계층에 영향을 미치며 종종 상당한 정확도 손실을 초래합니다. 당사의 하이브리드 방법은 특정 레이어만 양자화하고 다른 레이어는 그대로 두어 정확도를 유지하기 위해 양자화를 최적화합니다. 레이어 선택 알고리즘은 각 레이어가 정확도와 대기 시간에 미치는 영향은 물론 전체 대기 시간에 대한 8비트와 16비트 양자화 간 전환 효과를 고려합니다.
* 자동으로 레이블이 지정된 데이터, 자체 증류 및 대규모 데이터 세트를 포함하는 사전 교육 방식입니다.
* YOLO-NAS 아키텍처는 오픈 소스 라이선스로 제공됩니다. 사전 훈련된 가중치는 Deci의 PyTorch 기반 오픈 소스 컴퓨터 비전 교육 라이브러리인 SuperGradients에서 연구용(비상업적)으로 사용할 수 있습니다.

<br><br>

새로운 YOLO-NAS 아키텍처는 객체 감지 작업의 새로운 영역을 설정하여 최고의 정확도와 대기 시간 트레이드 오프 성능을 제공합니다.

이 저울은 오늘날의 기존 모델을 능가하여 최첨단(SOTA) 물체 감지에 대한 새로운 표준을 설정합니다. 생산용으로 특별히 설계된 YOLO-NAS는 NVIDIA® TensorRT™와 같은 고성능 추론 엔진과 완벽하게 호환되며 전례 없는 런타임 성능을 위해 INT8 양자화를 지원합니다.

이러한 최적화를 통해 YOLO-NAS는 짧은 대기 시간과 효율적인 처리가 필수적인 자율 주행 차량, 로봇 공학 및 비디오 분석 애플리케이션과 같은 실제 시나리오에서 탁월한 성능을 발휘할 수 있습니다.

이 모델의 혁신적인 아키텍처는 객체 감지 기능을 더욱 향상시키기 위해 추론 시 어텐션 메커니즘, 양자화 인식 블록 및 재매개변수화와 같은 최첨단 기술을 활용합니다. 이는 다양한 크기와 복잡성의 객체를 감지하는 YOLO-NAS의 탁월한 성능에 기여하여 산업 전반에 걸쳐 사용 사례에 대한 새로운 황금 표준을 만듭니다.

이 게시물에서 배우게 될 것처럼 YOLO-NAS는 정확도 및 대기 시간 절충과 관련하여 객체 감지 모델에 대한 새로운 벤치마크를 설정합니다.


# 딥 러닝을 사용하여 새로운 딥 러닝 아키텍처를 찾았습니다!

최신 YOLO 아키텍처인 YOLOv8의 성공에 영감을 받아 연구원들은 더 성능이 뛰어난 아키텍처를 찾는 데 도전했습니다.

당사의 독자적인 신경 아키텍처 검색(NAS) 알고리즘인 AutoNAC(Automated Neural Architecture Construction) 엔진을 활용하여 당사 연구팀은 YOLOv8을 능가하는 새로운 아키텍처를 발견했습니다.

왜 이런 식으로합니까?

손으로 "올바른" 아키텍처를 찾는 것은 매우 지루하고 비효율적입니다. 그래서 널리 사용되는 클라우드 GPU인 NVIDIA의 T4를 통해 계산된 추론 대기 시간을 최소화하도록 최적화된 새로운 객체 감지 모델을 발견하기 위해 AutoNAC를 적용했습니다. AutoNAC은 SOTA 건축 설계 원칙과 Deci의 새로운 신경 요소를 통합한 신경 설계 공간을 사용했습니다.

NAS를 활용하면 수동 탐색에 비해 상당한 이점을 얻을 수 있습니다.

NAS 알고리즘은 잠재적인 아키텍처의 방대한 검색 공간을 체계적으로 탐색하여 인간의 직관으로는 간과할 수 있는 새롭고 최적화된 구성을 효과적으로 식별할 수 있습니다. 이러한 알고리즘은 프로세스를 자동화함으로써 방대한 수의 후보 아키텍처를 효율적으로 평가하고 비교할 수 있으며 궁극적으로 정확성, 속도 및 복잡성이 최적의 균형을 이루는 솔루션으로 수렴됩니다.

NAS(Neural Architecture Search)는 수동으로 설계된 아키텍처를 능가하는 더 나은 인공 신경망 개발을 자동화하기 위해 제안되었지만 수반되는 상당한 리소스 요구 사항으로 인해 비실용적인 것으로 간주되었습니다. 광범위한 컴퓨팅 리소스를 보유한 대기업만 NAS를 활용했기 때문에 대부분의 개발자가 NAS에 액세스할 수 없었습니다. AutoNAC는 비용 효율적이고 대규모로 작동할 수 있도록 새롭고 빠르고 컴퓨팅 효율적인 세대의 NAS 알고리즘을 실행하여 이 문제에 대한 솔루션을 도입했습니다.

AutoNAC 엔진은 하드웨어 및 데이터를 인식하며 컴파일러 및 양자화를 포함하여 추론 스택의 모든 구성 요소를 고려합니다.

YOLO-NAS를 만들기 위해 우리 연구팀은 10^14 가능한 아키텍처의 헤아릴 수 없는 검색 공간으로 시작했습니다.

우리의 AutoNAC 엔진은 이 검색 공간을 가로질러 우리가 "효율성 프론티어"라고 부르는 지역에 집중했습니다. AutoNAC는 대기 시간과 처리량의 균형을 가장 잘 맞추는 아키텍처를 검색하여 효율성 최전선을 탐색하고 매핑합니다. YOLO-NASS, YOLO-NASM 및 YOLO-NASL 아키텍처를 생성하기 위해 이 프론티어의 세 지점을 샘플링합니다.

우리의 데이터 기반 접근 방식은 전체 프로세스에 약 3800 GPU 시간이 소요되는 이 혁신적인 아키텍처의 발견을 가속화했습니다.

수동 개입 및 발명에 대한 의존도를 줄이면 다양한 애플리케이션을 위한 보다 효율적이고 강력하며 다재다능한 딥 러닝 모델을 개발할 수 있습니다.


NAS 프로세스 중에 양자화 인식 RepVGG 블록을 모델 아키텍처에 통합하여 모델 아키텍처가 PTQ(Post-Training Quantization)와 호환되도록 했습니다.


# 교육 세부 정보

YOLO-NAS의 다단계 교육 프로세스에는 Object365, COCO 의사 레이블 데이터, KD(Knowledge Distillation) 및 DFL(Distribution Focal Loss)에 대한 사전 교육이 포함됩니다.

이 모델은 각 에포크에 필요한 광범위한 시간으로 인해 25-40 에포크(모델 변형에 따라 다름) 동안 2백만 개의 이미지와 365개의 범주가 있는 포괄적인 데이터 세트인 Objects365에서 사전 훈련됩니다(각 에포크는 50-80분이 소요됩니다. 8 NVIDIA RTX A5000 GPU). COCO 데이터 세트는 의사 레이블 데이터를 생성하는 데 사용되는 추가 123k 레이블 없는 이미지를 제공합니다. <정확한 모델>은 이러한 이미지에 레이블을 지정하기 위해 COCO에서 교육을 받은 다음 원본 118k 기차 이미지로 모델을 교육하는 데 사용됩니다.

YOLO-NAS 아키텍처는 또한 KD(Knowledge Distillation) 및 DFL(Distribution Focal Loss)을 통합하여 교육 프로세스를 향상시킵니다.

손실 함수에 KD 항을 추가하여 지식 증류를 적용하여 학생 네트워크가 교사 네트워크의 분류 및 DFL 예측 모두의 로짓을 모방할 수 있도록 합니다. DFL은 학습 상자 회귀를 분류 작업으로 사용하고 상자 예측을 유한 값으로 이산화하고 이러한 값에 대한 분포를 예측한 다음 가중 합계를 통해 최종 예측으로 변환합니다.



# 양자화 인식 아키텍처

YOLO-NAS의 아키텍처는 최적화된 성능을 위해 양자화 인식 블록과 선택적 양자화를 사용합니다.

이 모델의 디자인은 대기 시간/처리량 개선과 정확도 손실 사이의 균형을 기반으로 특정 레이어에서 양자화를 건너뛰는 적응형 양자화를 특징으로 합니다. INT8 양자화 버전으로 변환할 때 YOLO-NAS는 양자화 중에 1-2mAP 포인트를 잃는 다른 모델에 비해 더 작은 정밀도 드롭(S, M 및 L 변형의 경우 mAP의 0.51, 0.65 및 0.45포인트)을 경험합니다. 이러한 기술은 뛰어난 개체 감지 기능과 최고 수준의 성능을 갖춘 혁신적인 아키텍처에서 절정에 이릅니다.

YOLO-NAS 아키텍처와 사전 훈련된 가중치는 지연 시간이 짧은 추론의 새로운 영역을 정의하고 다운스트림 작업을 미세 조정하기 위한 훌륭한 출발점을 정의합니다.




