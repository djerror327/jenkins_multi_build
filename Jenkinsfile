pipeline{
    agent any
    tools{
        maven "Maven"
    }
    parameters{
        choice(name:"Hierarchy" , choices:['SM_Tune','SM_GO'],description:"")
    }
    stages{
        stage("Initiating parallel processing projects"){
            parallel{ 

                 // Project SM
                stage("Sarting Parallel project SM"){
                    stages{
                        stage("clone SM"){
                            steps{
                                script{
                                    if("${params.Hierarchy}"=='SM_Tune'){
                                        sh "git clone https://github.com/djerror327/SM.git"
                                    }
                                }
                        
                            }   
                        }
                        stage("Build SM"){
                            steps{
                                script{
                                    if("${params.Hierarchy}"=='SM_Tune'){
                                        sh "mvn clean install -f ./SM"
                                        sh "ls -lha SM"
                                    }
                                }
                            }
                    
                        }

                        
                 
                
                    }   
                }

                // Project cluster-resource-monitor
                stage("Sarting Parallel project cluster-resource-monitor"){
                    stages{
                        stage("Clone cluster-resource-monitor"){
                            steps{
                                script{
                                    if("${params.Hierarchy}"=='SM_GO'){
                                        sh "git clone https://github.com/djerror327/cluster-resource-monitor.git"
                                    }
                                }
                            }
                        }
                        stage("build cluster-resource-monitor"){
                            steps{
                                script{
                                    if("${params.Hierarchy}"=='SM_GO'){
                                        sh "mvn clean install -f cluster-resource-monitor"
                                        sh "ls -la cluster-resource-monitor"
                                    }
                                }
                            }
                        }
                    }
                }

                
            }
        }
    }
}
    
