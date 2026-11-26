pipeline {
    agent any
    options {
        skipDefaultCheckout()
    }
    stages {
        stage('Checkout') {
            steps {
                checkout scm
                sh 'ls -la public'
            }
        }
        stage('Test') {
            steps {
                sh 'test -f public/index.html'
                sh 'grep -qi "<html" public/index.html'
                sh 'grep -qi "</html>" public/index.html'
                sh 'grep -qi "<title>" public/index.html'
            }
        }
        stage('Deploy') {
            steps {
                sh 'cp -r public/* /var/www/html/'
            }
        }
    }
}
```[cite: 2]

*(Catatan: pada gambar terpotong di bagian bawah setelah baris `sh 'cp -r public/* /var/www/html/'`[cite: 2], jadi blok penutup `}` untuk `steps`, `stage('Deploy')`, `stages`, dan `pipeline` ditutup sesuai struktur standar declarative pipeline Groovy.)*
