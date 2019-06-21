Machine Learning Summer School:  Day 1
2019, June 17

David Carlson (lecture)

## Deep Learning

- understand **shallow network** before understanding **deep learning**
	- "learn a predictive model based on labeled data"
	- want to predict y from x (need an algorithm that is based on a training set (i.e. historical data)
	- one method to do this is a **linear predictive model **
		- only need to know if the prediction will be a positive or negative outcome
		- "probability that the outcome if positive"
		- **logistic Regression**
			- a network formulation
			- **gives the probability of a positive outcome**
			- a **complete simple shallow network**
				- **Example**
					- **A** predicting the weather (will it rain today?)
					- Need to build a **training set** which indicates we have **historical data** (i.e. training data)
						- (a) is it cloudy and (b) what is the outcome (did it rain or not)
						- see slide (**Learning Model Parameters**)  ((this is a shallow netowork))
					- **B** recognizing digits **MNIST** dataset
						- Vectorization = making a 2 dimensional array into a vector
			- Generalizing Logistic Regression
				- how to move from shallow to to deep
				- in the problem of identifying the red dots from the blue dots
				- need a non-linear classifier
				- Can use multiple filters to clarify which subset filter matches the type of 4 someone might write (what is a average 4?) 
				- number of (k) filters looks for each different sub-types
				- going **deeper** with additional layers of "latent processes" (this is an example of building networks)
				- This is a **multilayer Perceptron** (introduced in 1960 -- the most *fundamental network of a deep learning system*
				- Can use this is learn non-linear classification
				- Do we **always** want to **increase complexity?**
					- depends on goal (e.g. overfitting)
-------

break

------

## How do we learn a Deep Model?

Goal

- learn parameters that yield best performance
- how do we define performance
- Thus **Empirical Risk Minimization**  (ERM)  
	- define a **loss  function** 
	- take  a **true** value and a **prediction**
	- want to minimize average loss  (minimize through optimization)
	- **What is a Loss Function**
		- trying to minimize the uncertainty to hedge against uncertainty
- **Learn the Parameters / Gradient Dissent **  i.e. **Optimization**
		- The algorithm should figure out the gradient and slope (in a stepwise manner)
	- **Scaling to Big Data**
		- Calculating **gradient** requires looking at every data point.  This is **problematic** with **Big Data** (Plus, data is **big** because often data is redundant
		- **Approximate** the gradient
			-	Gradient Dissent towards Stochastic (i.e. Random) Gradient Dissent  (**SGD**)
				-	stochastic gradient dissent will find a good approximation of the minimum very very quickly (like a thousand million times faster).
					-	sometimes it will go in the wrong direction but most of the time it will be quicker and a pretty darn good estimate
			-	Take a single example (j) and use it to approximate the gradient
			-	when the magnitude of the gradient is smaller, the noise is more impact
			-	stochastic updates are more likel to go in the wrong direction in this case
			-	gradients are typically only small when we're near a good solution
			-	**SGD with momentum**
			-	caclcuate the gradient (**backpropogation**)   ///  use a `gradient() `function
- **Estimate Performance**:  model **validation** and **overfittng**
	- do we always want to increase complexity?
		- well, we need to validate the fact that adding complexity will actually help
		- deep models help us learn complex relationships
		- we can get a perfect performance on a training set but still fail in the real world = **overfitting**
			- this happens because we fit the data too well on our training data
			- **overfitting**
				- increase the parameters
				- identify complex relationships
				- **overfitting does not generalize** to the real world
			- **validation**
				- see if the network performs in the real world
				- get new data, run the experiment again
				- this is costly and can be infeasible
				- so **use existing data to estimate performance**
				- **split data into groups:  (a) train ; (b) validation ; (c) test**
					- **Test dataset**
						- not used to learn or fit the parameters
						- used once
					- **validation**
						- problematic if want to use a test once
						- can create a second held-out dataset (i.e the validation set)
						- this data is not used for learning
						- can be used to estimate performance
						- use to refine the model
		- **Validation during optimization**
			- maximize the generalization of the network on future data
			- when optimizing on training data, you are rewarded for overfitting
			- we can validate the model while running the optimization loop
				- **early stopping**
					- optimize to convergence:  stop when validation loss stops improving
					-  

<!--stackedit_data:
eyJoaXN0b3J5IjpbMTY0Njk1NTUwMCwxMTUwODI2NTY2LC0xMT
U2MjAwNDk4LDE0ODU0MTU2ODEsNTQwODE4MjgsLTUyMDM2OTg0
OCwtMTI5OTkxODY2OCwtMTMwNDQ5ODU1MywtNTA0MzUzMjc3LC
0yMTI3NDk0OTY1LC0yMDczNTk1NjEwLC0xNTk0NDMxNjkwLDE5
MTcxMjAxLDEwNTk0MTc4MDUsODA0Nzk1MDQ1LC0xNTE0NjYxNj
E5LC0xMzI5Nzk0ODkyXX0=
-->