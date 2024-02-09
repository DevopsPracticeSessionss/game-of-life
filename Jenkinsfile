pipeline{
    agent { label 'MAVEN_JDK_8'}
    stages{
        stage('vcs'){
             steps{
                git url: 'https://github.com/DevopsPracticeSessionss/game-of-life.git',
                branch: 'declarative'
             }
        }
        stage('package'){
            tools{
                jdk 'JDK_8_UBUNTU'
            }
                steps{
                    sh 'mvn package'
                }
        }
        stage('post build'){
            steps{
                archiveArtifacts artifacts: '**/target/gameoflife.war'
                junit testResults: '**/surefire-reports/TEST-*.xml'
            }
        }
    }
}