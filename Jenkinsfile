pipeline{
        agent any
        stages{
                stage('---build---'){
                        steps{
                               sh "docker build -t ayshamarty/account-client ."
                        }
                }
                stage('---push---'){
                        steps{
                                sh "docker push ayshamarty/account-client"
                        }
                }

                stage('---redeploy stack---') {
                    steps {
                            build job: "Account-API-Deploy", wait: true

                        }
                }
        }
}
