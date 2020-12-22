# \[Lecture 14\] Deep Reinforcement Learning

## CS231n 14강 리뷰

14강은 강화학습에 대해 알아본다.

![](.gitbook/assets/cs231n_lecture14_ljeun_page-0001.jpg)

## Reinforcement Learning \(강화학습\)

![](.gitbook/assets/cs231n_lecture14_ljeun_page-0003.jpg)

**Reinforcement Learning\(강화학습\)**은 **agent**가 최대 **reward**를 받을 수 있는 **action**을 취하도록 학습 시키는 것을 목적으로 한다. 이는 달리 말하면 최적의 **정책 함수\(policy\)**를 찾는 것과 같은 의미이다.

![](.gitbook/assets/cs231n_lecture14_ljeun_page-0004.jpg)

![](.gitbook/assets/cs231n_lecture14_ljeun_page-0005.jpg)

강화학습을 설명하기 위해 필요한 중요한 용어들이 있다.

**state\(상태\)**는 agent가 action을 선택하기 위해 받는 정보를 의미한다. 각 **agent\(주체\)**는 environment에서 action을 취하는 주체이며, **action**은 agent가 특성 state에서 취할 수 있는 행동을 말한다. 각 agent가 action을 취하면 reward\(보상\)을 받게 된다. 이 모든 것들이 일어나는 배경을 **environment\(환경\)**이라고 한다. 

agent가 특정 state에서 어떤 action을 취할지 골라주는 함수를 **policy\(정책\)**이라고 하며, 시작부터 종료까지 agent가 거친 일련의 \(state, action, reward\) 시퀀스를 **episode\(에피소드\)**라고 한다.

![](.gitbook/assets/cs231n_lecture14_ljeun_page-0006.jpg)

environment는 agent의 action에 따라 reward를 제공하고, 다음 state를 부여한다.

위 과정은 종료 상태가 될 때까지 즉, 하나의 에피소드가 끝날 때까지 반복된다.

![](.gitbook/assets/cs231n_lecture14_ljeun_page-0007.jpg)

다음은 강화학습의 예시이다.

각각 막대기를 세우거나, 로봇을 움직이거나, 높은 점수를 받거나, 게임에서 이기는 등의 목적을 갖고 있는 강화학습이다.

## Markov Decision Process \(MDP\)

![](.gitbook/assets/cs231n_lecture14_ljeun_page-0008.jpg)

**Markov Decision Process\(MDP\)**는 강화학습 문제를 수식화한 것다. 

**Markov Property**는 현재가 주어졌을 때,  과거와 미래는 독립인 t+1번째 state는 오로지 t번째의 state에만 의존하는 것을 의미한다. MDP는 Markov Property를 만족하고, 이는 \(S, A, R, P, r\)로 정의한다.

이 중 **P**는 **transition probability**로 특정 state에서 다음 번에 도달할 state들의 확률 분포를 의미한다.  
**r**은 **discount factor**로 미래의 가치를 현재 가치로 환산하는 것이다. 이는 같은 reward라면 빨리 얻는 것이 좋다는 것을 내포하고 있다.

![](.gitbook/assets/cs231n_lecture14_ljeun_page-0009.jpg)

위에서 본 강화학습 과정을 MDP를 통해 표현하면 다음과 같다.

![](.gitbook/assets/cs231n_lecture14_ljeun_page-0010.jpg)

간단한 MDP의 예시로 Grid World가 있다.  
Grid World는 시작 지점에서 끝 지점까지 최소한의 움직임으로 도달하는 것을 목표로 한다. 



![](.gitbook/assets/cs231n_lecture14_ljeun_page-0011.jpg)

Stochastic Policy는 ****2가지로 나눌 수 있다. **Random Policy**는 모든 action이 같은 확률을 가지는 경우이다. Optimal Policy 학습을 통해 얻은 정책으로, 얼마나 종료 지점에 가깝에 이동할 수 있는지에 따라 다른 확률을 가진다.

### Optimal Policy pi\*

![](.gitbook/assets/cs231n_lecture14_ljeun_page-0012.jpg)

MDP를 정의하면 **최적의 정책 pi\***을 찾아야 하는데, 이는 reward의 합을 최대로 만드는 정책을 의미한다.

실제 초기 상태를 샘플링할 때, 전이 확률 분포 등에서는 다음 상태가 확률적이다. 이러한 randomness를 다루기 위해서 **reward의 합의 기댓값을 최대화**하여 최적의 정책 pi\*를 계산하게 된다.

### Value Function & Q-value Function

![](.gitbook/assets/cs231n_lecture14_ljeun_page-0013.jpg)

최적의 정책을 찾기 위해 사용되는 몇 가지 정의가 존재한다. 정책에 따라 각 에피소드를 수행하면, \(_s0, a0, r0, s1, a1, r1, ..._\)와 같은 경로를 얻게 되는데, 이를 사용하여 정의한다.

