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

- You should see the argocd UI, login with default username `admin`

- Run this command to get the default password in plain unencoded text `kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d`

- See my other repos to deploy a simple nginx app using argocd

<img width="1312" height="882" alt="argocd" src="https://github.com/user-attachments/assets/c0458728-a547-476a-8aae-a58fced70806" />

