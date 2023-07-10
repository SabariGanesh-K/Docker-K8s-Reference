Docker Compose is a tool that allows you to define and manage multi-container applications. It uses a YAML file to specify the services, networks, and volumes required for your application's setup. With Docker Compose, you can easily orchestrate the deployment and management of multiple containers as a single application stack.

The real necessity of Docker Compose can be understood from the following aspects:

Simplified Application Setup: Docker Compose simplifies the process of setting up complex, multi-container applications. Instead of manually configuring and running each container separately, you can define the entire application stack in a single YAML file. This makes it easier to manage dependencies, define service interconnections, and ensure consistent configurations.

Multi-Container Orchestration: Docker Compose allows you to define and manage multiple containers that work together as a cohesive application. You can specify the relationships, dependencies, and communication between the services in your application stack. Docker Compose then handles the orchestration and startup sequence, ensuring that the containers are launched in the correct order.

Development and Testing Environments: Docker Compose is widely used in development and testing environments. It enables developers to quickly spin up the entire application stack, including all the necessary services, databases, and dependencies. This helps ensure that the development environment closely resembles the production environment, reducing issues related to configuration mismatches or missing dependencies.

Reproducible Builds: With Docker Compose, you can create a single configuration file that defines the entire application stack, including its services, volumes, and networks. This configuration can be shared across teams, ensuring consistent builds and deployments. It provides a standardized way to reproduce the same application environment across different development, staging, and production environments.

Scalability and Load Balancing: Docker Compose integrates well with container orchestration platforms like Docker Swarm and Kubernetes. It allows you to define scalable services and configure load balancing for your application. By specifying the desired replica count and scaling parameters in the Docker Compose file, you can easily scale your application up or down as needed.

Easy Deployment and Updates: Docker Compose simplifies the deployment and update process for your application stack. By defining the desired state of the application in the Compose file, you can easily deploy or update the entire stack with a single command. Docker Compose handles the creation, scaling, and updating of containers based on the specified configuration.

Without Docker Compose, the world would miss out on several benefits and conveniences:

Manual Configuration and Orchestration: Developers would need to manually configure and manage the setup and interconnections of multiple containers, which can be time-consuming, error-prone, and difficult to maintain.

Complex Application Stack Management: Managing the lifecycle and relationships between multiple containers would become more challenging, leading to increased operational complexity and potential configuration inconsistencies.

Inconsistent Environments: Developers would face difficulties in ensuring consistent environments across different stages of the application's lifecycle, including development, testing, and production.

Tedious Deployment and Updates: Deploying and updating multi-container applications would require multiple manual steps and potentially introduce human errors, resulting in longer deployment times and increased risks.

In summary, Docker Compose is necessary for simplifying the setup, deployment, and management of multi-container applications. It provides an easy-to-use and standardized approach for defining application stacks, handling dependencies, and orchestrating container lifecycles. Without Docker Compose, the world would miss out on streamlined development workflows, reproducible environments, and efficient management of complex application architectures.



# COMMANDS

## Build the app

    docker compose build

## Run the app

    docker compose up -d

When the app will run, launch the voting app in your browser http://localhost:5000


## List the containers

    docker compose ps

## Look at the db container logs

    docker compose logs -f web-fe


## Compose V2 commands

LS will list the current projects

    docker compose ls

## Let's try to deploy a second version

    docker compose up -d

This fails because we can only run an app a single time

## Deploy a second version using a different project name

Let's now use a project name to see if we can deploy a second version

    docker compose -p test up -d

This fails because the localhost port 5000 is already assigned.

Change the ports value from

    - "5000:80"

to

    - "5001:80"

## Deploy again

    docker compose -p test up -d

How many versions do we have running?

    docker compose ls

## Cleanup

    docker compose down
    docker compose ls
    docker compose -p test down
    docker compose ls