# vagrant-myenv

My minimal recipe for Vagrant that setup Ubuntu VM with common tools for DevOps, SRE, and typical software development.
This spins up an isolated environment in Virtualbox with one simple command.
It also comes with Packer files for AMI image for AWS and GCE image for GCP.

## Environment

### OS
* Ubuntu 20.04 LTS (Focal Fossa)

### DevOps tools
* Docker
* docker-compose
* Packer
* Terraform
* Ansible
* awscli
* gcloud cli

### K8S tools

* kubectl
* kubectx
* helm
* stern
* telepresence
* kustomize

### Programming

* Python3
* Go
* Node.js
* Ruby

## Getting started

### Setup

* Install Virtualbox and Vagrant
  * https://www.virtualbox.org/wiki/Downloads
  * https://www.vagrantup.com/docs/installation/
* Install Packer if you need to build AMI and GCE image
  * https://packer.io/intro/getting-started/install.html

### Install required Vagrant plugins

```
$ vagrant plugin install vagrant-vbguest
$ vagrant plugin install vagrant-disksize
```

### Provision and start VM

```
$ vagrant up
```

### Create AMI image for AWS

```
$ packer build packer-ec2.json
```

### Create GCE image for GCP

```
$ packer build packer-gce.json
```
