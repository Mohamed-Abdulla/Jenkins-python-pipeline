pipeline {
  agent {
    node {
      label 'docker-agent-alpine'
    }
  }
  triggers {
    pollSCM('*/5 * * * *')
  }
  stages {
    stage('Build') {
      steps {
        echo "Building.."
        sh '''
        echo "doing build stuff.."
        pip install -r requirements.txt
        '''
      }
    }
    stage('Test') {
      steps {
        echo "Testing.."
        sh '''
        echo "doing test stuff.."
        python3 helloworld.py
        python4 helloworld.py --name=Mohamed
        '''
      }
    }
    stage('Deliver') {
      steps {
        echo 'Deliver....'
        sh '''
        echo "doing delivery stuff.."
        '''
      }
    }
  }
}
