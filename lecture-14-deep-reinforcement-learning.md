# \[Lecture 14\] Deep Reinforcement Learning

## CS231n 14강 리뷰



![](.gitbook/assets/cs231n_lecture14_ljeun_page-0001.jpg)

![](.gitbook/assets/cs231n_lecture14_ljeun_page-0002.jpg)

## Reinforcement Learning \(강화학습\)

![](.gitbook/assets/cs231n_lecture14_ljeun_page-0004.jpg)

![](.gitbook/assets/cs231n_lecture14_ljeun_page-0005.jpg)

Reinforcement Learning에는 몇 가지 중요한 용어들이 있다.

state\(상태\)는 agent가 action을 선택하기 위해 받는 정보를 의미한다. 각각 agent\(주체\)는 environment에서 action을 취하는 주체이며, action은 agent가 특성 state에서 취할 수 있는 행동을 말한다. 각 agent가 action을 취하면 reward\(보상\)을 받게 된다. 이 모든 것들이 일어나는 배경을 environment\(환경\)이라고 한다. 

agent가 특정 state에서 어떤 action을 취할지 골라주는 함수를 policy\(정책\)이라고 하며, 시작부터 종료까지 agent가 거친 일련의 \(state, action, reward\)들을 episode라고 한다.

![](.gitbook/assets/cs231n_lecture14_ljeun_page-0003.jpg)

즉, Reinforcement Learning\(강화학습\)은 agent가 최대 reward를 받을 수 있는 action을 취하도록 학습시키는 것을 목적으로 한다. 이는 달리 말하면 최적의 정책 함수\(policy\)를 찾는 것과 같은 의미이다.

![](.gitbook/assets/cs231n_lecture14_ljeun_page-0006.jpg)

강화학습의 과정은 다음과 같다.

\(추가해야함\)

![](.gitbook/assets/cs231n_lecture14_ljeun_page-0007.jpg)

강화학습의 예시이다.

## Markov Decision Process \(MDP\)

![](.gitbook/assets/cs231n_lecture14_ljeun_page-0008.jpg)

Markov Decision Process\(MDP\)는 강화학습 문제를 수식화한 것이다.

![](.gitbook/assets/cs231n_lecture14_ljeun_page-0009.jpg)

![](.gitbook/assets/cs231n_lecture14_ljeun_page-0010.jpg)

![](.gitbook/assets/cs231n_lecture14_ljeun_page-0011.jpg)

![](.gitbook/assets/cs231n_lecture14_ljeun_page-0012.jpg)

![](.gitbook/assets/cs231n_lecture14_ljeun_page-0013.jpg)

![](.gitbook/assets/cs231n_lecture14_ljeun_page-0014.jpg)

![](.gitbook/assets/cs231n_lecture14_ljeun_page-0015.jpg)

![](.gitbook/assets/cs231n_lecture14_ljeun_page-0016.jpg)

![](.gitbook/assets/cs231n_lecture14_ljeun_page-0017.jpg)

![](.gitbook/assets/cs231n_lecture14_ljeun_page-0018.jpg)

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



