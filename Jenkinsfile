pipeline {
    agent {
        label "linux-agent"
    }
    environment {
        SSH_USERNAME = "bmosley"
        SSH_HOSTNAME = "192.168.2.27"
        SSH_HOSTPORT = "26"
    }
    triggers {
        githubPush()
    }
    stages {
        stage('ssh') {
            steps {
                sh '''
                    ls -la
                '''
                configFileProvider([configFile(fileId: '7c438220-7189-4779-9c9a-b20981978d7c', targetLocation: './mega.txt')]) {
                    sh '''
                        ls -la
                        cat "./mega.txt"
                        ls -la
                        ls -la
                    '''
                }
                // configFileProvider([configFile(fileId: '7d1228ec-e01f-4e69-a655-3a13512f7f73', targetLocation: './mega.txt', replacements: [
                //   replaceRegex(pattern: 'BAR', replacement: 'replacement-string')
                // ])]) {
                //   // Here you can define the steps that use the configuration file
                //     sh '''
                //         ls -la
                //         cat "./mega.txt"
                //     '''
                // }
                //   configFile(fileId: '7d1228ec-e01f-4e69-a655-3a13512f7f73', targetLocation: './mega2.txt', replacements: [
                //      replaceRegex(pattern: 'FOO', replacement: 'BAR'),
                //      replaceRegex(pattern: 'BAZ', replacement: 'QUX')
                //   ]) {
                //       sh '''
                //         ls -la
                //         cat "./mega2.txt"
                //     '''
                //      // Here you can define the steps that use the configuration file
                //   }
                // configFile(fileId: '7d1228ec-e01f-4e69-a655-3a13512f7f73', targetLocation: './mega.txt', replacements: [
                //   replaceRegex(pattern: 'FOO=\\d+', replacement: 'BAR=456')
                // ]) {
                //   // Here you can define the steps that use the configuration file
                // }
            }
           
        }
    }
}

