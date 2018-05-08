Mysql-utf8-Kubernetes 
=====================
1.创建cm文件<br>
oc create configmap config --from-file=key=mysqld.cnf <br>
2.根据openshift编排文件创建dc <br>
oc create -f mysql_dc.yaml <br>
3.编排文件是openshift  DeploymentConfig,使用k8s用户自行改成Deployment或者Replication Controller. <br>
其实有用的就那个配置文件，挂进去就行了。要为为啥标题写Mysql-utf8-Kubernetes 因为写OpenShift没人知道，over.
