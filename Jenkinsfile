node {
  checkout scm

  stage 'Build image'


  stage 'Push image to registry'
  
  docker build -t  gcr.io/virajtest-167408/medicos:55 .

  gcloud docker -- push gcr.io/virajtest-167408/medicos:55

  
  stage 'Deploy Application'
  sh("kubectl apply -f frontend.yaml")
  sh("kubectl get deployments")
  sh("kubectl get pods")
  sh("kubectl get services")
}
