pipeline{
    agent any
    tools{
        maven "Maven"
    }
    // parameters{
    //     choice(name:"Hierarchy" , choices:["SM_Tune","SM_GO"],description:"")
    // }
    stages{
        stage("Initiating parallel processing projects"){
            
            parallel{  

                stage("Project SM"){
                    input {
                message "Should we continue?"
                ok "Yes, we should."
                submitter "alice,bob"
                parameters {
                    string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
                }
            }
            steps {
                echo "Hello, ${PERSON}, nice to meet you."
            }
                    // when{
                    //     expression{
                    //         params.Hierarchy=="SM_Tune"
                    //         echo "SM TUNE"
                            
                    //     }
                    //     stages{
                    //         stage("clone SM"){
                    //              steps{
                    //                 sh "git clone https://github.com/djerror327/SM.git"
                    //              }
                    //         }
                    //         stage("Build SM"){
                    //             steps{
                    //                 sh "mvn clean install -f ./SM"
                    //                 sh "ls -lha SM"
                    //             }
                    //         }
                    //     }
                    // }
                    
                }
                stage("Project cluster-resource-monitor"){
                    stages{
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
                }

            }
        }
    }
}
