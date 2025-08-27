# DevOps_Jenkins_CI-CD

# End-to-End CI/CD Pipeline on AWS

This project demonstrates a **hands-on implementation of a complete CI/CD workflow** using popular DevOps tools on AWS.  
Code changes are automatically **cloned → scanned → built → stored → deployed → run live on Tomcat**.

---

## Architecture

The setup uses **5 AWS EC2 instances**, each dedicated to one major tool:

- **Jenkins** → Pipeline orchestration  
- **SonarQube** → Code quality analysis  
- **Nexus** → Artifact repository  
- **Tomcat** → Deployment target  
- **Maven + Git** → Build & SCM  

All integrated into a Jenkins pipeline with **5 stages**:

Clone → SonarQube Scan → Build → Nexus Upload → Deploy to Tomcat
---

## Tech Stack
- **Cloud**: AWS (EC2 instances)  
- **CI/CD**: Jenkins  
- **Code Quality**: SonarQube  
- **Artifact Management**: Nexus Repository Manager  
- **Deployment**: Apache Tomcat  
- **Build Tool**: Maven  
- **Version Control**: Git  

---

## Pipeline Flow

1. **Clone** → Jenkins pulls code from GitHub  
2. **Scan** → Code analyzed by SonarQube for bugs/vulnerabilities  
3. **Build** → Maven builds a `.war` file  
4. **Nexus Upload** → Artifact stored in Nexus repo  
5. **Deploy** → WAR copied to Tomcat `webapps/` and auto-deployed  

---

## Repository Structure

aws-cicd-jenkins-sonarqube-nexus-tomcat/

├── Jenkinsfile # Declarative pipeline definition

├── scripts/

│ └── deploy.sh # Script to deploy WAR to Tomcat

├── docs/ # Architecture diagram + screenshots

│ ├── architecture.png

│ ├── jenkins.png

│ ├── sonarqube.png

│ ├── nexus.png

│ └── tomcat.png

├── pom.xml # Maven config for sample app

├── src/ # Application source code (Java)

├── .gitignore

└── README.md

---

## Jenkins Credentials Setup
Add these in Jenkins → **Manage Jenkins → Credentials**:

- `SONAR_TOKEN` → SonarQube token (Secret text)  
- `NEXUS_CREDS` → Nexus username + password  
- `TOMCAT_SSH` → SSH private key for Tomcat server  

---

## How to Run
1. Launch 5 EC2 instances (Jenkins, SonarQube, Nexus, Tomcat, Build/SCM)  
2. Configure Jenkins with required plugins: *Git, Maven, SonarQube Scanner, Nexus Artifact Uploader*  
3. Clone this repo into Jenkins job (Pipeline type)  
4. Update public IPs/URLs in `Jenkinsfile` and `pom.xml`  
5. Run the pipeline → watch code flow through all stages  

---

## Screenshots
- Jenkins pipeline execution  
- SonarQube code scan results  
- Nexus artifact storage  
- Tomcat running deployed app  

(See `docs/` folder for all screenshots)

---

## Learning Outcomes
- Gained hands-on experience with **end-to-end CI/CD pipelines**  
- Understood how **DevOps tools integrate** in real-world workflows  
- Learned **automation best practices** on AWS  

---

## Tags
`#DevOps` `#AWS` `#CICD` `#Jenkins` `#SonarQube` `#Nexus` `#Tomcat` `#Maven` `#CloudComputing`  

---

