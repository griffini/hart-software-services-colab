pipeline {
  agent any
  stages {
    stage('Genconfig') {
      steps {
        sh '''cp boards/mpfs-icicle-kit-es/def_config .config
CROSS_COMPILE=riscv-none-embed- make BOARD=mpfs-icicle-kit-es genconfig
'''
      }
    }

    stage('Build') {
      steps {
        sh '''CROSS_COMPILE=riscv-none-embed- make BOARD=mpfs-icicle-kit-es -j2
'''
      }
    }

  }
}