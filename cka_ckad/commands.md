
---

- Shortcuts

```bash


printf "\nalias k='kubectl'\n\
alias kgn='k get no'\n\
alias kgp='k get po'\n\
alias kgns='k get ns'\n\
alias kgcs='k get cs'\n\
alias kgd='k get deploy'\n\
alias kd='k describe'\n\
alias kar='k api-resources'\n\
alias kcgc='k config get-contexts'\n\
alias kcuc='k config use-context'\n\
"\
>> ~/.bashrc
```
---

```bash
$ kubectl get pods --show-labels
```

---

```bash
$ kubectl run --generator=run-pod/v1 nginx --image=nginx --dry-run=true -o yaml > nginx_pod.yaml
```

---


```bash
$ kubectl run --generator=run-pod/v1 nginx --image=nginx --replicas=2 --dry-run=true -o yaml >> nginx_deploy.yaml
```

---

```bash
$ kgp --show-labels
NAME                     READY   STATUS    RESTARTS   AGE     LABELS
nginx-5578584966-lggjj   1/1     Running   0          9m36s   pod-template-hash=5578584966,run=nginx
nginx-5578584966-sflrp   1/1     Running   0          9m36s   pod-template-hash=5578584966,run=nginx
```

---

```bash

$ kgp -L env
NAME                     READY   STATUS    RESTARTS   AGE   ENV
nginx-5578584966-lggjj   1/1     Running   0          23m   prod
nginx-5578584966-sflrp   1/1     Running   0          23m   
```

---

```bash
$ ka deploy nginx test="true"
deployment.apps/nginx annotated

$ kgd nginx -o yaml | grep -A 2 anno
  annotations:
    deployment.kubernetes.io/revision: "1"
    test: "true"

```

---

```bash

```























---
- Blogs:
  - https://ahmet.im/blog/kubectl-aliases/