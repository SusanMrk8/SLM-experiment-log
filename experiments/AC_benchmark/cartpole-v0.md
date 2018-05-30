# AC CartPole-v0

**Name:** ac_cartpole

**Date completed:**

**Description:** Baseline experiment

**Hypotheses:** N/A

**Prerequisites:** N/A

**Algorithms:** Actor Critic

**Environments:** CartPole-v0

**Specs:**
```json
{
  "ac_cartpole": {
    "agent": [{
      "name": "ActorCritic",
      "algorithm": {
        "name": "ActorCritic",
        "action_pdtype": "default",
        "action_policy": "default",
        "action_policy_update": "no_update",
        "explore_var_start": null,
        "explore_var_end": null,
        "explore_anneal_epi": null,
        "gamma": 0.99,
        "add_entropy": false,
        "entropy_weight": 0.01,
        "continuous_action_clip": 2.0,
        "training_frequency": 1,
        "training_iters_per_batch": 8,
        "use_GAE": false,
        "lam": 1.0,
        "num_step_returns": 100,
        "policy_loss_weight": 1.0,
        "val_loss_weight": 1.0
      },
      "memory": {
        "name": "OnPolicyReplay"
      },
      "net": {
        "type": "MLPseparate",
        "hid_layers": [64],
        "hid_layers_activation": "relu",
        "clip_grad": false,
        "clip_grad_val": 1.0,
        "use_same_optim": false,
        "actor_optim_spec": {
          "name": "Adam",
          "lr": 0.02
        },
        "critic_optim_spec": {
          "name": "Adam",
          "lr": 0.02
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
      "max_episode": 10
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
        "net": {
          "hid_layers__choice": [
            [16],
            [64],
            [32, 16],
            [64, 32]
          ],
          "hid_layers_activation__choice": ["sigmoid", "relu", "tanh"],
          "actor_optim_spec": {
            "lr__uniform": [0.0001, 0.2]
          },
          "critic_optim_spec": {
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
