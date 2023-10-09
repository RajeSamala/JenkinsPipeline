pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building'
            }
        }
        stage('GitInstall') {
            steps {
                git 'https://github.com/jenkinsci/git-plugin'
                echo 'Git installed successfully'
            }
        }
        stage{
            steps {
                git url: 'https://github.com/cyrille-leclerc/multi-module-maven-project'
                withMaven {
                  sh "mvn clean verify"
                } // withMaven will discover the generated Maven artifacts, JUnit Surefire & FailSafe reports and FindBugs reports
              }
        }
        

        stage('Deploy') {
            steps {
                echo 'Deploying'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing'
            }
        }
        
    }