**Value Function**은 _'현재 속해있는 상태가 얼마나 좋은가?'_ 에 대한 값을 나타내는 것으로, **상태 s**와 **정책 pi**가 주어졌을 때, **누적된 보상의 기댓값**을 의미한다. 

Q-value Function은 _'현재 속해있는 상태에서 어떤 행동을 취해야 좋은가?'_ 를 의미한다. 이는 **상태 s**와 **정책 pi** 그리고 **행동 a**가 주어졌을 때 받을 수 있는 **누적된 보상의 기댓값**이다. 

![](.gitbook/assets/cs231n_lecture14_ljeun_page-0014.jpg)

최적의 정책 pi\*로부터 나온 최적의 정책 함수 **Q-value Function Q\***는 **Bellman equation**\(벨만 방정식\)을 만족한다. 즉, 벨만 방정식은 최적의 정책 함수를 찾는 가장 기본적인 방법이다.

따라서 벨만 방정식을 따르는 최적의 정책 함수 수식은 위와 같다.

![](.gitbook/assets/cs231n_lecture14_ljeun_page-0015.jpg)

**Q\***는 **어떤 행동을 취했을 때 미래에 받을 보상의 최대치**를 의미한다. 

다음 **Q\*\(state, action\)**를 구할 때, 현재 Q\*\(state, action\)를 안다면 이를 통해서 다음 상태에서 최상의 행동을 취할 수 있는 최적의 정책을 구할 수 있다. 여기서 말하는 **최적의 정책은 r+rQ\*\(s',a'\)의 기댓값을 최대화하는 행동을 취하는 것**이다.

벨만 방정식을 만족하는 최적의 정책을 푸는 방법에는 **Value Iteration**과 **Policy Iteration**이 있다. 

![](.gitbook/assets/cs231n_lecture14_ljeun_page-0016.jpg)

**Value Iteration**은 **벨만 방정식을 사용해 각 step마다 Q를 조금씩 최적화**하는 방법이다. 따라서 i가 무한대라면 최적의 정책 함수인 Q\*로 수렴하게 된다.

이를 구하는 과정에서 반복적인 업데이트를 위해 모든 Q\(s,a\)를 계산해야 한다. 기본적으로 전체 상태 공간은 매우 커서 계산하는 것이 사실상 불가능하기 때문에, neural network 등의 방법으로 Q\(s,a\)를 근사시켜 추정하게 된다.

![](.gitbook/assets/cs231n_lecture14_ljeun_page-0017.jpg)

앞서 말했듯이 **action-value function 추정을 위해 함수를 근사**시키게 되는데, 이 과정에서 deep neural network를 사용하고, 이를 **deep Q-Learning**이라고 한다.

Q-function은 벨만 방정식을 따르기 때문에, 식은 위와 같고 학습은 아래와 같이 진행된다.

![](.gitbook/assets/cs231n_lecture14_ljeun_page-0018.jpg)

**Foward Pass**의 loss 함수 Q-function 값과 벨만 방정식의 차이이다. 실제 학습 시 loss가 작아지도록, **두 차이가 최소가 되도록** 학습을 진행한다. 이 과정을 반복하며  Q가  Q\*에  가까워지도록  학습시 다.

**Backward Pass**는 **계산한 loss를 바탕으로 파라미터인 theta 업데이트**를 진행한다.

![](.gitbook/assets/cs231n_lecture14_ljeun_page-0019.jpg)



![](.gitbook/assets/cs231n_lecture14_ljeun_page-0020.jpg)

![](.gitbook/assets/cs231n_lecture14_ljeun_page-0021.jpg)

![](.gitbook/assets/cs231n_lecture14_ljeun_page-0022.jpg)

![](.gitbook/assets/cs231n_lecture14_ljeun_page-0023.jpg)

![](.gitbook/assets/cs231n_lecture14_ljeun_page-0024.jpg)

![](.gitbook/assets/cs231n_lecture14_ljeun_page-0025.jpg)

![](.gitbook/assets/cs231n_lecture14_ljeun_page-0026.jpg)

![](.gitbook/assets/cs231n_lecture14_ljeun_page-0027.jpg)

![](.gitbook/assets/cs231n_lecture14_ljeun_page-0028.jpg)

![](.gitbook/assets/cs231n_lecture14_ljeun_page-0029.jpg)

![](.gitbook/assets/cs231n_lecture14_ljeun_page-0030.jpg)



![](.gitbook/assets/cs231n_lecture14_ljeun_page-0031.jpg)

![](.gitbook/assets/cs231n_lecture14_ljeun_page-0032.jpg)

![](.gitbook/assets/cs231n_lecture14_ljeun_page-0033.jpg)

![](.gitbook/assets/cs231n_lecture14_ljeun_page-0034.jpg)

![](.gitbook/assets/cs231n_lecture14_ljeun_page-0035.jpg)

![](.gitbook/assets/cs231n_lecture14_ljeun_page-0036.jpg)





{% file src=".gitbook/assets/cs231n\_lecture14\_ljeun.pdf" caption="CS231n\_lecture14\_ljeun.pdf" %}



