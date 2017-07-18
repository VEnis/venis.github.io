---
category: "Q&A"
tags: docker etcd consul redis enterprise-integration
---

## Problem
There are some multiple API endpoints (REST services for example) that increased some counter every time API is called.
The counter value must be shared between endpoints. They are often dockerized and different containers can be run on 
different hosts.

## Solution

To solve given problem using for example database is overhead. Everything needed is just some distributed lightweight 
key-value storage with shared lock support. Here are some candidates:

* [etcd](https://coreos.com/etcd)
* [consul](https://www.consul.io), especially [consul-lock](https://www.consul.io/docs/commands/lock.html)
* [redis](http://redis.io)