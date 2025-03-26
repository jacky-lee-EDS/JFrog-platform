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
