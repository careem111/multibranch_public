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
                sh "cp /var/lib/jenkins/workspace/valaxy-app-mbranch_feature/webapp/target/*.war /home/jenkins/feature"
                sh "cp Dockerfile /home/jenkins/feature"
            }
        }

            }
        }
