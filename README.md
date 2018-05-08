Mysql-utf8-Kubernetes 
=====================
前瞻：查了好多资料，有说手动执行sql的，有说docker启动加参数的。docker这样可行，k8s上pod重启就无效了。<br>
还有说重写dockerfile的，这个倒是可行，但是麻烦。直接用官方镜像，用k8s的cm覆盖文件简简单单。<br>
1.创建cm文件<br>
oc create configmap config --from-file=key=mysqld.cnf <br>
2.根据openshift编排文件创建dc <br>
oc create -f mysql_dc.yaml <br>
3.编排文件是openshift  DeploymentConfig,使用k8s用户自行改成Deployment或者Replication Controller. <br>
其实有用的就那个配置文件，挂进去就行了。要为为啥标题写Mysql-utf8-Kubernetes 因为写OpenShift没人知道，over.
