# Chapter 3: Finite Markov Decision Processes
## 1. Ex3.7 (on page 44)
Is my solution correct? (for understanding of episodic task and continuing task)
### Question
Suppose you treated pole-balancing as an episodic task but also used discounting, with all rewards zero except for −1 upon failure. What then would the return be at each time? How does this return differ from that in the discounted, continuing formulation of this task?

### Solution
Let $K$ be the number of time steps before failure.\
For episodic task:
$$\begin{aligned}
G_t &= R_{t+1} + \gamma R_{t+2} + \gamma^2 R_{t+3} + ... + \gamma^K R_{t+k+1} =0 + 0 + 0 + ... + \gamma^K (-1)=-\gamma^K
\end{aligned}
$$

For continuing formulation of this task:
$$\begin{aligned}
G_t &= R_{t+1} + \gamma R_{t+2} + \gamma^2 R_{t+3} + ... + \gamma^K R_{t+k+1} + .... =0 + 0 + 0 + ... + \sum_{i=K}^{\infin} \gamma^i (-1) =-\gamma^K\frac{1}{1-\gamma}
\end{aligned}
$$

# Chapter 4: Dynamic Programming
## 1. page 60 about *expected update*
Why is this kind of operation called *expected update*? Is it becase this updat is based on some expectation according to certain policy? And what is sample next state, is this related to Monte Carlo Methods where policy is not needed during update?

## 2. Ex 4.4 (page 65)
### Question
The policy iteration algorithm given on this page has a subtle bug in that it may never terminate if the policy continually switches between two or more policies that are equally good. This is ok for pedagogy, but not for actual use. Modifiy the pseudocode so that convergence is guaranteed.
### Proposed Solution
let the actions chosen be a set of all possible best actions rather one arbitrary best action. \
Query: Is this the correct thinking direction?

## 3. page 69 about convergence of asynchrnous DP
"(In the undiscounted episodic case, it is possible that there are
some orderings of updates that do not result in convergence, but it is relatively easy to avoid these.)"\
what are these orderings, and how can they be avoided?

Some related queries about convergence: \
For more general case, does policy iteration / value iteration algorithms converge? will they find the optimal solution or possibly only a suboprimal solution? Since for every step only an improvement is guaranteed?\
On page 68, "All of these algorithms converge to an optimal policy for discounted finite MDPs", how to prove this? \
on page 72, "In some cases, GPI can be proved to converge, most notably for the
classical DP methods that we have presented in this chapter. In other cases convergence has not been proved, but still the idea of GPI improves our understanding of the methods."

## 4. page 71 
"Expected updates are closely related to Bellman equations: they are little more than these equations turned into assignment statements." \
what is this "little more"? expectation based on policy instead of choosing the max? \
e.g. Bellman optimality equation\
$v_*(s) = \max_a \mathbb{E}[R_{t+1} + \gamma v_* (S_{t+1}) | S_t = s, A_t = a]$
epeccted update:\
$v_{k+1}(s)= \mathbb{E}_\pi [R_{t+1} +\gamma v_k (S_{t+1})| S_t = s, A_t = a]$


