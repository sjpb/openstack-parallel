Wrapper for the OpenStack CLI to operate on multiple objects

# Install

Assuming RockyLinux 8.x:
```
git clone https://github.com/sjpb/openstack-parallel.git
cd openstack-parallel
sudo yum install -y python38
python3.8 -m venv venv
. venv/bin/activate
pip install -U pip
pip install python-openstackclient
```

# Usage

After activating venv use it in place of `openstack`, but pass:
- a comma-separated list of objects to operate on as the 2nd argument
- a Python regex for the object name(s) as the last argument

e.g.:
```
./openstack-parallel server,port delete ^ci
```

Will find all servers and ports with names starting with `ci`, display their names and prompt before deleting them.
