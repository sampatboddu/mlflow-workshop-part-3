 Managing the Complete Machine Learning Lifecycle with MLflow
=============================================================
![](images/mlflow-workshop.png)
Part 3 of 3
-----------
Other parts:
- [Part 1](https://github.com/dmatrix/mlflow-workshop-part-1)
- [Part 2](https://github.com/dmatrix/mlflow-workshop-part-2)

Content for the MLflow Series
-----------------------------
Machine Learning (ML) development brings many new complexities beyond the traditional software development lifecycle. Unlike in traditional software development, ML developers want to try multiple algorithms, tools and parameters to get the best results, and they need to track this information to reproduce work. In addition, developers need to use many distinct systems to productionize models.

To solve these challenges, [MLflow](https://mlflow.org), an open source project, simplifies the entire ML lifecycle. MLflow introduces simple abstractions to package reproducible projects, track results, 
encapsulate models that can be used with many existing tools, and central respositry to share models,
accelerating the ML lifecycle for organizations of any size.

Goal and Objective
------------------
Aimed at beginner or intermediate level, this three-part series aims to educate data scientists or ML developer in how you 
leverage MLflow as a platform to track experiments, package projects to reproduce runs, use model flavors to deploy in diverse environments, and manage models in a central respository for sharing.

What you will learn
-------------------
Understand the four main components of open source MLflow——MLflow Tracking, MLflow Projects, MLflow Models, and Model Registry—and how each compopnent helps address challenges of the ML lifecycle.
 * How to use [MLflow Tracking](https://mlflow.org/docs/latest/tracking.html) to record and query experiments: code, data, config, and results.
 * How to use [MLflow Projects](https://mlflow.org/docs/latest/projects.html) packaging format to reproduce runs
 * How to use [MLflow Models](https://mlflow.org/docs/latest/models.html) general format to send models to diverse deployment tools.
 * How to use [Model Registry](https://mlflow.org/docs/latest/model-registry.html) for collaborative model lifecycle management
 * How to use [MLflow UI](https://mlflow.org/docs/latest/tracking.html#tracking-ui) to visually compare and contrast experimental runs with different tuning parameters and evaluate metrics


Instructor
-----------

- [Jules S. Damji](https://www.linkedin.com/in/dmatrix/) [@2twitme](https://twitter.com/2twitme) 
---

MLflow workshop part 3
----------------------

In this part 3, we will cover:
 * Concepts and motivation behind Model Registry
 * Tour of the the Model Registry Documentation and APIs
 * Model Registry Workflows
   * Model Registry UI
   * Model Registry API
 * How to manage, annotate, and transition models with Model Registry
 * Use Model Registry UI on the local host
 * Deploy and serve a model on the local host
  * Visit a model example from [MLflow Project Keras Example](https://github.com/dmatrix/mlflow-workshop-project-expamle-1)

Prerequisites
-------------
* [Part 1](https://github.com/dmatrix/mlflow-workshop-part-1) and [Part 2](https://github.com/dmatrix/mlflow-workshop-part-2) of this series
* Knowledge of Python 3 and programming in general
* Preferably a UNIX-based, fully-charged laptop with 8-16 GB, with a Chrome or Firefox browser
* Familiarity with GitHub, git, and an account on Github
* Some knowledge of Machine Learning concepts, libraries, and frameworks 
     * scikit-Learn
     * pandas and Numpy
     * matplotlib
     * keras/TensorFlow
* PyCharm/IntelliJ or your choice of syntax-based Python editor
* pip/pip3 or conda and Python 3 installed
* Knowledge on how to use [conda](https://docs.conda.io/projects/conda/en/latest/user-guide/install/) or create [pipenv](https://pypi.org/project/pipenv/) enviroments 
* Loads of virtual laughter, curiosity, and a sense of humor ... :-)

Obtaining the Tutorial Material
--------------------------------

Familiarity with git is important so that you can get all the material easily during the tutorial and
workshop as well as continue to work on in your free time, after the session is over.

```git clone git@github.com:dmatrix/mlflow-workshop-part-3.git or git clone https://github.com/dmatrix/mlflow-workshop-part-3.git```

Documentation Resources
-----------------------

This tutorial will refer to documentation: 

1. [MLflow](https://mlflow.org/docs/latest/index.html)
3. [Numpy](https://numpy.org/devdocs/user/quickstart.html)
4. [Pandas](https://pandas.pydata.org/pandas-docs/stable/reference/index.html)
5. [Scikit-Learn](https://scikit-learn.org/stable/index.html)
6. [Keras](https://keras.io/optimizers/)
7. [TensorFlow](https://tensorflow.org)
8. [Matplotlib](https://matplotlib.org/3.2.0/tutorials/introductory/pyplot.html)

Installation and Setup environment
----------------------------------

1. ```git clone git@github.com:dmatrix/mlflow-workshop-part-3.git or git clone https://github.com/dmatrix/mlflow-workshop-part-3.git```
2. `cd <your_cloned_directory>/mlflow-workshop-part-3`
3. Install MLflow and the required Python modules within your [conda activated environment](https://docs.conda.io/projects/conda/en/latest/user-guide/install/) or [pipenv environment](https://pypi.org/project/pipenv) if using it
    * `pip install -r req.txt` or `pip3 install -r req.txt`
5. `cd src`
6. If using PyCharm or IntelliJ, create a project and load source files in the project or use your choice of syntax-highlighted editor, like Sublime or vim
7. [How to use PyCharm and MLflow](https://www.youtube.com/watch?v=yzn1hNkQuWA&feature=youtu.be)

Let's go!

Session Tutorials
-----------------

We'll use localhost (or your laptop) to run register models with Model Registry.

Tutorial 1 - Part 1 
-------------------

Coming soon...


Tutorial 2 - Part 1
-------------------
 
Let's take our model from the previous Workshop Part-2 (Projects & Models) (Tutorial 2 - Part 2) 
and deploy and serve it locally as a REST point tp a server launched MLflow CLI. 

1. ```mlflow run git@github.com:dmatrix/mlflow-workshop-project-expamle-1.git -P batch_size=10 -P epochs=1000``` 
    or
    ```python run_project_keras_lr.py```
    
This will run locally and print out the run id. 

2. From the same directory, providing the run id as argument, run:
 * ```deploy_model.sh <INSERT_YOUR_RUN_ID_HERE>``` 
 
This launch a gunicorn server serving at the localhost:5000. Now you can score locally
on the deployed model.
 
2. From another terminal send a REST call with Farenheight temperatures
  * run ```make_predictions.sh```

Homework/Lab Assignment
-----------------------

* Use Model Registry UI or API to register models from workshop part-1
* Use ```mlflow models predict [OPTIONS]``` only to predict
     
Cheers,

Jules
