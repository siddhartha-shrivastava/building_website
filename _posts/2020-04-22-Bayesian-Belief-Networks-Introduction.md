In the world of machine learning and advanced analytics, everyday data scientists solve tons of problems with the help of newly developed and sophisticated AI techniques. The main focus while solving these problems is to deliver highly accurate and error-free results. However, while implementing these techniques in a business context, it is essential to provide a list of actionable levers/drivers of the model output that the end-users can use to make business decisions. This requirement applies to solutions developed across industries. One such machine learning technique that focusses on providing such actionable insights is the Bayesian Belief Network, which is the focus of this blog. The assumption here is that the reader has some understanding of machine learning and some of the associated terminologies.

Several approaches are currently being used to understand these drivers/levers. However, most of them follow a simple approach to understand the direct cause-effect relationship between the predictors and the target. The main challenges with such an approach is that:

1. The focus remains on the relationship between predictors and target, and not on the inter-relationship between the predictor attributes. A simple  example is a categorical variable with various states

2. It is assumed that each of the predictors has a direct relationship with the target variables, while, in reality, the variables could be correlated and connected. Also, the influence of one predictor on the other is ignored while calculating the overall impact of the predictor on the target. For example, in almost every problem, we try handling multicollinearity and choosing a correlation cut-off to disregard the near collinear variables. Nevertheless, complete removal of multicollinearity in the model is rare

The Bayesian Network can be utilized to address this challenge. It helps in understanding the drivers without ignoring the relationship among variables. It also provides a framework for the prior assessment of the impact of any actions that have to be taken to improve the outcome. A unique feature of this approach is that it allows for the propagation of evidence through the network.

Before getting into the details of driver analysis using Bayesian Network, let us discuss the following:
1. The Bayesian Belief Network
2. Basic concepts behind the BBN
3. Belief Propagation
4. Constructing a discrete Bayesian Belief Network

1. The Bayesian Belief Network

A Bayesian Belief Network (BBN) is a computational model that is based on graph probability theory. The structure of BBN is represented by a Directed Acyclic Graph (DAG). Formally, a DAG is a pair (N, A), where N is the node-set, and A is the arc-set. If there are two nodes u and v belonging to N, and there is an arc going from u to v, then u is termed as the parent of v and v is called the child of u. In terms of the cause-effect relationship, u is the cause, and v is the effect. A node can be a parent of another node while also being the child to a different node. An example is illustrated in the image below-

Bayesian Belief Network-illustration

a and b are parents of u, and u is the child of a and b. At the same time, u is also a single parent for v. With respect to the cause-effect relationship, a and b are direct causes of u, and u is directly causing v, implying that a and b are indirectly responsible for the occurrence of v.

2. Basic concepts behind the BBN

The Bayesian Belief Network is based on the Bayes Theorem. A brief overview of it is provided below-

Bayesian Theorem

For two random variables X and Y, the following equation holds-

Bayes theorem

If the X and Y are independent of each other then

bayes theorem

 

Joint Probability

Given X1, X2,………,Xn are features (nodes) in a BBN. Then Joint probability is defined as:

joint probability formula

 

Marginal Probability

Given the joint probability, marginal probability of X1 = x0 is calculated as:

marginal probability formula

where x2 ,x3,…xn are the set of values corresponding to X2, X3,…..,Xn

 

3. Belief Propagation

Now let us try to understand belief propagation with the help of an example. We will consider an elementary network.

belief propagation

 

Now the above network says that the Train strike influences Allen’s and Kelvin’s work timings. And the probabilities are distributed as below:

conditional probability table

Given we know Train Strike probability P(T) and conditional probabilities P(K|T) and P(A|T). we can calculate P(A) and P(K).

