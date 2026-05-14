# dex

Add helm repo:
```bash
helm repo add dex https://charts.dexidp.io
```

Install dex:
```bash
helm upgrade -i dex --wait dex/dex \
  --namespace dex \
  --create-namespace
```

---

Generate Hash password:
```bash
htpasswd -bnBC 10 "" yourpassword | tr -d ':\n' ; echo
```

