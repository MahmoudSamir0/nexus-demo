## clone this repo 
 ```shell script
git clone https://github.com/MahmoudSamir0/nexus-demo.git
```
- enter the file of repo

 **copy this command**

```shell script
  cd nexus-demo
```

```shell script
 kubectl apply -f namespace.yml
```

```shell script
kubectl apply -f class.yml
```


```shell script
kubectl apply -f pv.yml
```


```shell script
kubectl apply -f pvc.yml
```


```shell script
kubectl apply -f service.yml
```

```shell script
kubectl apply -f deployment.yml
```

## now you pod is ready 

```shell script
kubectl get po -n nexus
```

```shell script
NAME                     READY   STATUS    RESTARTS      AGE
nexus-7c9c48876f-g98bv   1/1     Running   4 (20m ago)   22h
```

## open logs of the pod
 
```shell script
kubectl logs -f  -n nexus nexus-7c9c48876f-g98bv

```
## It will print this message to confirm that the pod is ready
```shell script
-------------------------------------------------

Started Sonatype Nexus OSS 3.49.0-02

-------------------------------------------------
2023-03-16 18:10:00,071+0000 INFO  [quartz-10-thread-3] *SYSTEM org.sonatype.nexus.quartz.internal.task.QuartzTaskInfo - Task 'Storage facet cleanup' [repository.storage-facet-cleanup] state change WAITING -> RUNNING
2023-03-16 18:10:00,125+0000 INFO  [quartz-10-thread-3] *SYSTEM org.sonatype.nexus.quartz.internal.task.QuartzTaskInfo - Task 'Storage facet cleanup' [repository.storage-facet-cleanup] state change RUNNING -> WAITING (OK)
2023-03-16 18:10:36,134+0000 INFO  [qtp2082078826-108] *UNKNOWN org.apache.shiro.session.mgt.AbstractValidatingSessionManager - Enabling session validation scheduler...
2023-03-16 18:10:36,183+0000 INFO  [qtp2082078826-108] *UNKNOWN org.sonatype.nexus.internal.security.anonymous.AnonymousManagerImpl - Loaded configuration: OrientAnonymousConfiguration{enabled=true, userId='anonymous', realmName='NexusAuthorizingRealm'}
```
## service port is 30011

## login as admin 
username : ```admin```
the password 

```
kubectl exec -it  -n nexus  nexus-7c9c48876f-g98bv -- /bin/bash
```

```
cat sonatype-work/nexus3/admin.password
```
## now change your password

# congratulation nexus is ready 
# *NOTE* It will take a long time to get ready
