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
				echo "BRANCH_NAME: ${env.BRANCH_NAME}"
				echo "CHANGE_ID: ${env.CHANGE_ID}"
				echo "CHANGE_URL: ${env.CHANGE_URL}"
				echo "CHANGE_TITLE: ${env.CHANGE_TITLE}"
				echo "CHANGE_AUTHOR: ${env.CHANGE_AUTHOR}"
				echo "CHANGE_AUTHOR_DISPLAY_NAME: ${env.CHANGE_AUTHOR_DISPLAY_NAME}"
				echo "CHANGE_AUTHOR_EMAIL: ${env.CHANGE_AUTHOR_EMAIL}"
				echo "CHANGE_TARGET: ${env.CHANGE_TARGET}"
				echo "CHANGE_BRANCH: ${env.CHANGE_BRANCH}"
				echo "BUILD_URL: ${env.BUILD_URL}"
			}
		}
	}
}