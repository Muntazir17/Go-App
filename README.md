# Go Web App

The Go Web App is a sample application that demonstrates the following key features:
- **High Performance**: Leveraging Go for optimized speed and concurrency.
- **Scalability**: Deployed on AWS EKS, ensuring reliable scaling based on demand.
- **Microservices Architecture**: Implemented using containerization for flexibility and maintainability.

![Go Web App](diagram.png)
## Continous Integration with GitLab

This project utilizes GitLab CI for continuous integration, ensuring that code changes are automatically tested and validated before deployment. The CI pipeline consists of the following stages:

1. **Build**: Compiles the Go application.
2. **Test**: Runs automated tests to validate the functionality of the application.
3. **Code Quality**: Integrates static code analysis using `golangci-lint` to maintain code quality.
4. **Docker Build and Push**: Builds the Docker image and pushes it to the container registry.
5. **Update Helm Chart**: Updates the Helm chart with the new image tag for seamless deployment.

The GitLab CI configuration is defined in the `.gitlab-ci.yml` file located at the root of the repository.

## Continuous Deployment with ArgoCD

For continuous deployment, we use **ArgoCD**, a declarative GitOps continuous delivery tool for Kubernetes. The deployment process involves the following steps:

1. **GitOps Approach**: The application configuration is stored in a Git repository, allowing ArgoCD to monitor changes.
2. **Helm Chart**: The application is packaged using Helm charts, enabling easy updates and rollbacks.
3. **Automated Synchronization**: ArgoCD automatically synchronizes the Kubernetes cluster state with the desired state defined in the Git repository, ensuring the application is always up-to-date.
