---
title: "Multi-Datacenter Replication Reference: Per Bucket"
description: ""
project: "riak_kv"
project_version: 2.9.10
menu:
  riak_kv-2.9.10:
    name: "Per Bucket"
    identifier: "managing_ref_mdc_per_bucket"
    weight: 101
    parent: "managing_ref_mdc"
toc: true
aliases:
  - /riak/2.9.10/ops/mdc/per-bucket
  - /riak/kv/2.9.10/ops/mdc/per-bucket
  - /riak/latest/using/reference/multi-datacenter/per-bucket-replication/
  - /riak/kv/latest/using/reference/multi-datacenter/per-bucket-replication/
  - /riakkv/latest/using/reference/multi-datacenter/per-bucket-replication/
---

To enable or disable replication per bucket, you can use the `repl`
bucket property.

Some changes have occurred between 1.1 and 1.2.

These `repl` values are available in Riak Enterprise version 1.1 and
above:

  * `true`
  - /riak/latest/using/reference/multi-datacenter/per-bucket-replication/
  - /riak/kv/latest/using/reference/multi-datacenter/per-bucket-replication/
  - /riakkv/latest/using/reference/multi-datacenter/per-bucket-replication/
---
Enable replication (realtime + fullsync)
  * `false`
  - /riak/latest/using/reference/multi-datacenter/per-bucket-replication/
  - /riak/kv/latest/using/reference/multi-datacenter/per-bucket-replication/
  - /riakkv/latest/using/reference/multi-datacenter/per-bucket-replication/
---
Disable replication (realtime + fullsync)

These option values are only available in Riak Enterprise version 1.2
and above:

  * `realtime`
  - /riak/latest/using/reference/multi-datacenter/per-bucket-replication/
  - /riak/kv/latest/using/reference/multi-datacenter/per-bucket-replication/
  - /riakkv/latest/using/reference/multi-datacenter/per-bucket-replication/
---
Replication only occurs in realtime for this bucket
  * `fullsync`
  - /riak/latest/using/reference/multi-datacenter/per-bucket-replication/
  - /riak/kv/latest/using/reference/multi-datacenter/per-bucket-replication/
  - /riakkv/latest/using/reference/multi-datacenter/per-bucket-replication/
---
Replication only occurs during a fullsync operation
  * `both`
  - /riak/latest/using/reference/multi-datacenter/per-bucket-replication/
  - /riak/kv/latest/using/reference/multi-datacenter/per-bucket-replication/
  - /riakkv/latest/using/reference/multi-datacenter/per-bucket-replication/
---
Replication occurs in realtime and during fullsync

### Example of Disabling

```curl
curl -v -XPUT http://127.0.0.1:8098/buckets/my_bucket \
  -H "Content-Type: application/json" \
  -d '{"props":{"repl":false}}'
```

### Example of Enabling

```curl
curl -v -XPUT http://127.0.0.1:8098/buckets/my_bucket \
  -H "Content-Type: application/json" \
  -d '{"props":{"repl":true}}'
```

## How Bucket Properties Work in Riak KV

When using Multi-Datacenter Replication, each bucket's write properties
are derived from the bucket's properties in the destination cluster. If
the bucket doesn't exist, the default properties of the destination
cluster are used.

It's important to note that this goes for properties such as `backend`.
If the bucket doesn't exist in the destination cluster, Riak will create
it with the default backend and _not_ with the backend used in the
source cluster.



