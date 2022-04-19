# Ansible - AWS infrastructure services

This is a simple demo to deploy a number of AWS services from Ansible playbook: - A VPC - An associated Internet Gateway to the previous created VPC - A Subnet in the VPC - Public subnet route table - Security group - Provision an EC2 instance - Show details (debug output)

## Prerequisites

Have an AWS account available and the credentials: - AWS_ACCESS_KEY_ID - AWS_SECRET_ACCESS_KEY

A valid and subscribed Ansible Automation Platform already deployed.

## Setting up the demo

1.  Create credentials

    - Git repository credentials on RHAAP

      - From main left menu, Resources>Crendentials click on Add
      - Input the requested information:
        - Name: NAME_OF_CREDENTIAL
        - Description: SHORT_DESCRIPTION
        - Organization: Default
        - Credential Tpe: Source Control
        - Username: GIT_USER
        - Password: GIT_TOKEN_OFPERSONAL_ACCOUNT
      - Click Save

      ![alt_text](https://github.com/san985tos/OpenDemoDays/blob/main/Ansible_AWS_infrastructure/screenshots/Screen%20Shot%202021-12-05%20at%2015.48.17.png)

    - AWS credentials

      - From main left menu, Resources>Crendentials click on Add
      - Input the requested information:
        - Name: NAME_OF_CREDENTIAL
        - Description: SHORT_DESCRIPTION
        - Organization: Default
        - Credential Tpe: Amazon Web Services
        - Access Key: AWS_ACCESS_KEY_ID
        - Secret Key: AWS_SECRET_ACCESS_KEY
      - Click Save

      ![alt_text](https://github.com/san985tos/OpenDemoDays/blob/main/Ansible_AWS_infrastructure/screenshots/Screen%20Shot%202021-12-05%20at%2015.51.38.png)

2.  Create project

    - From main left menu, Resources>Projects click on Add - - Input the requested information:

      - Name: NAME_OF_CREDENTIAL
      - Description: SHORT_DESCRIPTION
      - Organization: Default
      - Execution Environment: Ansible Engine 2.9 execution environment
      - Source Control Credential Type: Git
      - Source Control URL: THIS_REPO_URL
      - Source Control Branch: SELECT_BRANCH
      - Source Code Credentials: NAME_OF_CREDENTIAL_CREATED_IN_PREVIOUS_STEP
      - Ckeck all options
      - Click Save

      ![alt_text](https://github.com/san985tos/OpenDemoDays/blob/main/Ansible_AWS_infrastructure/screenshots/Screen%20Shot%202021-12-05%20at%2015.56.01.png)

3.  Create Template

    - From main left menu, Resources>Templates click on Add - Input the requested information:
      - Name: NAME_OF_CREDENTIAL
      - Description: SHORT_DESCRIPTION
      - Jobtype: Run
      - Inventory: Demo Inventory
      - Project: THE_CREATED_PROJECT
      - Execution Environment: Ansible Engine 2.9 execution environment
      - Source Control Branch: SELECT_THE_BRANCH
      - Playbook: SELECT_PLAYBOOK
      - Credentials: CREDENTIAL_CREATED_OF_AWS
    - Enable Show Changes option
    - Click Save

      ![alt_text](https://github.com/san985tos/OpenDemoDays/blob/main/Ansible_AWS_infrastructure/screenshots/Screen%20Shot%202021-12-05%20at%2016.10.09.png)

4.  Clcik on Launch to start the playbook execution

    ![alt_text](https://github.com/san985tos/OpenDemoDays/blob/main/Ansible_AWS_infrastructure/screenshots/Screen%20Shot%202021-12-05%20at%2016.11.22.png)
