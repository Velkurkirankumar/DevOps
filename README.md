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


# May 19

## Terraform

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
