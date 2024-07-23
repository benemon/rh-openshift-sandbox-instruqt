---
slug: deploy-cluster
id: voo9iflgvbd5
type: challenge
title: Deploy Cluster
tabs:
- title: Bastion
  type: terminal
  hostname: bastion
  workdir: /opt/openshift/cluster
- title: Proxy
  type: terminal
  hostname: proxy
- title: Configuration
  type: code
  hostname: bastion
  path: /opt/openshift/cluster
- title: OpenShift Console
  type: website
  url: https://console-openshift-console.apps.ocp.proxy.${_SANDBOX_ID}.instruqt.io
- title: Cloud Client
  type: service
  hostname: cloud-client
  path: /
  port: 80
difficulty: basic
---

Cluster Deploying
=================

> [!IMPORTANT]
> Due to the Instruqt Script Timeouts, the OpenShift Cluster deployment is undertaken as part of the challenge.

Run the installation command:

```bash,run
install-openshift-cluster
```

> [!NOTE]
> This is a wrapper script created to support installation on Instruqt.

Progress will be logged to the [Bastion tab](tab-0). Alternatively, check the content of the `.openshift-install.log` file in the [Configuration tab](tab-2), which will provide lower level debug output as the process continues. You may need to refresh the tab for the changes to appear.

More information about the install process can be found in the [Red Hat OpenShift Documentation](https://docs.openshift.com/container-platform/latest/welcome/index.html)

Installation will take a while, usually between 40 and 60 minutes. Go and make a cuppa or something.

The usual order of execution will output log entries like so:

```
INFO Credentials loaded from file "/root/.azure/osServicePrincipal.json"
INFO Consuming Install Config from target directory
INFO Creating infrastructure resources...
INFO Waiting up to 20m0s (until 10:53AM UTC) for the Kubernetes API at https://api.ocp.proxy.xxxxxxxxx.instruqt.io:6443...
INFO API v1.29.6+aba1e8d up
INFO Waiting up to 45m0s (until 11:18AM UTC) for bootstrapping to complete...
INFO Destroying the bootstrap resources...
INFO Waiting up to 40m0s (until 11:30AM UTC) for the cluster at https://api.ocp.proxy.xxxxxxxxx.instruqt.io:6443 to initialize...
INFO Waiting up to 30m0s (until 11:29AM UTC) to ensure each cluster operator has finished progressing...
INFO All cluster operators have completed progressing
INFO Checking to see if there is a route at openshift-console/console...
INFO Install complete!
INFO To access the cluster as the system:admin user when using 'oc', run 'export KUBECONFIG=/opt/openshift/cluster/conf/auth/kubeconfig'
INFO Access the OpenShift web-console here: https://console-openshift-console.apps.ocp.proxy.xxxxxxxxx.instruqt.io
INFO Login to the console with user: "kubeadmin", and password: "xxxx-xxxx-xxxx-xxxx"
INFO Time elapsed: 50m17s
```

Only when you see the `INFO Install complete!` message logged to the [Bastion tab](tab-0), or in the `.openshift-install.log` file in the [Configuration tab](tab-2) can installation be considered complete.

If you need to revisit the cluster details, these can be found in the `outputs.txt` file:

```bash,run
cat /opt/openshift/cluster/conf/outputs.txt
```

You'll find the access URL, the details of the default `kubeadmin` user, and the location of the `KUBECONFIG` file present.

The Bastion host comes preloaded with the OpenShift command line tools, which can be used to interact with the cluster.

```bash,run
oc
```

Cleaning Up
===========
If you want to tear down the OpenShift cluster and end the track gracefully, please copy and paste the command below.

```bash,run
export=CONFIRM_CLEANUP
```

Once done, you can click "Check" to finish.
