# chef-essentials-classroom

[![IaC](https://app.soluble.cloud/api/v1/public/badges/55b15e84-54b7-4a7d-9f59-8b9693aa2ba9.svg)](https://app.soluble.cloud/repos/details/github.com/galenemery/chef-essentials-classroom)  [![HIPAA](https://app.soluble.cloud/api/v1/public/badges/a8d86f1c-1a95-4497-bb49-a06f0123df05.svg)](https://app.soluble.cloud/repos/details/github.com/galenemery/chef-essentials-classroom)  [![CIS](https://app.soluble.cloud/api/v1/public/badges/bc37e238-00b6-4c09-8d5d-0f5f6b8a690d.svg)](https://app.soluble.cloud/repos/details/github.com/galenemery/chef-essentials-classroom)  

This repo contains all the components required to build Chef Essentials (Linux) training environments.

/cookbooks => Contains the build cookbook for configuring Chef Workstation and Chef Node images

/packer => Contains Packer templates that use the build cookbook to generate Amazon AMIs

/terraform => Contains Terraform plans for deploying classroom workstations/nodes to AWS


TODO: Lots of things coming down the pipeline in the immediate future. The commands below to
get started are likely to change as more abstraction is added to the tooling.


Currently the process to spin up a classroom is the following:

- The root config file is `terraform.tfvars` Update the values in `terraform.tfvars`
 to include your information specifically.

- Run the command `curl -w "\n" 'https://discovery.etcd.io/new?size=<insert the number of student nodes + 1 here>'`
  e.g. `curl -w "\n" 'https://discovery.etcd.io/new?size=45'`

- Paste the output of your curl command into the `disco` variable in `terraform.tfvars`

- Run the command `terraform apply -parallelism=<total node count>`
  e.g. `terraform apply -parallelism=45`

Voila! You should have a classroom!

Students should be able to log into the URL of the guacamole server with


Username: chef

Password: chef


The url should look something like this:

  `http://ec2-ip-of-guac-server.compute-1.amazonaws.com:8080/guacamole/#/`
