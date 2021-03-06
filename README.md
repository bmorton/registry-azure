# Docker Registry for Azure storage

This is a Docker Regsitry that is preconfigured to use Azure storage and to automatically pull its configuration from etcd.  To setup the values in etcd, use these commands:

```
etcdctl set /services/registry/AZURE_STORAGE_ACCOUNT_NAME youraccountname
etcdctl set /services/registry/AZURE_STORAGE_ACCOUNT_KEY youraccountkey
etcdctl set /services/registry/AZURE_STORAGE_CONTAINER storagecontainername
```

Make sure you pass `ETCDCTL_PEERS` to the container so it knows how to get to etcd.

This repo is based of a [blog post](http://azure.microsoft.com/blog/2014/11/11/deploying-your-own-private-docker-registry-on-azure/) on Azure's blog with the etcd stuff added for ease-of-use.
