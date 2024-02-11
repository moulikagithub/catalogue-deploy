pipeline {
    agent {
        node {
            label 'agent-1'
        }      
    }
    // environment { 
    //         packageVersion = ''
    //         nexusurl = '172.31.11.253:8081'
    // }
   
    options {
                timeout(time: 1, unit: 'HOURS')
                disableConcurrentBuilds() 
            }
    parameters {
        string(name: 'version', defaultValue: '', description: 'What is version')
        string(name: 'environment', defaultValue: 'dev', description: 'What is environment?')

    }   
    // build
    stages{
        stage('print version') {
            steps {
                sh """
                    echo "version is :${params.version}"
                    echo "environment is :${params.environment}"
                """
            }
        }
        
    }
    // post build
    post { 
        always { 
            echo 'I will always say Hello again!'
            deleteDir()
        }
        failure { 
            echo 'runs when their is failure'
        }
        success { 
            echo 'runs when success!'
        }
    }
}


     