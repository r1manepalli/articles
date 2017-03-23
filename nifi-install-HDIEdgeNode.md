NiFi Installation on HDInsight Edge Node

Install Script:
https://raw.githubusercontent.com/hau-mal/BigData/master/sh/nifi-install.sh
copy on Data Lake Store


Sample Arm Template:

```
                "installScriptActions": [
                    {
                        "name": "[concat('emptynode','-' ,uniquestring(variables('applicationName')))]",
                        "uri": "adl://hmadls.azuredatalakestore.net/cluster/shell/nifi-install.sh",
                        "roles": [
                            "edgenode"
                        ]
                    }
```


Setup an [SSH-Tunnel](https://github.com/Microsoft/azure-docs/blob/master/articles/hdinsight/hdinsight-linux-ambari-ssh-tunnel.md) to access the NiFi site.


Access:
http://*edgenode*.internal.cloudapp.net:8080/nifi/
Example:
http://ed10-hmaspa.0e01ln2yiiru1bma04rbw2f5xe.cx.internal.cloudapp.net:8080/