node {
  checkout scm

  stage 'Build image'


  stage 'Push image to registry'

  
  stage 'Deploy Application'
  sh("kubectl apply -f frontend.yaml")
  sh("kubectl get deployments")
  sh("kubectl get pods")
  sh("kubectl get services")
}
