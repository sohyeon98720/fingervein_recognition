# 지정맥 인식 시스템 개발

### 졸업프로젝트(2020.09~2020.11)
--------
### description
기존 졸업프로젝트([U-NET을 이용한 지정맥영상 segmentation](https://github.com/sohyeon98720/deepLearning_UNET))에 이어서 <br> **보안시스템**에 활용될 수 있도록 **인식 시스템 개발** 과정을 추가함

```sh
<기존과정>
  - u-net알고리즘을 통한 학습
  - 테스트
<추가과정>
  - 세선화
  - 분기점 검출
```

-----------
### details of process
- 세선화
- 분기점 검출
------------
### result
|x_train|y_train|x_test|predict|thinning|bifurcation|
|:--:|:--:|:--:|:--:|:--:|:--:|
|원본|원본+정맥강조+이진화|원본|예측|세선화|분기점 검출|
