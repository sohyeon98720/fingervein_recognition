# 손가락 정맥 인식 시스템 개발

### 졸업프로젝트(2020.09~2020.11)
--------
### description
기존 졸업프로젝트([U-NET을 이용한 손가락 정맥영상 segmentation](https://github.com/sohyeon98720/deepLearning_UNET))에 이어서 <br> **보안시스템**에 활용될 수 있도록 **인식 시스템 개발** 과정을 추가함

```sh
<기존과정>
  - u-net알고리즘을 통한 학습
  - 테스트
<추가과정>
  - 세선화
  - 분기점 검출
```

-----------
### details of each process
- 세선화
    - 전경에 해당하는 물체의 표면을 벗겨 최종적인 두께가 1픽셀이 되도록 만드는 것
    - zhang-suen알고리즘 사용
    - [참고자료-상세설명](http://blog.daum.net/ontologicallearning/6545339)
- 분기점 검출
  ```sh
  <기존방식> 전경픽셀을 기준으로 주변 8화소를 검사하여
             전경픽셀이 존재하는 개수를 카운트하여 3개 이상이면 분기점으로 판단
  
   <문제점>  대각선의 경우 1픽셀이 아닌 2픽셀(지그재그형태)로 이루어져
             이 과정에서 분기점을 정확하게 검출하지 못함
  
  <개선방식> 전경픽셀을 기준으로 주변 8화소를 시계방향으로 검사하여
             이웃한 픽셀이 전경->배경 횟수를 카운트하여 3개 이상이면 분기점으로 판단
  ```

------------
### result
|x_train|y_train|
|:--:|:--:|
|![image](https://user-images.githubusercontent.com/47767202/101986472-519ce400-3cd1-11eb-9a43-040be2b1606d.png)|![image](https://user-images.githubusercontent.com/47767202/101986486-68433b00-3cd1-11eb-868e-9836d9afd1e4.png)|
|원본|원본+정맥강조+이진화|
<br>

x_test|predict|thinning|bifurcation|
|:--:|:--:|:--:|:--:|
![image](https://user-images.githubusercontent.com/47767202/101986504-7d1fce80-3cd1-11eb-986d-b8c5078192d9.png)|![image](https://user-images.githubusercontent.com/47767202/101986512-8741cd00-3cd1-11eb-82d2-e4e11ee1d45f.png)|![image](https://user-images.githubusercontent.com/47767202/101986524-988ad980-3cd1-11eb-9723-1d16591392f5.png)|![image](https://user-images.githubusercontent.com/47767202/101986528-a17bab00-3cd1-11eb-8405-de2b4d87f9dd.png)|
|원본|예측|세선화|분기점 검출|


--------------
### paper submission
Finger vein image enhancement using U-Net <br>
ICNCT 2021 Session H : Bio/Health Converge  
http://www.i-inca.org/

