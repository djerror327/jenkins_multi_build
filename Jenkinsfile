pipeline{
    agent any
    tools{
        maven "Maven"
    }

    stages{
        stage("Initiating parallel processing projects"){
            parallel{  
                stage("Project SM"){
                    stages{
                        stage("clone SM"){
                            steps{
                                sh "git clone https://github.com/djerror327/SM.git"
                            }
                        }
                        stage("Build SM"){
                            steps{
                                sh "mvn clean install -f ./SM"
                                sh "ls -lha SM"
                            }
                        }
                    }
                }
            }
        }
    }
}
