
## What does a Data Scientist do?

>Doctor does "treatment"<br>
Teacher does "teaching"<br>
Constructor does "construction"<br>
Marketeer does "marketing"<br>
Politician does "politics"<br>
And YouTube influencer does "not qualify as a real job!"<br>
But there's one job (title)<br>
That no one knows<br>
What does the data scientist do?<br>
Ring-ding-ding-ding-dingeringeding!<br>
Gering-AI???-ding-Analytics???-dingeringeding!<br>
Gering-Software-Engineering???-ding-ding-dingeringeding!<br>
What the data scientist do?<br>
Wa-pa-pa-pa-pa-pa-pow!<br>
Wa-Databases???-pa-pa-pa-pa-pow!<br>
Wa-pa-pa-pa-Research???-pa-pow!<br>
What the data scientist do?<br>

#### Short(est) answer: A data scientist does "[models](#what-are-models)"
A little longer answer: Data scientists work with models, models built on (or backed by) <b>data</b> - to <i>reason; explain; design; communicate; act; predict; and explore</i> [1]<br><br>
Of course, to answer this "controversial" question, we need more explanation. A side note: the term "Data Scientist" was coined in 2008 [2].
First, let's outline the core responsibilities of a data scientist:
1. [Designing](#model-design) models which could help in making better and/or faster decisions
    * One misconception about data scientists is that they only deal with Machine Learning <i>predictive</i> models
2. Automating the [parameters estimation](#parameters-estimation) for the models
3. Making sure the [models can be updated](#updating-model), with new information, in the fastest; most friction-less way possible
4. [Explaining](#explaining-model); or building tools which could explain the models (or models' output)
5. Building [monitoring](#monitoring-model) tools which could assist in improving/controlling the models' output

## What are models
A model is a “representation” (or simplification) of a physical object; a process; a system; or a phenomenon. 
A representation is by definition not accurate, therefore, we have the aphorism:
>All models are wrong, but some are useful.

The <b>usefulness</b> of a model depends on the design; parameters; complexity; and assumptions made for the model. In different contexts/scenarios a model can become more or less useful. Let's explore an example scenario where a useful model can be employed.

### Designing Model
Let's suppose our (imagined) data scientist is working in an e-commerce company. After talking with several stakeholders/domain experts in the company; and doing some initial cost-feasibility analysis - she realises that operational forecasting is one of the most crucial areas where data science can support the business, the most. Currently the forecasting is done using some manual calculations. A business analyst looks at the sales of the last few weeks and estimates the expected number of sales for the future weeks using weighted averages. This estimate is then used by the warehouse planning manager to hire more or less temporary workers for the coming weeks. 

#### Risks involved
...with having a bad forecast:
* If the forecast turns out to be too high the warehouse manager ends up with too many workers who have no work to do, and therefore, the workers cost the company extra money
* On the other hand if the forecast is too low, the warehouse does not have enought workers and the customers do not get their packages delivered on time, therefore, there is the risk of loosing customers

#### Considerations for the model design
Given the context,
* Is it more important to make faster decisions or more accurate decisions?
   * As the forecast is going to be used for medium to long term planning it is not really important to make faster decisions, on the other hand, for a model used for making real-time decisions the preference might be made in favor of faster predictions
   * It will be irrational to rely entirely on the model forecast
   * The model forecast should be moderated by the domain specialist - operations analyst in this case
* Is it more important to make extremely accurate predictions or explainable predictions
   * A more complex model design might give a slight uplift in predictions accuracy but no (or little) explanation
   * On the other hand, a less complex model could explain the predictions really well, which could in return, help the operations analyst make much better (and informed) adjustments
* Is the model going to reduce the workload (or FTEs)
   * No, the model is only supposed to help the operations analyst make more accurate decisions. It might as well be the case that after employing the model, more analysts are needed. Analysts who can interpret model outputs; build dashboards/reporting tools for analysing differnet forecasts; maintain a collaborative feedback loop with the data scientists, to help improve the model.
   * On the other hand, an NLP (natural language processing) model could be employed to build a bot for replying to general customer services queries. This model could in return, reduce the workload for the customer services department.
* Which variables should be considered as good predictors for the forecast?
* What might be a representative funtional form for the model?
* How to access the input data for the model?
* Does the input data need cleaning up?

#### What is required from our data scientist to come up with a good model design
* Good communcation skills to understand the requirements and problem context
* Knowledge of experimental design
* An extensive vocabulary of models
* Statistics and probability theory
* Database and SQL skills
* Expertise in at least a couple programming languages
* Descriptive and exploratory analytics skills

### Estimating Model Parameters
After designing the model the next step is to automate the estimation of the model parameters. For our forecasting model, there are two types of parameters - model parameters; and hyper-parameters. To understand what model parameters are, let's say that our forecasting model can be expressed (in the simplest way) as follows:

>Forecast for the next week = <b>10000</b> + <b>1.15</b> x (sales of the same week from last year) + <b>1.05</b> x (mean sales of last week) + <b>5000</b> x (if the next week falls in the Christmas period)

For this example - 10000, 1.15, 1.05, and 5000 are the estimated values of the 4 model parameters. These 4 parameters come from the design phase of the model. How these parameters are estimated depends on the machine learning algorithm that is being used. The machine learning algorithms also have their own parameters, the hyper-parameters. These parameters can be thought of as the knobs of the machine learning algorithm, to control how the model parameters are trained/estimated. The combination of model parameters and hyper-parameters yield different forecasts. Automating the algorithm for selecting the best (accurate and stable) combination of parameters, is therfore, a crucial part for having a "useable" model.

#### What is required from our data scientist
* Knowledge of the fundamentals of machine learning
* An extensive vocabulary of machine learning algorithms and tools
* Linear algebra
* Differential calculus
* Computer science theory
* Software engineering/design

### Updating Model
An important property of (most) data science models is that they expire after some time. Some expire sooner than later. Our forecasting model is strongly based on the sales of the last week and last year. Therefore, it is really important to update our model every day. There are other ways where our model can expire or become unuseable/obselete:
* The operations analyst realises that the model predictions are consistently off during particular days or periods. She knows that the marketing team runs a recurring marketing event during these periods. She relays this information to the data science team, which in response deploys this new feature to the production model in no time.
* Lately the growth of the sales has been more linear as compared to the exponential growth we saw in the past years. Therefore, we now need to re-engineer our trend features.

#### What is required from our data scientist
* Basic data engineering skills
* Familiarity with continuous integration/deployment concepts and technologies
* Experience with Cloud platforms and services like AWS, GCP, Azure

### Explaining Model
Like mentioned before in some contexts it is really important to explain the model output. Imagine the level of confidence the operations analyst will have if she's presented with the explanation of the sales forecast [2] in the following manner:

![Model Explanation](./model-explanation.png)

* The different colours explain the contribution of different predictors in the forecast

#### What is required from our data scientist
* Knowledge of visualisation techniques and frameworks
* Knowledge of Game theory

### Monitoring Model
We have a useable forecasting model. Now it's time to make sure that the forecasts made by the model are <b>consistently</b> accurate, stable, and reliable. To achieve that, it is really important to set some benchmarks first, in collaboration with the operations analyst. The data scientist then needs to develop some monitoring mechanisms that would bring forward/raise alarms, if and when, the model produces unstable; inaccurate; or unreliable output. This will ensure two things - 1. We have control over our model; and the decisions we make using that model 2. The model can be improved/updated when it is not performing as expected.

#### What is required from our data scientist
* Experience with visualisation, monitoring, and dashboarding frameworks
* Statistics and probability theory

### Complete Skills Map
![Skills Map](./skills-map.png)

### References
[1] Scott E. Page, <i>The Model Thinker</i> (2018)<br>
[2] https://hbr.org/2012/10/data-scientist-the-sexiest-job-of-the-21st-century
