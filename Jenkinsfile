pipeline {
  agent any
  stages {
    stage('Clone repository') {
      parallel {
        stage('Clone frontend') {
          steps {
            echo 'git clone backoffice'
          }
        }

        stage('Clone backend') {
          steps {
            echo 'git clone backend'
          }
        }

      }
    }

    stage('Install dependencies') {
      parallel {
        stage('Install frontend dependencies') {
          steps {
            echo 'yarn'
            echo 'clone isolib submodule'
          }
        }

        stage('Install backend dependencies') {
          steps {
            echo 'Install backend'
            echo 'install common submodule'
          }
        }

      }
    }

    stage('build frontend') {
      parallel {
        stage('build frontend') {
          steps {
            echo 'yarn build'
          }
        }

        stage('Docker run') {
          steps {
            echo 'docker compose up'
          }
        }

      }
    }

    stage('Publish') {
      parallel {
        stage('Publish') {
          steps {
            echo 'copy files to AWS'
          }
        }

        stage('Start') {
          steps {
            echo 'yarn start'
          }
        }

      }
    }

    stage('Clean') {
      steps {
        echo 'Clear files'
      }
    }

  }
}