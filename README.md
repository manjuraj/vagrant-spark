## vagrant-spark

Launch a vagrant VM with pre-installed Apache Spark by running the
command `vagrant up`

## Prerequisite

- ansible >= 2.2.0.0
- virtualbox >= 5.1.8
- vagrant >= 1.8.6

### Up and Running

```sh
# add minimal ubuntu/trusty64 image from public catalog (first time only)
vagrant box add ubuntu/trusty64

# bring up vagrant cluster
vagrant up

# bring up vagrant cluster without provisioning
vagrant up --no-provision

# provision vagrant cluster (aka run ansible)
vagrant provision

# start spark cluster (requires user password for 'vagrant', which defaults
# to 'vagrant')

$HOME/spark/sbin/start-all.sh

# spark web UI

http://192.168.10.10:8081/

# spark REPL

$HOME/spark/bin/spark-shell

```
