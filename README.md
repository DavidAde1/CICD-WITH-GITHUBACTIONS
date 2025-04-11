## OBJECTIVE 
Orchestrating a CICD pipeline using Github actions to build and test a java program using gradle,and then after building a docker image we push it to a public docker repository.


##### build the project

    ./gradlew build

##### build Docker image called java-app. Execute from root

    docker build -t java-app .
    
##### push image to repo 

    docker tag java-app demo-app:java-1.0
    
