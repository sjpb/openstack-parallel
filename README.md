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

After activating venv use it in place of `openstack`, but pass a string to find in the object name instead of an actual object name as the last argument, e.g.:
```
./openstack-parallel server delete ci3006665556
```

Will find all servers with names containing `ci3006665556`, display their names and prompt before deleting them.

Note the pattern to match is just a substring, not a regular expression.
