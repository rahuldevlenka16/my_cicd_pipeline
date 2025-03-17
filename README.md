# my_cicd_pipeline

image build:

    docker build -t my-java-app .

    docker tag my-java-app rahuldevsecops/my-java-app:latest


docker hub command:
    
    docker login -u rahuldevsecops

    generate app pass and use it 

    docker push rahuldevsecops/my-java-app:latest

to run the docker app:
    
    docker run -rm -p 8080:80 rahuldevsecops/my-java-app:latest


--------------------------------------------------------------

kubectl commands:

    kubectl apply -f my-java-deployment.yaml #it contains for deployment and service config

    
    kubectl get pods
    
    kubectl get svc
    
    go run the app:
        localhost:<NodePort>
    
    Extra:
        kubectl port-forward service/my-java-app-service 8081:8081 
        # this will let access the service in port 8081 instead of node port



cleaning:

    kubectl delete deployments <deplyoment-name>
    kubectl delete deployments --all
    kubectl delete service <service-name>
    kubectl delete service --all
