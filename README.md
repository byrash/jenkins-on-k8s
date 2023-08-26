```
k create ns jenkins && k apply -f sa.yaml -f pv.yaml -f deploy.yaml -f svc.yaml -f trafeik.yaml -f ingress.yaml
```

To get node IP

```
 kubectl describe node | grep Addresses: -A 4
```

Trafeik Dashboard

```
http://192.168.106.2:30001/dashboard/#/
```

Jenkins URL

```
http://192.168.106.2:30000
```

Jenkins Admin pwd (Use first line)

```
k logs -n jenkins <<PODNAME>> | grep -i -B 2 "This may also"
```

or

```
 k exec -n jenkins pods/<<PODNAME>> -- cat /var/jenkins_home/secrets/initialAdminPassword
```
