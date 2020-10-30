# OTUS SA-2020-09 homework #02

## Installation instructions
* `helm repo add bitnami https://charts.bitnami.com/bitnami` (https://github.com/bitnami/charts/tree/master/bitnami/postgresql);
* `helm install otusapp-db bitnami/postgresql`;
* `helm dependency update ./otusapp-chart`
* DRY RUN: `helm install otusapp ./otusapp-chart --dry-run`
* INSTALL: `helm install otusapp ./otusapp-chart`
* UNINSTALL: `helm uninstall otusapp` & `kubectl delete all --all` & it's needed to remove old pvc instances (`kubectl get pvc` & `kubectl delete pvc {pvc_name}`).

The job (initdb.yaml) starts with a 10 second delay.

## Available endpoints

* `GET` http://arch.homework/otusapp/ksalov/
* `GET` http://arch.homework/otusapp/ksalov/health/
* `GET` http://arch.homework/otusapp/ksalov/version/
* `POST` http://arch.homework/otusapp/ksalov/user
* `GET` http://arch.homework/otusapp/ksalov/user/{user_id}
* `PUT` http://arch.homework/otusapp/ksalov/user/{user_id}
* `DELETE` http://arch.homework/otusapp/ksalov/user/{user_id}

## Postman tests
`newman run user_api.json`
