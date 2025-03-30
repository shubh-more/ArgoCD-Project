# ArgoCD-Project
ArgoCD Project POC 
1. Created a new roles
Create roles --> AWS services --> EKS-cluter --> nest --> 
provider a name

2. create role --> 
AWS-services --> EC2 --> Add policies --> 
AmazonEc2ContainerREgsitryReadonly
AmazoEKS_CNI_policy
AmazonEBSCSIDriverPolicy
AmazonEKSWorkerNodepolicy
--> provider name --> myNodeGroupPloicy

3. Create EKS --name,version, role --> SG
-- cluster endpoint --> next --> create

4. Compute --> NAme --slect role --> select node type & size -> NEXT --> create

5. Cloud shell --
aws eks update-kubeconfig --name shack-eks --region us-east-1

6. kubectl commands
# install argo
kubectl create  namespace argocd
kubectl apply -n argocd-f
GITHUB URL

7. Install argo cli
sudo curl --silent --location -o /usr/local/bin/argocd

sudo chmod +x /usr/local/bin/argocd


# get url & pass
kubectl patch svc arfocd -server -n argocd -p '{"spec": {"type" : "LoadBalancer"}}'

kubectl get all -n arocd
kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.paswword}" | base64 -d

make changes in argocd accordingly



