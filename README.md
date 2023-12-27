### 개발 배경
AI 학습 데이터 셋을 조금더 쉽게 만들기 위해서 이 프로젝트를 진행함 
1. 라벨링 데이터셋을 조금더 빠르게 검증하기 위해 다른 폴더로 옮기는 기능을 추가함
2. 라벨링 작업을 조금 더 편리하게 하기는 SAM을 추가하는 방향으로 잡아서 기능을 추가함
#### 추후 개발 남은 기능
1. SAM 추론을 Tread로 진행하여 SAM 추론 진행시 프로그램이 멈추는 기능을 막고싶음
### 환경설치
- `파이썬 >= 3.8`
- `pytorch>=1.7`

[pytorch](https://pytorch.org/get-started/locally/) 설치하러 가기
- ※웬만하면 GPU 사용을 권장합니다
#### 환경설치:SAM
```
pip install git+https://github.com/facebookresearch/segment-anything.git
pip install opencv-python pycocotools matplotlib onnxruntime onnx
```
#### 환경설치:labelimg
```
pip install PyQt5
pip install lxml
pyrcc5 -o libs/resources.py resources.qrc
```
### SAM model
[여기](https://github.com/haruItG/labelImg_revision/blob/main/labelImg.py#L109)를 SAM 모델 별로 변경해주세여합니다.
```python
self.sam = SA(model_name="모델 유형", model_path="모델경로")
```
#### 기본 예시
``` python
self.sam = SA(model_name="vit_b", model_path="sam_vit_b_01ec64.pth")
```
#### SAM 모델 종류
| 모델 유형 | 다운로드 링크 |
| :--: | :--: |
| vit_h | [ViT-H SAM model.](https://dl.fbaipublicfiles.com/segment_anything/sam_vit_h_4b8939.pth) |
| vit_l | [ViT-L SAM model.](https://dl.fbaipublicfiles.com/segment_anything/sam_vit_l_0b3195.pth) |
| vit_b | [ViT-B SAM model.](https://dl.fbaipublicfiles.com/segment_anything/sam_vit_b_01ec64.pth) |
### 단축키
| 단축키 | 설명 |
| :--: | :--: |
| Shift + Space bar | SAM 추론 진행 |
| Enter | 옮길 폴더로 옮기기 |

### SAM 추론 방법
- W키를 눌러서 CREATE 모드로 진입한다 
- Q키를 눌러서 SAM 모드로 진입한다
- 마우스 왼쪽 클릭시 초록색 원이 생성된다
- 마우스 오른쪽 클릭시 빨강색 원이 생성된다
  - 왼쪽 하단에 SAM List 아이템 더블 클릭시 원 삭제
- Shift + Space 를 누르면 즉시 추론을 진행한다.
  - 이때 추론 진행되는동안 잠시 프로그램이 멈춘다.
- 라벨링 박스가 생성된다
- 이때 부터는 [labelimg](https://github.com/HumanSignal/labelImg)사용방법과 동일하다.


![SAM 추론 모습](https://github.com/haruItG/labelImg_revision/blob/main/study/ezgif.com-resize.gif)


### Reference
- [labelimg](https://github.com/HumanSignal/labelImg)
- [AutoLabel](https://github.com/qpal147147/AutoLabel)
- [segment-anything](https://github.com/facebookresearch/segment-anything)
