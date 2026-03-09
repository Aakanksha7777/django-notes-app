@Library('Shared')_
pipeline{
    agent { label 'dev-server'}
    
    stages{
        stage("Code clone"){
            steps{
                sh "whoami"
          git url: "https://github.com/Aakanksha7777/django-notes-app.git", branch:"main"
            }
        }
        stage("Code Build"){
            steps{
            dockerbuild("notes-app","latest")
            }
        }
        stage("Push to DockerHub"){
            steps{
                dockerpush("dockerHubCreds","notes-app","latest")
            }
        }
        stage("Deploy"){
            steps{
                deploy()
            }
        }
        
    }
}
