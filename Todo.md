- [x] start fresh cluster from scratch
- [x] rolling restart cluster of cluster
- [x] add new data node to cluster
- [x] remove data node from cluster
- [x] delete old versions of cassandra
- [x] migrate all files from adhoc folder to main folder
- [x] change logging to different level and restart that node
- [x] update jvm properties only like logging properties
- [] install opscenter
- [] backup and restore to separate partitions/disks playbooks
- [] add repair crons on each cassandra node

#### Testing of Cluster
- [x] load sample data and test scaling of cassandra cluster
- [] add new seed node to cluster
- [] remove seed node from cluster
- [] add firewall rules for ufw or firewalld or iptables
- [] Take full offsite backup of cluster

#### Support for Aws Cloud
- [] provisioning initial resources
- [] creating auto scaling groups for data nodes
- [] backup to S3