# Kafka
  These can be used to set up a kafka Cluster on Amazon Linux.
  The following playbooks will create a 3 node Kafka Cluster.
  We will also install the java8 using the below playbooks.

## Kafka Cluster set up

### STEP 1
  Create 3 ec2 Instances and place their Private IP's in the "inventory.yml" file.
  ```
  [kafka_servers]
  server1-ip kafka_broker_id=1  zk_id=1 kfk_server=server1-ip
  server2-ip kafka_broker_id=2  zk_id=2 kfk_server=server2-ip
  server3-ip kafka_broker_id=3  zk_id=3 kfk_server=server3-ip
  ```
  "zk_id" should be set to unique value for each server and "kfk_server" should be the ip of the corresponding server.

### STEP 2

   modify the version of kafka you want to install and other variables in "kafka_servers" file under group_vars directory. By default it will install the kafka version of "kafka_2.10-0.10.2.1"

### STEP 3

  Now run run the following ansible command to complete the set up of kafka Cluster.
  ```
  ansible-playbook -i inventory.yml kafka.yml
  ```
  This will create an Kafka Cluster.
