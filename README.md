# Deploy ArgoCD no K8S
- Criar NS para instalação
  
  ```kubectl create namespace argocd```
- Cria recursos

  ```kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml```
- Lista recursos criados

  ```kubectl get all -n argocd```
- Senha de acesso do usuário admin

  ```kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d; echo```
- Port Forward da porta 8443(localhost) para o service argocd porta 443

  ```kubectl port-forward -n argocd service/argocd-server 8443:443```

