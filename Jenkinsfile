pipeline {
    agent {
        label 'dev_server'
    }

    triggers{
        githubPush()
    }
    
    stages {
        stage('Checkout Develop Branch') {
            steps {
               sh "Taking code checkout"
            }
        }
        stage('Verify Files'){
            steps{
                sh "ls -ls /home/ec2-user/dev/"
            }
        }
    }
    post{
            success{
                echo "Build succeeded !!"
                sh "echo 'Returning SUCCESS Status'"
            }
            failure{
                echo "Build Failed"
                sh "echo 'Returning FAILURE status'"
            }
            always{
                echo "This always runs, regardless of success/failure"
            }
        }
}
