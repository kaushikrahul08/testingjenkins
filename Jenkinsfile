node() {
    stage('checkout'){
        checkout scm
    }
    
    stage('azsplogin') {
     withCredentials([azureServicePrincipal('AKS-SP-ID')]) {
   sh "az login --service-principal -u $AZURE_CLIENT_ID -p $AZURE_CLIENT_SECRET -t $AZURE_TENANT_ID"
  // sh "az acr login -n aksregus -u aksregus -p <password>"
                    }
    }
    
     stage('docker build&push'){
      //sh "docker build -t sampleapp:v3 ."
      sh "docker tag kaushikrahul08/webapp:v3 kaushikrahul08/webapp:v4"
      sh "docker login -u 'kaushikrahul08' -p 'Dristi@1381' docker.io"
      sh "docker push kaushikrahul08/webapp:v4"
    } 
    
    stage ('login to aks context login ') {
        //bat "cd C:/Users/rahulsharma "
        //bat "az aks get-credentials --resource-group RG-AKS --name azkubeclr"
        //bat "kubectl config get-contexts" 
        //bat "kubectl config use-context azkubeclr"
        
    }
    
    
      stage ('deployment of pods ') {
        //bat "kubectl apply -f deployment.yml"
        //bat "kubectl apply -f balancer-service.yaml"
    }

}
