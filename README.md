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

- `python3-lxml` is installed on your system
    - for Debian distros (ex. Ubuntu) run the following command
        - ```sudo apt install ansible``` 

- `ansible collections`
    - A list of collections that you need to download are in the `requirements.yml` file. You can quickly install these collections to your machine by running the following command 
        - ```ansible-galaxy collection install -r requirements.yml ```



## System Requirements

In order for this process to go smoothly you should have a relatively beefy system. The Red Hat [docs](https://docs.openshift.com/container-platform/4.13/installing/installing_sno/install-sno-preparing-to-install-sno.html) state that we need the following resources just to deploy a single node cluster

| Profile | vCPU | Memory | Storage |
| ------- | ---- | ------ | ------- | 
| Minimum | 8vCPU cores | 16GB of RAM | 120GB |

Given the following specifications we recommend your machine have the following resources before you even consider using this code

| vCPU | Memory | Storage |
| ---- | ------ | ------- |
| 16vCPU cores | 32 GB of RAM | 1TB |

This automation was tested using the following hardware
```
CPU: Ryzen 9 5900X (12 cores, 24 vcpu)
Mem: 64GB of RAM
Storage: 1TB
```


