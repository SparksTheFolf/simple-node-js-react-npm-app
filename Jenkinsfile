pipeline {
    agent any
    stages {
        stage('Advanced Build') { 
            steps {
                sh '''
                    #!/bin/bash
                    echo "Starting advanced build process..."
                    
                    if [ -f package.json ]; then
                        npm install
                    else
                        echo "package.json not found!"
                        exit 1
                    fi
                    
                    for dir in src/*/ ; do
                        echo "Building $dir"
                        npm run build --prefix "$dir"
                    done
                '''
            }
        }
    }
}
