# Ansible_create_ec2_instance_and_deploy_wordpress_using_docker
create ec2 instance using Ansible and deploy wordpress on it using docker
## steps
1. install ansible using pip and globally
[*] pip3 install ansible
[*] sudo apt install ansible
[*] ansible --version
2. create an IAM USER with admin access and add his credentials locally
3. get vpc_id of the default subnet and any subnet from the default vpc and add it under roles/create-ec2-instances/vars instead of the 2 vars here
4. ansible-playbook create-ec2.yml -i inventory
5. get public up from aws console of the instance and add it under inventory/ec2 instead of the ip here line 2
6. go to roles/install-Wordpress-Mariadb and line40 edit the url to be your publicip:8080 
7. ansible-playbook install-docker-mariadb-wordpress.yml -i inventory --private-key keys/my_keypair.pem
