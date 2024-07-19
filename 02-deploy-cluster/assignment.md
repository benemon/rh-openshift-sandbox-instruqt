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

