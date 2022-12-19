pipeline {
    agent {label 'DOCKER'}
    triggers {
        pollSCM('* * * * *')
    }

    }
stages {
    stage('vcs') {
        steps {
            git url: 'https://github.com/nagvenkat1/saleor-1.git',
            branch: 'main'
        }
    }
    stage('build') {
        steps {
            sh 'docker image build -t nagvenkat/saleor:DEV .'
            sh 'docker image push nagvenkat/saleor:DEV'
        }
        }
    }
