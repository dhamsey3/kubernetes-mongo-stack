
# Single application cluster in a kubernetes set up

_Create a Kubernetes cluster:_

You can use a cloud provider like Google Cloud, AWS or Azure to create a Kubernetes cluster or use a tool like Minikube for a local development setup.
Create a Docker image of your application:

You will need to create a Docker image of your application, which includes all the necessary dependencies and configurations.

_Push the Docker image to a container registry:_

You need to push your Docker image to a container registry like Docker Hub or Google Container Registry.

_Write a Kubernetes deployment YAML file:_

You need to create a YAML file that describes how to deploy your application on Kubernetes. This file should include the details of the container image, port mappings, environment variables, and other necessary configuration.

_Create a Kubernetes deployment:_

Run the _kubectl apply -f <deployment-file.yaml>_ command to create a Kubernetes deployment using the YAML file you created in step 4.
Expose the Kubernetes deployment as a service:

Run the kubectl expose deployment <deployment-name> --port=<container-port> --target-port=<container-port> --type=LoadBalancer command to expose your Kubernetes deployment as a service. This will create a load balancer that maps to the container port specified in the YAML file.

_Verify the deployment:_

Use the _kubectl get pods_ command to verify that your application is running in a pod. Use the kubectl get services command to verify that the service is created and has an external IP address assigned.
  
_Access your application:_

Visit the external IP address assigned to your service in a web browser to access your application.

  The end result should look like the picture below.

<img width="1164" alt="Screenshot 2023-04-02 at 20 16 24" src="https://user-images.githubusercontent.com/73405591/229371245-1692b2ac-d4c5-456b-b983-6fa1bfd115ab.png">