P(A= Y) = |T,K P(A=Y,T,K) = P(A=Y,K=Y,T=Y) + P(A=Y,K=N,T=Y) + P(A=Y,K=Y,T=N) + P(A=Y,K=N,T=N)
= P(T=Y)*P(A=Y|T=Y)*P(K=Y|T=Y) + P(T=Y)*P(A=Y|T=Y)*P(K=N|T=Y)
+ P(T=N)*P(A=Y|T=N)*P(K=Y|T=N) + P(T=N)*P(A=Y|T=N)*P(K=N|T=N)
= P(A=Y|T=Y)*P(T=Y) + P(A=Y|T=N)*P(T=N) …………………………………..(As, P(K=Y|T=Y) + P(K=N|T=Y) =1 )
= 0.7*0.1 + 0.6*0.9 = 0.61

Similarly, making the above formulation shorter.

P(K= Y) = P(K=Y|T=Y)*P(T=Y) + P(K=Y|T=N)*P(T=N)
= 0.6*0.1 + 0.1*0.9 = 0.15

Now, let us say we came to know that Allen is late, but we do not know if there is a train strike. Can we know the probability that Kelvin will be late given we know that Allen is late? Let us see how the evidence that is Allen is late is propagating through the network.

Let us estimate the probability of the train strike given we already know Allen is late.

P(T=Y|A=Y) = P(A=Y|T=Y) * P(T=Y)/P(A=Y) = 0.7*0.1/0.61 = 0.12

The above calculation tells us that if Allen is late, then the probability that there is a train strike is 0.12. We can use this updated belief of the train strike to calculate the probability of Kelvin being late.

P(K=Y) = P(K=Y,T=Y) + P(K=Y,T=N) = P(K=Y|T=Y)*P(T=Y) + P(K=Y|T=N)*P(T=N)
= 0.6*0.12 + 0.1*0.88 = 0.16

This gives a slight increase in the probability of Kelvin being late. So, the evidence that Allen is late propagates through the network and changes the belief of the train strike and of Kelvin being late.

belief propagation-formula

 

4. Constructing a discrete Bayesian Belief Network

BBN can be constructed using only continuous variables, only categorical variables, or a mix of variables. Here, we will discuss discrete BBN, which is built using categorical variables only. There are two major constituents to constructing a BBN: Structure Learning and Parameter Learning.

Structure Learning

Structure learning is the basis of Bayesian Belief Network analysis. The effectiveness of the solution depends on the optimality of the learned structure. We can use the following approaches:

1. Create a structure based on domain knowledge and expertise.
2. Create an optimal local structure using machine learning algorithms. Please note that an optimal global structure is an NP-hard problem. There are many algorithms to learn the structure like K2, hill climbing and tabu, etc. You can learn more about these from the bnlearn package in R. Python aficionados can refer to the following link- http://pgmpy.chrisittner.de/
3. Create a structure using a combination of both the above approaches- use machine learning techniques to build the model, and with the reduced set of explanatory variables, use domain knowledge/expertise to create the structure. Of all the three, this is the quickest and most effective way.

Parameter Learning

Another major component of BBN is the Conditional Probability Table (CPT). Since each node in the structure is a random variable, it can take multiple values/states. Each state will have some probability of occurrence. We call these probabilities as Beliefs. Also, each node is connected to other nodes in the network. As per the structure, we learn the conditional probability of each state of a node. The tabular form of all such probabilities is called CPT.

Conclusion

This blog aims to equip you with the bare minimum concepts that are required to construct a discrete BBN and understand its various components. Structure learning and Parameter learning are the two major components that are necessary to build a BBN. The concepts of Bayes theorem, joint and marginal probability work as the base for the Network while the propagation of evidence is required to understand the functionality of BBN.

BBN can be used like any other machine learning technique. However, it works best where there are interdependencies among the predictors, and the number of predictors is less. The best part of the BBN is its intuitive way of explaining the drivers of evidence.

Stay tuned to this space to learn how this concept can be applied for event prediction, driver analysis, and intervention assessment of a given classification problem.
