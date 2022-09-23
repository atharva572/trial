<!-- PROJECT LOGO -->
  <h2 align="center">💻Churn Analysis Demo App </h2>

  <p align="center">
    An awesome project template to jumpstart your streamlit project!
    <br />
    <a href="#about"><strong>Explore the docs »</strong></a>
    <br />
    <br />
    <a href="https://mathco-streamlit-demo.azurewebsites.net/">View Demo</a>
    ·
    <a href="">Report Bug</a>
    ·
    <a href="">Request Feature</a>
  </p>
</div>

![My Image](assets/images/ezgif-1-50ed7401eb.gif)

<!-- TABLE OF CONTENTS -->
<details>
  <summary>Table of Contents</summary>
  <ol>
    <li><a href="#about">About The Project</a></li>
    <li><a href="#built-with">Built With</a></li>
    <li><a href="#getting-started">Getting-started</a></li>
    <li><a href="#app-description">App description</a></li>
    <li><a href="#usage">Usage</a></li>
    <li><a href="#development-best-practices">Development best practice</a></li>
    <li><a href="#deploying">Deploying</a></li>
    <li><a href="#contributing">Contributing</a></li>
    <li><a href="#license">License</a></li>
    <li><a href="#authors">Authors</a></li>
    <li><a href="#resources">Resources</a></li>
  </ol>
</details>

## About

This repository contains the code base of a demo app built using streamlit framework.
It shows how to integrate a multi-page app with databases and perform predictions.

🔆 The main focus of this app is to analyse and identify the
customers that are about to churn.

## Built with

- <b>Programming Language:</b> Python3
- <b>Framework:</b> Streamlit
- <b>DataBase Warehouse:</b> Snowflake DB
- <b>Storage:</b> Azure blob


## Steps for Pytest Implementation

- **What is Unit Testing?** : Unit Testing is the first level of software testing where the smallest testable parts of a software are tested. This is used to validate that each unit of the software performs as designed.

### Environment Setup
The classes needed to write tests are to be found in the 'unittest' module. Unittest module is now a part of the standard Python distribution; it requires no separate installation.
```sh
  pip install unittest
  ```
### Creating a Unit Test
The steps for writing any unit test is as follows: 

− Import the unittest module in your program.

− Define a function to be tested or import a function.

− Create a testcase by subclassing unittest.TestCase.

− Define a test as a method inside the class. Name of method must start with 'test'.

− Each test calls assert function of TestCase class. There are many types of asserts. 

− Finally, call main() method from the unittest module.

### Steps to run a unit test

- To run a single test class, you use the following command:
```sh
  python -m unittest <test_package.test_module.TestClass> -v
  ```

- To run the test cases present in a single file, use the following command:
```sh
  python -m unittest <testfilename> -v
  ```
- To run all the test present in the folder, use this command:
```sh
  python -m unittest discover -v
  ```


## Getting-started

The quickest way of getting started with this project is to clone this repository into your local machine by the
following commands:

- Clone the repository:
  ```sh
  git clone https://Mathco-Engineering-Labs@dev.azure.com/Mathco-Engineering-Labs/Mathco-Engineering-Lab/_git/streamlit-demo-001
  ```
- cd to the repository's root directory and install the project dependencies in the virtual developer env:
  ```sh
  pip install -r requirements.txt
  ```
- Next create a .env file to store all the db/storage credentials as environmental variables.(Contact any of the authors to get the credentials)

❗ Currently tha app is not fully parameterized. It has some static dependecies. So, we recommend going with the same db/storage that we have used for a quick start.

- As a final step, run the app locally from the root directory:
  ```sh
  streamlit run app.py
  ```

🎉 Now that you have the app running in your local machine. You can follow along this document to now more about the project, development best practices and to use this template to create a production ready app.

## App Description

### UI Components

- **App page** : This is the landing page of the app. Here users are provided with filter options to perform basic EDA

- **Data preview page**: This page provides the description of the data used for the analysis

- **Churn Predictor page**: This page allows the user to predict whether the customer is a existing customer or attrited customer based on the given filter values

- **Prediction History page**: Contains the prediction logs which can also be downlaoded as csv for further analysis

