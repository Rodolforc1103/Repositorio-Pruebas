pipeline {
    agent any 
    stages {
        stage('DELETION') { 
            steps {
                echo '--REMOVING REPOSITORY IF ALREADY EXIST --'
                sh "sudo rm -rf helloWordNodejs"
            }
        }
       stage('CLONE') { 
            steps {
                echo '--CLONE STAGE EXECUTION ---'
    sh "git clone https://github.com/jatinnandwani/helloWordNodejs.git"
            }
        }
        stage('TEST1') { 
            steps {
                echo '--TEST1 STAGE EXECUTION --'
            }
        }
        stage('TEST2') { 
            steps {
                echo '--TEST2 STAGE EXECUTION --'
            }
        }
        stage('BUILD') { 
            steps {
    echo '--BUILD STAGE EXECUTION --'
    sh "node helloWordNodejs/index.js"
            }
        }
  stage('DEPLOY') { 
            steps {
    echo '--WILL SEE IN NEXT PART --'
            }
        }
    }
