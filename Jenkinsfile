pipeline {
agent any
	tools
	{ 
		jdk 'JDK11’ 
	}
	environment 
	{ 
		JAVA_HOME = '/usr/lib/jvm/java-11-openjdk-amd64'
	}
	stages {
		stage ('Compile Stage') 
		{
			steps{
				withMaven(maven : 'maven3.9.3') {
						bat 'mvn clean compile'
				}
			}
		}
		stage ('Testing Stage') 
		{
			steps{
				withMaven(maven : 'maven3.9.3') {
						bat 'mvn clean test'
				}
			} 
		}
		stage ('Install Stage') {
			steps{
				withMaven(maven : 'maven3.9.3') {
						bat 'mvn clean install'
				}
			} 
		} 
	} 
}