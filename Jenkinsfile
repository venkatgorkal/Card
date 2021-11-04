@Library('mylibrary') _


import com.bns.SampleClass
import com.bns.GITUtility
import jenkins.model.Jenkins





pipeline {
    agent any
    stages {
        stage('Demo') {
            steps {
                echo 'Hello, world'
                sayHello 'Dave'
                script {
                    def repoName = scm.getUserRemoteConfigs()[0].getUrl().tokenize('/')[3].split("\\.")[0]
                    
                    def workspace =  "${env.WORKSPACE}"
                    def person = new SampleClass()
                    person.age = 21
                    person.increaseAge(10)
                    echo 'Incremented age, is now : ' + person.age
                    
                    
                    
                    def gitUtil = new GITUtility()
                    String local_path = "${workspace}/${repoName}"
                    String git_uri = "https://VenkatGorkal@bitbucket.org/VenkatGorkal/card.git"
                    String username = "VenkatGorkal"
                    String password = "DAsWMgUJNkFVU8wwNvKC"
                    String headBranch = "${env.GIT_BRANCH}"
                    println("headbranch : ${headBranch}")
                    //echo username
                    apiValidationService.validate(local_path,git_uri,username,password,headBranch)
                    //String out = ''
                    //apiValidationService.validate(local_path,git_uri,username,password,headBranch)

                }
                //sh 'printenv'
            }
        }
    }
}
