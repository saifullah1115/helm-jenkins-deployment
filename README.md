![N|Solid](https://www.arcanainfo.com/wp-content/uploads/2021/06/logo-arcana.png)](https://www.arcanainfo.com/)
# JAZZ TKG JENKINS

### It consists of Jenkins instance setup config's using HELM

-- installation
helm install jenkins jenkinsci/jenkins --values /tmp/jenkins.yaml -n jenkins
helm install jenkins jenkinsci/jenkins --values /opt/workspace/k8s-jenkins-helm/values.yaml -n jenkins
- plugins installation
Role-based Authorization Strategy
Strict Crumb Issuer

-- jenkins regcred secret
kubectl create secret docker-registry regcred -n jenkins \
    --docker-server=https://internal-registry.tkg.mobilink.net.pk \
    --docker-username=service-acc-jenkins-wos2 \
    --docker-password=Jenkins@123 \
    --docker-email=arcana.isb@arcanainfo.com

-- to upgrade jenkins
helm repo update
helm search repo jenkins
helm list -n jenkins
helm fetch jenkinsci/jenkins
helm upgrade jenkins -f values.yaml . -n jenkins
helm list
helm list -n jenkins
helm search repo jenkins

-- to uninstall jenkins
helm list --all-namespaces
helm uninstall jenkins -n jenkins


> Powered & developed by [ArcanaInfo](https://www.arcanainfo.com/)
