# ECR Template

The ECR pipeline will install your entando bundles [generated with entando-bundle tool]
bypassing the Entando Component Repository.

## Notes

If a private repository will be used to save your bundle than you'll need to configure
jenkins properly  (just add a username and password inside global credentials[this user will
need only read permissions] and set as ID for this credential `gitlab`)

## Prerequisites

1. Configure jenkins to use the custom nodejs agent docker image  
(`docker.io/entando/jenkins-agent-nodejs:12`). You can change this parameter inside jenkins's global
configuration section.

2. Add cluser-admin permissions for jenkins service account: 
`oc policy add-role-to-user cluster-admin system:serviceaccount:[your namespace]:jenkins -n [your namespace]`