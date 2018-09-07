cd /home/build/workspace/workshop/demo
git clone https://github.com/etcd-io/etcd.git
cd etcd/
git status
git branch -a
git checkout release-3.2
git status
make build
./bin/etcd &
# 2nd Terminal:
export ETCDCTL_API=3
./bin/etcdctl --write-out=table --endpoints=localhost:2379 member list
./bin/etcdctl --write-out="json" --endpoints=localhost:2379 member list
./bin/etcdctl put foo 42
./bin/etcdctl put bar 11
./bin/etcdctl get foo
./bin/etcdctl get bar

