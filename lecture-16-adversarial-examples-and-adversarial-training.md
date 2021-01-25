---
description: 14기 서아라
---

# \[Lecture 16\] Adversarial Examples and Adversarial Training

안녕하세요, 투빅스 14기 서아라입니다.

오늘 리뷰할 강의의  Adversarial Examples and Adversarial Training입니다.

아직 공부하는 단계이기도하고, 부족한 부분이 많아서 다소 맞지 않는 부분도 있을까 염려됩니다.

그래도 열심히 정리해보도록 하겠습니다. 도움이 되시길 바랍니다.



오늘 강의의 목차입니다.

우선 저희는 adversarial examples가 무엇인지에 대하여 배울 예정입니다.

그런 다음 그것이 왜 일어나는 지에 대하여 알아볼 것입니다.

그리고 그것이machine learning systems에서 어떤 위협을 주는지, 방어 대책은 있는지, 마지막으로 adversary가 없는 상황에서 adversarial examples들이 어떻게 machine learning의 성능을 향상시키는 지 등에 대하여 알아볼 것입니다.

Adversarial Examples를 설명할 때 가장 많이 쓰이는 이미지입니다.

사람은 너무 당연하게도 양 쪽의 사진이 모두 팬더라는 것을 압니다.

그러나 컴퓨터 같은 경우는 왼쪽의 사진에 가운데의 노이즈가 0.07의 비율로 포함된 오른쪽의 사진을 '긴코 원숭이'로 인식한다고 합니다.

놀랍게도, 팬더라고 인식했을 때\(57.7%\) 보다 더 높은 확신\(99.3%\)을 가지고 말입니다.

이와 같이 Adversarial attack이란 성능이 좋은 DNN을 이용한  Classifier들에 적대적 교란\(adversarial pertubation\)을 적용할 경우, 분류 알고리즘들이 쉽게 잘못된 분류를 할 수 있도록 하는 것을 의미합니다.



--4p 나중에 정리--



그동안 우리는 이러한 상황을 'over fitting'으로 설명해왔습니다.

말 그대로 한정된 데이터에 대하여 너무 많은 학습을 해버린 나머지, 우물안의 개구리가 되어 약간의 변형만 있어도 쉽게 다른 것으로 인식하게 되는 것으로 생각해왔다는 것입니다.



