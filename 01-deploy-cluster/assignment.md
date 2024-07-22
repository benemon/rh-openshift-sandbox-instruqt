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
  type: service
  hostname: console-openshift-console
  port: 443
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
> Due to the Instruqt Script Timeouts, the OpenShift Cluster deployment is undertaken by a one-shot systemd service as part of the challenge

Progress will be logged to the [Bastion tab](tab-0). Alternatively, check the content of the `.openshift-install.log` file in the [Configuration tab](tab-2).

```bash,run
tail -f /opt/openshift/cluster/conf/.openshift_install.log
```

More information about the install process can be found in the [Red Hat OpenShift Documentation](https://docs.openshift.com/container-platform/latest/welcome/index.html)

Installation WILL take a while, usually between 40 and 60 minutes. Go and make a cuppa or something.