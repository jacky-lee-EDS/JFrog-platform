1. 使用xsmall調整的custom-values.yaml  
---
2. 在GKE上建置  
---
3. 為了測試JAS功能  
---
4. 建置指令
```
helm repo add jfrog https://charts.jfrog.io
helm repo update
helm upgrade --install jfrog-platform --namespace jfrog-platform --create-namespace jfrog/jfrog-platform -f custom-values.yaml 
```
5. 檢查狀態
```
watch -n1 "kubectl get all -n jfrog-platform"
kubectl events -n jfrog-platform
helm get values jfrog-platform -n jfrog-platform -o yaml 
```
6. 刪除指令
```
helm uninstall jfrog-platform -n jfrog-platform
watch -n1 "kubectl get all -n jfrog-platform"
kubectl get pvc -n jfrog-platform -o name | xargs -n 1 kubectl -n jfrog-platform delete 
```
