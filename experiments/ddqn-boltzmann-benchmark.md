# DDQN Boltzmann Benchmark

This replaces the original Epsilon-greedy policy of DDQN with Boltzmann policy - the prob. dist. param output of the network is divided by a scalar called temperature; the higher the temperature, the more uniform the distribution becomes, and the sampling becomes more random. Over time, the temperature is lowered.