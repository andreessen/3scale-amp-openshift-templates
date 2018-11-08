
This repository contains the OpenShift Templates for the Red Hat 3scale API Management Platform.
Use amp.yml. Rollout resume order is the following:
```sh
$ for x in backend-redis system-memcache system-mysql system-redis zync-database; do echo Resuming dc:  $x; sleep 2; oc rollout resume dc/$x; done
```
wait for provisioning
```sh
$ for x in backend-listener backend-worker; do echo Resuming dc:  $x; sleep 2; oc rollout resume dc/$x; done
```
wait for provisioning
```sh
$ oc rollout resume dc/system-app
```
wait for provisioning
```sh
$ for x in system-resque system-sidekiq backend-cron system-sphinx; do echo Resuming dc:  $x; sleep 2; oc rollout resume dc/$x; done
```
wait for provisioning
```sh
$ for x in apicast-staging apicast-production; do echo Resuming dc:  $x; sleep 2; oc rollout resume dc/$x; donedc/$x; done
```
wait for provisioning
```sh
$ for x in apicast-wildcard-router zync; do echo Resuming dc:  $x; sleep 2; oc rollout resume dc/$x; done
```
wait for provisioning
