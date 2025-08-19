⚾ 야구공 파울/페어 판정 프로젝트

이 프로젝트는 Google Colab 환경에서 YOLOv8 + Kalman Filter를 활용하여  
투구 또는 타구 궤적을 추적하고, 한화이글스파크 기준 좌/우 폴과 비교해  
파울 여부를 자동 판정하는 시스템입니다.


🚀 실행 방법

1. Colab에서 노트북 열기
   - `PitcherBallTracking_py.ipynb`를 Google Colab에서 실행합니다.

2. 영상 파일 준비
   - 분석하고 싶은 야구 타격 영상을 pitch.mp4라 이름을 지어 아래와 같이 content 폴더에 넣어줍니다.
  📂 프로젝트 구조
  ├── PitcherBallTracking_py.ipynb # 메인 Colab 노트북
  ├── content/
  │ └── pitch.mp4 


3. YOLO 모델 다운로드
   - Colab 실행 시 `ultralytics` 라이브러리에서 `yolov8s.pt` 모델이 자동으로 로드됩니다.

4. 코드 실행 
   - 모든 셀을 순서대로 실행하면, `content/pitch.mp4`가 입력으로 처리되고  
     `pitch_foul_predict.mp4` 결과 영상이 생성됩니다.


⚙ 주요 기능
- YOLOv8 기반 공 검출 
  : 영상에서 baseball class만 추적  
-  흰 공 전용 필터링
  : 색상/원형성 검사로 오탐 최소화  
-  Kalman Filter 추적
  : 공이 가려져도 궤적 예측 유지  
-  파울 판정 
  : 야구장에 설치된 좌/우 파울 폴 각도를 기준으로 궤적 발사각 비교  


📌 참고 사항
- 분석 영상은 반드시 `content/pitch.mp4` 경로에 위치해야 합니다.  
- 큰 용량의 영상은 GitHub에 올리기보다는 Google Drive와 Colab 연동을 추천합니다.  
- 출력 결과(`pitch_foul_predict.mp4`)는 Colab 실행 환경에 저장되며, 필요시 Google Drive로 복사하세요.  

---

 🏟 적용 구장
- 좌/우 폴 각도는 한화이글스파크 구장 기준으로 설정되어 있습니다.  
- 필요시 다른 구장에 맞게 좌표/각도를 수정 가능합니다.  
