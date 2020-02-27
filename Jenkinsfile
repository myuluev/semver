pipeline {
    environment {
        tag = VersionNumber (versionNumberString: '${BUILD_DATE_FORMATTED, "yyyyMMdd"}-develop-${BUILDS_TODAY}')
    }

    stages {
        stage('Variables Print')
            steps{
                echo tag
            }
    }
}