### File Organization

    ├── README.md                           <- The top-level README for developers using this project.
    ├── src
    │   ├── app.py                          <- The main source file that intiates the app
    │   ├── pages                           <- Folder that holds the source code of the sub-pages
    |       ├── Data Preview.py
    |       ├── Churn Predictor.py
    |       └── Prediction History.py
    |   ├── db                               <- Modules for integrating db
    │       └── snowflake
    |           ├── Connection.py
    |           └── utility.py
    |   ├── models                           <- Trained and serialized models, model prediction and summaries
    │       └── xgboost
    |           └── utility.py
    |   ├── plot_generator                   <- Modules used to generate plots for reporting/EDA
    |       ├── gen_matplot.py
    |       ├── gen_ploty.py
    |       └── gen_seaborn.py
    |   ├── storage                           <- Modules for retrieving data from storage units
    |       └── azure_blob.py
    |   ├── util_func                         <- App's utility functions
    |       └── app_control.py
    ├── .azure                                <- Azure DevOps pipelines
    |    └── AzureDevopsPipeline.yml
    ├── .dockerignore
    ├── .gitignore
    ├── .Dockerfile                           <- Image used to setup docker container
    ├── .pre-commit-congif.yaml               <- To check the linting of the code before commit
    ├── .requirements.txt                     <- Dependencies for reproducing the developer environment

## Usage

This demo project is purely developed to show the capabilites of the streamlit framework and it's possible integration. The project is structured in such a way that you can easily use the template to develope medium to large streamlit apps, change the functionality of the application as per your need or even use this as a reference template for your project.But, as the functionalities used in this project has static dependecies we recommend to use this project for reference only.

## Development Best Practices

### Steps to follow for improving your Streamlit app performance

- Choose the widgets as per the need
- Pre-calculate inputs and cahce whenever possible
- Avoid downloading large, static models on the fly
- Remove unused code and data
- Optimize data storage formats

  #### For more info checkout: https://blog.streamlit.io/six-tips-for-improving-your-streamlit-app-performance/

### Project devOps

- For a better usability we recommend to fork the repository to your project repository
- Make use of any of the work frameworks such as agile, scrum, etc..
- Follow CI/CD guidelines
- Create pipelines to automate the testing and linting
- Abstract away the utility functions from the streamlit page's code (recommended to follow the folder structure of this project)

<b>Quick implementation of lint testing: </b>

- The pre-commit python library is already mentioned in the requirements.txt and the yaml file that mentions the hook details of the flake8 is already present in the repository.

- All you have to do is to install the hook mentioned in the yml file. Trigger the below command. It will install all the pre-commit hooks on your machine. This is the onetime activity per repository.
  ```sh
  $ pre-commit install
  ```
- We are almost done! Now if you create or change any Python file in this repository and try to commit the changes, Flake8 pre-commit hook will run and let you know if it passed or failed. If passed, it will complete the commit process, otherwise, it will show up the code quality errors that Flake8 identified. Unless and until you correct those errors, you will not be allowed to commit on this repository.

- Go ahead and correct the suggested issues and try to commit the changes again, your flake8 scan will pass and commit will be successful.

## Deploying

explain the different ways of deploying the app in a server

- Azure App service
- Azure VM
- Streamlit cloud

## Contributing

Contributions are what make the open source community such an amazing place to learn, inspire, and create. Any contributions you make are greatly appreciated.

If you have a suggestion that would make this better, please fork the repo and create a pull request. You can also simply open an issue with the tag "enhancement". Thanks again!

1. Fork the Project
2. Create your Feature Branch (git checkout -b feature/FeatureName)
3. Commit your Changes (git commit -m 'Add some FeatureName')
4. Push to the Branch (git push origin feature/FeatureName)
5. Open a Pull Request

## Authors

- Varun Saraogi - varun.saraogi@themathcompany.com
- Mansit Suman - mansit.suman@themathcompany.com
- Atharva Ballal - atharva.ballal@themathcompany.com
- Hariharasudhan - hariharasudhan.p@themathcompany.com

## Resources

### Streamlit Documentation

Streamlit’s <a href="https://docs.streamlit.io/">documentation website</a> is the best place to get you started:

- Streamlit library. A guide on how to build Streamlit apps with various Streamlit functions (the API reference), “Get started” tutorials, and a cheat sheet.
- Streamlit Cloud. Everything you need to know on how to deploy apps to Streamlit Cloud.
- Knowledge base. A growing collection of tutorial articles and FAQs about using Streamlit and troubleshooting problems.

### Streamlit Dicussion forum

Can’t find the information on the documentation website? Check out the Streamlit <a href="https://discuss.streamlit.io//">discussion forum</a> and read the <a href="https://docs.streamlit.io/knowledge-base">troubleshooting guide</a> for tips on resolving problems.

## For further details

Reach out to: engineering@themathcompany.com
