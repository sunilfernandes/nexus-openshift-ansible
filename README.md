nexus-openshift-ansible
=========

A playbook which uses Ansible's OC module to connect to Openshift API to deploy Sonatype Nexus.

This playbook uses a deployment config which pulls the docker image "docker.io/sonatype/nexus3" and deploys it to a project specified in an Openshift cluster.

After installation it uses a post-deploy step to create repositories using the nexus-functions script created by at Jorge Morales and Siamak Sadeghianfar from :

"https://raw.githubusercontent.com/OpenShiftDemos/nexus/master/scripts/nexus-functions"

Requirements
------------

* OC CLI version 3.6 and above
* A running OC cluster
* A user who has project creation as well as project edit rights
* Can login using API token to the cluster


Role Variables
--------------

Are defined in the Vars directory of the role

# OC related vars
openshift_cluster_url: <<Cluster URL goes here>>


#Project related vars

project_name: ansible-testproject

project_description: "Ansible test project"

nexus_service_name: nexus3

nexus_version: "3.7.1"

docker_repo: "docker.io/sonatype/nexus3"

nexus_volume_size: 2Gi

nexus_application_memory_size: 512Mi

nexus_application_memory_size_limit: 2Gi

Dependencies
------------

Cluster should allow access to Docker.io

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: localhost
      roles:
         - nexus

License
-------


Author Information
------------------

Sunil Fernandes (sunilf@gmail.com)
https://www.linkedin.com/in/sunilf/
