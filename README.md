## OBJECTIVE 
Orchestrating a CICD pipeline using Github actions to build and test a java program using gradle,and then after building a docker image we push it to a public docker repository.

## ACTIONS TAB
I went to the actions tab in this repository and picked a template for my workflow called **ci.yaml** The workflow is self explanatory, when you push or make a pull request to the master, the job that is defined gets started. I commited my workflow file to a new branch, then i made a pull request to the master branch and you can see below the simple workflow 
![BUILD JOB](/images/image1.png)

##### build the project

    ./gradlew build

##### build Docker image called java-app. Execute from root

    docker build -t java-app .
    
##### push image to repo 

    docker tag java-app demo-app:java-1.0
    
