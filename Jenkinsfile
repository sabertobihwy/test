pipeline {
    agent any

    stages {
        stage('pull code') {
            steps {
                git branch: 'main', credentialsId: 'github-hewenyan', url: 'git@github.com:sabertobihwy/test.git'
            }
        }
         stage('build code') {
            steps {
                sh '''echo "start building..."
                    echo "end building..."'''
            }
        }
         stage('deploy code') {
            steps {
sshPublisher(publishers: [sshPublisherDesc(configName: '192.168.2.112', transfers: [sshTransfer(cleanRemote: false, excludes: '', execCommand: 'echo "transfer files success..."', execTimeout: 120000, flatten: false, makeEmptyDirs: false, noDefaultExcludes: false, patternSeparator: '[, ]+', remoteDirectory: '${remote_dir}/', remoteDirectorySDF: false, removePrefix: '', sourceFiles: 'target/**')], usePromotionTimestamp: false, useWorkspaceInPromotion: false, verbose: false)])            }
        }
    }
}
