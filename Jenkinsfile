pipeline {
    agent any
    environment {
            VERSION = VersionNumber([
                versionNumberString : '1.0.${BUILD_DAY}',
                projectStartDate : '2020-01-01',
                PrefixVariable : ''
                ])
    }

    stages {
        stage ('Get Version') {
            steps {
                sh 'echo "$VERSION"';
            }

        }
    }
}