시각적 자극을 CS로 사용하여 AutoShaping analysis를 진행했다. 두 마리의 쥐를 각각 trained group과 control group으로 나누었다. Trained group은 Pavlovian learning이 이루어질 수 있도록 CS+와 reward를 pairing하여 9일 동안 매일 30분간 training 했다. Control group은 CS+와 reward를 pairing 하지 않고 reward를 random으로 지급하였다. 이때 대조군으로 CS+와 함께 CS-를 사용하였다. 결과적으로 training group는 10초간 visually CS+ presentation 하고 이후 CS+가 꺼지면 reward를 지급하였고, 10초간 CS- presentation 하고 이후 CS-가 꺼지면 reward를 지급하지 않았다. Control group은 CS+와 CS-를 똑같이 random하게 제시하였으나 reward를 지급하지 않았다. 위와 같이 조교님이 촬영하신 쥐의 1일차, 4일차, 7일차, 9일차 영상을 토대로 분석하였다. 



Python의 time, pyautogui, PIL의 ImageGrab, openpyxl의 Workbook, math와 같은 library를 사용하여 쥐의 행동을 ethogram으로 분석하는 pipeline을 만들었다. pipeline에서는 쥐의 위치와 stimulus CS+와 CS-의 presentation 유무, RM(Reward magazine)불빛의 presentation 유무를 원하는 시간 간격(t,본 실험에서는 1초 간격으로 설정)으로 확인하고 엑셀에 기록한다. 쥐의 위치는 Sign tracking과 Goal tracking activity를 확인하기 위해 CS+와 CS-가 presentation되었을 때 RM근처에 머무는 시간, CS+와 CS-가 presentation되었을 때 각각 CS+나 CS-에 머무는 시간을 확인했다. 화면을 t초 간격으로 capture해서 해당 좌표의 픽셀의 색이 알려진 쥐의 색과 유사한지 거리를 측정하였고, 일정 threshold 이하라면 해당 픽셀이 쥐를 나타낸다고 판단했다. 하나의 픽셀만 사용한다면 우연한 밝기의 차이로 해당 픽셀이 쥐를 나타낼 수도 있었기 때문에 RM 근처의 쥐의 유무는 8개의 픽셀을 사용해서 그 중 2개 이상이 쥐를 나타낸다면 RM에 쥐가 존재한다고 판단했다. CS+와 CS- 근처의 쥐의 유무는 6개의 픽셀을 사용하였고 2개 이상이여야 쥐가 존재한다고 판단했다. CS+와 CS-, RM presentation유무는 2개의 픽셀을 사용하였고 그 중 하나라도 불빛을 나타내면 presentation되었다고 판단했다. 

와! 
