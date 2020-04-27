pipeline {
	agent any
	environment {
		GIT_VARS = sh(script: 'git --no-pager show -s --format=\'%h|%an|%ae|%s\'', returnStdout: true).trim()
		APP_NAME = scm.getUserRemoteConfigs()[0].getUrl().tokenize('/')[3].split("\\.")[0].replace('^ms-', '')
	}
	stages {
		stage('LogProperties') {
			steps {
				echo "COMMIT_ID: ${GIT_VARS.split('\\|', 4)[0]}"
				echo "AUTHOR_NAME: ${GIT_VARS.split('\\|', 4)[1]}"
				echo "AUTHOR_EMAIL: ${GIT_VARS.split('\\|', 4)[2]}"
				echo "MESSAGE: ${GIT_VARS.split('\\|', 4)[3]}"
				echo "APP_NAME: ${APP_NAME}"
				echo "BRANCH_NAME: ${BRANCH_NAME}"
				echo "CHANGE_ID: ${CHANGE_ID}"
				echo "CHANGE_URL: ${CHANGE_URL}"
				echo "CHANGE_TITLE: ${CHANGE_TITLE}"
				echo "CHANGE_AUTHOR: ${CHANGE_AUTHOR}"
				echo "CHANGE_AUTHOR_DISPLAY_NAME: ${CHANGE_AUTHOR_DISPLAY_NAME}"
				echo "CHANGE_AUTHOR_EMAIL: ${CHANGE_AUTHOR_EMAIL}"
				echo "CHANGE_TARGET: ${CHANGE_TARGET}"
				echo "CHANGE_BRANCH: ${CHANGE_BRANCH}"
				echo "BUILD_URL: ${BUILD_URL}"
			}
		}
	}
}