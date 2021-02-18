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

**Create DeploymentConfig for IMPL**
`oc create dc myapp --image=172.30.18.201:5000/development/myapp:promoteImpl`
