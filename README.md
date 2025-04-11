## OBJECTIVE 
Orchestrating a CICD pipeline using Github actions to build and test a java program using gradle,and then after building a docker image we push it to a public docker repository.

## ACTIONS TAB
I went to the actions tab in this repository and picked a template for my workflow called **ci.yaml** The workflow is self explanatory, when you push or make a pull request to the master, the job that is defined gets started. I commited my workflow file to a new branch, then i made a pull request to the master branch and you can see below the simple workflow 
![BUILD JOB](/images/image1.png)

## DOCKER BUILD AND PUSH
The next step in the pipeline is to build our docker image and push it to a public repository in dockerhub. I added the action for this in my **ci.yml** file and saved my dockerhub secrets in the repository.
I encountered this error after commiteing to the master branch 
![PUSH DOCKER](/images/buildfail.png)

I solved this issue with editing my Dockerfile and changing the specified path
![BUILD&PUSH DOCKER](/images/success.png)

Let's verify the image was pushed to my public repository in dockerhub
![DOCKERHUB](/images/Dockerhub.png)


##### build the project

    ./gradlew build

##### build Docker image called java-app. Execute from root

    docker build -t java-app .
    
##### push image to repo 

    docker tag java-app demo-app:java-1.0
    
