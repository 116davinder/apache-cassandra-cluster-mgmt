[![Build Status](https://travis-ci.org/116davinder/apache-cassandra-cluster-mgmt.svg?branch=master)](https://travis-ci.org/116davinder/apache-cassandra-cluster-mgmt)

### To Run start new cluster
```ansible-playbook -i inventory/cluster.ini clusterSetup.yml```

### To do rolling restart of full cluster
```ansible-playbook -i inventory/cluster.ini clusterRollingRestart.yml```

### To add data node to running cluster
```ansible-playbook -i inventory/cluster.ini clusterAddDataNodes.yml```

### To remove data node to running cluster
```ansible-playbook -i inventory/cluster.ini clusterRemoveDataNodes.yml```

### To update logging properties to running cluster
Update Required vars in ```group_vars/all.yml``` .

```ansible-playbook -i inventory/cluster.ini clusterLogging.yml```

### To update jvm properties to running cluster
Update Required vars in ```group_vars/all.yml``` .

```ansible-playbook -i inventory/cluster.ini clusterJvmConfigs.yml```

### To remove old cassandra versions
Update ```cassandraOldVersion``` var in ```group_vars/all.yml``` .

```ansible-playbook -i inventory/cluster.ini clusterRemoveOldVersions.yml```

### Note*
* all properties update like ```logging/jvm``` will be done in rolling update fashion
and respective node will be restarted as well.

### OS support
* any os with systemd

### Tested Ansible Version
```
ansible 2.5.5
  config file = None
  configured module search path = [u'/home/vagrant/.ansible/plugins/modules', u'/usr/share/ansible/plugins/modules']
  ansible python module location = /usr/lib/python2.7/site-packages/ansible
  executable location = /usr/bin/ansible
  python version = 2.7.5 (default, Apr 11 2018, 07:36:10) [GCC 4.8.5 20150623 (Red Hat 4.8.5-28)]
```

### Tested OS Version
```
$cat /etc/redhat-release
CentOS Linux release 7.5.1804 (Core)
```

### Recommended Settings
* https://docs.datastax.com/en/dse/6.0/dse-admin/datastax_enterprise/config/configRecommendedSettings.html

### References
* http://cassandra.apache.org/download/