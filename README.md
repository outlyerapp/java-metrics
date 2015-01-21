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

