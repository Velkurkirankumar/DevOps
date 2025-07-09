# DevOps

# March 18th

# DevOps  [**To know more about DevOps click upon me :)**](https://about.gitlab.com/topics/devops/#dev-ops-defined)

- DevOps combines development (Dev) and operations (Ops) to increase the efficiency, speed, and security of software development and delivery compared to traditional processes. A more nimble software development lifecycle results in a competitive advantage for businesses and their customers.

![image](https://github.com/user-attachments/assets/2908912b-5ee3-4244-a15e-b6bc91ba41de)


**One of the major areas of DevOps is building and maintaining Pipelines**



**CI/CD Pipelines are supposed to**
- Build package
- Deploy Application in various environments
- Run the Automated Tests for each environment and Generate Reports

![image](https://github.com/user-attachments/assets/554bc1b1-e9d0-4626-a2d3-af0b6a113db5)


### Preview Terms
- Artifact: Build result is an artifact, the package is most important one to be preserved
- Repository: A storage location which can maintain history (i.e. versions or revisions )



# March 19th

### Version Control Systems (VCS)
- This is a source code repository which stores code and also the history which represents
    - the changes done
    - who has done it
    - when it was done
- Generally Version Control Systems are designed for multi users.
- Any VCS will have repositories which developers(users) will get a copy or equivalent to copy in their local workstation
- They get or make changes from/to VCS

![image](https://github.com/user-attachments/assets/662c2609-5c30-4e5e-8631-7a95afd66477)


### Generations of Version Control Systems
**Client Server:**
#### Examples:
- Subversion
- TFS
- ClearCase
- Perforce
- Distributed

#### Examples:
- Mercurial
- Git

#### Basic Design of Git
- In Git every one (client, server) have repositories
- IF you have to create a server you need to install same software as client (git) and for server features (USer management, Connectivity) - you can install additional components


![image](https://github.com/user-attachments/assets/eda8cebd-6f91-4fc3-8eba-0af692f6e932)


#### Problem:
- I have a huge room full of books, i want to send them to new home.

![image](https://github.com/user-attachments/assets/90b0a969-a4ec-4297-acbb-2fc5feafadb7)

# March 20


### Git

- Git has five stages, initially we will be focusing on three areas

![image](https://github.com/user-attachments/assets/6773bcc1-673c-4feb-83eb-fda1dd188ebb)


### Git Basic configuration

- This configuration is done to set username and email id of the author
- git config --global user.name "<your-username>"
- git config --global user.email "<your-email>"
- Our current focus areas


![image](https://github.com/user-attachments/assets/bd390232-93de-48a4-aad5-8e71cf621ee9)


## Local Repository

- Create a new directory in your system and cd into it
- Now execute git init to initialize a git repository


![image](https://github.com/user-attachments/assets/56815daa-a66d-4e4b-abfc-8415038fd73d)



## Working Tree

- This is area of work for us
- In this we make changes, add/delete files etc

![image](https://github.com/user-attachments/assets/55d7952d-cbca-49da-bf3e-938612f5c454)


### Staging Area

- This is area where the changes can be staged to be part of a commit

**Other things to know**

- **log:** This represents the history of the repo.
- **status:** This command represents what is your current status. For git the ideal status is working tree == local repo
- **Tracked and Untracked files:** Tracked files represent the files which were part of any commit i.e. they are part of git repo, whereas untracked files are not part of the repo yet.


# March 22

### Git contd

#### Overview

![image](https://github.com/user-attachments/assets/bc5abe2d-aa74-4908-b20a-e542cb956fa2)


- Lets create a new repo
- Git doesnot consider empty folders as change. Git considers only files as changes
- Every commit will have a unique commit id

![image](https://github.com/user-attachments/assets/1dc30b71-92cd-4c22-bcef-3a03c11919d7)


- In Git we have a concept of reference object, We have two reference objects
    - branch
    - tag

- In Git by default we are working on a branch called as master
- According to our understanding so far, A branch points to the latest commit


**Commands used**

```
git log
git status
git log --oneline
git restore --staged <file path>
```

![image](https://github.com/user-attachments/assets/97457670-6fd4-4fdb-bae2-1ce17f32f155)

- Git internally uses SHA1 hash for everything

- **Commit:** This is hash of changes, parent commit, author, date time, message

**For git**

- file: blob
- folder: tree

# March 23

### Git Contd..

**To Staging Area**

- Add all changes git add -A
- Add only modified files but not untracked

**ignoring files**

- To ignore certain files, in the root folder of repository create a file called as .gitignore
- To remove all untracked files from working tree git clean -fd .

**Git branch**

- [Refer Here](https://www.atlassian.com/git/tutorials/using-branches) for docs
- Branch always points to latest commit on it
- In Git default branch is master and now a days majority of the organizations have moved to main as default branch.
- To rename branch git branch -m <new-name>
- To create a new branch git branch <new-branch-name>

![image](https://github.com/user-attachments/assets/c555b725-ca87-4401-a62b-e03a8d50eb49)

- To checkout to a branch (HEAD pointing to other branch)

![image](https://github.com/user-attachments/assets/d586bde0-cb00-4645-86d5-984d2140a2fb)


![image](https://github.com/user-attachments/assets/0a5f801b-c419-40eb-afa3-52c39ae76f36)


- Now lets do a couple of commits

![image](https://github.com/user-attachments/assets/6d1992ac-19c4-4685-b5c3-9bdefa1c9d00)

![image](https://github.com/user-attachments/assets/404f1e65-f6bc-4eac-a305-e26cd23614e5)

- Lets checkout to main

#### Git Tag

- [Refer Here](https://www.atlassian.com/git/tutorials/inspecting-a-repository/git-tag) for docs
- Tag always points to a specific commit


# March 25

### Branches

- Bringing the changes from one branch to another
    - Merging
    - Rebase
    - Cherry-pick (specific commits not complete branch)
- [Refer Here](https://www.atlassian.com/git/tutorials/using-branches/git-merge) for merge documentation

### Lab Setup

- I have create a local repo to simulate the below graph

![image](https://github.com/user-attachments/assets/27b336a8-8531-4d39-8c48-a9b827e3c0e5)

### Merge Instructions

- Always check out to destination branch (branch which wants changes)

```
git checkout <destination-branch-name>
```

- Execute the command to merge from the source branch (branch from which changes are requrired)

```
git merge <source-branch>
```

### Fast Forward Merge

- Overview

![image](https://github.com/user-attachments/assets/08d3894f-2104-4171-8e91-7a2df5910318)

- Commands

![image](https://github.com/user-attachments/assets/2cd94180-5ae1-495f-be7e-fc9f90b1f61f)

### Merge (Standard)

- Overview

![image](https://github.com/user-attachments/assets/39756edd-667b-47e7-92aa-a4b8c0ef6663)

- use the same commands

### Rebase

- Overview

![image](https://github.com/user-attachments/assets/0d47547d-e428-4e10-98d0-70ce77a33da4)

- [Refer Here](https://www.atlassian.com/git/tutorials/rewriting-history/git-rebase) for docs.

- **Commands:**
      - checkout to destination or target branch git checkout <destination-branch-name>
      - rebase from source branch git rebase <source-branch>

![image](https://github.com/user-attachments/assets/da73e882-b6db-43dd-baf9-f62deb4a44d1)

### Merge-conflicts

- [Refer Here](https://www.atlassian.com/git/tutorials/using-branches/merge-conflicts) for docs

![image](https://github.com/user-attachments/assets/65131ef7-ccde-4410-8257-9d3dd90a04ce)


# March 26

## Rebase Conflicts

- We can get merge conflicts during rebase as well
- Watch classroom video for example

## Cherry pick

- [Refer Here](https://www.atlassian.com/git/tutorials/cherry-pick) for docs

![image](https://github.com/user-attachments/assets/7c7b4630-36d2-481e-adbb-32baa8857f6b)


## Interactive Rebase

### Change the commit message of latest commit

- Fixing commit message of latest commit

![image](https://github.com/user-attachments/assets/3f187b0c-fc72-42c2-a9e5-48dbc0b871fd)


### Watch classroom video for
- Changing older commit messages
- Deleting commits
- combining commits (squash)
- rework on older commit



# March 27

## Recovering Deleted commits
- Git has two types of logs
    - log
    - ref-log: This is a permanent log but available only in .git folder
- Watch classroom video for steps

## Detached Head
- Detached Head refers to a state where HEAD is pointed towards a commit rather than a branch.
- We can use this for verifying changes but never start committing changes in this case, as changes might be lost.
- Best Practice: If you want to work on the older commit,
     - checkout to that commit
     - create a branch from there git switch -c "<branch-name>"
     - Now make changes in this branch
     - if the changes are required any where else use merge or cherry-pick.

## Remote

- Git remote is another repo which is ideally containing the same code as yours.
- Git Remote can be hosted
     - locally on your system for local usage (This doesnot make sense)
     - Organizations hosting git on servers owned by them (Self Hosted Git)
          - Gitolite
          - Gerrit (Hosting + Code Reviews)
          - Gitlab Self Hosted Version
          - GitHub Enterprise (SelfHosted)

     - Cloud Hosted Git Remotes Cloud deployment consulting
          - GitHub
          - [ Azure](https://directdevops.blog/2025/03/27/devops-classroom-notes-27-mar-2025/#) Source Repos
          - AWS Code Commit
          - Atlassian Bit Bucket
          - GitLab

## Fourth Area of Git
- Remote Repo

![image](https://github.com/user-attachments/assets/345c9a96-3d50-4f82-9ad2-0760a575caf4)


## Terms
- Clone: When you donot have local copy of the repo and want it on your system you perform clone
- pull: to get the latest commits into your local repo (need to dive more)
- push: to send the commits from your local repo to remote repo
- Every remote repo has a url and a name. origin is the default remote repo name.

## Lets create a repo in github
- In github we can create public repos or private repos.
- Let me create a public repo

![image](https://github.com/user-attachments/assets/06cbb276-f43e-410c-9577-8230299697e7)

## Lets clone a repo

- Let clone git clone repo-url

![image](https://github.com/user-attachments/assets/ae3d26d8-004f-44f6-8839-e85e244ef3a7)

- lets cd into folder and execute git commands

![image](https://github.com/user-attachments/assets/ca70da7c-96bf-4669-afd3-d29060bc07a7)

- Lets create a commit and push the changes

# March 28

## Git Remote Repos contd

- Every remote repo added to the git brings in additional branches
- One local repo can be connected to more than one remote repos.
- The command to push the changes is

### git push <remote-name> <branch-name>

![image](https://github.com/user-attachments/assets/6e406927-5018-4225-baac-b7adc056b776)

- Git pull fetch + merge : DO this when you dont have local changes
- git pull –rebase fetch + rebase: DO this when you have local changes for cleaner history.
- Git push => git push <default-remote> <upstream branch>
- Upstream branch: For the local branch in your repo what is the equivelent remote branch
- Syncing changes from one remote repo to other is a straight forward
     - Add two repos as remote to you local repo (clone from source repo and add remote of the destination)
     - now push branches by using git push <dest-remote> <branch>

### Developer Workflows

- Developer will be working on new features or defects
- Note: Watch the classroom recording


# April 1

## Continuous Integration (CI)

- To solve the problems with Big Bang Integration, Continuous Integration was proposed
- The Basic Idea of CI is
      - Perform Integration of all components on every change by any component, initially it might fail
- CI =
    - Build/package the code
    - Run tests:
         - unit tests, integration tests
         - smoke tests, sanity tests
    - Static Code Analysis

- Who should run CI?
    - Manual: Not feasible
    - Automated

- To Perform Automated CI, We need [ softwares](https://directdevops.blog/2025/04/01/devops-classroom-notes-01-apr-2025/#). This is what CI/CD Engine is all about. Some Examples
    - Cruise Control
    - Jenkins/Hudson
    - Azure DevOps
    - Github Actions

#### Basic Principle of Automate
- Know manual steps
- Improve Readabililty:
    - automated steps
    - executions

#### Manual steps

###### Building/Packaging the code

- I will be focusing of 4 tech stacks
    - java
    - .net
    - python
    - react/angular using node js
- We will Docker build steps

### Running Applications
#### Categorization
- Compiled: executable with no extra installation 
    - C
    - C++
    - Golang
- Interpreted: directly run code with installed interpretor
    - Python
    - node js
- Hybrid: Get IL/Bytecode and run on IL with install runtime
    - Java
    - C#

![image](https://github.com/user-attachments/assets/1c090dc0-03c4-4bbb-a0da-c5fc51907569)


#### Java

- Basic Build steps
- [Refer Here](https://directdevops.blog/2025/04/01/devops-classroom-notes-01-apr-2025/cicd33.png)

#### Exercise
- Compile a C language hello-world code
- Findout what GNU make tool.

# April 3

### Lab setup for building java projects

- Create a free tier ubuntu vm on azure or aws

#### Tools helping Building java code
- We have javac which is basic java compiler
- For larger projects in very intitial phases, javac was used with make files
- [Apache Ant](https://ant.apache.org/) was introduced which helps in building java projects. Ant projects have build.xml which will have build instructions. The build.xml is configuration of what has to be done

#### Maven

- Maven is a tool that is introduced to manage projects. Maven
    - manages dependencies
    - performs build, package, artifact management
    - create documentations
- Maven uses Convention over Configuration model

#### Setup on Ubuntu

- Install openjdk 17

```sudo apt install openjdk-17-jdk -y```

- Install [maven](https://maven.apache.org/)

```sudo apt install maven -y
```
```
mvn --version
Simple maven commands mvn <goal>
```
- Simple maven commands mvn <goal>
```
mvn compile
mvn test
mvn package
```

- Conventions:
     - [pom.xml](https://maven.apache.org/guides/introduction/introduction-to-the-pom.html) file is required in the root directory of the project
     - [Folder structure](https://maven.apache.org/guides/introduction/introduction-to-the-standard-directory-layout.html)
- We have created a pom.xml file with following content

```
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 https://maven.apache.org/xsd/maven-4.0.0.xsd">
    <modelVersion>4.0.0</modelVersion>
    <groupId>io.learningthoughts.projects</groupId>
    <artifactId>helloworld</artifactId>
    <version>1.0-SNAPSHOT</version>

    <properties>
        <maven.compiler.source>17</maven.compiler.source>
        <maven.compiler.target>17</maven.compiler.target>
    </properties>
    <dependencies>
        <!-- https://mvnrepository.com/artifact/software.amazon.awssdk/s3 -->
        <dependency>
            <groupId>software.amazon.awssdk</groupId>
            <artifactId>s3</artifactId>
            <version>2.31.6</version>
            <scope>compile</scope>
        </dependency>
    </dependencies>

</project>
```

- We have created the folder structure src/main/java
![image](https://github.com/user-attachments/assets/2498f7a5-
97cd-40d1-b83a-e07dee593366)


- Now execute mvn compile
![image](https://github.com/user-attachments/assets/fbbcc155-34be-46b3-afc1-719007b7dd49)

- To package mvn package
![image](https://github.com/user-attachments/assets/c077ceed-7fb4-4975-b9c2-af3983c464b0)

- Projects skeleton or structure can be created using archetypes

```
mvn archetype:generate \
  -DgroupId=io.learningthoughts \
  -DartifactId=generated \
  -DarchetypeArtifactId=maven-archetype-quickstart \
  -DarchetypeVersion=1.5 \
  -DinteractiveMode=false
```

# April 4

## Building Java Code using Maven

- Maven Goals:
    - [Refer Here](https://www.baeldung.com/maven-goals-phases) to this article
- [POM Schema](https://maven.apache.org/pom.html)
- Maven Projects are generally organized in two styles
    - pom.xml with src folder (default structure): This represents a single project. Spring petclinic
    - pom.xml with modules which are directories which contain child poms[Broadleaf](https://github.com/BroadleafCommerce/DemoSite)

- Commands
   - mvn <phase>:
        - mvn package

   - mvn :
        - mvn clean package

![image](https://github.com/user-attachments/assets/f7f4e317-f2c9-4400-917a-39e2dc474093)



# April 5

## Maven Contd..

- Maven Remote Repositories can be hosted using Many tools
    - Jfrog Artifactory
    - Nexus
    - Github Pacakges
    - Azure Artifacts

### Lets redefine CI
- CI = build + test + package + archiveArtifact
- Sample Projects
    - [Spring petclinic](https://github.com/spring-projects/spring-petclinic)
    - [Broadleaf Demosite](https://github.com/BroadleafCommerce/DemoSite)

#### Activity: Build a Java Project
- This project requires jdk 17 and maven 3.9.9
- This requires downloading and setting up maven, refer classroom video for steps

#### Activity: Build a Java Project which has maven wrapper
- This project requires jdk 17 and maven 3.9.9

```./mvnw package```

### Gradle
- This was introduced by google for building andriod projects
- Gradle has features for both ant and maven
- Gradle has a feature of incremental build

#### Compare Maven and Gradle
- Here's how some common tasks compare between Maven and Gradle:

| Task             | Maven Command              | Gradle Command          |
|------------------|----------------------------|--------------------------|
| Clean            | `mvn clean`                | `./gradlew clean`        |
| Compile          | `mvn compile`              | `./gradlew build`        |
| Run Tests        | `mvn test`                 | `./gradlew test`         |
| Package JAR      | `mvn package`              | `./gradlew jar`          |
| Add Dependencies | Edit `pom.xml`             | Edit `build.gradle`      |



### Building .net core projects

- Install .net sdk 9 [Refer Here](https://learn.microsoft.com/en-us/dotnet/core/install/linux-ubuntu-install?tabs=dotnet9&pivots=os-linux-ubuntu-2404#ubuntu-2404) for steps
- Projects:
    - [eShop](https://github.com/dotnet/eShop)
    - [nopCommerce](https://github.com/nopSolutions/nopCommerce)

### Building reactjs projects using npm
- Lets try build,test, package of a react js aplication
- [todoMvc](https://github.com/tastejs/todomvc) is sample repo
- To install node and npm i prefer [nvm](https://github.com/nvm-sh/nvm?tab=readme-ov-file#install--update-script)
- Basic steps: Navigate to package.json to find out scripts
- Generally
```
npm install
npm run build
npm run test
```

- There are other alternatives like npx, yarn etc…
![image](https://github.com/user-attachments/assets/8eb9e8cb-89c6-4c20-93b0-c7a321e9677e)


# April 6

## CI-CD Engines
- This software helps in building CI/CD Pipelines
- A Pipeline is set of steps that needs to be executed in some order
- Popular Options:
    - Jenkins
    - Bamboo
    - Azure DevOps
    - Github Actions
    - Gitlab CI

- Popular styles of pipelines
    - UI Enabled Pipeline Creations:
        - Jenkins (Free Style Projects)
        - Azure DevOps (Classic Pipelines)
    - Pipeline as Code: Pipeline steps are part of version control.

### Azure DevOps
- Azure DevOps offers complete ALM (Application Lifecycle Management) tools i.e. it offers
    - Boards (Plan, Organize projects)
    - Azure Source Repos (Version Control)
    - Azure Pipelines
    - Azure Test Plan
    - Azure Artifacts
- Azure DevOps Has [two major options](https://azure.microsoft.com/en-us/pricing/details/devops/azure-devops-services/)
    - Azure DevOps Server
    - Azure DevOps Service

- [Signup For Azure Devops](https://learn.microsoft.com/en-us/azure/devops/user-guide/sign-up-invite-teammates?toc=%2Fazure%2Fdevops%2Fget-started%2Ftoc.json&view=azure-devops&tabs=microsoft-account)
- Azure DevOps Organization: [Refer Here](https://learn.microsoft.com/en-us/azure/devops/organizations/accounts/create-organization?view=azure-devops) for creation, For creating [Projects](https://learn.microsoft.com/en-us/azure/devops/organizations/projects/create-project?view=azure-devops&tabs=browser)

![image](https://github.com/user-attachments/assets/d963d38b-ed38-4928-9117-7bdc4841cdbb)


- Findout the following terms in the context of Agile
    - Epic
    - User Story
    - Product Backlog
    - Sprint Backlog
    - Daily Standup Meetings

#### Azure Source Repos
- Azure DevOps has a way to host version control systems. It supports git and TeamFoundation Version Control
- Azure DevOps Notifications can be linked to [microsoft teams](https://learn.microsoft.com/en-us/azure/devops/service-hooks/services/teams?view=azure-devops)

#### Azure Pipeline Agents
- Agents are the systems where the pipelines are executed.
- [Agent types](https://learn.microsoft.com/en-us/azure/devops/pipelines/agents/agents?view=azure-devops&tabs=yaml%2Cbrowser)
    - Microsoft Hosted Agents
    - Self Hosted Agents

#### Activity
- Import Spring petclinic into Azure DevOps Source Repos and ensure main is the default branch. [Refer Here](https://dev.azure.com/khajatech/DevOps2025/_git/spring-petclinic.git)

![image](https://github.com/user-attachments/assets/af9e5a65-0ef0-44da-b2bb-e59fadfac1a0)


- Set Git Credentials via ssh preferably

![image](https://github.com/user-attachments/assets/0f282a21-9af5-4ce2-a357-3e8e48511fff)

- Now create a develop branch
- Watch classroom video for basic pipeline
- Next Steps:
    - Configuring Self Hosted Agents
    - Learning to write basic pipelines in yaml
- Exercise: [YAML and JSON](https://www.youtube.com/watch?v=ggOmHlnhPaM&list=PLuVH8Jaq3mLud3sVDvJ-gJ__0zd15wGDd&index=15)

# April 7th

## Azure Pipelines

- Azure Pipelines are written in YAML Format.
- YAML is a data representation format with key value (name value) pairs as it basic structure.

- The tool will define th structure
    - [Azure DevOps](https://learn.microsoft.com/en-us/azure/devops/pipelines/yaml-schema/?view=azure-pipelines)
    - [K8s](https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.32/)
    - [Compose](https://docs.docker.com/reference/compose-file/)
- YAML represents data in name value
- name: <value>

- Values can be of following types
    - text
    - number
    - boolean
    - list/array
    - map/object
- Text
```
title: Court
title: "Court"
title: 'Court'
```

- numbers
```
duration: 149
rating: 9.5
```

- boolean
```
imax: false
imax: no
```

- list or array
```
cast: ["Priyadarshi", "Harsh", "Shivaji"]
cast:
- Priyadarshi
- Harsh
- Shivaji
```

- map/dictionary/object:
- Crew:
```
  director: Ram Jagadeesh
  producer: Nani
  music: Vijay
```

- complete yaml
---
title: Court
duration: 149
rating: 9.5
imaxEnabled: no
Cast:
  - Priyadarshi
  - Harsh
  - Shivaji
Crew:
  director: Ram Jagadeesh
  producer: Nani
  music: Vijay

- Lets write about one more movie in the same yaml
---
title: Court
duration: 149
rating: 9.5
imaxEnabled: no
Cast:
  - Priyadarshi
  - Harsh
  - Shivaji
Crew:
  director: Ram Jagadeesh
  producer: Nani
  music: Vijay
---
title: Chhaava
duration: 161
rating: 9.2
imaxEnabled: no
Cast:
  - Vicky
  - Rashmika
  - Akshay
Crew:
  director: Laxman Utekar
  producer: Dinesh Vijan
  music: A.R Rehman

- If we want some one to fill the movie we define fields and types
```
title: <text>
duration: <number>
ratings: <number>
imaxEnabled: <boolean>
Cast: text array | list<text> | list<string>
Crew: <Crew>

Crew:
director: <text>
producer: <text>
music: <text>
```

### Understanding Azure DevOps Pipeline Concepts
- pipeline structure (First Version)

![image](https://github.com/user-attachments/assets/2346458b-4d86-47da-b692-fdc0d427a2fd)

- An Agent i.e. a machine to build can be chosen at
    - Pipeline
    - Stage
    - Job
![image](https://github.com/user-attachments/assets/dcb2435d-10b0-44e3-979c-482a2f817926)

- To Simplify the pipeline
    - If your pipeline has one stage and muliple jobs, then represent pipeline has set of jobs
    - If your pipeline has one stage, one job and multiple steps, then represent pipeline as set of steps

#### Lets create our first dummy pipeline
- Lets create a pipeline which runs on microsoft hosted agent which will have Windows OS
- It will have 3 stages
    - Build
    - It will have 1 jobs
        - build the code
    - System Test
        - It will have 1 job which starts the selenium tests
    - Deploy
        - It will have 1 job which runs the terraform
- Pool defines the agents. Check for [agent names](https://learn.microsoft.com/en-us/azure/devops/pipelines/agents/hosted?view=azure-devops&tabs=yaml#software)
- This is dummy as it will only print the value but not execute

---
name: dummy
pool: windows-2022
stages:
- stage: build
  jobs:
  - job: build
    steps:
    - script: echo Building
- stage: test
  jobs:
  - job: test
    steps:
    - script: echo testing
- stage: deploy
  jobs:
  - job: deploy
    steps:
    - script: echo deploying
I have one stage, one job and 3 steps
---
name: dummy
pool: ubuntu-latest
steps:
- script: echo step1
- script: echo step2
- script: echo step3


- Pipeline generated in last session
- trigger: 
    - main
- pool:
    - vmImage: ubuntu-latest

- steps:
- task: Maven@3
``` 
inputs:
    mavenPomFile: 'pom.xml'
    mavenOptions: '-Xmx3072m'
    javaHomeOption: 'JDKVersion'
    jdkVersionOption: '1.17'
    jdkArchitectureOption: 'x64'
    publishJUnitResults: true
    testResultsFiles: '**/surefire-reports/TEST-*.xml'
    goals: 'package'
```

# April 8

## Configuring Self hosted Agent in Azure DevOps
- [Refer Here](https://learn.microsoft.com/en-us/azure/devops/pipelines/agents/linux-agent?view=azure-devops&tabs=IP-V4) for self hosted linux agents

## Lets create an Ubuntu 24.04 Agent
- Softwares:
    - Openjdk
    - Maven

- Azure DevOps Agent Setup:
    - This requires a PAT (Personal Access Token)

![image](https://github.com/user-attachments/assets/c5e5f8bc-bd69-4479-8534-7c01b8c03b34)


### Activity
- Lets create a pipeline to build the maven project
- [Azure Devops YAML Schema](https://learn.microsoft.com/en-us/azure/devops/pipelines/yaml-schema/?view=azure-pipelines)
- Generic Pipeline:
    - When to run
    - What has to be executed
    - Where it has to run
    - metadata
- In Azure DevOps Pipelines
    - What is decided by steps
    - Where is decided by pool section
    - when is decided by triggers
- Manual step
```
git clone <url>
cd <folder>
mvn package
```
- When: whenver any change is pushed to main branch
- Where: ON a self hosted agent
- [Refer Here](https://github.com/dummyrepos/Spc-ado-march25/commit/721e681e4259e7593302d2f1a1a1c38db15219cb) for the first pipeline

```
name: spring-pet-clinic
name: spring-pet-clinic

trigger:
  - main

pool: Default

steps:
  - script: ./mvnw clean package
Lets try using Task

name: spring-pet-clinic

trigger:
  - main

pool: Default

steps:
  - task: Maven@4
    displayName: Maven Build
    inputs:
      mavenPOMFile: 'pom.xml'
      goals: 'package'
      testResultsFiles: '**/surefire-reports/TEST-*.xml'
```

- [Refer Here](https://github.com/dummyrepos/Spc-ado-march25/commit/ddcd0c09c90439ca8514d2c73190913d83b936c4) for the changes with task

### Azure DevOps Steps
- A step is an activity in azure devops pipeline.
- [Azure DevOps Steps types](https://learn.microsoft.com/en-us/azure/devops/pipelines/yaml-schema/steps?view=azure-pipelines#list-types)
- [Azure DevOps Tasks](https://learn.microsoft.com/en-us/azure/devops/pipelines/tasks/reference/?view=azure-pipelines)


# April 9

## Pull requests (Merge Requests) PR
Directly allowing push to the branches might lead to failure propagations.
To ensure that the each change is reviewed and the tests are passing, we use pull requests

![image](https://github.com/user-attachments/assets/45f17db5-2c5b-4a23-ad37-28f2dfd9f94d)

- [Azure DevOps PRs](https://learn.microsoft.com/en-us/azure/devops/repos/git/about-pull-requests?view=azure-devops)
- Watch classroom video for creating PRs
- Next Steps:
    - elaborate pipelines for
        - PR:
            - build
            - unit test
            - packaging
            - code analysis
        - Branch:
            - build
            - unit test
            - packaging
            - code analysis
            - Functional tests


# April 10

### CI strategy
- We have following usecases
    - Developers create PRs
    - PRs getting merged into development branch
    - Tester need to test the application
        - Unit tests, smoke tests, Sanity Test => every change (Day Builds)
        - System Tests => Happen once in a day which combines all of the development activtity (Night Builds)

![image](https://github.com/user-attachments/assets/7572eec0-5f79-4b14-93c7-c848e1757bbf)


# April 12

## Microsoft Hosted Agents
- Microsoft hosted agents are hosted by ado
- For list of agents with softwares installed in it [Refer Here](https://learn.microsoft.com/en-us/azure/devops/pipelines/agents/hosted?view=azure-devops&tabs=yaml#software)

### Dotnet core build on Microsoft Hosted Agent
- Watch classroom video
- Run on every pull request to develop branch

```
---

pool:
  vmImage: ubuntu-latest

trigger: none

pr:
  - develop

steps:
  - task: DotNetCoreCLI@2
    displayName: Restore Projects
    inputs:
      command: restore
      projects: "src/NopCommerce.sln"
  - task: DotNetCoreCLI@2
    displayName: Build the Web Project
    inputs:
      command: build
      projects: "**/Nop.Web.csproj"
```

- Run on every change pushed to develop branch i.e. this executes whenever a PR is merged.

```
pool:
  vmImage: ubuntu-latest

trigger:
  - develop


steps:
  - task: DotNetCoreCLI@2
    displayName: Restore Projects
    inputs:
      command: restore
      projects: "src/NopCommerce.sln"
  - task: DotNetCoreCLI@2
    displayName: Build the Web Project
    inputs:
      command: build
      projects: "**/Nop.Web.csproj"
  - task: DotNetCoreCLI@2
    displayName: Run the tests
    inputs:
      command: test
      projects: "**/Nop.Tests.csproj"
```

- Run pipeline on schedule
    - day build every 2 hours on a weekday
    - nightly build on release branch at 10 PM
- Day build for every 2 hours on weekdays

```
pool:
  vmImage: ubuntu-latest

trigger: none

schedules:
  - cron: "30 */2 * * 1-5"
    displayName: "CI Schedule every 2 hours on Weekday"
    branches:
      include:
        - develop
    batch: false
    always: false


steps:
  - task: DotNetCoreCLI@2
    displayName: Restore Projects
    inputs:
      command: restore
      projects: "src/NopCommerce.sln"
  - task: DotNetCoreCLI@2
    displayName: Build the Web Project
    inputs:
      command: build
      projects: "**/Nop.Web.csproj"
  - task: DotNetCoreCLI@2
    displayName: Run the tests
    inputs:
      command: test
      projects: "**/Nop.Tests.csproj"
```

- Exercise: Try React Js Project

## Reusability
### Parameter & Variables

- [ Azure](https://directdevops.blog/2025/04/12/devops-classroom-notes-12-apr-2025/#) DevOps Pipeline Variables
- Azure DevOps has lots of predefined variables with information about
    - build
    - agent


- Allows us to use Environmental Variables
- Allows to create user defined variables
- Allows to organize variables in a variable group

### Exercise:
- Add publish in the devops ci pipeline which runs once every 2 hours
- Also add configuration = Release for CI and configuration = Debug for PR pipeline


# April 13

## Variables in pipelines
- [Predefined variables](https://learn.microsoft.com/en-us/azure/devops/pipelines/build/variables?view=azure-devops&tabs=yaml)
- [user defined variables](https://learn.microsoft.com/en-us/azure/devops/pipelines/process/variables?view=azure-devops&tabs=yaml%2Cbatch#user-defined-variables)

## Template
- A Template is a reusable pipeline component
- Watch classroom Recording

## Azure DevOps Marketplace
- In [Azure DevOps Marketplace](https://marketplace.visualstudio.com/azuredevops/) we can find community task
- We can create our own [custom tasks](https://learn.microsoft.com/en-us/azure/devops/extend/develop/add-build-task?view=azure-devops)

# April 26

### Github Actions
- Github Actions run workflows on github events such as
    - push
    - pull request
    - schedule etc..
- Github actions workflow is a yaml file which is stored in .github/workflows folder
- Workflows run on Runners. Runners are of two types
    - [Github/Microsoft Hosted Runners](https://docs.github.com/en/actions/using-github-hosted-runners/using-github-hosted-runners/about-github-hosted-runners#standard-github-hosted-runners-for-public-repositories)
    - Self Hosted Runners

### Pricing
- Here’s the GitHub Actions pricing comparison between open-source (public repositories) and private projects:

| Feature                | Open-Source Projects (Public Repos) | Private Projects |
|------------------------|-------------------------------------|------------------|
| **GitHub-hosted runners** | Free (unlimited minutes)[1][2]        | Limited free minutes based on plan (see below), then pay-per-use[1][5] |
| **Storage included**       | Not specified                         | 500 MB (Free) to 50 GB (Enterprise Cloud)[1][5] |
| **Overage charges**        | Not applicable                        | Storage: $0.008/GB/day[1]  <br> Minutes:  <br> - Linux: $0.008/min  <br> - Windows: $0.016/min  <br> - macOS: $0.08/min[5] |

- Private project plans (monthly free minutes/storage):

| Plan                     | Free Minutes | Free Storage |
|--------------------------|--------------|---------------|
| **GitHub Free**          | 2,000        | 500 MB        |
| **GitHub Pro**           | 3,000        | 1 GB          |
| **GitHub Team**          | 3,000        | 2 GB          |
| **GitHub Enterprise Cloud** | 50,000       | 50 GB         |

- Note: Larger runners (not standard) always incur charges, even for public repositories[1]. Self-hosted runners remain free for both public and private repos[1][9].

- Citations:

[1] https://docs.github.com/billing/managing-billing-for-github-actions/about-billing-for-github-actions

[2] https://github.com/pricing

[3] https://github.com/pricing/calculator

[4] https://docs.github.com/get-started/learning-about-github/githubs-products

[5] https://octopus.com/devops/github-actions/

[6] https://projectmanagers.net/github-pricing/

[7] https://docs.github.com/en/apps/github-marketplace/listing-an-app-on-github-marketplace/setting-pricing-plans-for-your-listing

[8] https://www.upguard.com/blog/bitbucket-vs-github

[9] https://docs.github.com/en/actions/administering-github-actions/usage-limits-billing-and-administration

- Answer from Perplexity: pplx.ai/share

#### Workflow YAML
- [Refer Here](https://docs.github.com/en/actions/writing-workflows/workflow-syntax-for-github-actions) for structure

![image](https://github.com/user-attachments/assets/e88ab108-7f54-4a6c-a4d7-e49cca384956)

- Workflow has
    - Events: Which trigger workflow
    - Jobs:
        - Each job executes on a runner
        - job consists of steps
              - A step can be acheived
              - actions
              - run

#### First Workflow : Spring petclinic
- Whenever developer raises a pull request execute mvn package
- [Refer Here](https://github.com/KhajasCICDSamples/spring-petclinic-apr25) for repository
- For screen shots watch classroom video

```
# This workflow will build a Java project with Maven, and cache/restore any dependencies to improve the workflow execution time
# For more information see: https://docs.github.com/en/actions/automating-builds-and-tests/building-and-testing-java-with-maven

# This workflow uses actions that are not certified by GitHub.
# They are provided by a third-party and are governed by
# separate terms of service, privacy policy, and support
# documentation.


name: Day build

on:
  push:
    branches: [ "main" ]
  pull_request:
    branches: [ "main" ]

jobs:
  build:

    runs-on: ubuntu-latest

    steps:
    - uses: actions/checkout@v4
    - name: Set up JDK 17
      uses: actions/setup-java@v4
      with:
        java-version: '17'
        distribution: 'temurin'
        cache: maven
    - name: Build with Maven
      run: mvn clean package

```

- [Refer Here](https://github.com/KhajasCICDSamples/spring-petclinic-apr25/commit/c5902d2b1aa009663ef8c7cc4af12190c00fc1da) for the changes done
- [Refer Here](https://github.com/KhajasCICDSamples/spring-petclinic-apr25/commit/b5315785fa001c6890a06eb247f4738ebfaa5b24) for the first version written by us.

### How to write a Workflow
- [Refer Here](https://docs.github.com/en/actions/writing-workflows/workflow-syntax-for-github-actions)
- Events that can trigger the workflows [Refer Here](https://docs.github.com/en/actions/writing-workflows/choosing-when-your-workflow-runs/events-that-trigger-workflows)
- [Actions market place](https://github.com/marketplace?type=actions)

##### Exercise:
- Try building nop Commerce on push to the branch
- [Refer Here](https://github.com/KhajasCICDSamples/nopCommerce-apr-25) for repo
- [Refer Here](https://github.com/KhajasCICDSamples/nopCommerce-apr-25/commit/e1b6d103310fe4cfbdbec1882cab0b75cd5ff34c) for changes

### Setup self hosted runner.
- [Refer Here](https://docs.github.com/en/actions/hosting-your-own-runners/managing-self-hosted-runners/adding-self-hosted-runners) for adding selfhosted runners

### Test results and uploading artficats
- [Refer Here](https://github.com/KhajasCICDSamples/spring-petclinic-apr25/blob/main/.github/workflows/maven.yml) for yaml

##### Exercise:
- try publishing the nop commerce publish folder zip
- Try executing the workflow on pull request and show test results


# April 27

### Code Quality Analysis
- Static code analysis:
    - SonarQube
    - CodeQL
- Analysis using Sonar Cloud
    - Create a [Sonar Cloud Account](https://sonarcloud.io/) with your github account
    - Analyze new project and select organization/repositories in your Github
    - Generate a sonar cloud token
- [Refer Here](https://docs.sonarsource.com/sonarqube-server/latest/devops-platform-integration/github-integration/introduction/) for code analysis

# May 4

### Branching Strategy
- on a broader note we have following branching strategies
    - Git Flow
    - GitHub Flow
    - Gitlab Flow
    - Trunk
- Our Branching Strategies
    - main branch: This reflects the production state
    - develop branch: This reflects the latest delivered changes after merging pull requests
    - release branches: Will reflect the changes done the developers during last day
    - feature/defect branches: created from develop branch and pull request will be created to merge changes into develop branch
- Watch classroom video for steps

- Fifth area of git

![image](https://github.com/user-attachments/assets/07e3b1df-0951-40a4-a484-1caeb297cc44)

- [Refer Here](https://git-scm.com/docs/git-stash) for git stash reference
- [Refer Here](https://www.atlassian.com/git/tutorials/saving-changes/git-stash) for docs

### Git clone types
- Git has three major types of clones
    - normal => working tree + local repo + remote connection
    - bare clone => local repo + remote connection


# May 19 (Terraform)

# Terraform

### Why Do We need Terraform (Infra Provisioning)

#### Hypothetical application (Tomato – clone of zomato)
- We are trying to build a food delivery application with the following architecture

![image](https://github.com/user-attachments/assets/05c2081d-3282-4dbf-9a34-f1a4821bd684)

- Infrastructure (Servers, Network, storage etc) is required to run your application.
- Possible ways of Getting Infra
    - On-premises:
        - Physical Servers
        - Virtual Machines
    - Cloud
        - Virtual Machines
        - Networking
        - Storage
        - Databases
        - Kubernetes

- If your organization is using physical servers directly, only way to create infra is manual in nature. But if the infrastrucutre is virtual (On-premises/Cloud) we can automate infra creation an updates
- On-Premise Hypervisor Providers

| Hypervisor                            | Type   | Key Strengths                                                                                           | Typical Use Case                                |
|---------------------------------------|--------|----------------------------------------------------------------------------------------------------------|-------------------------------------------------|
| VMware ESXi / vSphere                 | Type 1 | High stability and performance; advanced features like vMotion, Fault Tolerance; strong security; wide guest OS support | Large enterprises, data centers                |
| Microsoft Hyper-V                    | Type 1 | Seamless Microsoft ecosystem integration; cost-effective for Windows; scalable and secure               | Microsoft-centric organizations                 |
| KVM (Kernel-based Virtual Machine)    | Type 1 | Open-source and customizable; excellent performance and scalability; broad Linux support                | Linux environments, cloud infrastructure        |
| Citrix XenServer / Xen               | Type 1 | Strong isolation and security; supports paravirtualization and hardware virtualization; live migration  | Enterprises using Citrix products, cloud providers |
| Red Hat Virtualization (RHEV)        | Type 1 | Enterprise support; integration with Red Hat products; advanced management and automation               | Red Hat-based enterprise environments           |
| Nutanix Acropolis Hypervisor (AHV)   | Type 1 | Tight integration with Nutanix HCI; simple and user-friendly management                                 | Nutanix hyperconverged infrastructure deployments |


![image](https://github.com/user-attachments/assets/611a2b82-c952-4339-ae1e-9f4eef9395c5)

- Since we have lot of different providers with their own tools/sdks to automate, Learning all options is not sensible.
- This is where Terraform By HashiCorp comes to our rescue, Use any provider but automate infra using Terraform
- Terraform offers declarative approach in infra creation
- Terraform has its own language called as HCL (Hashicorp Configuration lanaguage)
- New Trend: Tools like terraform, cloud have started offering CDKs where you can use any programming language for declarative approaches.



# May 20

# Terraform

- [Terraform](https://developer.hashicorp.com/terraform) developed by Hashicorp is most widely infra provisioning tool.
- Terraform is developed in Golang
- Opentofu is a fork of Terraform

#### How Terraform works
- Terraform is a single executable.
- Terraform uses Providers to interact with specific cloud / hypervisors
- [Providers](https://registry.terraform.io/browse/providers) are not part of terraform installation, they are part of infra creation.

| Provider Name         | Type              | Description / Use Case                                     |
|-----------------------|-------------------|-------------------------------------------------------------|
| AWS                   | Public Cloud      | Amazon Web Services: Compute, storage, networking, etc.     |
| Azure                 | Public Cloud      | Microsoft Azure: IaaS, PaaS, SaaS services                  |
| Google Cloud          | Public Cloud      | Google Cloud Platform: Compute, storage, analytics         |
| Alibaba Cloud         | Public Cloud      | Alibaba Cloud: Cloud computing and data services           |
| DigitalOcean          | Public Cloud      | Developer-focused cloud infrastructure                     |
| VMware vSphere        | On-premises       | Virtualization platform for managing VMs                   |
| OpenStack             | On-premises       | Open-source cloud platform for private clouds              |
| Kubernetes            | Hybrid/On-premises| Container orchestration, can be on-prem or cloud           |
| Helm                  | Hybrid/On-premises| Kubernetes package manager                                 |
| Cloudflare            | SaaS/Edge         | CDN, DNS, and security services                            |
| Datadog               | SaaS              | Monitoring and analytics platform                          |
| GitHub                | SaaS              | Source code management and CI/CD                           |
| GitLab                | SaaS              | DevOps platform for CI/CD and SCM                          |
| Okta                  | SaaS              | Identity and access management                             |
| Azure Active Directory| SaaS              | Microsoft identity and access management                   |
| HashiCorp Vault       | Security          | Secrets management and data protection                     |
| HashiCorp Consul      | Networking        | Service discovery and configuration                        |
| F5                    | On-premises       | Application delivery networking                            |
| Palo Alto Networks    | On-premises       | Network security (PAN-OS)                                  |
| Cisco                 | On-premises       | Networking hardware and software                           |


- Every Provider will have
    - Resources: an infra element which we can manage from terraform
    - DataSources
- Arguments: on a general note in terraform arguments are inputs
- Attributes: on a general note in terraform attributes are outputs

![image](https://github.com/user-attachments/assets/45de9cad-0fe5-4a88-ba20-90bb750c8c7a)

- To terraform we give a folder with .tf files as input
- Example Terrafrom template

```
terraform {
  required_providers {
    aws = {
      source = "hashicorp/aws"
      version = "6.0.0-beta1"
    }
  }
}

provider "aws" {
  # Configuration options
  region = "ap-south-1"
}


resource "aws_vpc" "main" {
  cidr_block = "10.10.0.0/16"
  tags = {
    Name = "layered-network"
  }
}
```

### Exercise
- Findout documentation for the following
    - aws ec2 instance terraform aws ec2

![image](https://github.com/user-attachments/assets/524397e5-bc7f-4d3c-9e3c-73a84ce3c5b5)

![image](https://github.com/user-attachments/assets/5b8e2f35-160b-4482-a33a-5d7fdd814c32)

- azure storage account
- gcp storage bucket
- aws s3 bucket
- aws eks
- azure aks
- Next Step:
- Lets learn how to write terraform hashicorp configuration language

# May 21

### Writing Terraform Templates

#### Installation
- Windows
    - Terminal Setup
    - Git For Windows
    - chocolatey or winget
    - Visual Studio Code
    - Terraform
    - AWS CLI
    - Azure CLI

- Mac
    - Homebrew
    - Git brew install git
    - Visual Studio Code brew install --cask visual-studio-code
    - Terraform brew tap hashicorp/tap && brew install hashicorp/tap/terraform
    - awscli brew install awscli
    - azure cli brew install azure-cli

### Writing templates
- create a new folder
- open this in visual studio code (Ensure Terraform extension is installed)
- create a new file called as main.tf
- Terraform uses Hashicorp Configuration language, Resources, Providers are Blocks

```
<block-type> <name> .. {

}
```
- [Provider Block](https://developer.hashicorp.com/terraform/language/providers/configuration)

```
provider <name> {
    arg1 = value
    ..
    ..
    argn = value
}
```

- [Resource Block](https://developer.hashicorp.com/terraform/language/resources/syntax)

```
resource <type> <name> {
    arg1 = value
    ..
    ..
    argn = value
}
```

- When we pass arguments terraform has the following [data types](https://developer.hashicorp.com/terraform/language/expressions/types#types)

## Configuring terraform to work with AWS
## Configuring terraform to work with Azure

# May 22

### Using Terraform to Create AWS S3 Bucket
- Resource:
    - S3 Bucket
- Inputs required for resource:
    - region (location)
    - name
- Try: Creating  S3 bucket manually

### Configure AWS CLI Credentials
- Terraform provider by default uses CLI Credentials
- Watch classroom recording on how to create credentials
- Ensure AWS CLI is installed
- Once access key is generated execute aws configure on terminal

### Lets write template
- references
    - [aws provider](https://registry.terraform.io/providers/hashicorp/aws/latest/docs)
    - [s3 bucket resource docs](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/s3_bucket)
      ![image](https://github.com/user-attachments/assets/e5dc2809-5ee9-4135-b14f-d62148f17400)

- [Refer Here](https://github.com/asquarezone/NewTerraformZone/commit/afd1c8b2e9d741371a6836e353d61720666bc87e) for changes done

### Terraform workflow

![image](https://github.com/user-attachments/assets/004bc8bb-e9fa-4406-8f98-870db6a11989)

### Terraform always tries to match your desired state
- In Terraform we use declarative programming to define what we want (desired state)
- Terraform will work to manage infrastructure to meet your desired state.

# May 24

### Terraform contd…
#### Configuring Terraform to work with Azure
- Terraform by default uses  Azure CLI Credentials
- Once Azure CLI is installed. Launch Terminal and execute az login command
- Azure has two providers
    - [hashicorp](https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs): this is what we will be using
    - [microsoft](https://registry.terraform.io/providers/Azure/azapi/latest/docs)

### Lets create a storage account in Azure
- [Refer Here](https://learn.microsoft.com/en-us/azure/storage/common/storage-account-create?tabs=azure-portal) for quick start
- Resources
    - Resource Group:
        - inputs:
            - name
            - location
    - Storage Account
- First we need to create [resource group](https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs/resources/resource_group)
- [Refer Here](https://github.com/asquarezone/NewTerraformZone/commit/aca736701c9e3b8ad6348ef2bd893d7a04a6bb89) for the work done

### Order of Creation
- In Terraform, Resources are created in parallel unless they are dependent on each other.
- There are two ways of defining dependencies
    - intrinsic/implicit
    - extrinsic/explicit

#### Resource name in terraform
- This refers to pointing to a specific resource type.name
```
resource "azurerm_resource_group" "base" {
    name = "fromtf1"
    location = "centralindia"

}

# azurerm_resource_group.base
```

#### Explicit Dependency
- Explicit dependecy can be added to a resource by using a meta argument called as depends_on
```
resource "azurerm_storage_account" "store" {
    name = "fromtfltmay25"
    resource_group_name = "fromtf1"
    location = "centralindia"
    account_tier = "Standard"
    account_replication_type = "RAGRS"
    # explicit dependency
    depends_on = [ azurerm_resource_group.base ]

}
```

- [Refer Here](https://github.com/asquarezone/NewTerraformZone/commit/40a80366ac57a9220489f0e7b48f4c5cb95e73b4) for the template with depends_on


# May 25

## Terraform contd
#### Terraform console
- [Refer Here](https://developer.hashicorp.com/terraform/cli/commands/console) for using terraform console
- To launch terrform console, execute terraform console command in directory with .tf files

#### Implicit depenedency
- [Refer Here](https://github.com/asquarezone/NewTerraformZone/commit/a3b450ba69c94e7a6e59e3ab71aa6b169191edb8) for the changes
- A resource will be dependent on other resource implicitly if the attributes of the other resource are used as arguments.

### AWS: Create a VPC with 4 subnets
- Overview
![image](https://github.com/user-attachments/assets/b55b7b3a-5671-448e-9851-4323fb8dfde2)
- Manual steps

#### Style Guide & Linting in terraform
- Lets follow google style guide for terraform [Refer Here](https://cloud.google.com/docs/terraform/best-practices/general-style-structure)
- terraform fmt or format document in vscode
- updated workflow
    - init
    -  fmt
    - validate
    - apply
    - destroy
- We would be creating the following files in terraform template
    - providers.tf: This file will have all the necessary stuff for configuring providers
    - main.tf: This is where we start with declaring resources
- [Tags for aws](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/guides/resource-tagging)
- [Refer Here](https://github.com/asquarezone/NewTerraformZone/commit/3a2d6cf36f7ff32125c2a827dce9f65093d8a57c) for the changes done

#### Exercise:
-Create a network (Virtual network) in central india with 4 subnets
- note: in  azure there is no need to provide zone while creating subnet

# May 28

## Terraform contd
- AWS: Create a VPC with 4 subnets revisited
- Overview:
![image](https://github.com/user-attachments/assets/aeccccb0-34d5-448f-a516-81107efe5c7d)

#### Variables
- [Terraform variables](https://developer.hashicorp.com/terraform/language/values/variables) allows users to pass the values during execution
- Variable block supports the arguments as [listed here](https://developer.hashicorp.com/terraform/language/values/variables#arguments)
- syntax
```
variable <name> {
    type = 
}
```

- Generally as per google’s style guide we create all the variables in variables.tf or inputs.tf
- To use the variable the syntax is var.<name>
- [Refer Here](https://github.com/asquarezone/NewTerraformZone/commit/3ab288f36b69acfd6ce7ebc64321e0d8534fa4ca) for the variables added to aws vpc and 4 subnets
- We can create a file <name>.tfvars where we can apply all the values and pass this file during terraform apply
- Generally we will have <environment>.tfvars
- [Refer Here](https://github.com/asquarezone/NewTerraformZone/commit/2ba72369db00c429e514e93aea4d9e617bacf10e) for changes done
- Few variables to pass
```terraform apply -var var1=value1 -var var2=value2```
- many variables to pass, create a .tfvars file such as dev.tfvars
```terraform apply -var-file="dev.tfvars"```
- [Refer Here](https://github.com/asquarezone/NewTerraformZone/commit/b2cccf61631a0903bd9e667559e5f4a010189f90) for variables with object types

#### Go through the template and lets discuss about any unknows in next 5 mins

# May 31

### Terraform functions
- Terraform offers [functions](https://developer.hashicorp.com/terraform/language/functions)

#### Terraform meta argument count
- [Refer Here](https://developer.hashicorp.com/terraform/language/meta-arguments/count) for count which helps in creating multiple resources.
- [Refer Here](https://github.com/asquarezone/NewTerraformZone/commit/6c98e8baf831e71b17be39b0f0fb514f0b5698a5) for the changes done to create multiple resources based on variables passed using count function

### Terraform expressions
#### Terraform conditional creation of resources
- We can use count to do this
```
resource 'xxxxx' 'yy' {
    count  = 0
}
```
- [Refer Here](https://github.com/asquarezone/NewTerraformZone/commit/6bdb20f4f380bf51397a3ce952434c153f1f08ce) for the changes done.

#### Terraform locals
- [Refer Here](https://developer.hashicorp.com/terraform/language/values/locals) for official docs
- [Refer Here](https://github.com/asquarezone/NewTerraformZone/commit/2359b401a924a427a61e9795847e13c595a74036) for changes
#### Terraform outputs
- [Refer Here](https://developer.hashicorp.com/terraform/language/values/outputs)
- [Refer Here](https://github.com/asquarezone/NewTerraformZone/commit/431bc3acb2fb7f779cb680a3716b18ff2f45496e) for the changes done

![image](https://github.com/user-attachments/assets/f162c927-d2aa-4167-bc44-49ec80352ea0)

#### Terraform block
- [Refer Here](https://developer.hashicorp.com/terraform/language/terraform) for official docs of terraform block
- [Versioning constraints](https://developer.hashicorp.com/terraform/language/expressions/version-constraints)

# June 1

### Datasources
- Datasources are used to fetch information about resources.
- Datasource will not create any thing, rather it fetches information and [Refer Here](https://developer.hashicorp.com/terraform/language/data-sources) for official docs
- [Refer Here](https://github.com/asquarezone/NewTerraformZone/commit/ab0a4996db8fc551de5d89db092072b0162a3995) for datasources example

#### How does terraform know what it has created
- Terraform on execution will create a file called as terraform.tfstate locally in the same directory where the terraform is executed from.
- This state file contains the information about the resources created in this execution
- Terraform during execution, will check if there is a state file. If the state file exists,
    - it takes backup of the current state file
    - it executes the refresh internally to get the current state
    - difference between what we want vs current state becomes plan
    - Terraform executes the plan
- Terraform apply => refresh + plan + apply
- Since the state file is present in the local folder, to make the template available for multi users, it is recommended to use Terrform Backends (Common state storage )

![image](https://github.com/user-attachments/assets/9e259db3-ba73-44ab-963d-59c08be62806)

### Activity 1: ntier in Azure
- Overview

![image](https://github.com/user-attachments/assets/8a00a9f7-b610-4e9a-976d-b6dd7dd421cf)

- Manual steps: Watch classroom recording
- summary
    - create resource group
    - create virtual network with subnets
    - create a network resource groups
    - create virtual machines
    - login into vms and install necessary softwares
- create resource group [Refer Here](https://github.com/asquarezone/NewTerraformZone/commit/3f46f0ed72933af73987bdec5db7442fc327054e) for changes.
- As a best practice, lets start using [terrascan.](https://github.com/tenable/terrascan)

# June 2

#### Activity 1: contd
- [Refer Here](https://learn.microsoft.com/en-us/azure/virtual-network/quickstart-create-virtual-network?tabs=portal) for virtual network creation
- Creating virtual network with subnets and web security group with rules [Refer Here](https://github.com/asquarezone/NewTerraformZone/commit/b3e65166f86e0a3e64038459c4e4ec0f6703f793)
- using for each for security group rules [Refer Here](https://github.com/asquarezone/NewTerraformZone/commit/772a7872bfa1a598f929648541328836612f4f1b) for changes
- [Refer Here](https://github.com/asquarezone/NewTerraformZone/commit/c114160433e9ea6091979e182de85f5251e1170e) for optional values in variables.

# June 3

#### Activity 1 contd

##### Lets add network interface
- Network interface requires
    - subnet
    - public ip
    - nsg

![image](https://github.com/user-attachments/assets/2d3d16d2-50ac-423b-8d6f-24d6b497ce20)

- As of now, we have subnets, nsg, so lets create a public ip address
- [Refer Here](https://github.com/asquarezone/NewTerraformZone/commit/d2a13601da8331c2b95c73ba2148d6751f6cef61#diff-15ca888ab7a48c326f2d26cd052a942b8683a27bced93ac3e1245672ae2030ac) for the changes.
- Now lets try adding the network interface [Refer Here](https://github.com/asquarezone/NewTerraformZone/commit/bf418b7adb596ee72c82ce98a4a61a619315cf9f) for changes

##### Exercise:
- Create a linux vm with username and password
- Now try creating app and db servers

# June 4

#### Activity 1 contd
- Creating a linux vm in azure requires
    - network interface with nsg connected to a subnet (optional public ip)
    - credentials:
        - username/password
        - username/key
    - Image: os
```
publisher = "Canonical"
offer = "0001-com-ubuntu-server-jammy"
sku = "22_04-lts-gen2"
version = "latest"
```
- [Refer Here](https://github.com/asquarezone/NewTerraformZone/commit/d08dba6cb9a5abda28cb9a1b9d92b562f379600b) for the changes done to create virtual machine

#### Tainting terraform resources
- Tainting a terraform resources is marking for the resource to replaced during next terraform apply.

#### Installing softwares in virtual machine
- Option 1: Userdata/Custom Data from cloud providers
- Option 2: [Terraform provisioning](https://developer.hashicorp.com/terraform/language/resources/provisioners/syntax)

### Terraform Provisioners
- Provisioners can execute some extra stuff in virtual machines.
- Terraform has 3 types of provisioners
    - file
    - local-exec
    - remote-exec
- For the remote connections provisioner will have a [connetion object](https://developer.hashicorp.com/terraform/language/resources/provisioners/connection)
- [Refer Here](https://developer.hashicorp.com/terraform/language/resources/provisioners/connection) also
- [Refer Here](https://github.com/asquarezone/NewTerraformZone/commit/06e86750f4346ba15af7e7bf440adc637f4e295f) for the changes done to include a provisioner.

# June 5

### Terraform contd
#### Activity 1: contd
- Terraform has [null resource](https://registry.terraform.io/providers/hashicorp/null/latest/docs/resources/resource)
- Now if we add provisioning in null resource and whenever we want changes if we can replace null resource, we can execute scripts on demand
- [Refer Here](https://github.com/asquarezone/NewTerraformZone/commit/0b7ec4e48aa9a6358d20f4a17d1e57f7deb866ad) for the changes done.

##### Exercise:
- create an app server and instal tomcat in it
- create a db serever and install mysql in it

# June 6

#### Activity -2 : Creating an ntier application in AWS
- Overview

![image](https://github.com/user-attachments/assets/fbfa75a5-1a0a-45b1-8b80-ed8b2d2d053e)

- Manual steps
- Create a vpc
    - cidr
    - region
- Create six subnets
    - zone
    - cidr
- Create an internet gateway and attach to vpc
- modify default route table to add route to internet gateway
    - route:
        - cidr: 0.0.0.0/0
        - forward to internet gateway
- add 3 security groups for web, app, db servers
- Now import a key pair
- create an ec2 instance with subnet selected, AMI (os image), key pair with public ip enabled (user data-> script to install during creation)
    - AMI id
- [Refer Here](https://github.com/asquarezone/NewTerraformZone/commit/f5e6ec20bc8a4eb0420438858c23f0463e4fe899) for the basic template
- Exercise: Create till security groups in terraform

# June 8

#### Activity 2 contd
- Added changes to create vpc with subnets, associate internet gateway and configure default rout table [Refer Here](https://github.com/asquarezone/NewTerraformZone/commit/0fdb7f4faa5f73882f50f15b4cb007d12ece969e)
- Execute the current template in your account using terraform and Create
    - web security group (in a reusable way)
- [Refer Here](https://github.com/asquarezone/NewTerraformZone/commit/bbc374e5199619e40898c30374898026d0779e8f) for the changes

- Exercise:
    - Add app and db server
    - create variables for web server and key pair

# June 9

### Terraform Modules
- [Modules](https://developer.hashicorp.com/terraform/language/modules) are reusable terraform templates
- Modules will not have providers and can be called by multiple templates

![image](https://github.com/user-attachments/assets/377f9a3b-44c4-4c59-a6d7-5a225add605a)

- Modules can be present in [(module sources)](https://developer.hashicorp.com/terraform/language/modules/sources)
    - local folder
    - git
    - Terraform Cloud
- To call a module we use a module block

```
module <name> {
    source = "<module-source>"
    arg1 = value1
    arg2 = value2
    ...
    argn = valuen
}
```

- To create a module, just create a new folder with some name, ensure you have
    - resources
    - variables (inputs/arguments)
    - outputs (outputs/attributes)
- Added module for security group [locally](https://github.com/asquarezone/NewTerraformZone/commit/dc580552fec42e718260ce06ad08e731c3971a9d)
- [Refer Here](https://github.com/asquarezone/NewTerraformZone/commit/205b50b16de87e9bfc18ef881034fdfbb0c0f63d) for modules for vpc, security group
- Terraform also has a registry where lots of modules are already [available](https://registry.terraform.io/browse/modules)
- [Refer Here](https://registry.terraform.io/modules/terraform-aws-modules/vpc/aws/latest) for a community module on vpc and try creating vpc with this module

```
module "vpc" {
  source = "terraform-aws-modules/vpc/aws"
  version = "5.21.0"

  name = "my-vpc"
  cidr = "10.0.0.0/16"

  azs             = ["ap-south-1a", "ap-south-1b"]
  private_subnets = ["10.0.1.0/24", "10.0.2.0/24"]
  public_subnets  = ["10.0.101.0/24", "10.0.102.0/24"]

  enable_nat_gateway = false
  enable_vpn_gateway = false

  tags = {
    Terraform = "true"
    Environment = "dev"
  }
}
```

# June 10

### Hosting Modules on Git
- [Refer Here](https://github.com/asquarezone/TerraformModules) for the location where modules are hosted
- [Refer Here](https://github.com/asquarezone/NewTerraformZone/commit/b0956e776a32443a948c6fdd879bee8a57945723) for the changes done to use modules hosted on git.

### Sharing states with Backend
- By default the backend is local, so when we execute terraform it creates the state terraform.tfstate file in the same folder.
- This will not work for multi user executions.

![image](https://github.com/user-attachments/assets/b92257cb-64ae-40e6-91f7-a9b64622ff90)

- The better idea would be to have the state stored in a central and accessible locations

![image](https://github.com/user-attachments/assets/9ad4429f-ba13-44af-b339-3a26acb165e5)

![image](https://github.com/user-attachments/assets/1a929bc6-c170-47b6-8478-8e91afb8f474)

- For creation of buckets etc watch classroom video
- [Refer Here](https://github.com/asquarezone/NewTerraformZone/commit/4f9bf4e94c2c11976d953a0bdd68a750c01943e3) for the changes done to add state

![image](https://github.com/user-attachments/assets/66768386-7287-4bec-8c76-e17ce67643f0)


# June 11

### Terraform Azure Backend
- [Azure RM backend](https://developer.hashicorp.com/terraform/language/backend/azurerm)
- [Refer Here](https://github.com/asquarezone/NewTerraformZone/commit/437054a087345c8ad604d1e3da60bf44603aa13e) for the changes done to add azurerm backend
- Azurerm backend supports locking by default which will allow only one user to execute resources
- [Refer Here](https://github.com/asquarezone/NewTerraformZone/commit/a413cceecbeda02e241504f19e1b53288f69aa92) for the changes done to implement locking in AWS S3 backend 

### Terraform Workspaces
- Workspace enables multiple environments.
- Note: all these days we have been using workspaces unknowingly. The default workspace in terraform is called as default
- [Refer Here](https://developer.hashicorp.com/terraform/language/state/workspaces) for official docs of Terraform Workspace
- Workspace works with backend and it will have state file per workspace.
- [Refer Here](https://github.com/asquarezone/NewTerraformZone/commit/85055cacf9e423a3898484ea73c345ca808c62e4) for workspace changes done
- We had create two additional workspace dev & qa

# June 13

## Terraform state import
- importing existing resources into terraform [Refer Here](https://developer.hashicorp.com/terraform/language/state/import) and [Refer Here](https://developer.hashicorp.com/terraform/language/import)
- Note: Watch classroom recording for steps
- [Refer Here](https://github.com/asquarezone/NewTerraformZone/commit/1155f41aceab272ebff5bf4c1c68497abec30428) for the template created.

# June 14

## Terraform meta arguments
- [lifecycle](https://developer.hashicorp.com/terraform/language/meta-arguments/lifecycle): This has two arguments
    - prevent_destroy
    - create_before_destroy

```
resource "aws_vpc" "nop" {
  cidr_block           = "10.10.0.0/16"
  enable_dns_hostnames = true
  enable_dns_support   = true
  tags = {
    "Name" = "nop-vpc-dev"
  }
  lifecycle {
    prevent_destroy = true
    create_before_destroy = true
  }
}
```

- [provider](https://developer.hashicorp.com/terraform/language/meta-arguments/resource-provider)
    - [Refer Here](https://github.com/asquarezone/NewTerraformZone/commit/efce217e825f32c62ed72306f58e5d5d096e742e) for using multiple providers and provider meta argument.

#### AKS-store Deployment
- [Refer Here](https://github.com/Azure-Samples/aks-store-demo) for aks store
- To deploy this application we need a kubernetes cluster
- Lets understand how to create a kubernetes cluster on  Azure (AKS)
- [Refer Here](https://learn.microsoft.com/en-us/azure/aks/learn/quick-kubernetes-deploy-portal?tabs=azure-cli) for steps to create AKS cluster
- [Refer Here](https://github.com/asquarezone/NewTerraformZone/commit/edafac01bee62cb9fbbd2af620682901a12d822c) for the changes done to create aks cluster with kubeconfig.

# June 15

## Terraform cloud
- Terraform cloud supports features such as
    - direct vcs integration
    - user control
    - remote state (backend) and workspace support
- [Refer Here](https://app.terraform.io/public/signup/account) for signing up for a free account
- [Refer Here](https://github.com/dummyrepos/experiment-tfcloud) for the dummy repo created

### Dynamic Block
- [Refer Here](https://developer.hashicorp.com/terraform/language/expressions/dynamic-blocks) for official docs
- [Refer Here](https://github.com/asquarezone/NewTerraformZone/commit/1ba5b62bdf3c61b50f048dd04b8af8d3d603e678) for the changes which include dynamic block to create ingress rules in security
- Avoid dynamic blocks as they are less readable.


# June 17 (Docker)

### Possible Application Execution Options
- Consider any web application & we need to run it
- To run this application we have the following possibilities
### Physical server
- Ensure you have right sized physical servers with necessary os in it
- Ensure networking is established

![image](https://github.com/user-attachments/assets/45ff019a-d277-41d5-a660-1ef506c92e53)

- Capex (upfront investment) for a servers
- Opex (ongoing)

#### Hypervisors

![image](https://github.com/user-attachments/assets/821c23b2-01e1-445c-bc74-064712dd9d64)

#### Containers

![image](https://github.com/user-attachments/assets/f7e95ba9-caba-4ff8-b389-31bbd8621933)

# June 18

### Containers contd…
- Lets run a java based application
- To run a java based application we need java to be installed
### Physical System
- We have used a springpetclinic application and deployed into physical system

![image](https://github.com/user-attachments/assets/b44e77b3-eeee-4e0d-9fa1-84a35d439f5e)

### Virtual Machine
- Lets use Azure To create a linux (Ubuntu) and setup this application

### Container
- We used docker playground and used an existing image to create a container

#### What should i run in a contaner
- Ideally run the server side components in a container.

#### How is container working at a high level
- Docker when installed on a larger note has two major components
    - client:
        - This is a command line tool which can interact with daemon/engine
    - daemon/engine:
        - This is responsible of container management
- Users execute docker commands using client and client interacts with daemon to get the job done

#### Creating a container
- Command docker run nginx -d means create a container, lets examine what happens now
    - 1. client sends request to daemon/engine
    - 2. daemon checks the local repo for the image, if not found tries to download from registry and even if not found throws error
    - 3. once the image is available a container is created using image and allocating resources (cpu, ram, ntework)
- Registry: A registry is collection of container images and each container is represented as repository.
    - container image has a repo name and version which is called as tag.
    - docker image <repo-name>:<tag>
    - if u dont pass tag latest is its default value
    - when we said docker run nginx => docker run nginx:latest
- Repo names have conventions depending on which registry you are using
- docker hub is the default registry.
- Other registries are also available
    - artifactory
    - azure container registry
    - aws elastic container registry

…
- Docker hub convention
    - official images: they directly have names
        - nginx
    - Trusted Partner: This is an organization trusted by docker [publishing images](https://hub.docker.com/search?badges=verified_publisher)
    - your(account) images: These are repos built by us <account-name>/<app-name> shaikkhajaibrahim/spc-gcp
#### First steps into docker/containers
- Containerize applications which is ensuring your application has a image (docker image/container image).

# June 19

## Basic container operations
- Creating a docker container in docker playground for this we need to create account in [docker hub](https://hub.docker.com/)
- Container lifecycle

![image](https://github.com/user-attachments/assets/1533911a-4347-4c42-878a-e9f0161fdf2c)

- Container operations
    - Create
    - start
    - run (create + start)
    - stop
    - pause
    - unpause
    - remove/delete

- [docker cheatsheet](https://docs.docker.com/get-started/docker_cheatsheet.pdf)
- Create a container and start it

```
docker container run -d httpd:latest

docker run -d httpd:latest
```

![image](https://github.com/user-attachments/assets/123965c2-d114-410d-bfe0-c85720206f50)

- To list all the running containers
```
docker ps
docker container ls
```

![image](https://github.com/user-attachments/assets/94453c2b-37db-4283-85aa-d44ca093a950)

- Every container when created gets a unique container id and if you have not passed the name docker randomly assigns a name
- So lets create a container with a name
```
docker container run -d httpd:latest
docker run -d httpd:latest
```

![image](https://github.com/user-attachments/assets/473a0f0f-1612-4611-ade8-ff6b4a715593)

- * To manage the container we can pass container id or name
- * Lets stop a container

```
docker stop <container-id|name>
docker container stop <container-id|name>
```

![image](https://github.com/user-attachments/assets/917860ff-6063-4707-a157-7b852c6ab2f1)

- * lets start the containers

![image](https://github.com/user-attachments/assets/5a4c8693-ac81-4175-b3c3-2e75f4356450)

- * Let try removing the container

![image](https://github.com/user-attachments/assets/4feb8992-6b0f-411f-ac07-018da872d765)

### Examine containers
- Lets create two containers web1 and web2

![image](https://github.com/user-attachments/assets/14e2d2c3-031b-4e88-8948-4b08d213db32)

![image](https://github.com/user-attachments/assets/52273e76-3863-4f0f-bf9e-78a929fccb72)

- watch classroom recording for remaining examination.
### Exercise:
- What happens when you start a linux machine in terms of processes what gets launched first

# June 21

## Docker contd
#### Story of dot-cloud
- This was a sanfransico based startup working on PaaS products
- For their internal use they have created a product which is called as docker (dock worker) and open sourced this
- This was [first demo](https://www.youtube.com/watch?v=9xciauwbsuo)
- This was very well apprecieted and the companies name was changed to Docker Inc.
- Docker democratized containers.

### How containers work internally
- Refer Here for internals
- Three important linux concepts make this happen
    - cgroups
    - capabilities
    - namespaces

#### Terms
- Stateful vs Stateless
- Containers work seamless for Stateless and for stateful to preserve data we need to do few extra steps.

# June 22

## Microservices
- Microservice is a smaller and indivudually runnable service which can be deployed independently

![image](https://github.com/user-attachments/assets/327f6b34-b65e-4515-8ff5-a224dfe87a3c)

#### Next Steps
- containerizing your application.
- understanding
- network
- storage
- resources
- best practices
- Using orchestration to deploy microservices and run them effeciently

#### Setup
- We will setup the docker on Linux Machine
- SSH into linux machine (ubuntu)
```
curl -fsSL https://get.docker.com -o install-docker.sh
sh install-docker.sh
```

- once the docker installed add your current user to docker group
```
sudo usermod -aG docker <user-name>
# sudo usermod -aG docker ubuntu
```
- After this exit, relogin and execute docker info

![image](https://github.com/user-attachments/assets/aeb40f0b-b4ef-4b76-ac1a-8b9be2a76d3a)

### Containerizing applications
- I want to run a simple website
- Our webdesigner has created the following design Refer Here
- Findout how to deploy this to a server.
- To deploy a website, we need webserver
- we have two popular flavors
    - apache
    - nginx
- Manual steps:

```
sudo apt update
sudo apt install nginx unzip -y
wget https://templatemo.com/tm-zip-files-2020/templatemo_591_villa_agency.zip
unzip templatemo_591_villa_agency.zip
cd templatemo_591_villa_agency/
sudo cp  --recursive . /var/www/html/
```

- Access your server by ip http://<server-ip>

![image](https://github.com/user-attachments/assets/aa7513ed-1b16-40b8-986d-e7eb77a2e41e)

- What is needed to run this application
    - nginx
    - website
- How to access your application http://<ipaddress>:80
- Containerizing application can be done in two ways
    - creating a container and manually deploying application (not recommended)
    - Write Dockerfile
- Option 1: Create image manually
    - Create a container in interactive mode and run necessary commands to deploy your application

# June 23

# Docker
### Architecture
- [Refer Here](https://directdevops.blog/2019/01/31/docker-internals/) and look into underlying components

![image](https://github.com/user-attachments/assets/d9017f25-3beb-49db-8b06-65b0bae1ec1a)

### Running & Executing in containers in different modes
- Containers by default run in attached mode which displys in the stdout, stderr in the current terminal
- ```docker run --name web1 nginx```
- Containers can be run in the background without blocking terminal which is referred as detached mode, which returns a container id
- ```docker run -d --name web2 nginx```

![image](https://github.com/user-attachments/assets/a4887d70-074b-4b41-a550-8762ebebda5f)

- * Other mode is interactive terminal, when you want to run a shell (we will discuss further later)
- * Once the container is running we can execute commands in the container
- * docker exec
- * docker exec -it <bash|terminal>

### Containerizing applications using Dockerfile
- [Dockerfile](https://docs.docker.com/reference/dockerfile/) is a text file which contains instructions to create docker image
- Instructions will have the following form
- ```<INSTRUCTION> <VALUE>```
- Dockerfile has lots of instructions supported

![image](https://github.com/user-attachments/assets/83ab6c8f-ec01-4122-ad4c-c8522e37b019)

- Lets define some popular instructions
    - FROM
    - RUN
    - ADD | COPY
    - CMD
    - EXPOSE
    - LABEL
- FROM: this instruction defines the base image
- LABEL: This is used to add metadata
- RUN: This runs a command during image building
- CMD: This command executes when creating a container
- ADD | COPY: They are used to copy files or directories into image
- EXPOSE: This publishes the port on which your application is accessed.

##### Lets containerize the website used in previous class
- Refer Here for previous classroom notes
- Create a new folder called website and create a new file in this folder with name Dockerfile
- Refer Here for the changes done
- To build the docker ensure your are in the folder where Dockerfile exists & Execute
- ```docker image build -t villa:1.0 .```

![image](https://github.com/user-attachments/assets/d104c3bf-adb6-4ea5-b9dd-3e402f2eed02)

- The Dockerfile used is
```
FROM nginx
ADD html/ /usr/share/nginx/html
EXPOSE 80
```
- Lets containerize the application
- [Refer Here](https://referenceappslt.s3.ap-south-1.amazonaws.com/spring-petclinic-3.3.0-SNAPSHOT.jar) for the spring pet clinic
- The manual step to run this application is
    - Ensure jdk 17 is installed
    - java -jar spring-petclinic-3.3.0-SNAPSHOT.jar is the command to start the application
    - This application runs on port 8080
- Approximate Dockerfile
```
FROM openjdk:17
ADD https://referenceappslt.s3.ap-south-1.amazonaws.com/spring-petclinic-3.3.0-SNAPSHOT.jar /spring-petclinic-3.3.0-SNAPSHOT.jar
EXPOSE 8080
```

# June 24

## Docker contd
#### Dockerfile
- Dockerfile has instructions to build a docker image
#### FROM
- This helps in selecting a base image
- Experiments
    - Exploring options of FROM
    - choosing different base images
##### Experiment 1
- Lets just add FROM statement in Dockerfile
- ```FROM eclipse-temurin:17-jdk```
- pull the base image docker image pull eclipse-temurin:17-jdk and verify images docker image ls

![image](https://github.com/user-attachments/assets/04bc20b5-69b3-4d5e-bb68-1818a0aa8c3d)

- Now lets build image

![image](https://github.com/user-attachments/assets/c3a3b7e3-cfbf-4483-a114-8334282423d1)

- Now lets add metadata
```
FROM eclipse-temurin:17-jdk
LABEL author="khaja"
```

![image](https://github.com/user-attachments/assets/875a4147-c2f4-488a-86e0-4abbe26f287d)

- There is a base image called as scratch which is empty
- Platforms:
    - amd
    - arm

![image](https://github.com/user-attachments/assets/4dd648b9-14b4-441f-b887-44241625e360)

#### RUN
- [Run](https://docs.docker.com/reference/dockerfile/#run) instruction executes the command during image building
- Consider the following Dockerfile
```
FROM ubuntu:24.04
LABEL author="khaja"
LABEL project="classroom"
RUN apt update &&
    apt install openjdk-17-jdk -y
```

![image](https://github.com/user-attachments/assets/5c7a5d27-73fc-4bb0-b359-f5e977ae7c3f)

### ADD or COPY
- [ADD](https://docs.docker.com/reference/dockerfile/#add) can copy files from local as well as web into docker image
- [COPY](https://docs.docker.com/reference/dockerfile/#copy) can copy the local files or folders into docker image
- Sample Dockerfile

```
FROM ubuntu:24.04
LABEL author="khaja"
LABEL project="classroom"
RUN apt update && \
    apt install openjdk-17-jdk -y

ADD https://referenceappslt.s3.ap-south-1.amazonaws.com/spring-petclinic-3.3.0-SNAPSHOT.jar /spring-petclinic-3.3.0-SNAPSHOT.jar
```

### ENTRYPOINT/CMD
- This is used to start the application
##### Note
- Remove all images docker image rm -f $(docker image ls -q)
- When we create a container, container searches for start up command (CMD) if not found searches in base image startup
- container is running as long as startup command is in running state

# June 25

### Slim images
#### Java Application that uses Spring-boot
- To run spring boot application we require JAVA JDK and a jar file
- We have build the package locally
- using the dockerfile in the changeset [Refer Here](https://github.com/dummyrepos/spring-petclinic-docker-june-25/commit/1a1880ffd02d22f79c062920276c2ffc19dfd914) we have built the docker image which copies the jar file into docker image
- [Refer Here](https://github.com/dummyrepos/spring-petclinic-docker-june-25/commit/f9829c54a6313b1d3fa4392a6cb8bdaf11600ea8) for the changes to use the slim version or alpine version.

- Best Practices:
    - It is not recommended to run your application as root user.
    - It is not recommened to run your applications from root directory
- From now on lets always have application directory
- [WORKDIR](https://docs.docker.com/reference/dockerfile/#workdir)
- [Refer Here](https://github.com/dummyrepos/spring-petclinic-docker-june-25/commit/6ea54f3a0dd585dd2f5f28a6376960a3756da954) for the changes to include WORKDIR
- [USER instruction](https://docs.docker.com/reference/dockerfile/#user) will set the user
- [Refer Here](https://github.com/dummyrepos/spring-petclinic-docker-june-25/commit/1df8c3e56aa2a6436f1892e79c1ac8bd93da9921) for the changes that create a user

# June 26

### Dockerfile contd
#### Multi-staged docker build
- Multi-staged docker build involved building image in different stages
- each stage has its own from instruction and only last stage is your application image
- Lets look at sample

```
FROM <image> as build
...
...

FROM <image> as test
...
...

FROM <image>
...
...
```

- This requires copying files from local or git into image

#### Samples
- Lets have a single stage where we copy the code into docker iamge
- Cloning code from git into image ADD https://github.com/dummyrepos/spring-petclinic-docker-june-25.git /usr/share/spc or we can copy the code from local folder into image ADD . /usr/share/spc
- Generally when we are building the image we might not require all the files of local folder into image, for that we create a file called as .dockerignore and specify all files and folder either - directly or by patterns which we donot want to copy.
- Sample .dockerignore
```
.git/
.git*
k8s/
target/*
**/Dockerfile
**/docker-compose.yml
# Build output and cache directories
target/
build/
.gradle/
out/

# IDE files
.idea/
.vscode/
*.iml

# Version control
.git/
.gitignore

# Environment and configuration files (often sensitive)
.env
*.properties
*.yml
*.yaml

# Logs and temp files
*.log
tmp/


# OS-specific files
.DS_Store
```

##### Now lets have our first stage where we build the maven package
- command mvn package
- spc requires jdk 17, so lets find a image which has maven with jdk 17
- [Refer Here](https://github.com/dummyrepos/spring-petclinic-docker-june-25/commit/305af74ba7a46217807f01865c1f3549a04d15d1) for changes to have multi staged docker file

### Search for how to build react js application and run it on nginx
- Dockerfile
```
FROM node:lts AS build
ADD . /app
WORKDIR /app
RUN npm install
RUN npm run build

FROM nginx
RUN rm -rf /usr/share/nginx/html/
COPY --from=build /app/dist /usr/share/nginx/html
EXPOSE 80
```
- [Refer Here](https://github.com/dummyrepos/sample-react) to this repo and create a docker image

# June 28

## Dockerfile
#### Asp.dotnet core application containerization
- [Refer Here](https://github.com/dummyrepos/nopCommerce-jun25) for the repo
- The Dockerfile only building the code is

```
From mcr.microsoft.com/dotnet/sdk:9.0 As build
Add . /nop
WORKDIR /nop
RUN dotnet build -c Release src/Presentation/Nop.Web/Nop.Web.csproj
```

- [Refer Here](https://github.com/dummyrepos/nopCommerce-jun25/blob/develop/Dockerfile) for the full version
- Exercise: Ensure we have a user created in Dockerfile as of now we are running application as root user.
#### SHELL FORM and EXEC FORM
- shell form
```
RUN apt update
CMD java -jar spc.jar
```
- EXEC form

```CMD ["java", "-jar", "spc.jar"]```

- SHell form any command is executed with /bin/sh -c <command> and this does not react well with signals sigint
- Exec form directly executes the command which makes application PID-1 in a container and handles signals. You can expand variables in EXEC form
- Use Shell form for RUN and EXEC form for ENTRYPOINT and CMD

#### Other Dockerfile instructions to consider
- ENTRYPOINT/CMD
- ARG
- ENV

#### While building docker image i want to pass variables
- Consider the following docker file
```
FROM openjdk:17
ADD https://referenceappslt.s3.ap-south-1.amazonaws.com/spring-petclinic-3.3.0-SNAPSHOT.jar /spring-petclinic-3.3.0-SNAPSHOT.jar
EXPOSE 8080
CMD java -jar /spring-petclinic-3.3.0-SNAPSHOT.jar
```

- [Refer Here](https://docs.docker.com/reference/dockerfile/#arg) for ARG instruction
```
FROM openjdk:17
ARG JAR_URL='https://referenceappslt.s3.ap-south-1.amazonaws.com/spring-petclinic-3.3.0-SNAPSHOT.jar'
ADD ${JAR_URL} /spring-petclinic-3.3.0-SNAPSHOT.jar
EXPOSE 8080
CMD ["java", "-jar", "/spring-petclinic-3.3.0-SNAPSHOT.jar"]
```
- build command
```docker image build --build-arg JAR_URL='https://referenceappslt.s3.ap-south-1.amazonaws.com/spring-petclinic-3.3.0-SNAPSHOT.jar' -t spc:1 .```

- ARGs are accesible only while building image not while running container.
##### I Want to set values which i will be using in a container
- Lets consider the following
```
FROM openjdk:17
ARG JAR_URL='https://referenceappslt.s3.ap-south-1.amazonaws.com/spring-petclinic-3.3.0-SNAPSHOT.jar'
ADD ${JAR_URL} /spring-petclinic-3.3.0-SNAPSHOT.jar
EXPOSE 8080
CMD ["java", "-jar", "/spring-petclinic-3.3.0-SNAPSHOT.jar"]
```

- [ENV](https://docs.docker.com/reference/dockerfile/#env)
```
FROM openjdk:17
ARG JAR_URL='https://referenceappslt.s3.ap-south-1.amazonaws.com/spring-petclinic-3.3.0-SNAPSHOT.jar'
ADD ${JAR_URL} /spring-petclinic-3.3.0-SNAPSHOT.jar
ENV TEST='DEFAULT'
EXPOSE 8080
CMD ["java", "-jar", "/spring-petclinic-3.3.0-SNAPSHOT.jar"]
```

![image](https://github.com/user-attachments/assets/81c6ff05-9129-4efe-b13f-63b7dead4f11)

### ENTRYPOINT and CMD
- CMD can be overriten while running the docker by passing any thing after image name during run
```docker run ..... <image> [------]```
- ENTRYPOINT can be change via –entrypoint during run
- When you run a docker container it will run ENTRYPOINT + CMD as PID 1
- Case 1: This will execute echo hello when container starts
```
FROM alpine
ENTRYPOINT [ "echo" ]
CMD ["hello"]
```
- Case 2: Only entrypoint
```
FROM alpine
ENTRYPOINT [ "echo", "hello" ]
```
- Case 3: Only CMD
```
FROM alpine
CMD [ "echo", "hello" ]
```
- Case 4: NO CMD and NO Entrypoint the container will try to run base images Start command
##### Optimizations in Dockerfile
- Storage
- Security

# 30 June

### Docker contd…
##### Docker Image Layers
- Lets run the simple apline image with sleep 1d as cmd

![image](https://github.com/user-attachments/assets/dd2fd8e9-8398-498f-bc0b-6e29e0496be0)

- Docker image is collection of readonly layers
- Each docker container gets a writable layer for all changes done w.r.t storage and image layers are reused across containers

![image](https://github.com/user-attachments/assets/8dc1ad01-ceb0-4462-9538-369d30710419)

- When we make any change in existing file which is part of image gets copied into writable layer and then modified (copy on write strategy)
- When you delete the container writable layer is deleted.

#### How are layers getting created
- Docker Image layers are create during image creation
- Image automatically gets parent layers (FROM)
- Any instruction that leads to change in storage will create a layer.
- Having too many layers is not a good idea, layers are created for reusability.
- On a broader note, the following instructions majorly lead to layer creation
    - RUN
    - ADD | COPY
- Generally we club lots of commands in a RUN statement

```
RUN apt update && \
    apt install openjdk-17-jdk -y && \
    .... \
    ... \
    ... \
```
#### How does Docker deal with layers
- Docker Storage drivers deal with layers and make them available as disks to container
- Right now overlay2 is used in docker
- refer the following articles
- [Refer Here](https://directdevops.blog/2019/09/26/docker-image-creation-and-docker-image-layers/) for image creation and layers and [Refer Here](https://directdevops.blog/2019/09/27/impact-of-image-layers-on-docker-containers-storage-drivers/) for storage drivers

#### Example
- Try finding a docker commad to run mysql container with
    - username: qtdevops
    - password: qtdevops
    - database: qtlms
```
docker run -d --name db \
    -e MYSQL_ROOT_PASSWORD=qtdevops \
    -e MYSQL_PASSWORD=qtdevops \
    -e MYSQL_USERNAME=qtdevops \
    -e MYSQL_DATABASE=qtlms \
    -p 3306:3306 \
    mysql:8.0
```
- How to persist the data i.e. data should not be lost post container deletion => Volumes

1 July

#### Docker Volumes
- Docker volumes have a life time independent of docker container.
- Volumes act as mount onto a specific folder(s) in a container
- [Docker volumes](https://docs.docker.com/engine/storage/volumes/) and [Refer Here](https://directdevops.blog/2019/10/03/docker-volumes/) for the article
- Types:
    - Volumes:
        - Create a volume which gets create in /var/lib/docker
        - And mount the volume to a folder in container.
    - Bindmounts:
        - Mount an existing folder on dockerhost into container.
    - tmpfs
- Lets create a simple alpine container with a bindmount (/home/Dell/docs -> /docs)
```docker container run -d --name bindmountdemo -v /home/Dell/docs:/docs alpine sleep 1d```
- execute experiment commands commands such as (Watch classroom video)
    - df -h
    - ls
    - cat
##### Lets use the volume
- Create a volume
```docker volume create --help```

![image](https://github.com/user-attachments/assets/46490f94-2963-43c8-a102-61cbd18ae706)

![image](https://github.com/user-attachments/assets/a618b301-308c-467b-8299-c6a9e2093f0e)

- We can create volume by default even if the user doesnot create a volume that is by adding VOLUME instruction in Dockerfile.
```
FROM alpine
RUN mkdir /docs
VOLUME /docs
CMD ["sleep", "1d"]
```

![image](https://github.com/user-attachments/assets/b0103e49-ef47-406a-8d61-43ca0cff2775)

- Watch classroom recording for mysql

### Docker networking
- Docker has two major types of networking
- single host (developer setup)
- multi host (docker swarm): This is not an area of interest for us as we will be exploring kubernetes for multi host .
- Network also is implemented as a driver [Refer Here](https://directdevops.blog/2019/10/05/docker-networking-series-i/)
- Port Forwarding.

![image](https://github.com/user-attachments/assets/5e91bcd8-e720-4adc-8fd7-cd0ceb430c06)

# July 2

### Docker Networking contd
- By default docker container run on bridge network (default)
- We can create our own bridge networks
- container can be connected to network even after creation.
- Lets create two containers d1 and d2 in default bridge network
```
docker run --name d1 -d alpine sleep 1d
docker run --name d2 -d alpine sleep 1d
```

![image](https://github.com/user-attachments/assets/33d50015-a96f-4270-ab45-c938fadc825d)

- Now lets inspect container and find ip addresses. Try ping

![image](https://github.com/user-attachments/assets/52ae32b9-9130-44e9-acfa-228ae9fc092b)

- Default bridge network allows ip based resolution but not name based resolution
- Where a custom bridge network allow name based resolutions
- Lets create a custom bridge network with range 192.168.0.0/24
```docker network create --driver bridge --subnet 192.168.0.0/24 learning```

![image](https://github.com/user-attachments/assets/b81793e9-091a-465e-b0ce-35bb39997c45)

- Now lets create two container l1 and l2 and try connectivty by name and ip
```
docker run --name l1 --network learning -d alpine sleep 1d
docker run --name l2 --network learning -d alpine sleep 1d
```

![image](https://github.com/user-attachments/assets/3b34625e-0c0f-40c8-abb2-d9d2bd162a3a)

![image](https://github.com/user-attachments/assets/b85f606a-fc4a-49b6-8fa4-ef8608685d9c)

### Nop Commerce with network
- We have a image called as nop:1.0 which is our application and also we have pulled mysql image
- lets create a network called as nop-net with range 10.100.0.0/24
```docker network create --driver bridge --subnet 10.100.0.0/24 nop-net```

- Lets create a volume for database nop-vol
```docker volume create nop-vol```
- Lets create a database container nopdb in nop-net with nop-vol attached
```
docker run \
  --name nopdb \
  --network nop-net \
  -e POSTGRES_USER=nop \
  -e POSTGRES_PASSWORD=qtdevops \
  -e POSTGRES_DB=nop \
  -p 5432:5432 \
  -d postgres
```

![image](https://github.com/user-attachments/assets/4e5349d4-df8a-4988-80b5-490dcce5c191)

- Now lets create nop container in nop-net
```
docker container run -d \
    --name nop \
    --network nop-net \
    -p 80:5000 \
    shaikkhajaibrahim/febnop:latest
```
- To be continued to show the running version

#### Registry
- Registries are where we store/distribute our images
- Popular Registries
    - Docker hub
        - Private
        - Public Registries
    - Azure Container Registy (ACR)
    - AWS Elastic Container Registry (ECR)
    - GCR
    - Jfrog/Artifactory

- Registries will have repositories where each repo reprsents and application image which will have versions as tags.
- Login into registy
    - docker hub docker login
- Create a tag according to repo


![image](https://github.com/user-attachments/assets/2db14705-3d87-412c-a79f-03ebb244f260)
![image](https://github.com/user-attachments/assets/0c88879e-c35e-4153-936d-4332b5e32ba9)

# July 5

### Kubernetes
- Production-Grade Container Orchestration
- History:
    - Google had a project called as borg and later omega which they use for their internal applications.
    - Google built a project based on learnings in borg and omega in golang they called it as kubernetes (k8s).
    - This project was donated to CNCF
- As of now k8s is defacto container orchestration system.

#### Basic Architecture
- K8s is a cluster which is one or more nodes
- K8s cluster have two types of nodes
    - Master Node(s):
        - Manage the cluster
    - Node(s):
        - Run the workloads (applications)

![image](https://github.com/user-attachments/assets/bd8db065-efe1-40e0-9710-e596332da417)

- [Refer Here](https://directdevops.blog/2019/10/10/kubernetes-master-and-node-components/) for master and node components
- K8s Master Node Components

![image](https://github.com/user-attachments/assets/83aebd47-d7a3-4f51-8557-6b377cd977d1)

- K8s Node Components

![image](https://github.com/user-attachments/assets/e77ae42c-f980-44a4-97ea-2f9b9a61d91b)

- K8s always tries to maintain a desired state.

![image](https://github.com/user-attachments/assets/02748a5b-3f2f-4d37-b2b2-5b32534e8f9d)

### K8s interfaces for extensability
- k8s when it started used to support only docker as container technology.
- K8s to call docker used to have lots of code dockershim which was part of k8s release.
- K8s has introduced a standard called CRI (Container Runtime Interface). Any container technology can be used in k8s as Container Runtime if it has CRI.
- K8s also has
    - CNI (Container Network Interface)
    - CSI (Container Storage Interface)

#### Options for using k8s
- Self-Hosted/On-prem:
    - Install on your own servers
- Cloud-Hosted (Managed) k8s:
    - Azure AKS
    - Google GKE
    - AWS EKS
- Single Host k8s (Developers):
    - minikube
    - kind

#### Installing k8s
- To Install k8s we need atleast two nodes
    - master node
    - node
- Installing k8s using [kubeadm](https://kubernetes.io/docs/reference/setup-tools/kubeadm/) and [Refer Here](https://kubernetes.io/docs/setup/production-environment/tools/kubeadm/install-kubeadm/) for installation guide
- In the class i have used Azure
- Create two vms in same network and ensure they have atleast 2 vCPUs and 2 GB of RAM.
- Installing container runtime on all nodes [Refer Here](https://kubernetes.io/docs/setup/production-environment/tools/kubeadm/install-kubeadm/#installing-runtime)
- For this installation lets use containerd

```
sudo apt update
sudo apt install -y curl gnupg2 software-properties-common apt-transport-https ca-certificates
sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/trusted.gpg.d/docker.gpg
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
sudo apt update
sudo apt install -y containerd.io
containerd config default | sudo tee /etc/containerd/config.toml >/dev/null 2>&1
sudo sed -i 's/SystemdCgroup = false/SystemdCgroup = true/g' /etc/containerd/config.toml
sudo systemctl restart containerd
sudo systemctl enable containerd
```

- Now install the following kubelet, kubectl and [kubeadm on all nodes](https://kubernetes.io/docs/setup/production-environment/tools/kubeadm/install-kubeadm/#installing-kubeadm-kubelet-and-kubectl)

```
sudo apt-get update
# apt-transport-https may be a dummy package; if so, you can skip that package
sudo apt-get install -y apt-transport-https ca-certificates curl gpg
# If the directory `/etc/apt/keyrings` does not exist, it should be created before the curl command, read the note below.
# sudo mkdir -p -m 755 /etc/apt/keyrings
curl -fsSL https://pkgs.k8s.io/core:/stable:/v1.33/deb/Release.key | sudo gpg --dearmor -o /etc/apt/keyrings/kubernetes-apt-keyring.gpg
echo 'deb [signed-by=/etc/apt/keyrings/kubernetes-apt-keyring.gpg] https://pkgs.k8s.io/core:/stable:/v1.33/deb/ /' | sudo tee /etc/apt/sources.list.d/kubernetes.list
sudo apt-get update
sudo apt-get install -y kubelet kubeadm kubectl
sudo apt-mark hold kubelet kubeadm kubectl
```

### Now lets create a k8s cluster
- [Refer Here](https://kubernetes.io/docs/setup/production-environment/tools/kubeadm/create-cluster-kubeadm/)
- Change the ip forward settings on all nodes
```
vi /etc/sysctl.conf
# see the image below and uncomment the highlighted line
sudo sysctl -p
```

![image](https://github.com/user-attachments/assets/30348221-b591-4cbb-9e97-a2463379ea59)

- on the master node execute as sudo or root user

```kubeadm init```

![image](https://github.com/user-attachments/assets/54f36f44-9b93-460b-bf12-672b6331e289)

- Now login into node as root user and run the kubeadm join command from above image

![image](https://github.com/user-attachments/assets/ec297331-e0f0-4c92-a14a-958e831713f7)

- As of now nodes are not ready due to CNI not being installed. lets install weavenet
```kubectl apply -f https://github.com/weaveworks/weave/releases/download/v2.8.1/weave-daemonset-k8s.yaml```

![image](https://github.com/user-attachments/assets/2789c703-3e54-468f-9afd-39e543d53047)


#### Quickly using k8s
- [killerkoda](https://killercoda.com/playgrounds/scenario/kubernetes)

# July 6

#### Kubeadm with docker
- Lets build a two node cluster with ubuntu 22.04
- Install docker on both nodes
```
cd /tmp
curl -fsSL https://get.docker.com -o install-docker.sh
sh install-docker.sh
sudo usermod -aG docker <username>
```
- Now install [cri-dockerd](https://github.com/Mirantis/cri-dockerd/releases) as of now we are using deb package [Refer Here](https://github.com/Mirantis/cri-dockerd/releases/download/v0.4.0/cri-dockerd_0.4.0.3-0.ubuntu-jammy_amd64.deb)

```
wget https://github.com/Mirantis/cri-dockerd/releases/download/v0.4.0/cri-dockerd_0.4.0.3-0.ubuntu-jammy_amd64.deb
sudo dpkg -i cri-dockerd_0.4.0.3-0.ubuntu-jammy_amd64.deb
```

- Now install kubeadm, kubectl and kubelet on both nodes
```
sudo apt-get update
# apt-transport-https may be a dummy package; if so, you can skip that package
sudo apt-get install -y apt-transport-https ca-certificates curl gpg
# If the directory `/etc/apt/keyrings` does not exist, it should be created before the curl command, read the note below.
# sudo mkdir -p -m 755 /etc/apt/keyrings
curl -fsSL https://pkgs.k8s.io/core:/stable:/v1.33/deb/Release.key | sudo gpg --dearmor -o /etc/apt/keyrings/kubernetes-apt-keyring.gpg
echo 'deb [signed-by=/etc/apt/keyrings/kubernetes-apt-keyring.gpg] https://pkgs.k8s.io/core:/stable:/v1.33/deb/ /' | sudo tee /etc/apt/sources.list.d/kubernetes.list
sudo apt-get update
sudo apt-get install -y kubelet kubeadm kubectl
sudo apt-mark hold kubelet kubeadm kubectl
```

- In this mode in all kubeadm we need to pass --cri-socket=unix:///var/run/cri-dockerd.sock
- our init commmand with flannel as CNI
- ```kubeadm init --pod-network-cidr=10.244.0.0/16 --cri-socket=unix:///var/run/cri-dockerd.sock```

- Then join the other node to the cluster
- Lets install CNI flannel
```kubectl apply -f https://github.com/coreos/flannel/raw/master/Documentation/kube-flannel.yml```

#### K8s Workloads – Pod
- Docker creates a Container, Hypervisor creates Virtual Machines and k8s creates Pods
- Pod has container(s) in it.
- Every Pod gets a unique ip with in a k8s cluster
- Pod can have one or more containers in it.
- Containers with in pod communicate over localhost (127.0.0.1) i.e. two containers cannot be inside pod which require same port

![image](https://github.com/user-attachments/assets/abbdf966-9450-4017-84c5-f6b1726e7572)

- In a Pod if we have more than one container
    - primary container => maincar container
    - other container(s) => sidecar containers

- Ideally a Pod should run an application component/microservice in it

![image](https://github.com/user-attachments/assets/0cbefbab-1cab-4fe7-a7d2-5d34bed50612)

- [Refer Here](https://www.restapitutorial.com/) for restapi

#### Interacting with k8s
- K8s has a [REST API](https://kubernetes.io/docs/concepts/overview/kubernetes-api/) for all the resources of k8s exposed by kube api server
- All the resources that can be created by k8s can be fetched by kubectl api-resources command
- [API Versioning](https://kubernetes.io/docs/reference/using-api/#api-versioning)
- API Groups:
    - core
    - other

- ApiVersion
```
# format
<apiGroup>/<version>
# core group
<version>
```
- ApiVersion examples

```
v1 => group => core, version => v1

network.k8s.io/v2beta3 => group => network.k8s.io, version v2beta3
```

- [Pod](https://kubernetes.io/docs/concepts/workloads/pods/)
- [Refer Here](https://kubernetes.io/docs/reference/kubectl/quick-reference/) for kubectl cheatsheet
- Creation types:
    - imperative:
        - construct a command line
    - declartive
        - create a manifest file (YAML)

#### Play with pods
- Imperative

![image](https://github.com/user-attachments/assets/026d4dfd-d9a8-4444-a075-9317a878e443)

- declartive
```
apiVersion: v1
kind: Pod
metadata:
  name: web-3
spec:
  containers:
  - name: nginx
    image: nginx:1.14.2
    ports:
    - containerPort: 80
```

![image](https://github.com/user-attachments/assets/e80c6105-eb46-49b4-be68-c3241d025128)

![image](https://github.com/user-attachments/assets/5952a159-edb0-4b69-946f-ee9745d39189)

#### Choosing CNI for kubeadm

| **CNI Plugin**     | **Overlay / Routing**                | **Network Policy Support**           | **Security Features**                                | **Performance** | **Advanced Features**                                                   | **Ease of Use** | **Cloud Friendly** | **Notable Use Cases / Notes**                        |
|--------------------|--------------------------------------|--------------------------------------|------------------------------------------------------|------------------|---------------------------------------------------------------------------|------------------|---------------------|-------------------------------------------------------|
| **Calico**         | Overlay & BGP                        | Yes (advanced)                       | Distributed firewall, policy enforcement              | High             | BGP routing, egress/ingress control, multi-cluster                      | Medium           | Partial             | Highly scalable, strong security focus               |
| **Flannel**        | Overlay (VXLAN, host-gw, others)     | No                                   | None                                                 | Good             | Simple L3 fabric                                                       | Easy             | Yes                 | Simplicity, basic connectivity                       |
| **Cilium**         | Overlay & native routing (eBPF)      | Yes (L3-L7, DNS, HTTP)               | eBPF-based, identity-based, application-aware         | Very High        | Deep observability, service mesh integration, multi-cluster             | Medium           | Yes                 | Advanced security, microservices focus               |
| **Weave Net**      | Overlay (mesh)                       | Yes                                  | Basic                                                | Good             | DNS, encryption, mesh topology                                        | Easy             | Yes                 | Simple install, mesh networking                      |
| **Kube-router**    | Routing (BGP, IPVS, VXLAN)           | Yes                                  | Network policy                                       | High             | Service proxy, BGP peering                                             | Medium           | Partial             | Combines routing, proxy, policy                      |
| **Antrea**         | Overlay & native                     | Yes                                  | Policy enforcement                                   | High             | Flow visibility, multi-cluster                                         | Medium           | Yes                 | VMware-backed, modern features                      |
| **Multus**         | N/A (meta-plugin)                    | N/A                                  | N/A                                                  | N/A              | Multi-homed pods (multiple CNIs)                                      | Medium           | Yes                 | Attach multiple networks to pods                    |
| **OVN-Kubernetes** | Overlay & native                     | Yes                                  | Policy enforcement                                   | High             | VLAN, QoS, advanced topologies                                         | Medium           | Yes                 | Based on Open Virtual Network                        |


Key notes:
- Calico: Advanced network policy, BGP routing, distributed firewall, excellent for large-scale and secure clusters[2][3][4][5].
- Flannel: Very simple, easy to deploy, basic connectivity, no network policy support[3][4][1][5].
- Cilium: eBPF-powered, high performance, deep observability, supports L3-L7 policies, integrates with service mesh, advanced security[2][3][4][5].
- Weave Net: Mesh overlay, simple install, supports encryption and basic policies[4][1][5].
- Kube-router: Combines routing, proxy, and policy in one, BGP support, high performance[4][1].
- Antrea: Modern, supports advanced policies, observability, multi-cluster, designed for Kubernetes[4].
- Multus: Not a networking provider itself, but enables pods to use multiple CNIs (e.g., for SR-IOV, DPDK, etc.)[4].
- OVN-Kubernetes: Advanced features, Open vSwitch-based, supports VLAN, QoS, and complex topologies[4].

#### Cloud compatibility varies: Flannel, Cilium, and Weave Net work well in cloud environments, while Calico may need extra configuration for some clouds[1].


##### Feature summary:
- Overlay networking: Flannel, Weave Net, Cilium, Calico (optional)
- Native routing: Calico, Cilium, Kube-router, OVN-Kubernetes
- Network policy: Calico, Cilium, Antrea, Kube-router, Weave Net (basic)
- Advanced security: Calico, Cilium, Antrea
- Service mesh integration: Cilium, Antrea
- Multi-cluster support: Calico, Cilium, Antrea
- This table should help you compare and select the right CNI for your kubeadm-based Kubernetes cluster based on your requirements[2][3][4][1][5]

```
[1] https://github.com/weibeld/cni-plugin-comparison
[2] https://kubevious.io/blog/post/comparing-kubernetes-container-network-interface-cni-providers/
[3] https://www.plural.sh/blog/kubernetes-cni-guide/
[4] https://www.devopsschool.com/blog/list-of-cni-plugins-used-in-kubernetes/
[5] https://gyptazy.com/kubernetes-the-four-most-common-cnis/
[6] https://kubernetes.io/docs/concepts/extend-kubernetes/compute-storage-net/network-plugins/
[7] https://github.com/kubernetes/website/issues/45007
[8] https://www.reddit.com/r/kubernetes/comments/1110k8p/suggestions_for_k8s_cni/
[9] https://learn.microsoft.com/en-us/azure/aks/concepts-network-cni-overview
[10] https://docs.tigera.io/calico/latest/getting-started/kubernetes/hardway/install-cni-plugin
[11] https://kubernetes.io/blog/2021/04/20/defining-networkpolicy-conformance-cni-providers/
[12] https://kubernetes.io/docs/setup/production-environment/tools/kubeadm/create-cluster-kubeadm/
[13] https://www.suse.com/c/rancher_blog/comparing-kubernetes-cni-providers-flannel-calico-canal-and-weave/
[14] https://stackoverflow.com/questions/62129716/is-it-possible-to-have-2-network-plugins-for-the-kubernetes-cluster
[15] https://www.tigera.io/learn/guides/kubernetes-networking/kubernetes-cni/
[16] https://blog.developersteve.com/kubernetes-networking-cni-plugins-and-policy-solutions-918167dff965
[17] https://kubernetes-docsy-staging.netlify.app/docs/concepts/extend-kubernetes/compute-storage-net/network-plugins/
[18] https://kubernetes.io/docs/concepts/cluster-administration/addons/
[19] https://rstforum.net/whitepaper/understanding-kubernetes-cni
[20] https://overcast.blog/choosing-the-right-container-network-interface-plugin-in-kubernetes-45391c7d4cc8
```

# 7 July

### Writing Manifests
#### YAML
- This a file format for representing data which uses name value or key value pairs as a basic structure.
- YAML files generally have an extension of .yml or .yaml
- Basic structure
```
name-1: <value-1>
name-2: <value-2>
..
..
name-n: <value-n>
```
- Types of data
    - Simple/Scalar
        - Text
        - number
        - boolean
    - Complex
        - object/map
        - array/list
- Text
```
city: Hyderabad
city: 'Hyderabad'
city: "Hyderabad"
```
- number
```population: 11.3```
- boolean
```
metro: true
metro: yes
```
- list or array
```
areas: ['Ameerpet', 'SRNagar']
areas:
- Ameerpet
- SR Nagar
areas:
  - Ameerpet
  - SR Nagar
```
- object|map:
```
address:
  flatno: 601-b
  builing: nilgiri
  area: Ameerpet
  city: Hyderabad
```

#### YAML Tutorial
- [Refer Here](https://learnxinyminutes.com/yaml/)
- [Refer Here](https://docs.ansible.com/ansible/latest/reference_appendices/YAMLSyntax.html)
- Generally YAML for a specific tool comes with a structure or schema
- Lets create a structure for filling a product information in ecommerce website
- create a yaml file based on following
```
name string
manufacturer: string
skus: sku array
gst: number (default: 18)

## sku 
name: string
description: string
price: number
```       
- Lets create a sample yaml file
```
---
name: Sony PlayStation5 
manufacturer: Sony
skus:
  - name: Slim
    description: Slim
    price: 54990
  - name: Muscular
    description: Muscular
    price: 154990
```
#### Lets start writing pod manifests
- Kubernetes Pods have containers
- Any thing which you create in k8s is an object
- [Refer Here](https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.33/) for k8s api reference
- [Refer Here](https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.33/#pod-v1-core) for pod spec

#### Example 1: A pod with nginx container
- [Refer Here](https://github.com/asquarezone/KubernetesZone/commit/52d175ae4c3e7b6b51ba1bef036bbb76deb10c2e) for the changes done

![image](https://github.com/user-attachments/assets/9e61dec1-b0bf-40b9-84cb-7d709336e097)

- API Server fills the status

![image](https://github.com/user-attachments/assets/ccd101a8-d10d-4531-b87c-ca661ad4fd95)

![image](https://github.com/user-attachments/assets/f5a3f9a4-edeb-41bb-9e0f-9eb51b8339d1)

#### Example 2: A pod with nginx container and alpine container
- [Refer Here](https://github.com/asquarezone/KubernetesZone/commit/9d7ab4e73e3bdc28bfd9ea890779f08ef0274061) for the changes done

![image](https://github.com/user-attachments/assets/0be9ca95-6ea7-4f87-bba7-2e4a47758501)

#### Example 3: A pod with alpine container without cmd
```
apiVersion: v1
kind: Pod
metadata:
  name: third
spec:
  containers:
    - name: alp
      image: alpine
```

![image](https://github.com/user-attachments/assets/8813eb6f-48d4-45e8-bc92-d457428be85b)

# July 8

### Pods contd
#### Dealing with environmental variables
- container
```
docker run -d --name mysqldb \
     -e MYSQL_ROOT_PASSWORD=qtdevops \
     -e MYSQL_DATABASE=nop \
     -e MYSQL_USER=qtdevops \
     -e MYSQL_PASSWORD=qtdevops \
     mysql:latest
```

- Activity 4: lets try writing a manifest to create a mysql container in a Pod

```
apiVersion: v1
kind: Pod
metadata:
  name: forth
spec:
  containers:
    - name: mysql
      image: mysql:latest
      env:
        - name: MYSQL_ROOT_PASSWORD
          value: qtdevops
        - name: MYSQL_USER
          value: qtdevops
        - name: MYSQL_PASSWORD
          value: qtdevops
        - name: MYSQL_DATABASE
          value: nop
```

![image](https://github.com/user-attachments/assets/ef7cdb3f-a2e0-4fa2-b325-44c56ac358cd)


#### Dealing with commands or entrypoints
- Certain containers we might need to pass a CMD
- ```docker run -d --name test alpine sleep 1d```
- Lets try writing a manifest for this

```
apiVersion: v1
kind: Pod
metadata:
  name: fifth
spec:
  containers:
    - name: alp
      image: alpine
      args:
        - sleep
        - 1d
```

#### Resources in kuberntes
- [Refer Here](https://kubernetes.io/docs/concepts/configuration/manage-resources-containers/) for resources and limits
- A pod With resources defined has an impact on [QoS](https://kubernetes.io/docs/tasks/configure-pod-container/quality-service-pod/)

```
apiVersion: v1
kind: Pod
metadata:
  name: second
spec:
  containers:
    - name: first
      image: nginx
    - name: second
      image: alpine
      command:
        - sleep
        - 1d
```

# July 9

#### Labels
- A label is a key value pair that can be applied to any kubernetnes object
- This can be used for querying objects
- To add labels in manifest, refer metadata section.
- [Refer Here](https://kubernetes.io/docs/concepts/overview/working-with-objects/labels/) for official docs
- manifest

```
---
apiVersion: v1
kind: Pod
metadata:
  name: one
  labels:
    app: nginx
    env: dev
    project: learning
spec:
  containers:
    - name: web
      image: nginx
      resources:
        requests:
          cpu: 100m
          memory: 10M
        limits:
          cpu: 500m
          memory: 128M
---
apiVersion: v1
kind: Pod
metadata:
  name: two
  labels:
    app: nginx
    env: qa
    project: learning
spec:
  containers:
    - name: web
      image: nginx
      resources:
        requests:
          cpu: 100m
          memory: 10M
        limits:
          cpu: 500m
          memory: 128M
---
apiVersion: v1
kind: Pod
metadata:
  name: three
  labels:
    app: nginx
    env: uat
    project: learning
spec:
  containers:
    - name: web
      image: nginx
      resources:
        requests:
          cpu: 100m
          memory: 10M
        limits:
          cpu: 500m
          memory: 128M
```

- ![image](https://github.com/user-attachments/assets/1e9b1510-ed8f-41f6-af5f-87e0a17f953c)

- Once labels are applied we can query them using selectors
- [Selectors](https://kubernetes.io/docs/concepts/overview/working-with-objects/labels/#label-selectors) are of two types
    - Equality Based: Two major operations equals & not equals
    - Set Based:
        - in
        - notin
        - exists
        - doesnot exists
- Query using

```
kubectl get po
kubectl get po -l 'env = dev'
kubectl get po -l 'env in (dev,qa)'
```
#### Usecases
- My pod requires some service to be up & then it should start
    - types of containers in pod
- How to ensure pods are running
    - controller objects
        - replica set
        - deployments => zero down time & rollbacks
        - daemonset
- How to run batch jobs
    - Job
    - CronJob
- How about rather than static replicas i need dynamic => Autoscalers
- Load balancing/Service Interactions
    - Service
    - Ingress
    - Exposing the services to external world
        - Loadbalancers
        - Port forwarding
- Storage Solutions:
    - Persistent Volumes
    - Controller:
        - StatefulSet
- Configuration & Secrets
    - configmaps
    - secrets
    - vaults (secret vaults)
- Administrative:
    - backup
    - upgrade
    - Authentication & Authorization
    - Network policies
- Manifest => Static YAML , To enable Dyanmic YAML
    - HELM
    - Kustomize
- GitOps:
    - ArgoCD
- Troubleshooting: (Observability)
    - Monitor
    - Prometheus & Grafana
- Security:
- Service Mesh
