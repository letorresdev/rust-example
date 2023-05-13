pipeline {
  agent any
  
  environment {
    RUST_VERSION = '1.56.0'
  }
  
  stages {
    stage('Install Rust') {
      steps {
        sh "curl https://sh.rustup.rs -sSf | sh -s -- -y --default-toolchain ${env.RUST_VERSION}"
        sh  'source $HOME/.bashrc'
        sh 'export PATH=$HOME/.cargo/bin:$PATH'
        sh 'rustc --version'
      }
    }
    
    stage('Build') {
      steps {
        sh 'cargo build'
      }
    }
    
    stage('Test') {
      steps {
        sh 'cargo test'
      }
    }
    
    stage('Run') {
      steps {
        sh 'cargo run'
      }
    }
  }
  
  post {
    always {
      junit 'target/debug/deps/*.xml'
      archiveArtifacts 'target/debug/*.wasm'
    }
    
    success {
      mail to: 'letorres.dev@gmail.com',
           subject: 'Build successful',
           body: 'Good job team!'
    }
    
    failure {
      mail to: 'letorres.dev@gmail.com',
           subject: 'Build failed',
           body: 'Please investigate the issue and fix it ASAP.'
    }
  }
}
