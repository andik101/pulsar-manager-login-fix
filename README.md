# Pulsar manager version 0.3.0

Manifest for pulsar-manager **dashboard login issue** in kubernetes cluster, for fix and change username or password.

[Pulsar Manager](https://pulsar.apache.org/docs/en/administration-pulsar-manager/) is a web-based GUI management and monitoring tool that helps administrators and users manage and monitor tenants, namespaces, topics, subscriptions, brokers, clusters, and so on, and supports dynamic configuration of multiple environments.

## Introduction

This repo maintains the configuration file for **pulsar manager version 0.3.0**, which fix the issue of dashboard login `username or password is incorrect` for [Pulsar Manager](https://github.com/apache/pulsar-manager#access-pusar-manager) deployment on a [Kubernetes](http://kubernetes.io) cluster.



## Installing the UI Superuser `pulsar`

To install in kubernetes cluster:

```bash
$ kubectl apply -f pulsar-manager-superuser-job.yaml
```

The command deploys a batch Job on the Kubernetes cluster in the default configuration.

> **Note**: Pulsar manager backend service must be changed. Please before deploy this, must be check and change the service name of ***pulsar-manager-backend*** as you have deployed it in your cluster. In this case the service name is **pulsar-manager-backend and port 7750**. Also, you can change the username and password of default ***pulsar*** as you wish.


The docker image used for this deployment is the Streamnative maintained pulsar-manager version 0.3.0 chart.


### Using password
The username and password for pulsar manager dashboard is stored in application.json of the pulsar-manager-backend service, in path: /pulsar-manager/users/superuser 
