@Library('jenkins-shared-lib')_

node {
    
   stage('checkout') {
        checkout([
            $class: 'GitSCM',
            branches:[[name: '*/master']],
            extensions:[[$class: 'LocalBranch'], [$class: 'WipeWorkspace']],
                 userRemoteConfigs: [[url: 'file:///var/client']],
            doGenerateSubmoduleConfigurations: false
        ])
    }
    
    stage('Run shell script') {
        echo 'Running shell script'
        sayscript 'cow'
    }

    stage('Nexus upload') {
        sh('touch test.zip')
        nexus_upload2()
    }
}
