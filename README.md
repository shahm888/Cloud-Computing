# Cloud-Computing
Kubernetes is open-source orchestration software for deploying, managing, and scaling containers.
Here, I have done handson experience on Minikube, is a tool that makes it easy to run Kubernetes locally. Minikube runs a single-node Kubernetes cluster inside a Virtual Machine (VM)(I used VM ware work stationplayer ) on your laptop for users looking to try out Kubernetes or develop with it day-to-day.

Contain:week 3.pdf
Creating running and sharing a container image
1. Create the app
a. Creating a trivial Node.js app
b. Creating a Docker file for the image
2. Building the container image
3. Running the container image
Exploring the inside of a running container
Pushing the image to an image registry

Contain week 4.pdf
RUNNING YOUR FIRST APP ON KUBERNETES
Step :1 Starting a Minikube virtual machine
Step:2Displaying cluster information
Step:3 Deploying your Node.js app
Step:4 Listing pods.
Step:5 Creating a Service object & Listing Services
Step:6 Horizontally scaling the application
Step:7 Examining what nodes your app is running on.

Contain week 5.pdf

Creating a simple YAML descriptor for a pod,
Viewing application logs,
Sending requests to the pod,
Specifying labels when creating a pod,
Overwrite labels:
Listing pods using a label selector,
Using labels for categorizing worker nodes,
Looking up an object’s annotations,
Discovering other namespaces and their pods,
Creating a namespace
Managing objects in other namespaces,
Deleting a pod by name,
Deleting pods by deleting the whole namespace,
Deleting all pods in a namespace, while keeping the namespace,
Deleting (almost) all resources in a namespace,

Contain week 6.pdf
Create Nodejs app called “app.js” and Docker file
Create Docker image
Push the docker image to docker hub.
Creating an HTTP-based liveness probe
Create a pod from the kubia-liveness-probe.yaml
Seeing a liveness probe in action
Here the kubia-livness pod restarted 2 times. We can obtain the logs of previous container by
running kubectl logs “kubia-liveness” --previous.
Description after pod restarted:
Configuring additional properties of the liveness probe
liveness probe with an initial delay
Pod describe shows the delay of 15s
Introducing Replication Controllers
Creating a Replication Controller
Seeing the Replication Controller in action
Getting information about a Replication Controller
Displaying details of a Replication Controller with kubectl describe
Moving pods in and out of the scope of a Replication Controller
Changing the pod template
Horizontally scaling pods
Scaling down with the kubectl scale command
Deleting a Replication Controller
Creating and examining a Replica Set
Using the Replicase’s more expressive label selectors
Wrapping up Replica Sets
Daemon Set:
Adding the required label to your node (s
Removing the required label from the node
Defining a Job resource
Running multiple pod instances in a Job
Cronjob
Understanding how scheduled jobs are run

Contain week 11.pdf
Setting environment variables for a container
Making the interval in your fortune image configurable through an- n environment variable
Step-1: Fortune script with interval configurable through environment variable.
Step-2: Docker file for the updated fortune image
Step-3: Build Docker image and push the image to DockerHub.
Step-4: Create pod from fortune-pod-env.yaml
Step-5: Logs to prove environment variable usage in Pod’s container

 Decoupling configuration with a ConfigMap
Step-1: Different ways to create ConfigMap
a) Using the kubectl create configmap command and display yaml.
b) Creating a ConfigMap entry from yaml.
c) Creating a ConfigMap entry from the contents of a file
d) Creating a ConfigMap from files in a directory
e) Combining different options
Step-2: Passing a ConfigMap entry to a container as an environment variable
Logs to prove:
Step-3: Passing all entries of a ConfigMap as environment variables at once
Step-4: Passing a ConfigMap entry as a command-line argument
Step-5: Using a configMap volume to expose ConfigMap entries as files
a) Creating the ConfigMap
b) Using the ConfigMap’s entries in a volume
c) Exposing certain ConfigMap entries in the volume
d) Setting file permissions
Step-6: Updating an app’s config without having to restart the app
a) Editing a ConfigMap
b) Signaling Nginx to reload the config
c) Understanding how the files are updated atomically

 USING SECRETS TO PASS SENSITIVE DATA TO CONTAINERS
Introducing the default token Secret
Creating a Secret
Comparing ConfigMaps and Secrets
Using the Secret in a pod.

Understanding secret volumes are stored in memory
Understanding image pull Secrets
Creating a Secret for authenticating with a Docker registry
Using the docker-registry Secret in a pod definition

contain week 12.pdf

Exposing metadata through environment variables
Downward API used in environment variables: downward-api-env.yaml
If your "downward" pod is not coming up and getting stuck at "ContainerCreating", then this
is due the "CPU & Memory" limit set under resources in "downward-api-env.yaml" file. The
limits are really low for today's VM on which your kubernetes cluster is running. So that is the
reason the creation of pod is failing.
Solution:
Remove the resources in downward-api-env.yaml file.
Environment variables in the downward pod


Passing metadata through files in a downwardAPI volume
Pod with a downwardAPI volume: downward-api-volume.yaml
Files in the downwardAPI volume
Displaying labels and annotations in the downwardAPI volume

Exploring the Kubernetes REST API
Accessing the API server through kubectl proxy
Exploring the Kubernetes API through the kubectl proxy
Exploring the batch API group’s REST endpoint
You probably have no Job resources deployed in your cluster, so the items array will be empty.
You can try deploying the Job in Chapter08/my-job.yaml and hitting the REST endpoint again to
get the same output in a item array .
Listing all Job instances in the cluster
Retrieving a specific Job instance by name
