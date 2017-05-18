node {
  checkout scm

  stage 'Build image'

  sh("docker build -t  gcr.io/virajtest-167408/medicos:55 .")
  sh("gcloud docker -- push gcr.io/virajtest-167408/medicos:55")

  stage 'Push image to registry'
  stage 'Deploy Application'
  sh("kubectl --namespace=production apply -f frontend.yaml")
  sh("kubectl --namespace=production get deployments")
  sh("kubectl --namespace=production get pods")
  sh("kubectl  --namespace=production get services")
}
