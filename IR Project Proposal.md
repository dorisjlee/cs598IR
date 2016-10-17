
Once we have shown how these multiple streams can be handled, we show how they can be used to model different kinds of trends. Fashion consumers and producers need to understand different kinds of trends: consumers want to know what is on trend now (e.g. get a recommendation for purchase now), while fashion designers and buyers want to predict how history repeats itself (e.g. which old trends are coming back into vogue in the next few seasons or even years). These two distinct trend needs require two distinct forms of models to support them: time series modeling to predict long-term trend re-occurence and modeling on streams to predict current trends. Past work has shown that learning these models on single streams requires non-trivial adaptations \cite{bayesian_modeling_streams, streaming_variational_bayes}, and we are the first to show how they can work on multiple streams in a single learned model.

Our contributions are thus two-fold. First, we show a method for handling fashion streams including obtaining, processing, and combining these streams despite differing update rates, content types and data cleansing needs. Second, we show how these streams can be used to model two distinct types of trends, current and on-going trends useful for consumers as well as longer-term predictive trends useful for fashion producers. 


-----------------------------------
You must write a one-page proposal before you actually begin your project in-depth. These will be submitted via Compass and are due Saturday, October 22nd at 11:59pm.

In the proposal, you should address the following questions and include the names and email addresses of all the team members. (As long as these questions are addressed, the proposal does not have to be very long. A couple of sentences for each question would be sufficient.)

If your project is aiming at the research track, you should focus on the following in your proposal:

What is your research question? Clearly define the research problem/question.
Why is this an interesting question to ask and why would we care about the answer to this question or a solution to the problem?
Has any existing research work tried to answer the same or a similar question, and if so, what is still unknown? (In other words, what is the novelty of your research question?) Provide a brief list of related work.
How do you plan to work out the answer to the question? (At the proposal stage, you are only expected to have a sketch of your methods.)
How would you evaluate your solution? That is, how do you plan to demonstrate that your solution/answer is good or is reasonable?
A rough timeline to show when you expect to finish what. List a couple of milestones if possible (they can be tentative).


# IR Project Proposal 
Doris Jung-Lin Lee (jlee782@illinois.edu)

This is a research track project where we will be looking at ways to integrate multiple data streams for updating the Latent Dirchlet Allocation (LDA) model. More specifically, we will be looking at recent advances in streaming LDA could be applied to fashion applications to combine multiple heterogenous data streams.


Prior work in computational approaches to fashions have focussed on using static data repositories to characterizing styles and build  visual or textual recognition and understanding of the relationship between clothing items and styles[3-9]. While there has been existing work that studies trends in fashion [3-4], these studies are still based partitioning static datasets into separate time periods, and then applying their models independently. 

Temporal changes are important in fashion, as trends and fads come and go quickly and new items are introduced every few months or even every few days for fast-fashion brands. Since people often want to be``on trend," fashion applications depend on being able to capture these trends. 

Streaming fashion data has its own technical challenges including: 

  - data may have various different update rates and noisy level (e.g. fashion-related hashtags versus highly-curated fashion magazine articles). From an applications point-of-view, it is important to incorporate these priors into model in a sensible manner.
  - need to constantly update the model to ensure that the downstream applications reflects the most up-to-date trends.


I have already reviewed existing literature on how various inference methods for LDA could be modified to take in data streams including work on updating population posterior [1] and applying stochastic variational inference[2]. The data sources that we have in mind includes information on products that updates daily as new products enter the market, information on fashion history and critique (which includes seasonal runway data, magazine reviews and daily social content from famous designers and fashion thinkers), and some other info source category.



Integrated approach to trend analysis is hard because online data stream (social media content, search keywords, product reviews) are often noisy and ---- topic model  
Model parameters and distribution changes over time.


Recent work by our group have shown that topic modelling is 



Latent Dirchlet Allocation 

streaming data

Recent works by ----- have shown that 



variational topic modelling 

variational inference 

## References: 
[1] Mcinerney, J., & Blei, D. M. (2016). The Population Posterior and Bayesian Inference on Streams, 1–10.
[2] Boyd, N., Wibisono, A., Wilson, A. C., Jordan, M. I., & Broderick, T. (2013). Streaming Variational Bayes, 1–9.
[3]  He, R., & Mcauley, J. (n.d.). Ups and Downs : Modeling the Visual Evolution of Fashion Trends with One-Class Collaborative Filtering.
[4] McAuley, J., & Leskovec, J. (2013). From amateurs to connoisseurs: modeling the evolution of user expertise through online reviews. In Proceedings of the 22nd International Conference on World Wide Web, 897–908. Retrieved from http://dl.acm.org/citation.cfm?id=2488466
[5] Vittayakorn, S., Yamaguchi, K., Berg, A. C., & Berg, T. L. (2015). Runway to realway: Visual analysis of fashion. Proceedings - 2015 IEEE Winter Conference on Applications of Computer Vision, WACV 2015, 951–958. http://doi.org/10.1109/WACV.2015.131
[6] Chen, H., Xu, Z. J., Liu, Z. Q., & Zhu, S. C. (2006). Composite templates for cloth modeling and sketching. Proceedings of the IEEE Computer Society Conference on Computer Vision and Pattern Recognition, 1, 943–950. http://doi.org/10.1109/CVPR.2006.81
[7] Yamaguchi, K., Brook, S., Hill, C., Berg, T. L., & Hill, C. (n.d.). Paper Doll Parsing: Retrieving Similar Styles to Parse Clothing Items.
[8] Arora, S. (n.d.). Decoding Fashion Contexts Using Word Embeddings.
[9] Kristen Vaccaro, Sunaya Shivakumar, Ziqiao Ding, Karrie Karahalios, and R. K. (2016). The Elements of Fashion Style.

