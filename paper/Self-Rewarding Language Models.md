## Self-Rewarding Language Models (https://arxiv.org/abs/2401.10020)

[We posit that to achieve superhuman agents, future models require superhuman feedback in order to provide an adequate training signal.](https://arxiv.org/abs/2401.10020) 

Current approaches commonly train reward models from human preferences, which may then be bottlenecked by human performance level, and secondly these separate frozen reward models cannot then learn to improve during LLM training. 

In this work, we study Self-Rewarding Language Models, where the language model itself is used via LLM-as-a-Judge prompting to provide its own rewards during training. We show that during Iterative DPO training that not only does instruction following ability improve, but also the ability to provide high-quality rewards to itself. 

Fine-tuning Llama 2 70B on three iterations of our approach yields a model that outperforms many existing systems on the AlpacaEval 2.0 leaderboard, including Claude 2, Gemini Pro, and GPT-4 0613. While only a preliminary study, this work opens the door to the possibility of models that can continually improve in both axes.

현재의 접근 방식은 일반적으로 인간의 선호도에 기반한 보상 모델을 훈련시키는데, 이는 인간의 성능 수준에 의해 한계에 부딪힐 수 있으며, 또한 이러한 별도의 고정된 보상 모델은 LLM 훈련 중에 개선을 학습할 수 없습니다. 

본 연구에서는 언어 모델 스스로가 LLM-as-a-Judge 프롬프트를 통해 훈련 중 자체 보상을 제공하는 자가 보상 언어 모델(Self-Rewarding Language Models)에 대해 연구합니다. 
반복적인 DPO 훈련 중에 지시사항을 따르는 능력뿐만 아니라 자신에게 고품질 보상을 제공하는 능력이 향상됨을 보여줍니다. 

저희의 접근법을 세 차례 반복하여 Llama 2 70B를 미세 조정한 결과, AlpacaEval 2.0 리더보드 상에 있는 많은 기존 시스템들을 능가하는 모델이 탄생했으며, 여기에는 Claude 2, Gemini Pro, GPT-4 0613 등이 포함됩니다. 
이는 초기 연구에 불과하지만, 양쪽 축에서 지속적으로 개선될 수 있는 모델의 가능성에 대한 문을 열어줍니다.

