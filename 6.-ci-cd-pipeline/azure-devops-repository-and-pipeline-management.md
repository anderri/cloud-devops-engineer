# Azure DevOps: Repository & Pipeline Management

### DevOps Workflow

&#x20;

Development -> Peer review -> QA -> Pre-production -> Production



### DevOps Automation Pattern

Plan -> Code -> Integrate -> Test -> Release -> Deploy -> Operate



![](<../.gitbook/assets/Screen Shot 2022-10-31 at 1.12.31 pm.png>)

### DevOps Automation Pattern Implementation

* Azure Management Script
* Environment Creation Script&#x20;
* Deployment Script

### Azure CloudOps Implementation Pattern

![](<../.gitbook/assets/Screen Shot 2022-10-31 at 1.22.30 pm.png>)



### Azure Tools and Technologies for CloudOps

![](<../.gitbook/assets/Screen Shot 2022-10-31 at 1.28.59 pm.png>)

#### Plan

* Azure Board
* GitHub
* PowerBI

#### Develop and Deploy

* Visual Studio&#x20;
* Azure Pipelines
* Jenkins Workload to Azure

#### Build and Test

* Azure Repo
* Azure Artifact&#x20;

#### Deliver

* Azure Resource Manager
* HashiCorp
* Terraform

#### Operation

* Azure Automation
* Azure Monitor
* Azure Blueprints
* Azure Security Center&#x20;
* Datadog and Nagios



![](<../.gitbook/assets/Screen Shot 2022-10-31 at 1.36.37 pm.png>)



### Version Control Workflow and Azure Repos

&#x20;![](<../.gitbook/assets/Screen Shot 2022-10-31 at 1.43.38 pm.png>)

Web Hooks -> Event Driven&#x20;

API -> Request & Response



#### Simple Branching Strategy

* Use feature branches for new features and bug fixes
* Merge feature branches into a master branch with pull requests
* Maintain high quality and up-to-date master branch.&#x20;

Steps:&#x20;

* Install git
* git init .
* git status
* go to Azure DevOps -> Select Organization -> Create new project
* Go to AzDevOps->Project->Repos->Files-> "Push an existing repository from command line" and copy https
* git remove add origin https://asdfasdfas
* git push -u origin --all&#x20;

#### Branching with AzureDevOps

* AzDevOps->Repos->Branches>New branch
* Name it, Select the branch and work items

#### Buld Pipeline

* Install azure-cli
* az extension add --name azure-devops
* devops configure --defaults organization=//dev/azure/com/organizationame project=name
* az login
* az pipelines create --name "testpipeline.CI" --repository https://github.com/name/pipelines-java.git --branch master&#x20;
* Commit directly to the master branch or Create a new branch for this commit and start a pull request.&#x20;



