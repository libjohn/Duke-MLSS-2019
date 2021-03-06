## Reinforcement Learning

Larry Carin - 2019, June 21

reinforcement learning is mean to address the challenge, or fact, that it is hard to acquire sufficient data for ML analysis.  _Alpha Go_ (e.g. see Netflix movie) brought RL back to the fore/attention of people's attention.  [Google DeepMind ](https://en.wikipedia.org/wiki/DeepMind).

**Problem**:  MRI is the highest state of the art for diagnosis but it's too expensive to apply to every patient.  RL can be a way of achieving a cost-effective trial-and-error to re-inforce the learning (develop a policy) how an agent (doctor) should learn.
**Goal**:  design a policy that achieves the best outcome at the lowest possible price. 
**Outcome** There are _M_ possible outcomes that the doctor can take

- clinical variables ('S') that affect the outcome but do not tell us everything about the state
- introduce a reward ('r') to associate the MD taking actions ('a') for a patient in state ('s'), and then the patiatient transisting to new sate of health s'  _r(s, a, s')_.  

what is the optimal thing for a doctor to do to maximize the **average** reward?.  
- policy has to be non-myopic (it has to think bout long term impact
to do this discritize the continuous range of action values into m bins
Q function Q(s, a) is an n x m matrix, denoting he value of taking action a whe in satate s
	objective is to **learn the Q** function
	**Q Learning**
	because the policy is **myopic** -- based on **immediate reward**,-- we will modify this with a temporal extension  .  This is done by adding an estimate of future reward..  gamma is a discount applied to reward factors.  This enables us to care more about the present than the future.  

ineresating question about the ethical implications of exploration v exploitation
- e-greedy
- if the outcome changes in a significant way, that outcome will change the policy
- with probability (epsilon), choose a subt + 1 at random

**Deep Q Networks** have an interesting characteristic where the right-hand side of the equation is **supervise learning **
---
## Generalization Error in Neural Netoworks
Hands-On Afternoon
Henry Pfister
- -

---
 DNN & CNN are essentially the same for this lecture.  In the 90s the prevailing wisdom was to never set error toward zero (why don't they overfit)

model complexity is roughly training time when it comes to picking the bias between overfitting and underfitting

### Rethinking Generalization

Figure taken from [ZBH+16]. Note: (a) uses Inception network
[ZBH+16] also shows 2n+d weights sufficient for n samples in d dimensions and connects NNs to kernel methods!

The above paper also studies (makes important the concept of) regularlization

models with _skip connections_ find the minima more smoothly -- and calls into question both layer complexity and gradient disscent concepts

in the bias trade-off (looking for an approximation of zero before the overfitting makes things worse).  In an under-parameeterized line-graph the risk gets wors with the over fitting.  But if you move beyond the overfitting by implementing over-parmeterized (modern interpolating regime) then the **duble descent risk curve* makes the risk got back towrds zero

What can we do with this

- lindear models (AS17) can explain this
- statistical physics will all this a "jamming" transition -- weights near the cusp inherit the random disposition
	- right past the cust there will be average bad behavior
	- but use an ensemble over multiple initialization (to average the bad behavior)
	- so averaging just past the cusp, then the performance (training to zero error) near zero is reached much quicker with minimal variance  -- this  is theoretical and it maybe doesn't scale to large networks

the future of this points to neural tangent kernels