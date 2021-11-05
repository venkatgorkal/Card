@Library('mylibrary') _



import jenkins.model.Jenkins





pipeline {
    agent any
    stages {
        stage('Demo') {
            steps {
                echo 'started....'
                script {
                    def repoName = scm.getUserRemoteConfigs()[0].getUrl().tokenize('/')[3].split("\\.")[0]
                    
                    def workspace =  "${env.WORKSPACE}"
                    String local_path = "${workspace}/${repoName}"
                    String git_uri = "https://VenkatGorkal@bitbucket.org/VenkatGorkal/card.git"
                    String username = "VenkatGorkal"
                    String password = "DAsWMgUJNkFVU8wwNvKC"
                    String headBranch = "${env.GIT_BRANCH}"
                    println("headbranch : ${headBranch}")

                    apiValidationService.validate(local_path,git_uri,username,password,headBranch)


                }
                //sh 'printenv'
            }
        }
    }
}
