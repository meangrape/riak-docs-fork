---
title: "Installing on Debian and Ubuntu"
description: "Installing on Debian and Ubuntu"
menu:
  riak_ts-1.5.2:
    name: "Debian and Ubuntu"
    identifier: "installing_on_debian_ubuntu"
    weight: 201
    parent: "installing"
project: "riak_ts"
project_version: "1.5.2"
toc: true
version_history:
  locations:
    - ["1.0.0-1.3.1", "installing/debian-ubuntu"]
    - ["1.4.0+",      "setup/installing/debian-ubuntu"]
aliases:
  - /riakts/1.5.2/installing/debian-ubuntu/
  - /riakts/1.5.2/setup/installing/debian-ubuntu/
  - /riak/ts/1.5.2/installing/debian-ubuntu/
  - /riak/ts/latest/setup/installing/debian-ubuntu/
  - /riak/ts/latest/installing/debian-ubuntu/
---

[download]: {{<baseurl>}}riak/ts/1.5.2/downloads/
[openfileslimit]: {{<baseurl>}}riak/kv/2.2.0/using/performance/open-files-limit
[planning]: {{<baseurl>}}riak/ts/1.5.2/using/planning
[security basics pam]: {{<baseurl>}}riak/ts/1.5.2/using/security/sources-management/#pam-based-authentication


Riak TS can be installed on Debian or Ubuntu-based systems using a binary
package available [here][download].

{{% note %}}
Debian is only supported for developing with Riak TS and NOT for general operations.
{{% /note %}}


## Dependencies

### `ulimit`

Debian and Ubuntu give you a very small limit on open file handles. Even with a
backend that uses very few file handles, it's possible to run out. See
[Open Files Limit][openfileslimit] for more information about changing the limit.


### PAM Library Requirement for Ubuntu

You must have the `libpam0g-dev` package used for [Pluggable Authentication Module (PAM)][security basics pam] authentication in order to install Riak TS.

To install this dependency:

```bash
sudo apt-get install libpam0g-dev
```


## Install Riak TS

Once you have [downloaded][download] the package, execute the following command to install Riak TS:

```bash
sudo dpkg -i riak-ts_1.5.2-1_amd64.deb
```


## Verify your installation

You can verify that Riak TS is successfully installed by running: 

```bash
dpkg -l | grep riak
```

If Riak TS has been installed successfully `riak-ts` is returned.


## Start your Riak TS node

Once you've installed Riak TS, start it on your node:

```bash
riak start
```

## Verify Riak TS is running

You can verify that Riak TS is started and ready to use by pinging it.

```bash
riak ping
```

If Riak TS has started, you will receive a `pong` response. If it has not started, you will receive an error. 


## Next Steps

Now that you've installed Riak TS, check out [Planning Your Riak TS Table][planning].
