## Docker-Kubernates Peer Learning
<hr>

### Rahul Kumar

**Docker task**

He created a dag with two tasks in Python language, which consists of tasks of the name - 
    * Create_table - creating the table 
  * Insert_into_table - Inserting the data into a table
  * Created a connection to the database to airflow.
  * Created a docker-compose file with all the different services required.
  * Using the docker-compose command he started the airflow container.
  * He created a connection with Postgres and validated it.

How my approach is different from this? <br>
The above-described approach is similar to mine, but the environment which we used is different, he created the image from airflow:2.5.1 whereas mine is airflow:2.6.1
He made to store all the queries, in a folder from which imported .sql files and ran them using PostgresOperator.

**Kubernetes steps** <br>

* He created a personalized Docker image that includes the Postgres database and the necessary installation tools for connecting to Airflow. He used a docker file to execute instructions prior to installation.
* He starts the Postgres service and deploys the Postgres pod using the Kubectl command.
* Then he started the airflow service, deployed the airflow pod, and produced a dag in the airflow container.
* 
How my approach is different from this? <br>
- He  had created a docker file consisting of some pre-necessary commands  to make a connection with airflow.
Later he also used the same minikube service for the rest of the things.

  

### Gnana Praneeth Kothapally
**Docker task** <br>
* created a dag with two tasks in Python language, which consists of tasks of the name - 
* Create_table - creating the table 
* Insert_into_table - Inserting the data into a table
* Query_task - Querying a table, which validates the entries.
* A connection was established to the database for airflow.
* compiled all the necessary services into a docker-compose file.
* He launched the airflow container by using the docker-compose command.
* He established and verified a connection to Postgres.

How my approach is different from this? <BR>
* The above-described approach is similar to mine, but the environment which we used is different, he created the image from airflow:2.3.2 whereas mine is airflow:2.6.1
* He made to store all the queries, in a folder from which imported .sql files and ran them using PostgresOperator.
* He made a task over there in the dag itself, to validate the entries in Postgres connection.

**Kubernetes steps** <br>

* He created a custom docker image for Postgres with airflow installed in it.
* Pushed the Postgres image and the custom airflow image in docker hub for public access.
* Installed minikube to make a Kubernetes cluster.
* Created the Postgres-deployment.yaml file which contains the pod containing Postgres container.
* Created a service of type clusterIP by running postgres-service.yaml to give access to postgres pods inside the cluster.
* Created persistent volumes dags-storage.yaml to mount the dags folder inside the airflow container to the local directory.
* Created a service of type load balancer by running airflow-service.yaml to access airflow webserver from the local system.
* Accessed the airflow webserver by running the command minikube servi

How my approach is different from this? <br>

We both followed a similar approach, there is not much difference between the two approaches followed.
