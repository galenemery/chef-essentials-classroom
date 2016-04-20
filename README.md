# chef-essentials-classroom

This repo contains all the components required to build Chef Essentials (Linux) training environments.

cookbooks/ => Contains the build cookbook for configuring Chef Workstation and Chef Node images

packer/ => Contains Packer templates that use the build cookbook to generate Amazon AMIs

terraform/ => Contains Terraform plans for deploying classroom workstations/nodes to AWS
