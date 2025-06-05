# POLICY EVALUATION

## AIM
To develop a Python program to evaluate the given policy.

## PROBLEM STATEMENT
To find best policy from two policies which are defined by user using policy evaluation function. Where the mdp includes 16 states from 0-15, 0 is the starting state, assigning some 4 random state as holes and 15 is the goal state and then we need to calculate optimal state value function for each state such that we can reach goal using optimal policy using policy evaluation.
## POLICY EVALUATION FUNCTION
```python
def policy_evaluation(pi, P, gamma=1.0, theta=1e-10):
    prev_V = np.zeros(len(P), dtype=np.float64)
    # Write your code here to evaluate the given policy
    while True:
      V = np.zeros(len(P))
      for s in range(len(P)):
        for prob, next_state, reward, done in P[s][pi(s)]:
          V[s] += prob * (reward + gamma *  prev_V[next_state] * (not done))
      if np.max(np.abs(prev_V - V)) < theta:
        break
      prev_V = V.copy()
    return V
```
## OUTPUT:
### POLICIES
![449760695-adc0d7ff-2c33-4531-aa07-455e1b194ad2](https://github.com/user-attachments/assets/e0155004-0ba1-4723-9abb-3436ebfbdd30)


### STATE VALUE FUNCTION
![449760868-9f338471-7f9d-4db4-b177-ec850bb37705](https://github.com/user-attachments/assets/66dc2e9d-cdc3-464e-9547-7f66320c9733)

### BEST POLICY

![449761029-ee90e193-3ceb-4ab7-ae41-d435b996ac85](https://github.com/user-attachments/assets/00ee7840-d697-4c73-bccf-a12fa0d9ca04)


## RESULT:

Thus, The Python program to evaluate the given policy is successfully executed.
