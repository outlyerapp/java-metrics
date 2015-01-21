# java-metrics

1. Install the latest jmxtrans from https://github.com/jmxtrans/jmxtrans/downloads

1. wget the appropriate .json files from this repo into /var/lib/jmxtrans

1. Find and replace SERVER, PORT and APIKEY_FINGERPRINT

1. service jmxtrans restart

# Troubleshooting

Check /var/log/jmxtrans/jmxtrans.log

The APIKEY_FINGERPRINT is a concetenation (with no spaces or other separators) of the Dataloop API Key and the agent fingerprint that you want the metrics to appear under.

You can find your API Key in /etc/dataloop/agent.conf

You can find your agent fingerprint in /etc/dataloop/agent.finger

The SERVER and PORT strings refer to the JMX connection details. If you are running jmxtrans on the same machine as the service you wish to monitor then SERVER will be 'localhost' and the port will be whatever port JMX runs on.

# Enabling JMX

Each service will require slightly different instructions. Here is a good link for Tomcat7 : http://tomcat.apache.org/tomcat-7.0-doc/monitoring.html
(the 'enabling jmxremote' section).

With Kafka it was as simple as starting with the JMX_PORT environment variable set.

    env JMX_PORT=8110 bin/kafka-server-start.sh config/server.properties
