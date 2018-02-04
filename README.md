<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [Machine Learning Intro](#machine-learning-intro)
  - [What is ML?](#what-is-ml)
    - [Finding Patterns](#finding-patterns)
    - [Learning](#learning)
    - [ML in a Nutshell](#ml-in-a-nutshell)
    - [Why is ML so popular?](#why-is-ml-so-popular)
      - [Who's Interested in ML?](#whos-interested-in-ml)
      - [What is a data scientist?](#what-is-a-data-scientist)
      - [ML Offerings](#ml-offerings)
    - [The Role of R](#the-role-of-r)
  - [The ML Process](#the-ml-process)
    - [Asking the Right Question](#asking-the-right-question)
    - [Illustrating the ML Process](#illustrating-the-ml-process)
    - [Scenario: Detecting Credit Card Fraud](#scenario-detecting-credit-card-fraud)
    - [Scenario: Predicting Customer Churn](#scenario-predicting-customer-churn)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

# Machine Learning Intro

> Intro to Machine Learning with Pluralsight.

A gentle introduction and some definitions (non technical).

## What is ML?

### Finding Patterns

ML finds patterns in data. Uses those patterns to predict the future. Examples:
- Detect credit card fraud by finding patterns in data to detect when new transaction is likely to be fraudulent.
- Determine if a customer is likely to switch to a competitor.
- Decide when to do preventive maintenance on a factory robot.

### Learning

Requires:
- Identifying patterns.
- REcognize patterns when seen again

ML does this with provided data. Suppose data on cc transactions looks like:

| Name        | Amount           | Fraudulent  |
| ------------- |:-------------:| -----|
| Smith     | $2,600.45 | No |
| Potter     | 2$,294.58      |   Yes |
| Peters | $1,003.30      |    Yes |
| Adams | $8,488.32      |    No |

This data suggests if name starts with `P`, it's fraudulent. Having so little data demonstrates that it's difficult to find patterns that are *predictive*, i.e. to help understand if a new transaction is likely to be fraudulent.

Now consider more data records and more fields:
![more data](images/more-data.png "more data")

Now a pattern emerges - transaction is fraudulent if card holder is in their 20's, card issued in USA, used in Russia, amount > $1,000. But even so can't guarantee this is predictive. To do a good job, need so much data that it's too much for a human to process.

### ML in a Nutshell

![nutshell](images/nutshell.png "nutshell")

- Start with data that contains patterns.
- Feed data into *Machine learning algorithm* that finds patterns in the data.
- Algorithm generates *Model* - functionality (typically code) that is able to recognize patterns when presented with new data.
- Applications use Model, supplying new data to see if it matches known patterns (eg: new cc transactions).
- Model returns probability if given new data matches pattern (eg: if new cc transaction is fraudulent).

### Why is ML so popular?

Doing ML well requires:
- Lots of data, which is increasingly more available in *Big Data* era.
- Lots of compute power, also increasingly available in *Cloud* era.
- Effective ML agorithms, also more available as a result of years of research.

#### Who's Interested in ML?

- Business leaders: Want solutions to business problems (eg: fraudulent transactions, customers switching to competitors). These people also have the $$ to pay for ML solutions.
- Software developers: Want to build better/smarter applications. These applications can rely on models created via ML to make better predictions. Apps can be smarter even if developer writing them did not create the ML model.
- Data scientists: Want powerful, easy-to-use tools.

#### What is a data scientist?

Role combines:

- Statistics
- ML software
- Knowledge in a specific problem domain, eg: cc transaction fraud, robot preventive maintenance, etc.

#### ML Offerings

ML also referred to as *Predictive Analytics*.

![nutshell](images/nutshell.png "nutshell")

### The Role of R

Open source programming language *and* environment. Supports ML, statistical computing and more. Has many packages. Very popular.

Python also increasingly popular.

## The ML Process

### Asking the Right Question

Most important part of the process.

**Is the right data to answer the question available?**

For example, maybe in determine cc fraud, the most predictive piece of information is whether card holder is a home owner or renter. Or how long they've lived at current address. In this case, you would need this data to answer the question "Is a cc transaction fraudulent?".

**Do you know how you'll measure success?**

How good must the model predictions be to make the process quality as success. Eg: if cc fraud model predicts accurately in 8 of 10 cases, is that good enough? 6 of 10? Do you need 9 of 10? Determine success criteria up front so you know when you're done.

### Illustrating the ML Process

![iteration](images/iteration.png "iteration")

- Choose raw data, work with domain experts. Raw data is not in right form, may have dupes, extra info not needed etc.
- Apply pre-processing to raw data to get *Prepared Data*, which becomes input to ML. May have to iterate on pre-processing to get good useful data. Majority of time will be spent in this phase.
- Apply ML algorithms to data.
- Result is *Candidate Model*. Iterate applying algorithms to data to get increasingly better models, until a model that is good enough to deploy emerges.
- Deploy chosen model.
- Applications can make use of deployed model.

**Repeating the ML Process**

Entire process must be repeated, model must be recreated regularly, to keep model up to date with changing reality. For example processing new data or algorithms.

![repeat](images/repeat.png "repeat")

### Scenario: Detecting Credit Card Fraud

![scenario-cc-fraud](images/scenario-cc-fraud.png "scenario-cc-fraud")

- Given cc customers supplying their payment info to payment application (eg: POS terminal at grocery store). Which should app reject because they're likely fraudulent?
- Start with historical transaction data, run through ML process to get model that app can call to make decision.

### Scenario: Predicting Customer Churn

![customer-churn](images/customer-churn.png "customer-churn")

- Eg: mobile phone company with customers who call in to call center.
- Call center staff use Call Center App.
- For each caller, want staff to know, how likely is that customer to switch to a competitor.
- Staff can offer customers who are about to switch a better deal than a loyal customer.
- Mobile phone company may have large volume of detailed call data on their customers. They could use an app to aggregate it (eg: Hadoop, Spark), then combine this data with other data such as CRM system. Then the resulting data combined from multiple sources can be fed into the ML process.

2:48 https://app.pluralsight.com/player?course=understanding-machine-learning&author=david-chappell&name=understanding-machine-learning-m3&clip=3&mode=live
