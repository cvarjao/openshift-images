
# How to Use

### Prerequisites
* [oc](https://github.com/openshift/origin/releases) client (verified with [v3.6](https://github.com/openshift/origin/releases/tag/v3.6.0))
### Installing
```
oc new-app https://github.com/cvarjao/openshift-images.git --context-dir=openshift3/jenkins-2-rhel7 --strategy=docker --name jenkins
```

