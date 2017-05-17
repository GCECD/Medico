node {
  checkout scm

  stage 'Build image'


  stage 'Push image to registry'

  
  stage 'Deploy Application'
  sh("kubectl apply -f frontend.yaml")
}
