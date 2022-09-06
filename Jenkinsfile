pipeline{
    agent any

    parameters{
        string(name: 'ansible_server', defaultValue: '127.0.0.1', description: 'docker Server')
    }

    stages{
        stage('build'){
            steps{
                sh 'mvn clean install package'
                }
            }
        stage('copy war file and dockerfile'){
            steps{
                sh "scp /var/lib/jenkins/workspace/hello_private/webapp/target/*.war jenkins@${params.ansible_server}:/home/jenkins"
                sh "scp Dockerfile jenkins@${params.ansible_server}:/home/jenkins"
                 }	
           }

   	}
}
