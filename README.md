# k8s-first-deploy

kubectl create -f nginx-deploy.yaml

kubectl get deploy -l app=nginx-app

kubectl get rs -l app=nginx-app

kubectl get po -l app=nginx-app

kubectl describe deploy nginx-deployment

Update Nginx 1.7.9 to 1.9.1

kubectl set image deploy nginx-deployment nginx-container=nginx:1.9.1

kubectl edit deploy nginx-deployment

kubectl rollout status deployment/nginx-deployment

kubectl get deploy

Rollback

kubectl set image deploy nginx-deployment nginx-container=nginx:1.91 --record

kubectl rollout status deployment/nginx-deployment

kubectl rollout history deployment/nginx-deployment

kubectl rollout undo deployment/nginx-deployment

kubectl rollout status deployment/nginx-deployment

Scale up & down

kubectl scale deployment nginx-deployment --replicas=5

kubectl get deploy

kubectl get po

kubectl scale deployment nginx-deployment --replicas=1

kubectl get deploy

kubectl get po -l app=nginx-app

Clean up

kubectl delete -f nginx-deploy.yaml

kubectl get po -l app=nginx-app
