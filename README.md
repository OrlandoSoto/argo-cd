## REQUIREMENTS:

- local kubernetes cluster, e.g https://k3d.io/stable/#releases

- kubectl https://kubernetes.io/docs/tasks/tools/install-kubectl-linux/

## STEPS

- Create a namespace for argocd `kubectl create namespace argocd`

- Obtain installation yaml `curl -O https://raw.githubusercontent.com/argoproj/argo-cd/heads/master/manifests/install.yaml`

- Install argo `kubectl apply -n argocd -f install.yaml`

- Verify pods have been created by running `kubectl get po -n argocd` and `kubectl get svc -n argocd`

- Run this command to view argocd on your browser `kubectl port-forward -n argocd svc/argocd-server 8080:80`

- Open your browser and go to either `localhost:8080` or `127.0.0.1:8080`

- You should see the argocd UI