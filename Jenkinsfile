#!/user/bin/env groovy
@Library('jenkins-shared-library') //when there is nothing separating this library definition and the start of the actual pipeline script, you have to put an underscore like this @Library('jenkins-shared-library')_ to indicate the end of this statement and it means that the next line is the start of the pipeline. However, in this case, we have a variable definition, def gv, separating them so you don't need the underscore. 



def gv

pipeline {
    agent any
    tools {
        maven 'maven-3.9'
    }
    stages {
        stage("init") {
            steps {
                script {

                    echo "placeholder for the init stage"
                    // gv = load "script.groovy"
                }
            }
        }

        stage("build jar") {
            steps {
                script {
                    buildJar()
                }
            }
        }

        stage("build and push image") {
            steps {
                script {
                    buildImage 'chisom444/demo-images:jma-5.0'
                    // buildImage 'nanatwn/demo-app:jma-3.0'
                    // dockerLogin()
                    // dockerPush 'nanatwn/demo-app:jma-3.0'
                }
            }
        }
        
        stage("deploy") {
            steps {
                script {
                    // gv.deployApp()
                    echo "placeholder for the deploy stage "
                }
            }
        }               
    }
}
