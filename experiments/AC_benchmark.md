# Actor Critic Benchmark

[Proposed by Konda and Tsitsiklis in 2003](http://www.mit.edu/~jnt/Papers/J094-03-kon-actors.pdf), Actor Critic is a method that uses an actor and a critic. The actor outputs parameters to sample the actions; the critic calculates the value for the policy loss.

TODO clear below; link original paper

**Name:** Actor Critic Benchmark

**Date completed:** 2018_02_04_013652, ongoing

**Description:** Standard Benchmark on Actor Critic

**Hypotheses:** N/A

**Prerequisites:** N/A

**Algorithms:** Actor Critic with Generalized Advantage Estimation, episodic training

**Environments:** CartPole-v0, Acrobot-v1

**Specs:** ("actor_critic.json", "actor_critic_benchmark")

**Running instructions:**
```json
{
  "actor_critic.json": {
    "actor_critic_benchmark": "benchmark"
  }
}
```

**Commit**: c4538fc9c6e6cd5f1fb91ba742d95225ca4ad4a1

**Results summary:**

data: ActorCritic_CartPole-v0_2018_02_04_013652
![](/assets/ActorCritic_CartPole-v0_experiment_graph.png)
![](/assets/ActorCritic_CartPole-v0_t21_s0_session_graph.png)
