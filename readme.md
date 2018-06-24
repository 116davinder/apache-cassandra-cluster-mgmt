[![Build Status](https://travis-ci.org/116davinder/apache-cassandra-cluster-mgmt.svg?branch=master)](https://travis-ci.org/116davinder/apache-cassandra-cluster-mgmt)

### To Run start new cluster
```ansible-playbook -i inventory/cluster.ini clusterSetup.yml```

### To do rolling restart of full cluster
```ansible-playbook -i inventory/cluster.ini clusterRollingRestart.yml```

### To add node to running cluster
```ansible-playbook -i inventory/cluster.ini clusterAddNodes.yml```

### OS support
* any os with systemd

### Recommended Settings
* https://docs.datastax.com/en/dse/6.0/dse-admin/datastax_enterprise/config/configRecommendedSettings.html

### References
* http://cassandra.apache.org/download/