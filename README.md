# Kubernetes and Docker Guide
This repository aims to dump all my learnings in a comprehensive way to help others understand containerization with Kubernetes and Docker. 

## Why Businesses Love Kubernetes So Much!
First, let's understand why Kubernetes has so much hype, and why it is the first choice when it comes building and managing applications. The following section breaks down the complicated jargons into smaller understandable components. 

## Kubernetes Cluster Structure

```
  Cluster
├── Node (Master Node)
│   ├── Control Plane Components (API server, scheduler, etc.)
└── Node (Worker Node)
    ├── Pod
    │   ├── Container
    │   └── Container
    ├── Pod
    │   ├── Container
    └── Pod
        ├── Container
```


### Components Explained

- **Cluster**: The entire Kubernetes environment containing multiple nodes.
- **Node**:
  - **Master Node**: Manages the cluster, handling the control plane components responsible for the overall state and operations of the cluster.
  - **Worker Node**: Runs the application workloads inside pods. Multiple worker nodes can exist in a cluster. How much memory and cpu will be assigned to these Worker Nodes is communicated through configuration file which is discussed in the next section.
  
- **Control Plane Components**:
  - **API Server**: The front end of the Kubernetes control plane, exposes the Kubernetes API.
  - **Scheduler**: Assigns pods to nodes based on resource requirements and constraints.
  - **Controller Manager**: Manages controllers that handle routine tasks to ensure the desired state of the cluster.
  - **etcd**: A distributed key-value store for storing all cluster data.
  
- **Pod**: The smallest deployable unit in Kubernetes, encapsulates one or more containers.

- **Container**: A lightweight, standalone executable package that includes everything needed to run a piece of software.

## Container Structure


```
Container
├── Application Code
├── Runtime (e.g., Python, Node.js)
├── Dependencies (libraries, frameworks)
├── System Tools (basic utilities)
├── Configuration Files (settings, environment variables)
├── Libraries and Binaries
```

### Components Explained

- **Application Code**: The actual codebase for the application running inside the container.
- **Runtime**: The environment needed to run the application code, such as Python or Node.js.
- **Dependencies**: Libraries and frameworks required by the application to function.
- **System Tools**: Basic utilities and tools available within the container.
- **Configuration Files**: Settings and environment variables necessary for the application’s configuration.
- **Libraries and Binaries**: Additional software packages and binaries needed by the application and its dependencies.


## But Wait! How Does Kubernetes Manage All This? 
Here comes the magic. Whatever state we want to maintain within the cluster is communicated to Kubernetes through a configuration file typically written in YAML. 

### Configuration File (YAML)

A YAML configuration file allows you to define the desired state of various Kubernetes resources such as pods, deployments, services, and more. Here is a brief overview of what you can define in a YAML file:

- **Deployments**: Define the desired state for your applications, such as the number of replicas, the container image to use, and update strategies.
- **Services**: Define how to expose your pods to the network, enabling communication between different parts of your application.
- **ConfigMaps and Secrets**: Manage configuration data and sensitive information that your applications need.
- **CronJobs**: Schedule tasks to run at specific times or intervals.
- **Global Settings**: Specify configurations that apply cluster-wide, such as resource quotas and limits.
