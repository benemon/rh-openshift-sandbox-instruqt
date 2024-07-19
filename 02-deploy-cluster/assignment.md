---
slug: deploy-cluster
id: umhsmry2pdni
type: challenge
title: Deploy Cluster
tabs:
- title: Bastion
  type: terminal
  hostname: bastion
  workdir: /opt/openshift/cluster
- title: Azure Portal
  type: service
  hostname: cloud-client
  path: /
  port: 80
- title: Configuration
  type: code
  hostname: bastion
  path: /opt/openshift/cluster
difficulty: basic
---

Deploy the OpenShift Cluster!
=============================

Switch to the [Bastion tab](tab-0) and run the following command to deploy the OpenShift cluster based on the configuration defined in the `install-config.yaml`.

```bash,run
openshift-install create cluster --dir=conf
```

> [!IMPORTANT]
> This WILL take a while, usually between 40 and 60 minutes. Go and make a cuppa or something.