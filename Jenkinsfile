node {
    stage ('checkout') {
        git clone: 'https://github.com/Rupamranjan5146/mariadb_sample.git'
    }
	post {
    always {
      echo 'always runs regardless of the completion status of the Pipeline run'
    }
    success {
      mail to: 'rupam.kumari306@gmail.com',
      subject: "Pipeline build is success : ${currentBuild.fullDisplayName}",
      body: "Error in ${env.BUILD_URL}"
    }
    failure {
      mail to: 'rupam.kumari306@gmail.com',
      subject: "Pipeline has failed: ${currentBuild.fullDisplayName}",
      body: "Error in ${env.BRANCH_NAME} ${env.BUILD_URL}  ${env.JOB_NAME}"
    }
	}
}
