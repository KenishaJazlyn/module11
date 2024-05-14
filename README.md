#### Reflection 1
1. Compare the application logs before and after you exposed it as a Service.
    Yes, there is a difference because once the service is exposed, it can receive and log incoming requests. For example, if the hello-node service is repeatedly refreshed, the log will record each of these requests.
    ![alt text](image.png)
2. Notice that there are two versions of `kubectl get` invocation during this tutorial section.
The first does not have any option, while the latter has `-n` option with value set to
`kube-system`.
What is the purpose of the `-n` option and why did the output not list the pods/services that you
explicitly created?
> Hint: Do some reading about [Namespace in Kubernetes
documentation](https://kubernetes.io/docs/concepts/overview/working-with-objects/namespaces
/).
To make notes of your experience and reflection, please do the following:

In Kubernetes, the -n or --namespace option in kubectl commands specifies the namespace to target, isolating resources within the cluster. If we run kubectl get without specifying a namespace, it defaults to the default namespace and lists resources like pods or services created there. When the -n kube-system option is used, kubectl targets the kube-system namespace, which contains system-level resources critical for Kubernetes itself to operate, hence not showing the user-created services or pods unless they were specifically deployed in this namespace.

#### Reflection 2
1. What is the difference between Rolling Update and Recreate deployment strategy?
> Hint: Read the Deployments documentation.
2. Try deploying the Spring Petclinic REST using Recreate deployment strategy and document
your attempt.
3. Prepare different manifest files for executing Recreate deployment strategy.
4. What do you think are the benefits of using Kubernetes manifest files? Recall your experience
in deploying the app manually and compare it to your experience when deploying the same app
by applying the manifest files (i.e., invoking `kubectl apply -f` command) to the cluster.
5. (Optional) Do the same tutorial steps, but on a managed Kubernetes cluster (e.g., GCP). You
need to provision a Kubernetes cluster on Google Cloud Platform. Then, re-run the tutorial steps
(Hello Minikube and Rolling Update) on the remote cluster. Document your attempt and highlight
the differences and any issues you encountered.