# SARSA Epsilon-greedy CartPole-v0

**Name:** sarsa_epsilon_greedy_cartpole

**Date completed:**

**Description:** Baseline experiment

**Hypotheses:** N/A

**Prerequisites:** N/A

**Algorithms:** SARSA with Epsilon-greedy policy

**Environments:** CartPole-v0

**Specs:**
```json
{
  "sarsa_epsilon_greedy_cartpole": {
    "agent": [{
      "name": "SARSA",
      "algorithm": {
        "name": "SARSA",
        "action_pdtype": "default",
        "action_policy": "epsilon_greedy",
        "action_policy_update": "linear_decay",
        "explore_var_start": 1.0,
        "explore_var_end": 0.1,
        "explore_anneal_epi": 100,
        "gamma": 0.99,
        "training_frequency": 32
      },
      "memory": {
        "name": "OnPolicyBatchReplay"
      },
      "net": {
        "type": "MLPNet",
        "hid_layers": [64],
        "hid_layers_activation": "sigmoid",
        "clip_grad": false,
        "clip_grad_val": 1.0,
        "loss_spec": {
          "name": "MSELoss"
        },
        "optim_spec": {
          "name": "Adam",
          "lr": 0.01
        },
        "lr_decay": "rate_decay",
        "lr_decay_frequency": 500,
        "lr_decay_min_timestep": 1000,
        "gpu": true
      }
    }],
    "env": [{
      "name": "CartPole-v0",
      "max_timestep": null,
      "max_episode": 1000
    }],
    "body": {
      "product": "outer",
      "num": 1
    },
    "meta": {
      "max_session": 4,
      "max_trial": 100,
      "search": "RandomSearch",
      "max_generation": null
    },
    "search": {
      "agent": [{
        "algorithm": {
          "explore_anneal_epi__choice": [10, 30, 50, 100]
        },
        "net": {
          "hid_layers__choice": [
            [16],
            [64],
            [32, 16],
            [64, 32]
          ],
          "hid_layers_activation__choice": ["sigmoid", "relu", "tanh"],
          "optim_spec": {
            "lr__uniform": [0.0001, 0.2]
          }
        }
      }]
    }
  }
}
```

**Running instructions:** use the spec above

**Commit:** 454f620fce3e6fe2f87a91bffd74667d1f8a94f9

**Results summary:**
