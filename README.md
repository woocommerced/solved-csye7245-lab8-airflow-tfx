Download Link: https://assignmentchef.com/product/solved-csye7245-lab8-airflow-tfx
<br>
This lab demonstrates the functionalities of Airflow to programmatically automate, author, schedule and monitor workflows.

<ul>

 <li><strong>Airflow</strong> is a platform to programmatically automate, schedule and monitor workflows.</li>

 <li>In Airflow, a <strong>DAG – or a Directed Acyclic Graph</strong> – is a collection of all the tasks you want to run, organized in a way that reflects their relationships and dependencies.</li>

 <li>The <strong>Airflow scheduler</strong> executes your tasks on an array of workers while following the specified dependencies.</li>

 <li>Rich command line utilities make performing complex surgeries on DAGs a snap.</li>

 <li>The rich user interface makes it easy to visualize pipelines running in production, monitor progress, and troubleshoot issues when needed.</li>

</ul>

<h1>Experiment Setup</h1>

<ol>

 <li>Create a new project and install the required dependencies.</li>

</ol>

pip install apache-airflow




<ol>

 <li>EXPORT AIRFLOW_HOME</li>

</ol>

Enter the path of the present working directory

<ol>

 <li>Initialize the instance</li>

</ol>




airflow db init

<ol>

 <li>Create an admin user</li>

</ol>

airflow users create 

–username admin 

–firstname YourName 

–lastname YourLastName 

–role Admin 

–email <a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="12776a737f627e7752776a737f627e773c717d7f">[email protected]</a>




<ol>

 <li>Start the Daemon in the background.</li>

</ol>




airflow webserver -D

It usually runs on port 8080

<ol>

 <li>To check whether Airflow Daemon is running:</li>

</ol>

List the services running on port 8080




<strong>lsof -i tcp:8080 </strong>

<strong> </strong>

<ol>

 <li>Start the scheduler</li>

</ol>

<strong>airflow scheduler</strong>

<strong>Check the web server on 127.0.0.1:8080</strong>




<ol start="8">

 <li>Create folder dags inside AIRFLOW_HOME</li>

</ol>

Place the DemoDag python file under the ‘dags’ folder.

<ol start="9">

 <li>Kill and Start the scheduler again to show the dags on the web server</li>

</ol>

lsof  -i tcp:8080

Kill the pid of the running services on port 8080

<ol>

 <li>Start the web server again by ‘airflow webserver -D’</li>

 <li>The file can now be seen under the ‘dags’ folder.</li>

</ol>

<ul>

 <li>Dags can be scheduled and run every minute or hourly/daily</li>

 <li>You can also pause/unpause the dag depending on the requirement</li>

</ul>

<ol>

 <li>Trigger your dag</li>

 <li>Check the logs for additional information</li>

</ol>




<ol start="14">

 <li>Adding tasks to a DAG</li>

</ol>

Adding task_2 by making changes in the code and clicking the ‘Update’ button

Checking logs for additional information

<ol>

 <li>Restructuring the code</li>

</ol>

<h1><strong>Airflow TFX</strong></h1>

<ol>

 <li>Installing ‘requirements.txt’</li>

 <li>You can now see the ‘taxi_pipeline’ dag in the dags folder.</li>

</ol>

<h1>3.      The Tree view looks something like this:</h1>




<ol>

 <li>Successful execution of ‘taxi pipeline’.</li>

</ol>










<ul>

 <li><a href="https://www.tensorflow.org/tfx/guide/examplegen">ExampleGen</a> ingests and splits the input dataset.</li>

 <li><a href="https://www.tensorflow.org/tfx/guide/statsgen">StatisticsGen</a> calculates statistics for the dataset.</li>

 <li><a href="https://www.tensorflow.org/tfx/guide/schemagen">SchemaGen</a> SchemaGen examines the statistics and creates a data schema.</li>

 <li><a href="https://www.tensorflow.org/tfx/guide/exampleval">ExampleValidator</a> looks for anomalies and missing values in the dataset.</li>

</ul>

<h1>Lessons learned</h1>




<ol>

 <li>This lab helps us understand how Airflow allows users to create workflows with high granularity and track the progress as they execute.</li>

 <li>Airflow enables us to have a platform that can run and automate all the jobs on a schedule.</li>

 <li>You can also add/transform jobs as and when required.</li>

</ol>

<h1></h1>

<h1>References</h1>




<ol>

 <li><a href="https://www.tensorflow.org/tfx/tutorials/tfx/airflow_workshop">https://www.tensorflow.org/tfx/tutorials/tfx/airflow_workshop</a></li>

</ol>




<ol>

 <li><a href="https://github.com/tensorflow/tfx/tree/master/tfx/examples/airflow_workshop">https://github.com/tensorflow/tfx/tree/master/tfx/examples/airflow_workshop</a></li>

</ol>