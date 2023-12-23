# Discrete Batch-Constrained deep Q-Learning (BCQ)

Code for Batch-Constrained deep Q-Learning (BCQ) for discrete actions. Additionally, we include a full pipeline for training DQN in Atari. If you use our code please cite our [Deep RL workshop NeurIPS 2019 paper](https://arxiv.org/abs/1910.01708).

Repo is setup for Atari and toy tasks in [OpenAI gym](https://github.com/openai/gym). 
Networks are trained using [PyTorch 1.4](https://github.com/pytorch/pytorch) and Python 3.6. 

### Overview

To begin a behavioral policy (DQN) needs to be trained by running:
```
python main.py --train_behavioral
```

train_behavioralは行動方策（behavioral policy）の訓練を行う．これはデータセットを収集する際に使う方策であり，訓練後は学習した方策を保存する

This will save the PyTorch model. A new buffer can then be collected by running:
```
python main.py --generate_buffer
```

generate_bufferはデータセットの収集を行う．train_behavioralで訓練した行動方策を読み込んで収集する．ここでは行動方策の訓練はせず，得られたデータをバッファに追加していき，最後に保存するという処理を行う．

Finally train BCQ by running:
```
python main.py
```

Settings can be adjusted by changing the dicts in main.py. This is a reproduction of the code in the original paper, and results will not correspond exactly.

### Bibtex

```
@article{fujimoto2019benchmarking,
  title={Benchmarking Batch Deep Reinforcement Learning Algorithms},
  author={Fujimoto, Scott and Conti, Edoardo and Ghavamzadeh, Mohammad and Pineau, Joelle},
  journal={arXiv preprint arXiv:1910.01708},
  year={2019}
}
```
