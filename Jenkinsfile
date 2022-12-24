pipeline{
    agent any
    tools{
        maven "Maven"
    }
    parameters{
        choice(name:"Hierarchy" , choices:["SM_Tune","SM_GO"],description:"")
    }
    stages{
        stage("Initiating parallel processing projects"){
            
            parallel{ 
                    
                stages{
                    stage("clone SM"){
                        when{
                            expression{
                                params.Hierarchy=="SM_Tune"
                                echo "SM TUNE"
                            }
                        }
                        steps{
                            sh "git clone https://github.com/djerror327/SM.git"
                        }
                        
                    }
                    stage("Build SM"){
                        when{
                            expression{
                                params.Hierarchy=="SM_Tune"
                                echo "SM TUNE"
                            }
                        }
                        steps{
                            sh "mvn clean install -f ./SM"
                            sh "ls -lha SM"
                        }
                        
                    }
                
                   
                    // stage("Clone cluster-resource-monitor"){
                    //     steps{
                    //         sh "git clone https://github.com/djerror327/cluster-resource-monitor.git"
                    //     }
                    // }
                    // stage("build cluster-resource-monitor"){
                    //     steps{
                    //         sh "mvn clean install -f cluster-resource-monitor"
                    //         sh "ls -la cluster-resource-monitor"
                    //     }
                    // }
                }
            }
                    
        }
    }
}
    
