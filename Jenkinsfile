node {
  
  def project = 'virajtest-167408'
  def appName = 'medicos'  
  def imageTag = "gcr.io/${project}/${appName}:${env.BRANCH_NAME}.${env.BUILD_NUMBER}"
  
  checkout scm
  stage 'Dev Deployment'
  stage 'Dev Testing' 
  
  stage 'UAT Deployment' 
  stage 'UAT Testing' 
  
  stage 'Production Build - Build Container image and Push in GCP Registry'   
  sh("docker build -t ${imageTag} .")

  stage 'Production Deployment' 
  sh("gcloud docker push ${imageTag}") 
 
  stage 'Production Deployment(Deploy Application as a Microservice(Kubernetes on GCP))'
/*  sh("kubectl --namespace=production get deployments")
  sh("kubectl --namespace=production get pods")
  sh("kubectl  --namespace=production get services")
  
  
  sh("kubectl --namespace=production apply -f frontend.yaml")
  
  sh("kubectl --namespace=production get deployments")
  sh("kubectl --namespace=production get pods")
  sh("kubectl  --namespace=production get services")*/
  
  sh("sed -i.bak 's#gcr.io/cloud-solutions-images/hello-node:1.0.0#${imageTag}#' ./*.yaml")
  sh("kubectl  apply -f frontend.yaml")
  
  sh("kubectl get deployments")
  sh("kubectl  get pods")
  sh("kubectl get services")
}
