# Single Application Cluster Setup in Kubernetes

This guide outlines the process for deploying a single application within a Kubernetes cluster, from cluster creation to application access.

## Step 1: Create a Kubernetes Cluster

Begin by setting up a Kubernetes cluster using one of the methods below:

- **Cloud Providers**: Utilize Google Kubernetes Engine (GKE), Amazon Elastic Kubernetes Service (EKS), or Azure Kubernetes Service (AKS) for cloud-based clusters.
- **Local Development**: Use Minikube for a local development environment, simulating a Kubernetes cluster on a machine.

## Step 2: Dockerize The Application

Create a Docker image for the application:

- Package the application into a Docker image, ensuring all necessary dependencies and configurations are included. The Dockerfile should be properly configured for the application's environment.

## Step 3: Push the Docker Image to a Registry

Upload the Docker image to a container registry:

- Push the Docker image to a registry such as Docker Hub or Google Container Registry to make it accessible for Kubernetes deployment.

## Step 4: Write a Kubernetes Deployment YAML File

Define the application's deployment on Kubernetes:

- Draft a YAML file (`deployment-file.yaml`) that specifies the deployment details, including the Docker image, ports, environment variables, and other configurations.

## Step 5: Create a Kubernetes Deployment

Deploy the application using `kubectl`:

- Run `kubectl apply -f <deployment-file.yaml>` to deploy the application, replacing `<deployment-file.yaml>` with the path to the YAML file.

## Step 6: Expose The Deployment as a Service

Make the deployment accessible:

- Expose the deployment by executing:

Replace `<deployment-name>` and `<container-port>` with specific details to create a LoadBalancer service for external traffic.

## Step 7: Verify the Deployment

Check the status of the deployment:

- Confirm the application's pod is running with `kubectl get pods`.
- Check the service creation and the external IP assignment with `kubectl get services`.

## Step 8: Access The Application

Visit the deployed application:

- Use a web browser to navigate to the external IP address assigned to the service and access the application.

Following these steps will get the application deployed and accessible within a Kubernetes cluster.


<img width="1164" alt="Screenshot 2023-04-02 at 20 16 24" src="https://user-images.githubusercontent.com/73405591/229371245-1692b2ac-d4c5-456b-b983-6fa1bfd115ab.png">
