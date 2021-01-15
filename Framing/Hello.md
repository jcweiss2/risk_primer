### How much you count
You are an everyday John Doe.

You know a researcher Doe II who spends his life studying populations for risk of heart attack.

You do not want a heart attack.  Fortunately, from your general world knowledge you are low risk.
But, low risk means 1 in 1000 per year, and your risk aversion compels you to be willing to act on yourself to further lower your risk.  How do you do it?

Consult Doe II of course.  Doe II has trained a model to estimate your risk based on risk factors, including age, gender, body mass index (BMI), physical activity, and diabetes.  Doe II suggests you lower your age (not possible), be female (not possible), lower your BMI, increase your physical activity, and lower your blood sugar.

Your BMI is 22, you already walk 30 minutes 3 times weekly, and your fasting blood sugar level is 70.  You wonder if Doe II's model really applies to you. 

Doe II's model was a survival model built on the general population and you verify that his population included patients like you.  You are reassured because: you are a member of the population, the model is built from population samples, and Doe II's recommendations are based on the model:

$\text{you} \in \text{population}$; $\text{samples} \in \text{population};$ 
$\text{samples} \rightarrow \text{train model} \rightarrow \text{recommendations}$
$\text{you} \rightarrow \text{use model} \rightarrow \text{your recommendations}$

But you tread on because the recommendations are unhelpful.
In your exploration, you find that survival models optimize by maximizing log likelihoods, and that [the log likelihood weighs risk proportionally to risk accumulated over time](https://arxiv.org/abs/1911.05109).  So, if two people, one with 10 times the risk (1 in 100 versus 1 in 1000), were each observed for heart attack for one year, the model would optimize 10 *times* more to the high risk person.

You raise this with Doe II, who says this is always how it has been done.  To assuage you, he offers to run a classification algorithm instead, in case it is simply a problem with the pesky survival formulation.  Furthermore, he assures you that his data is perfectly collected for one year (no censorship).

You reflect on Doe II's offer.  You learn that binary classification problems ({heart attack, no heart attack}) typically use cross-entropy. So, compared to another person, you count as much as your cross-entropy.  How much is that?  



  And in margin classifiers (e.g. SVMs), if you're not a support vector, you don't count at all.
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEyNDc5MzU3MTgsLTE4NDI4MjI0OTYsLT
IwMDQxMTIxNDgsLTk0MDM2Mzg5MiwtMTIwNDY2MjYzMSwtMTIw
MDY0MjQyLDQwMTk2Mjk5MSw4MzkzMDMzNzddfQ==
-->