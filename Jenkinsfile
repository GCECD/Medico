node {
  checkout scm

  stage 'Build Stage' 
  stage 'Run Tests'   
  stage 'Build Container Image'   
  sh("docker build -t  gcr.io/virajtest-167408/medicos:latest .")
  stage 'Deploy Container to Cloud Repository'
  sh("gcloud docker -- push gcr.io/virajtest-167408/medicos:latest")

 
  stage 'Deploy Application as a Microservice(kubernetes on GCP)'
/*  sh("kubectl --namespace=production get deployments")
  sh("kubectl --namespace=production get pods")
  sh("kubectl  --namespace=production get services")
  
  
  sh("kubectl --namespace=production apply -f frontend.yaml")
  
  sh("kubectl --namespace=production get deployments")
  sh("kubectl --namespace=production get pods")
  sh("kubectl  --namespace=production get services")*/
  
  sh("kubectl  apply -f frontend.yaml")
  
  sh("kubectl get deployments")
  sh("kubectl  get pods")
  sh("kubectl get services")
}
