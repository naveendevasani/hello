pipeline {
        agent any
                stage('One') {
                        steps {
                                echo 'hi this is naveen'
                        }
                }
                stage ('Two') {
                        steps {
                                input ('do you want to proceed?')
                        }
                }
                stage ('Three') {
                        when {
                                not {
                                        branch "master"
                                }
                        }
                        steps {
                                echo "hello hai"
                        }
                }
stage ('Four') {
                parallel {
                        stage ('Unit Test') {
                                        steps {
                                                echo "Running the unit test."
                                        }
                        }
                        stage ('Integration test') {
                                                agent {
                                                        docker {
                                                                reuseNode false
                                                                image 'ubuntu'
                                                        }
                                                }
                                                steps {
                                                        echo 'Running the integration test..'

                                                }
                        }
                }
