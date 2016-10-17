## HW #5 
Doris Jung-Lin Lee (jlee782@illinois.edu)  
__1)a)__ 
 If $\lambda$ =0, then the 2nd model is the same as the first model. This intuitively makes sense because if the documents do not contain background words (or that background words are accounted for inside some distribution), then all the words in the document are topic words, so it ends up being the same formulation as the original PLSA.
__b)__

__c)__ If $\lambda$ is large, then there are not a lot of words that are topic words. This means that the words of a particular topic would be small, but very "clean" (free of background words). If $\lambda$ is small, then the topic distribution may be very "noisy" (containing background words). Since background words co-occur with many topics (i.e. the word "AND", "THE" is equally probable to exist in topics "SPORTS" or "DATA MINING") , we could infer that a word is a background word if it occurs in many topics. My hypothesis is that __as $\lambda$ increases, then there will be more (background) words that are common across multiple topics.__ One way to systematically measure this is to try several different values for $\lambda$ and for each trial measure how simmilar are the words in the various topic distribution. An entropy based measure could be used or we could use something like KL divergence to measure the simmilarity between various topic distributions.



__2)a)__ 
In the E-step, we compute the expectation over the probability of the latent variable chosen as topic k given the model parameters and observations: 

$$q(y_{i,j}=1)=p(y_{i,j}=1|D,\theta^{(n)})=\frac{(1-\lambda)\sum_{k=1}^K p(z_{i,j}=k|\pi_i^{(n)})p(w|\theta_k)}{\lambda p(w|D)+(1-\lambda)\sum_{k=1}^K p(z_{i,j}=k|\pi_i^{(n)})p(w|\theta_k)}$$

$$q_{z|y}(z_{i,j}=k)=p(z_{i,j}=1|y_{i,j}=1,\theta^{(n)},\pi_i^{(n)})=\frac{p(z_{i,j}=k|\pi_i^{(n)})p(w_{i,j}|\theta_k^{(n)})}{\sum_{k=1}^K p(z_{i,j}=k|\pi_i^{(n)})p(w_{i,j}|\theta_k^{(n)})}$$

The number of times we expect to see the word type w assigned to topic k $n_{w,k}$ is simply the sum of $p(z_{ij}=k|D,\Pi^{(n)},\theta^{(n)})$ (i.e. probability for a word to be chosen as topic k would) over all possible words in the document.

$$n_{d,k} = \sum_{w \in d}p(z_{d,j}=k|D,\Pi^{(n)},\theta^{(n)})=\sum_{w \in d}c(w,d)q_y(y_{d,w}=1)q_{z|y}(z_{d,w}=k)$$

Simmilarly, the number of times we expect to see any word token in d assigned to topic k is the sum of the probability for that word to be chosen as topic k over all words in the document(including all instances of that word in the document) and all documents in the corpus. 

$$n_{w,k} = \sum_{d\in D} \sum_{w \in d}c(w,d)q_y(y_{d,w}=1)q_{z|y}(z_{d,w}=k)$$

__b)__ 
In the M-step, we can re-estimate the parameters by normalizing the counts that we obtained in the E step. Since the probabilities are just the counts over the total (of all words in a topic, and over all topics) 

$$p(z_{d,w}=k|\Pi_d^{(n+1)}) =\frac{n_{d,k}}{\sum_{k'=1}^K n_{d,k'}}=\frac{\sum_{w\in d} c(w,d) q_y(y_{d,w}=1) q_{z|y}(z_{d,w}=k)}{\sum_{k'=1}^K \sum_{w\in d} c(w,d) q_y(y_{d,w}=1) q_{z|y}(z_{d,w}=k)} $$

$$p(w|\theta_k^{(n+1)}) =\frac{n_{w,k}}{\sum_{w'\in V}n_{w',k}}=\frac{\sum_{d\in D} c(w,d) q_y(y_{d,w}=1) q_{z|y}(z_{d,w}=k)}{\sum_{w'\in V}\sum_{d\in D}  c(w,d) q_y(y_{d,w}=1) q_{z|y}(z_{d,w}=k)} $$
 