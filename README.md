# Consistent and Version Space
<h4>Definition — Consistent —</h4>
A hypothesis h is consistent with a set of training examples D if and only if h(x) = c(x) for each example (x, c(x)) in D.
<img src="https://miro.medium.com/max/550/1*GDQjWi5ENGM3_wuNSJs2ug.jpeg">

A training example x is said to satisfy hypothesis h when h(x) = 1, regardless of whether x is a positive or negative example of the target concept.
An example x is said to consistent with hypothesis h iff h(x) = c(x)
<hr>
The set of training examples D are below:

<img src="https://miro.medium.com/max/875/1*yJoGs6oMEtLsfa4lpVG-Gw.jpeg">

The hypothesis h = < Sunny, Warm, ?, Strong, ?, ?>. Now for each example (x, c(x)) in D, we will evaluate h(x) equals c(x).

- (<Sunny, Warm, Normal, Strong, Warm, Same>, yes) → h(x)=c(x)
- (<Sunny, Warm, High, Strong, Warm, Same>, yes) → h(x)=c(x)
- (<Rainy, Cold, High, Strong, Warm, Change>, No) → h(x)=c(x)
- (<Sunny, Warm, High, Strong, Cool, Change>, yes) → h(x)=c(x)

<b>Now we can say, hypothesis h is consistent with a set of training examples D
Lets say, we have a hypothesis h1=< ?, ?, ?, Strong, ?, ?>, is this hypothesis consistent with set of training example D ?</b>
  
In case of training example (3), h(x) != c(x). So hypothesis h1 is not consistent with D.
  
<b> Lets say, we have a hypothesis h2 = < ?, Warm, ?, Strong, ?, ?>, is this hypothesis consistent with set of training example D ?</b>
All the training examples hold h(x) = c(x). So hypothesis h2 is consistent with D.

  <h4>Definition — Version space —</h4>
  The version space, denoted VS_H,D with respect to hypothesis space H and training examples D, is the subset of hypotheses from H consistent with the training examples in D.
  <img src="https://miro.medium.com/max/406/1*TKqSl29P7BT5kNUEnfCmZA.jpeg">
  In above example, we have two hypothesis from H and they are consistent with D.
  <b>h=< Sunny, Warm, ?, Strong, ?, ?> and h2=< ?, Warm, ?, Strong, ?, ?></b>
    So this set of hypothesis { h, h1} is called a Version Space.
    #The List-Then-Eliminate algorithm
    One obvious way to represent the version space is simply to list all of its members. This leads to a simple learning algorithm, which we might call the List-Then-Eliminate algorithm. The algorithm is as follows :
    <img src="https://miro.medium.com/max/875/1*-8k2EElpG2MFYIUHT8FNng.jpeg">
    The LIST-THEN-ELIMINATE algorithm first initializes the version space to contain all hypotheses in H and then eliminates any hypothesis found inconsistent with any training example.<br>
    <h4>Representation for Version Spaces —</h4>
    we can represent the version space in terms of its most specific and most general members.
    For the above enjoysport training examples D, we can output the below list of hypothesis which are consistent with D. In other words, the below list of hypothesis is a version space.
<img src="https://miro.medium.com/max/875/1*3Soyt1mN8X4CH9JwUGT54w.jpeg">
    In the list of hypothesis, there are two extremes representing general (h1 and h2) and specific (h6) hypothesis. Lets define these 2 extremes as general boundary G and specific boundary S.<br>
<h4>Definition — G</h4>
The general boundary G, with respect to hypothesis space H and training data D, is the set of maximally general members of H consistent with D.
    
<h4>Definition — S</h4>
The specific boundary S, with respect to hypothesis space H and training data D, is the set of minimally general (i.e., maximally specific) members of H consistent with D.
    
 <h4>Version Space representation theorem —</h4>
 Let X be an arbitrary set of instances and Let H be a set of Boolean-valued hypotheses defined over X. Let c: X →{O, 1} be an arbitrary target concept defined over X, and let D be an arbitrary set of training examples {(x, c(x))). For all X, H, c, and D such that S and G are well defined,
<img src="https://miro.medium.com/max/769/1*ZAKJ_ILj_6MksV7-743ESQ.jpeg">
    
The below figure shows the version space for enjoysport concept learning including both general and specific boundary sets.
<img src="https://miro.medium.com/max/875/1*BwSOAyJGg-3a_ReKrYxGgg.jpeg">
    From Version Space representation theorem, there exist a hypothesis s belongs to specific boundary set S, and there exist a hypothesis g belongs to general boundary set G, a hypothesis h belongs hypothesis space H holding the relationship “g is more-general-than-or-equal-to h and h is more-general-than-or-equal-to s” forms a version space.
  
