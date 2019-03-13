[![Build Status](https://travis-ci.org/116davinder/apache-cassandra-cluster-mgmt.svg?branch=master)](https://travis-ci.org/116davinder/apache-cassandra-cluster-mgmt)

### To Start new cluster
* Update Required vars in ```group_vars/all.yml``` .
* Update Required vars in ```inventory/cluster.ini``` .

```ansible-playbook -i inventory/cluster.ini clusterSetup.yml```

### To do rolling restart of full cluster
```ansible-playbook -i inventory/cluster.ini clusterRollingRestart.yml```

### To add data node to running cluster
* Update Required vars in ```inventory/cluster.ini``` .

```ansible-playbook -i inventory/cluster.ini clusterAddDataNodes.yml```

### To remove data node to running cluster
* Update Required vars in ```inventory/cluster.ini``` .

```ansible-playbook -i inventory/cluster.ini clusterRemoveDataNodes.yml```

### To update logging properties to running cluster
* Update Required vars in ```group_vars/all.yml``` .

```ansible-playbook -i inventory/cluster.ini clusterLogging.yml```

### To update jvm properties to running cluster
* Update Required vars in ```group_vars/all.yml``` .

```ansible-playbook -i inventory/cluster.ini clusterJvmConfigs.yml```

### To add auto repair crons to running cluster
* It generate random number between 0 to 6 to select weekday for cron to run for given node.
* It will also use sepuential full repair for given node.

```ansible-playbook -i inventory/cluster.ini clusterRepairCrons.yml```

### To remove old cassandra versions
* Update ```cassandraOldVersion``` var in ```group_vars/all.yml``` .

```ansible-playbook -i inventory/cluster.ini clusterRemoveOldVersions.yml```

### To Upgrade existing cluster
* Update ```cassandraVersion``` var in ```group_vars/all.yml``` .

It will install latest version in parallel but restart will be done in rolling fashion.**(seed nodes first then data nodes)**

```ansible-playbook -i inventory/cluster.ini clusterSetup.yml```

### To down grade existing cluster
**Prequisties**
* Update ```cassandraOldVersion``` var in ```group_vars/all.yml``` .
* It won`t download old version cassandra tar files. if required then use ```clusterSetup.yml``` instead of ```clusterDownGradeVersion.yml```.

It will Change symlink for service and will do the rolling restart of full cluster.**(seed nodes first then data nodes)**

```ansible-playbook -i inventory/cluster.ini clusterDownGradeVersion.yml```

### **Note***
* before any installation/upgrade/downgrade of cassandra. please review cassandra templates.
located at ```roles/configure/templates```
* all properties update like ```logging/jvm``` will be done in rolling update fashion
and respective node will be restarted as well.
* cluster downgrade should be reviewed first. it may cause data corruption or other serious damage to cluster.

### OS support
* any os with systemd

### Tested Ansible Version
```
ansible 2.7.8
  config file = None
  configured module search path = [u'/home/vagrant/.ansible/plugins/modules', u'/usr/share/ansible/plugins/modules']
  ansible python module location = /usr/lib/python2.7/site-packages/ansible
  executable location = /usr/bin/ansible
  python version = 2.7.5 (default, Apr 11 2018, 07:36:10) [GCC 4.8.5 20150623 (Red Hat 4.8.5-28)]
```

### Tested OS Version
```
$cat /etc/redhat-release
CentOS Linux release 7.6.1810 (Core)
```

### Recommended Settings
* https://docs.datastax.com/en/dse/6.0/dse-admin/datastax_enterprise/config/configRecommendedSettings.html

### References
* http://cassandra.apache.org/download/