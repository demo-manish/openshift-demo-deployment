# openshift-demo-deployment

**Create project**
`oc project development`

**Create new app** 
* * This will create buildconfig, deployment, and service
`oc new-app --name myapp <git url>`

**Expose Service through route**
`oc expose myapp`

**Create pipeline**
`oc apply -f pipeline.yaml`

**Create DeploymentConfig for QA**
`oc create dc myapp --image=172.30.18.201:5000/development/myapp:promoteQA`
`oc expose dc myapp --port=8080`
`oc expose service myapp --name=myapp-qa`

**Create DeploymentConfig for IMPL**
`oc create dc myapp --image=172.30.18.201:5000/development/myapp:promoteImpl`

**Give jenkins user permission to pull image**
`oc policy add-role-to-user system:image-puller system:serviceaccount:<projectname>:jenkins -n <namespace>`

**Give jenkins user permission to edit on qa and impl projects**
`oc policy add-role-to-user edit system:serviceaccount:<projectname>:jenkins -n <namespace>`