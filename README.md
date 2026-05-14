# dex

Add helm repo:
```bash
helm repo add dex https://charts.dexidp.io
```

Install dex:
```bash
helm upgrade -i dex dex/dex \
  --namespace dex \
  --create-namespace \
  --values values.yaml \
  --wait
```

---

Generate Hash password:
```bash
htpasswd -bnBC 10 "" yourpassword | tr -d ':\n' ; echo
```

Create ClusterRoleBinding for flux-web-admin:
```
kubectl apply -f - <<EOF
apiVersion: rbac.authorization.k8s.io/v1
kind: ClusterRoleBinding
metadata:
  name: flux-web-admin
subjects:
  - kind: User
    name: admin@example.com
    apiGroup: rbac.authorization.k8s.io
roleRef:
  kind: ClusterRole
  name: flux-web-admin
  apiGroup: rbac.authorization.k8s.io
EOF
```









