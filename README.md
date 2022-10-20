## Credits

This kick ass content is from https://github.com/DickChesterwood/istio-fleetman and his course (highly recommended) is on Udemy.

This is guide is largely notes from my experience, including some adjustments to deployments.


## CCI Training

1. Clone this repo (fork not needed, but optional)
2. Install `minikube`
3. Jump into `_coursework`


** NOTE: MACOS DOCKER USERS **

Docker does not support ports routing so the `minikube ip` is useless.

instead use `minikube service <service-name> --url &` (must run in background) which spits out a tunnel URL to use.

```
 minikube service kiali --url -n istio-system &
 minikube service fleetman-webapp --url &
 minikube service tracing  --url -n istio-system & # you can view embed jaeger traces in kilai too
 minikube service grafana  --url -n istio-system &
 ...
```
** to quickly kill all 5 background jobs **
```
for i in {1..5};do
 kill %$i
done

```