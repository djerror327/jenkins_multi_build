pipeline{
    agent any
    tools{
        maven "Maven"
    }

    stages{
        stage("clone"){
            steps{
                sh "git clone https://github.com/djerror327/SM.git"
                sh "ls -lha"
            }
        }
    }
}
