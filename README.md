# Operationalizing Machine Learning with Microsoft Azure ML

This is the second project of the Machine Learning Engineer Nanodegree with Microsoft Azure from Udacity.

## Overview

In this project, an AutoML run was performed on a bank marketing dataset, to predict whether contacted customers would subscribe to the bank product offered. The best model found was deployed and consumed. A pipeline was created and published in the same experiment.

## Architectural Diagram

Here is an architectural diagram of the project:
![Architectural Diagram](../img/architectural-diagram.jpg)

## Key Steps

1. Upload bank marketing dataset
   In this step, the bank marketing dataset was uploaded.

&nbsp; &nbsp; ![Bank Marketing Data](../img/01-registered-bank-marketing-dataset.jpg)

2. Run AutoML with auto featurization
   In this step, an Automated ML run was performed as a classification task with auto featurization.
   The best model was found to be Voting Ensemble, which is a very robust model as it actually takes into account the different 'votes' about the label that all the different models predict from the dataset.

&emsp; &emsp; ![ ](../img/02-automl-run-completed.jpg)

3. Deploy the best model
   In this step, the best model from the AutoML run, Voting Ensemble, was deployed.

&emsp; &emsp; ![ ](../img/03-best-model-deployed.jpg)
&emsp; &emsp; ![ ](../img/03-best-model-deployed-healthy.jpg)

4. Enable logging
In this step, logging was enabled with a Python script and the Application Insights page could be used to monitor the app.

&emsp; &emsp; ![ ](../img/04-logging-results.jpg)
&emsp; &emsp; ![ ](../img/04-application-insights-enabled.jpg)
&emsp; &emsp; ![ ](../img/04-logging-results-3.jpg)

5. Check swagger documentation
   In this step, swagger ui was used to see the input required for an API request in order to obtain predictions from the deployed model. Two modes of API requests were seen, i.e. GET and POST.

&emsp; &emsp; ![ ](../img/05-swagger-ui.jpg)
&emsp; &emsp; ![ ](../img/05-swagger-get.jpg)
&emsp; &emsp; ![ ](../img/05-swagger-post.jpg)

6. Consume model endpoint
   After finding out the json structure of the input, in this step a Python script was run to get the prediction from the endpoint by sending the new data in the required input structure.

&emsp; &emsp; ![ ](../img/06-consume-endpoint.jpg)

7. Create, publish, and consume a pipeline
   After the model was deployed, a pipeline was created and publish to ease duplicating the project flow. Another run was scheduled and eventually re-run.

&emsp; &emsp; ![ ](../img/07-published-pipeline-rest-endpoint-active.jpg)
&emsp; &emsp; ![ ](../img/07-published-endpoint-active.jpg)
&emsp; &emsp; ![ ](../img/07-notebook-run.jpg)
&emsp; &emsp; ![ ](../img/07-scheduled-pipeline-run.jpg)

## Screen Recording

Below is a link to a screen recording of the project in action.
https://youtu.be/53lSjGeCU0c

<iframe width="560" height="315" src="https://www.youtube.com/embed/53lSjGeCU0c" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### How to Improve

Accuracy can be used as the primary metric in the AutoML run to compare the results with the latest run  which used AUC Weighted.
Data cleaning could be performed prior to running AutoML to increase accuracy.
A benchmark could be added to similar projects to serve as a monitoring baseline.