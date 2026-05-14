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

