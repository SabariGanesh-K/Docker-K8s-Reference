In Kubernetes, a namespace is a virtual cluster that provides a way to partition and isolate resources within a Kubernetes cluster. It allows you to create multiple virtual clusters within a single physical cluster, enabling teams or applications to have their own isolated environments.

The necessity and use cases of Kubernetes namespaces are as follows:

Resource Isolation: Namespaces provide resource isolation within a Kubernetes cluster. By creating separate namespaces, you can ensure that resources like pods, services, and storage volumes are isolated and not shared across namespaces. This allows multiple teams or applications to coexist within the same cluster without interfering with each other.

Multi-Tenancy: Namespaces enable multi-tenancy in Kubernetes. Different teams or projects can have their own namespaces, providing logical separation and independent management of resources. This ensures that resources allocated to one namespace do not impact or conflict with resources in other namespaces.

Access Control and RBAC: Kubernetes provides Role-Based Access Control (RBAC) mechanisms at the namespace level. You can define different roles and permissions for users or groups within a namespace, allowing fine-grained access control. This enables secure and controlled access to resources based on namespaces, ensuring proper segregation of responsibilities and enforcing security policies.

Resource Quotas and Limits: Namespaces allow you to set resource quotas and limits for specific namespaces. This helps in enforcing resource usage and preventing one namespace from consuming excessive resources, ensuring fair resource allocation among different teams or applications.

Development and Testing Environments: Namespaces can be used to create separate environments for development, testing, and staging within the same cluster. Each environment can have its own namespace, allowing teams to test and validate their applications without impacting the production environment or other namespaces.

Simplified Management: Namespaces provide a logical organization and management structure for resources. It simplifies the management and monitoring of resources by grouping them into separate namespaces. This makes it easier to navigate, troubleshoot, and manage applications and services within a large Kubernetes cluster.

Resource Sharing and Collaboration: Namespaces allow for controlled resource sharing and collaboration between teams or projects. Selected resources within a namespace can be shared or made accessible to other namespaces, enabling collaboration while still maintaining isolation and security.

In summary, Kubernetes namespaces are necessary for resource isolation, multi-tenancy, access control, and management of resources within a Kubernetes cluster. They provide a way to logically divide and segregate resources, enabling teams or applications to operate independently while sharing the same underlying infrastructure. Namespaces play a crucial role in creating secure, scalable, and manageable Kubernetes environments.


## Get namespaces

Open a terminal and get the currently configured namespaces.

    kubectl get namespaces
    kubectl get ns

## Get the pods list

Get a list of all the installed pods.

    kubectl get pods

You get the pods from the default namespace.  Try getting the pods from the docker namespace.  You will get a different list.

    kubectl get pods --namespace=kube-system
    kubectl get pods -n kube-system

## Change namespace

Change the namespace to the docker one and get the pods list.

    kubectl config set-context --current --namespace=kube-system

## Get the pods

    kubectl get pods

## Now change back to the default namespace

    kubectl config set-context --current --namespace=default
    kubectl get pods

## Create and delete a namespace

    kubectl create ns [name]
    kubectl get ns
    kubectl delete ns [name]