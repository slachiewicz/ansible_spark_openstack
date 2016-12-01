https://github.com/johandahlberg/ansible_spark_openstack
clonado en mi local: https://github.com/flopezag/ansible_spark_openstack

virtualenv env

source ./env/bin/activate

pip install -r requirements.txt 

git clone https://github.com/johandahlberg/ansible_spark_openstack.git

download your .openrc file

copy keystone IdM credentias

Create security group and rules
    openstack security group create spark --description "internal security group for spark"
    openstack security group rule create spark --protocol tcp --dst-port 1:65535

export OS_NETWORK_NAME="node-int-net-01"

Create ssh-keygen
    mkdir files
    ssh-keygen -N '' -f cloud -q

Create keypair
    openstack keypair create spark

Get ID of the network
    openstack network show node-int-net-01    => 473dacd2-42a6-4c1c-93e8-1b29f098846e

Update the main.yaml con los atributos anteriores.