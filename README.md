# Reinforcement Learning self-play

As demonstrated by OpenAI. [Competitive Self-Play](https://openai.com/blog/competitive-self-play/)

# Project Cregan

The aim of this project is to train gameplay agents until they have superhuman ability. Then we can watch them play and in turn learn from their strategies.

## Kaggle Learn course code

Most of the connect four code is from this [Kaggle Learn course, Intro to Game AI and Reinforcement Learning](https://www.kaggle.com/learn/intro-to-game-ai-and-reinforcement-learning)

Running this code requires a GPU in practice. Training the agent (`model.learn(total_timesteps=80000)`) takes 15m with a GPU. Using a CPU would take 100-1000x times longer.

The connect four code from the Kaggle Learn course uses the PPO1 algorithm from the stable_baselines library. (`model = PPO1(CustomCnnPolicy, vec_env, verbose=0)`). [More info about PPO](https://openai.com/blog/openai-baselines-ppo/).

The libraries in this code are locked to old versions.

The code trains an agent using self-play against the "random move" agent, so it is overfit to beating that agent. Doing this properly will involve taking the winning agent, then training an agent against that one. And as it stands, it takes 15 minutes to run this once!

## Tips and tricks for using jupyter

### How to turn on a GPU in Google Colab

![Click Change runtime type](images/gpu1.png)
![Choose GPU](images/gpu2.png)

I didn't have any luck running that code in a Kaggle notebook. I had problems with dependencies and very slow running time.

I switched to Google Colab and turned on a GPU.

### Managing libraries in jupyter

In general, after installing libraries a user needs to restart a jupyter notebook. You can save time by running all of that code in a block at the top, then restarting.

To make the dependencies easier to manage, I put the `!pip install` and `!apt-get` code in the top code block. When you load this notebook for the first time, run these blocks, then restart your runtime.

![Click restart runtime](images/restart-runtime.png)

After restarting the runtime, all of the libraries should be available to load.
