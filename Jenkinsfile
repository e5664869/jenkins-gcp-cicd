 pipeline {
    agent  any 
    
}
    environment {
        PROJECT_ID = 'terraform-on-gcp-403504'
        CLUSTER_NAME = '<<Your GKE Cluster Name>>'
        LOCATION = 'us-central1'
        CREDENTIALS_ID = 'terraform-on-gcp-403504'
    }
    stages {
        stage("Checkout code") {
            steps {
                checkout scm
            }
        }

        stage("Build image") {
            steps {
                script {
                    myapp = docker.build("ganeshmete11@gmail.com/hello:${env.BUILD_ID}")
                }
            }
        }

/*
        stage("Push image") {
            steps {
                script {
                    docker.withRegistry('https://registry.hub.docker.com', 'DockerId') {
                            myapp.push("latest")
                            myapp.push("${env.BUILD_ID}")
                    }
                }
            }
        }
*/
/*
        stage('Deploy to GKE') {
            steps{
                sh "sed -i 's/hello:latest/hello:${env.BUILD_ID}/g' deployment.yaml"
                step([$class: 'KubernetesEngineBuilder', projectId: env.PROJECT_ID, clusterName: env.CLUSTER_NAME, location: env.LOCATION, manifestPattern: 'deployment.yaml', credentialsId: env.CREDENTIALS_ID, verifyDeployments: true])
            }
        }
*/
    }    
} 