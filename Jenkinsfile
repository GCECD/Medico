node {
  checkout scm

  stage 'Build image'   
  sh("docker build -t  gcr.io/virajtest-167408/medicos:latest .")
  stage 'Push image to registry'
  sh("gcloud docker -- push gcr.io/virajtest-167408/medicos:latest")

 
  stage 'Deploy Application'
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
