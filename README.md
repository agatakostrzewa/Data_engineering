# Data_engineering
## My first data pipeline - GANS project

### Project overview and deliverables
Creating an automated data pipeline in the cloud is not a trivial task. There will be two major phases of the project, each with its own sub-phases.

#### Phase 1: Local pipeline
In this first phase you will run scripts to collect data from the internet and store the data in a database. The scripts will be executed by your computer, in Jupyter notebooks, and the database will also be created in your local MySQL instance —also on your own computer.

##### 1.1. Scrape data from the web
Some of the data you will need is going to be floating around the internet, as the content of websites. You will have to learn how to access this information by downloading and extracting the HTML code of these sites, mostly using Python’s most popular web scraping library: beautifulsoup.

##### 1.2. Collect data with APIs
The internet is full of data providers. To acquire the specific data you need, you will need to learn how to authenticate yourself and assemble a request with the right parameters. All of this is done through little pieces of software called APIs. Python’s requests library is going to be your main tool to interact with APIs.

##### 1.3. Create a database model
When you collect data with Python scripts, you will have data stored as dictionaries or Pandas DataFrames. Python objects are great for local exploration and analysis, but not the best format to make data quickly available to the rest of the company. Relational databases are the solution.

Determining the logical structure of the database is an important first step when a company wants to start storing data in a relational database. Which tables will you need? How will these tables be related to each other? Only after answering these questions (and more), you will create the database.

##### 1.4. Store data on a local MySQL instance
Once you’ve created the database model, you will test that the connection between Python and MySQL works by setting up the database locally on your computer and storing the data you collected from the APIs and your web scraper on it.

#### Phase 2: Cloud Pipeline
If you use Google Drive or Apple’s iCloud, your files are already on the cloud. The cloud is a catch-all name for any technological resources or services accessed via the internet. And it has many advantages when it comes to building data pipelines: scalability, flexibility, automation, maintenance…

##### 2.1. Set up a cloud database
The first step in moving your pipeline to the cloud will be the storage one. You will use RDS, the Relational Database Service from the largest public cloud provider: Amazon Web Services (AWS), to set up your MySQL database.

##### 2.2. Move your scripts to Lambda
Lambda is an AWS service for running code seamlessly in the cloud. You will move your data collection scripts from Jupyter Notebooks into AWS Lambda functions.

##### 2.3. Automate the pipeline
One of the advantages of running code in AWS is that scheduling and automation are easy. In our case, we will use CloudWatch Events / EventBridge to create rules that will trigger the execution of the data collection scripts.

#### Phase 3: Medium article
