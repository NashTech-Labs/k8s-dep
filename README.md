#### Python client for the kubernetes API

# crud operations on deployment

we can use the client module to interact with the resources. 

`Resources:` kubectl get commands are used to create deployment using yaml files in a cluster for eg:

To create the deployment in the cluster, we fire following kubectl command:

```kubectl apply -f deployment.yaml``` 

Get the list of all deployment

`kubectl get deployment`

But In Python, we instantiate AppsV1Api class from client module:

`client_api = client.AppsV1Api()`         

Here I've created the client with it's respective class AppsV1Api
and storing in a var named as client_api. so furture we can use it.

`KubeConfig:` to pass the on local cluster e.g minikube we use bellowcommand: 

`config. load_kube_config()`

#### Authenticating to the Kubernetes API server

But what if you want to list all the automated deployment of a GKE Cluster, you must need to authenticate the configuration

`configuration.api_key = {"authorization": "Bearer" + bearer_token}` 

I've used Bearer Token which enable requests to authenticate using an access key.

#### Creating deployment:

Call the funcation create_deployment(cluster_details, deployment)

And run following command:

`python3 dep-crud.py`

#### get the list of all deployment:

call the funcation   get_deployments(cluster_details)

`python3 dep-crud.py`

#### update the deployment:

call the funcation   update_deployment(cluster_details, deployment)

`python3 dep-crud.py`

#### delete deployment:

call the funcation  delete_deployment(cluster_details, deployment)

`python3 dep-crud.py`
