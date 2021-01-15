### How much you count
You are an everyday John Doe.

You know a researcher Doe II who spends his life studying populations for risk of heart attack.

You do not want a heart attack.  Fortunately, from your general world knowledge you are low risk.
But, low risk means 1 in 1000 per year, and your risk aversion compels you to be willing to act on yourself to further avoid risk.  How do you do it?

Consult Doe II of course.  Doe II has trained a model to estimate your risk based on risk factors, including age, gender, body mass index (BMI), physical activity, and diabetes.  Doe II suggests you lower your age (not possible), be female (not possible), lower your BMI, increase your physical activity, and lower your blood sugar.

Your BMI is 22, you already walk 30 minutes 3 times weekly, and your fasting blood sugar level is 70.  You wonder if Doe II's model really applies to you. 

Doe II's model was a survival model built on the general population and you verify that his population included patients like you.  You are reassured because: you are represented in the data, the model is built on the data, and Doe II's recommendations are based on the model:

$``\text{you} \in \text{data}; \text{data} \rightarrow \text{model} \rightarrow \text{recommendations}"$

But you tread on because the recommendations are unhelpful.
In your exploration, you find that survival models optimize by maximizing log likelihoods, and that [the log likelihood weighs risk proportionally to risk accumulated over time](https://arxiv.org/abs/1911.05109).  So, if two people, one with 10 times the risk (1 in 100 versus 1 in 1000), were each observed for heart attack for one year, the model would optimize 10 *times* more to the high risk person.

You raise this with Doe II, who says this is always how it has been done.  He says that he supposes he could ruBut he does tell you that his data is perfectly collected for  one year.  
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTM0OTAzNTkyNCwtMjAwNDExMjE0OCwtOT
QwMzYzODkyLC0xMjA0NjYyNjMxLC0xMjAwNjQyNDIsNDAxOTYy
OTkxLDgzOTMwMzM3N119
-->