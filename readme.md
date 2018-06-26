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

### Note*
* all properties update like ```logging/jvm``` will be done in rolling update fashion
and respective node will be restarted as well.

### OS support
* any os with systemd

### Recommended Settings
* https://docs.datastax.com/en/dse/6.0/dse-admin/datastax_enterprise/config/configRecommendedSettings.html

### References
* http://cassandra.apache.org/download/