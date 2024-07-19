# rh-openshift-sandbox-instruqt

Make sure to add an ENV_VAR call TF_VAR_pull_secret to the bastion container configuration before pushing to Instruqt.

This should contain a Base64 Encoded version of the Red Hat Pull Secret.

The Pull Secret can be retrieved from the [Red Hat Cloud Console for OpenShift](https://console.redhat.com/openshift). Note that a Red Hat login is required.