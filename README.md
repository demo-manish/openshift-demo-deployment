# openshift-demo-deployment

**Create project**
`oc project development`

**Create new app** 
* * This will create buildconfig and deploymentconfig
`oc new-app --name myapp <git url>`

**Expose Service through route**
`oc expose myapp`

**Create pipeline**
`oc apply -f pipeline.yaml`
