node {
    stage('checkout') {
    git 'https://github.com/sandeepGundu/jenkinsDemo.git'
    }
    env.PATH="C:/apache-maven-3.9.9/bin;C:\\Windows\\System32"
    stage('build'){

    }
    bat 'mvn package'
    stage('archive'){

    }
    archiveArtifacts artifacts: 'target/*.jar', followSymlinks: false
    step([$class: 'JUnitResultArchiver', checksName: '', testResults: '/target/surefire-reports/TEST*.xml'])
    notify('Completed')
}

def notify(status)
{
    emailext body: 'Hey I am sending mail ', subject: "'about build' ${status} Job ${env.JOB_NAME}", to: 'sandeepkumar_gundu@epam.com'
}
