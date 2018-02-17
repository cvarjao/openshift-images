
# How to Use

### Prerequisites
* [oc](https://github.com/openshift/origin/releases) client (verified with [v3.6](https://github.com/openshift/origin/releases/tag/v3.6.0))

note: Tested using MacOS 
### Installing
```
oc create sa jenkins
oc policy add-role-to-user view system:serviceaccount:csnr-devops-lab-tools:jenkins
oc annotate sa/jenkins serviceaccounts.openshift.io/oauth-redirectreference.jenkins='{"kind":"OAuthRedirectReference","apiVersion":"v1","reference":{"kind":"Route","name":"jenkins"}}' --overwrite
oc new-app https://github.com/cvarjao/openshift-images.git --context-dir=openshift3/jenkins-2-rhel7 --strategy=docker --name jenkins
```

### Updating Upstream image
```
oc import-image jenkins-2-rhel7:v3.6 --from=registry.access.redhat.com/openshift3/jenkins-2-rhel7:v3.6
```
