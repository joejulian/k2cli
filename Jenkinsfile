podTemplate(label: 'k2cli', containers: [
    containerTemplate(name: 'jnlp', image: 'jenkinsci/jnlp-slave:2.62-alpine', args: '${computer.jnlpmac} ${computer.name}'),
    containerTemplate(name: 'golang', image: 'golang:1.7.5', ttyEnabled: true, command: 'cat')
    ]) {
        node('k2cli') {
            container('golang'){

                stage('hello!') {
                    echo 'hello world!'
                }

                stage('checkout'){
                    checkout scm
                    sh 'go version'
                    // git url: 'https://github.com/samsung-cnct/k2cli'
                }

                stage('build'){
                    sh 'go build -v'
                }

                stage('test') {
                    sh 'go test -v'
                }

            }
        }
    }