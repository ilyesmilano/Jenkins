Jenkins :

# Build types :

    * free style:
        -shell scripts that gonna be executed based on some events like a dev make a commit to the master git repository.
        - are easy because we use the Ui and some plugins to build.

    * Pipelines:
        - are uild in diff stages :
            stages{
                stage("clone"){
                    step{
                        pull up the code from github
                    }
                }
                stage("build"){
                    step{
                        docker build or jar file
                    }
                }
                stage("test"){
                    step{
                        runs test on the code
                        docker run it
                    }
                }
                stage("package"){
                    step{
                        it get packaged so its ready for deploiment
                        docker push
                    }
                }
                stage("deploy"){
                    step{
                        deploy to docker hub
                    }
                }
            }
