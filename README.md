# Multi-Armed-Bandit-Problem
Python implementation and observation results for different algorithms in k - Armed Bandits Problem
Implemented algorithm first is the epsilon-greedy algorithm, where the bandit with highest action value is selected (1-epsilon) times and a random bandit is selected epsilon times. Increasing the value of epsilon increases exploration, but decreases exploitation. The below image clearly shows the difference-
![Epsilon - Greedy](https://github.com/SuperSadiq1234/Multi-Armed-Bandit-Problem/blob/master/BanditsA2.png)

 To implement this in Bandits.py, tweak with the value of the variable epsilon2

Initially, \epsilon = 0.01 performs worse as it hasn't explored every bandit yet. But over time, it performs better than \epsilon = 0.1, as it selects the best bandit only 91% of the time.




Another way to make the algorithm better is to implement Optimistic Initial Values Algorithm by taking-
temp_Q2 = np.zeros(num_band) + 10
This makes sure exploration is done before exploitation. Now combining Optimistic Initial Values and \epsilon = 0.01, we get-
![Epsilon - Greedy with Optimistic Initial Values](https://github.com/SuperSadiq1234/Multi-Armed-Bandit-Problem/blob/master/BanditsB2.png)

Clearly, now the \epsilon=0.01 performs better than \epsilon=0.1 from the start
To implement this algorithm, add a number to the zero vector temp_Q. Tweak with the value of the number. The graph above is for temp_Q2 += 10




Another algorithm that can be used is exponential recency weighted average, which gives more preference to latest values, rather than older values. Non- Stationary problems work better with this algorithm, but worse than \epsilon - greedy on stationary problems. Here is an implementation of it on a stationary problem-
![Exponential Recency Weighted Average](https://github.com/SuperSadiq1234/Multi-Armed-Bandit-Problem/blob/master/BanditsC2.png)

As this was a static problem, it performs far worse than our first algorithm
