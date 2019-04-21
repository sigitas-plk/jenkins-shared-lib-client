@Library('jenkins-shared-lib')_

node {
    stage('Run shell script') {
        echo 'Running shell script'
        sayscript 'cow'
    }

    stage('Nexus upload') {
        sh('touch test.zip')
        nexus_upload2()
    }
}