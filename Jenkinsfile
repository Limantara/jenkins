#!/usr/bin/env groovy

pipeline {
    agent any 
    stages {
        stage("PRINT CONFIGURATION INFORMATION") {
            steps {
                script {
                    /* 
                     * Print Jenkins environment variable values
                     */
                    def printEnv = {
                        def s = ""
                        def properties = [
                            "CHANGE_ID", "CHANGE_URL", "CHANGE_TITLE", "CHANGE_AUTHOR", 
                            "CHANGE_AUTHOR_DISPLAY_NAME", "CHANGE_AUTHOR_EMAIL", "CHANGE_TARGET", 
                            "BUILD_NUMBER", "BUILD_ID", "BUILD_DISPLAY_NAME", "BUILD_TAG", "BUILD_URL",
                            "JOB_NAME", "JOB_BASE_NAME", "JOB_URL", 
                            "JENKINS_HOME", "JENKINS_URL", 
                            "NODE_NAME", "NODE_LABELS",
                            "EXECUTOR_NUMBER", "WORKSPACE"
                        ]
                        
                        for(p in properties) {
                            s += p + " = " + env.getProperty(p) + "\n"
                        }
                        println s
                    }
                    
                    printEnv();
                }
            }
        }
    }
    post {
        always {
            println "sending email"
            // mail to: elimantara@apple.com, subject "Test Jenkins Email"
        }
    }
}