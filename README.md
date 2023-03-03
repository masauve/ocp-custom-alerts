# ocp-custom-alerts

This shows a basic example of creating a custom alert and receiver in OpenShift 4.

The alerts configured in this example are:
* pv-high-utilisation: warning - when a pv has less than 1Gb available capacity
* pv-90-capacity: critical - when a pv is 90% utilized.

to apply the configuration, you must first enable OpenShift User Workload Monitoring:
``` oc apply -k manifests/config/base ```

then apply the configuration rules for alerting:
``` oc apply -k manifests/alerts/base ```

These alerts assume a receiver named slack.

To configure an alert receiver, follow these steps in the OpenShift console and use the label notification=slack to send these alarms:

https://docs.openshift.com/container-platform/4.12/monitoring/managing-alerts.html#configuring-alert-receivers_managing-alerts


