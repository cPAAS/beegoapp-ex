# beegoapp

beegoapp is a chat app based on the beego framework.

1. sti-go builder image

it is from the `sti-go` repo.

2. create beegoapp

`beegoapp/openshift/create-new-app.sh` will create everything using the template.

3. sti scripts

app provides the sti scripts inside to override them from sti-go builder image.

issue: how to use the save-artifacts to solve the go dependency issue ?
currently the dependent modules are placed along with the app code.

4. Jenkins job config

`Change Merged` event will trigger a deploy job, it will:

- Perform a build in openshift, there are two methods:

method 1: Shell script
```
curl -k --header "" https://master1.ceyes.os:8443/oapi/v1/namespaces/mytest/buildconfigs/beego-example/webhooks/genericsecet101/generic
```

method 2 (recommended):
```
Openshift pipeline plugin: Perform builds in OpenShift
specify the BuildConfig to trigger.
```

# other app (TBD)
