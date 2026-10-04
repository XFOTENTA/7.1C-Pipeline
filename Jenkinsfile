pipeline {
    // Run on any available Jenkins machine (your Windows PC)
    agent any

    // Check GitHub for new commits every 2 minutes; build only if something changed
    triggers {
        pollSCM('H/2 * * * *')
    }

    stages {
        // Stage 1: Build - compile and package the code
        stage('Build') {
            steps {
                echo 'Task: Compile the source code and package it into a build artefact (JAR file)'
                echo 'Tool: Maven (mvn clean package)'
            }
        }

        // Stage 2: Unit and Integration Tests
        stage('Unit and Integration Tests') {
            steps {
                echo 'Task: Run unit tests to check each function works, and integration tests to check components work together'
                echo 'Tools: JUnit (unit tests) and Selenium (integration tests)'
            }
        }

        // Stage 3: Code Analysis - check the code meets industry standards
        stage('Code Analysis') {
            steps {
                echo 'Task: Analyse the code for bugs, code smells, duplication and coding-standard issues'
                echo 'Tool: SonarQube'
            }
        }

        // Stage 4: Security Scan - look for vulnerabilities
        stage('Security Scan') {
            steps {
                echo 'Task: Scan the code and its dependencies for known security vulnerabilities'
                echo 'Tool: Snyk (or OWASP Dependency-Check)'
            }
        }

        // Stage 5: Deploy to Staging
        stage('Deploy to Staging') {
            steps {
                echo 'Task: Deploy the application to a staging server (AWS EC2 instance)'
                echo 'Tool: AWS CodeDeploy'
            }
        }

        // Stage 6: Integration Tests on Staging
        stage('Integration Tests on Staging') {
            steps {
                echo 'Task: Run integration tests on the staging environment to check the app works in a production-like setup'
                echo 'Tool: Selenium (with Postman for API tests)'
            }
        }

        // Stage 7: Deploy to Production
        stage('Deploy to Production') {
            steps {
                echo 'Task: Deploy the application to the production server (AWS EC2 instance)'
                echo 'Tool: AWS CodeDeploy'
            }
        }
    }
}
