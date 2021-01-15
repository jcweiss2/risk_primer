### How much you count
You are an everyday John Doe.

You know a researcher Doe II who spends his life studying populations for risk of heart attack.

You do not want a heart attack.  Fortunately, you know from your general world knowledge that you are low risk.
But, low risk means 1 in 1000 per year, and your risk aversion compels you to be willing to act on yourself to further lower your risk.  How do you do it?

Consult Doe II of course.  Doe II has trained a model to estimate your risk based on risk factors, including age, gender, body mass index (BMI), physical activity, and diabetes.  Doe II suggests you lower your age (not possible), be female (not possible), lower your BMI, increase your physical activity, and lower your blood sugar.

Your BMI is 22, you already walk 30 minutes 3 times weekly, and your fasting blood sugar level is 70.  You wonder if Doe II's model really applies to you. 

Doe II's model was a survival model built on the general population and you verify that his population included patients like you.  You are reassured because: you are a member of the population, the model is built from representative population samples, and Doe II's recommendations are based on the model:

$\text{you} \in \text{population}$; $\text{samples} \in \text{population};$ 
$\text{samples} \rightarrow \text{train model} \rightarrow \text{recommendations}$
$\text{you} \rightarrow \text{use model} \rightarrow \text{your recommendations}$

But you tread on because the recommendations are unhelpful.
In your exploration, you find that survival models optimize by maximizing log likelihoods, and that [the log likelihood weighs risk proportionally to risk accumulated over time](https://arxiv.org/abs/1911.05109).  So, if two people, one with 10 times the risk (1 in 100 versus 1 in 1000), were each observed for heart attack for one year, the model would optimize 10 *times* more to the high risk person.

You raise this with Doe II, who says this is always how it has been done.  To assuage you, he offers to run a classification algorithm instead, in case it is simply a problem with the pesky survival formulation.  Furthermore, he assures you that his data is perfectly collected for one year (no censorship).

You reflect on Doe II's offer.  You learn that binary classification problems ({heart attack, no heart attack}) typically use cross-entropy. So, compared to another person, you count as much as your cross-entropy.  How much is that?  

Supposing the classification model gets your risk exactly right (i.e. is Bayes-optimal): your cross-entropy is:
 $-0.001\ \text{log}_{2}0.001\approx 0.01$, 
 and the person with 10 times the risk is:
 $-0.01\ \text{log}_{2}0.01\approx 0.07$.  
 So they still count 7 times more than you.
 
(You consider turning to margin classifiers (e.g. SVMs), but you realize if you're not a support vector, you don't count at all.)

Realizing that you remain unsettled, Doe II suggests building a secondary model on the subgroup.  But who should be included?  First, the next model still proportionally focus on the highest risk members.  Second, if the initial model is not very good for low risk individuals, high risk members could bleed in, and low members could leak out.  And third, members who pass the first filtration may be selected for based on their characteristics, which may result in an unrepresentative population.

Equivocator Doe III is alerted to your dilemma.  They say, weighting is up to you, and you just have to weight "according to your use case", whatever that means.  You care about your risk, and you care about the factors that affect your risk.  So from that perspective, you care about other's risk insofar as: (1) you are uncertain about your own risk, and they represent 
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTM5NTUxMTA5MSwtMjE0NTQ0NTE1NCw5ND
MxMTIzNDksLTEyNDc5MzU3MTgsLTE4NDI4MjI0OTYsLTIwMDQx
MTIxNDgsLTk0MDM2Mzg5MiwtMTIwNDY2MjYzMSwtMTIwMDY0Mj
QyLDQwMTk2Mjk5MSw4MzkzMDMzNzddfQ==
-->