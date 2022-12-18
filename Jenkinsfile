pipeline{
    agent any
    tools{
        maven "Maven"
    }

    stages{
        parallel(
            a:{
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
            b:{
                stage("Clone cluster-resource-monitor"){
                    steps{
                        sh "git clone https://github.com/djerror327/cluster-resource-monitor.git"
                    }
                }
                stage("build cluster-resource-monitor"){
                    steps{
                        sh "mvn clean install -f cluster-resource-monitor"
                        sh "ls -la cluster-resource-monitor"
                    }
                }
            }
        )
    }
}
