# SingleNodeOpenShift

## Description

Ansible automation that will stand up a single node OpenShift cluster on your host machine using the assisted installer API [Red Hat Assisted Installer](https://access.redhat.com/documentation/en-us/assisted_installer_for_openshift_container_platform/2022/html/assisted_installer_for_openshift_container_platform/installing-with-api#doc-wrapper). 

After running this automation you should have a local OpenShift cluster stood up and accessable via a browser on your machine. Your cluster will only be available to the machine your ran the `deploy-cluster.yml` playbook.

## Pre-Requisites
- You have loaded your `offline_token` and have it saved some place safe.  Ansible will ask you to enter this token when you run the `deploy-cluster.yml` playbook.

- You have downloaded your `pull-secret.txt` file from the [OpenShift Cluster Manager](https://console.redhat.com/openshift/assisted-installer/clusters) following the documentation described [here](https://access.redhat.com/documentation/en-us/assisted_installer_for_openshift_container_platform/2022/html/assisted_installer_for_openshift_container_platform/installing-with-api#configuring-the-pull-secret_installing-with-api). 

- You have updated the variable `pull_secret_path` in `vars.yml` to point to the downloaded file.



## Dependancies
- `python3.9+` is installed on your system

- `ansible` is installed on your system
    - for Debian distros (ex. Ubuntu) run the following command
        - ```sudo apt install ansible``` 

- `ansible collections`
    - A list of collections that you need to download are in the `requirements.yml` file. You can quickly install these collections to your machine by running the following command 
        - ```ansible-galaxy collection install -r requirements.yml ```





