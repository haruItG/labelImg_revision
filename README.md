labelimg 수정본입니다.
원본 코드는 [출처](https://github.com/HumanSignal/labelImg) 입니다

### 환경설치
---
- `파이썬 >= 3.8`
- `pytorch>=1.7`
---
#### 환경설치:SAM
---
```
pip install git+https://github.com/facebookresearch/segment-anything.git
```
#### 환경설치:labelimg
---
```
conda install pyqt=5
conda install -c anaconda lxml
pyrcc5 -o libs/resources.py resources.qrc
python labelImg.py
```
### SAM model
---
이 부분 다운받은 모델 별로 설정 해주셔야 합니다.
```python
self.sam = SA(model_name="vit_b", model_path="sam_vit_b_01ec64.pth")
```

- **`default` or `vit_h`: [ViT-H SAM model.](https://dl.fbaipublicfiles.com/segment_anything/sam_vit_h_4b8939.pth)**
- `vit_l`: [ViT-L SAM model.](https://dl.fbaipublicfiles.com/segment_anything/sam_vit_l_0b3195.pth)
- `vit_b`: [ViT-B SAM model.](https://dl.fbaipublicfiles.com/segment_anything/sam_vit_b_01ec64.pth)
### 단축키
| 단축키 | 설명 |
| :--: | :--: |
| Shift | SAM 추론 진행 |
| Enter | 옮길 폴더로 옮기기 |

### SAM 추론 방법
- W키를 눌러서 CREATE 모드로 진입한다 
- Q키를 눌러서 SAM 모드로 진입한다
- 마우스 오른쪽 클릭시 초록색 원이 생성된다
- 마우스 왼쪽 클릭시 빨강색 원이 생성된다
- Shift + Space 를 누르면 즉시 추론을 진행한다.
  - 이때 추론 진행되는동안 잠시 프로그램이 멈춘다.
- 이때 부터는 [labelimg](https://github.com/HumanSignal/labelImg)사용방법과 동일하다.


### Reference
---
[labelimg](https://github.com/HumanSignal/labelImg)
[AutoLabel](https://github.com/qpal147147/AutoLabel)
[segment-anything](https://github.com/facebookresearch/segment-anything)
