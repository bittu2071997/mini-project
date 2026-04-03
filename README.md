Mini-project: Django Notes App Deployment on Kubernetes

Step 1: Clone Repository
  git clone https://github.com/LondheShubham153/django-notes-app.git
  cd django-notes-app

Step 2: Build Docker Image
  docker login -u <your-dockerhub-username>
 👉 Enter your DockerHub Personal Access Token when prompted

Step 4: Tag & Push Image
  docker tag notes-app-k8s:latest <your-dockerhub-username>/notes-app-k8s:latest
  docker push <your-dockerhub-username>/notes-app-k8s:latest

Step 5: Kubernetes Deployment
Step 6: Kubernetes Service
Step 7: Create Namespace
  kubectl create namespace notes-app

Step 8: Deploy Application
  kubectl apply -f deployment.yml
  kubectl apply -f service.yml

Step 9: Verify Resources
  kubectl get pods -n notes-app
  kubectl get svc -n notes-app

Step 10: Access Application
  kubectl port-forward svc/notes-app-service -n notes-app --address 0.0.0.0 8080:8000
  👉 Open in browser: http://<EC2-PUBLIC-IP>:8080
