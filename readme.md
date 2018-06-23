[![Build Status](https://travis-ci.org/116davinder/apache-cassandra-cluster-mgmt.svg?branch=master)](https://travis-ci.org/116davinder/apache-cassandra-cluster-mgmt)

### To Run start new cluster
```ansible-playbook -i inventory/cluster.ini clusterSetup.yml```

### To Run adhoc tasks playbooks
* Export ansible.cfg path

    ```ANSIBLE_CONFIG=<apache-cassandra-cluster-mgmt>/ansible.cfg```

* Run required playbook

    ```ansible-playbook -i inventory/cluster.ini adhoc_tasks/clusterRollingRestart.yml```

### OS support
* any os with systemd

### Recommended Settings
* https://docs.datastax.com/en/dse/6.0/dse-admin/datastax_enterprise/config/configRecommendedSettings.html

### References
* http://cassandra.apache.org/download/