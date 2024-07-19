---
slug: initial-setup
id: dyt20wscbfqx
type: challenge
title: Initial Setup
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


Create the Configuration Files and Infrastructure
=================================================

As part of this step, we've created the prerequisite configuration files and infrastructure in Azure required to provision the latest `major.minor` release of Red Hat OpenShift Container Platform.

The cluster will be provisioned using the Full Stack Automation mode, which will provision the underlying infrastructure and deploy the cluster using the default configuration options.

More information can be found [in the documentation](https://docs.openshift.com/container-platform/latest/installing/installing_azure/installing-azure-default.html)

If you'd like to have a look at the `install-config.yaml` file before the installation begins, open the [Configuration tab](tab-2), and look inside the `conf` directory for the `install-config.yaml` file.

> [!NOTE]
> This file contains all of the options necessary to deploy an OpenShift cluster. If you want to make changes, now is the time to do it!