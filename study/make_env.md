

# 독자 환경
- RTX 4080
- 드라이버 버전 - v536.67
# CUDAToolKit
[다운로드](https://developer.nvidia.com/cuda-downloads) 

이곳에서 다운받을경우 최신 버전이 다운받아진다. 11.8버전을 다운받아야 하므로 #Old 버전 여기서 다운받았다.

>독자는 윈도우 11환경에서 사용하기에 아래 옵션을 사용했다. 각자 맞는 환경을 선택해서 다운로드 받으면된다.

CUDA Toolkit 11.8 설치하자.(RTX 4080 기준)

- `Windows` 
- `x86_64` 
- `11` 
- `exe(local)`

>개발 환경에 따라 11.2 혹은 11.3버전을 다운받아야 함!!

### Old 버전 CUDA Toolkit 다운로드 받기

[다운로드](https://developer.nvidia.com/cuda-toolkit-archive)

여기서 11.8 버전을 다운받았다.
## 설치 환경 확인 방법

CMD 창에서 명령어`set`을 입력한다.

```
CUDA_PATH=C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v11.8
CUDA_PATH_V11_8=C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v11.8
Path=C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v11.8\bin;C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v11.8\libnvvp
```
위 명령어를 있으면 설치가 잘 된것이다.

# cuDNN
호환버전 cuDNN 8.9.4 설치하자.

호환버전확인 하러가기[클릭](https://docs.nvidia.com/deeplearning/cudnn/support-matrix/index.html)

CUDA Tookit 11.8버전이랑 호환되는 cuDNN버전은 8.9.4 확인
cuDNN 8.9.4는 Compute Compatibility=7.5와 호환되는 것 확인
cuDNN 8.9.4와 호환되는 드라이버 >=450.80.82 만족하는 것 확인

[cuDNN 다운로드](https://developer.nvidia.com/rdp/cudnn-download)

## 설치 방법 
다운 받은 zip파일을 풀었을 때 생성되는 폴더 3개(bin, lib, include)를
CUDA Toolkit 폴더에 동일한 폴더에 덮어 쓰기하면 됨.
CUDA Toolkit 폴더 위치 : `C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v11.8\`

# C/C++ 설치
[다운로드](https://visualstudio.microsoft.com/ko/vs/older-downloads/)
MS Visual Studio 설치해서 C/C++ 다운받자
어느 버전이든 상관없지만 독자는 2019 버전을 다운받음
- 데스크톱 및 모바일 (5)
	- .NET 데스크톱 개발 - 체크
	- C++를 사용한 데스크톱 개발 - 체크
	- 유니버설 Windows 플랫폼 개발 - 체크
- 설체 세부 정보 (추가 체크 해야 할 항목만 정리)
	- C++를 사용한 데스크톱 개발
		- v142 빌드 도구용 C++/CLI 지원(최신)
		- v142 빌드 도구용 C++ 모듈(x64/x86-실험적)
		- MSVC v141 - VS 2017 C++ x64/x86 빌드 도구(v14.16)
- 유니버설 Windows 플랫폼 개발
	- C++(v142) 유니버설 Windows 플랫폼 도구
	- C++(v141) 유니버설 Windows 플랫폼 도구
# 아나콘다 가상환경
## 설치

[다운로드](https://www.anaconda.com/download)

아나콘다를 다운받아서 설치를 한다.

## 가상환경 생성
``` Anaconda prompt
conda create --name {가상환경 이름} python=3.9
```
가상환경 파이썬 버전은 파이토치 버전이 지원하는 3.8-3.10 버전을 다운받아주면되지만 편의상 3.9버전을 다운받아준다.
## 가상환경 진입
```
conda activate {가상환경 이름}
```

!경고!
모든 가상환경은
`(실행시킨 가상환경 이름) conda install git`
앞에 가상환경 이름이 붙인 상태에서 환경 설치를 해야함
base 기본 환경이고 base 공간에 base 대신 내가 만든 가상 환경 이름이 적혀있으면 진입 성공
이게 진입 한 경우
# 환경 설치
## git 설치
``` conda
conda install git
```
## 파이토치
[파이토치 다운로드 하러가기 - 클릭](https://pytorch.org/get-started/locally/)

파이토치는 CPU 와 GPU 버전이 나뉘기 떄문에 여기 들어가서 명령어를 가져와서 다운받아준다.

## ultralytics YOLO
``` 
pip install ultralytics
```

## onnx 관련 패키지 설치
```
pip install onnx==1.12.0 onnxruntime onnx-simplifier
```

## requirements.txt 내에 리스트된 패키지 설치
```
pip install torch>=1.7 opencv_python loguru scikit-image tqdm torchvision>=0.10.0 Pillow thop ninja tabulate tensorboard lap motmetrics filterpy h5py
```

