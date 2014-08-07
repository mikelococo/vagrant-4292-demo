vagrant-4292-demo
=================

A repo to demo https://github.com/mitchellh/vagrant/issues/4292

Usage
=====

```
bundle install
bundle exec kitchen list
bundle exec kitchen create
```

Expected output is that a box gets created. Actual output is the following stacktrace:

```
o$ bundle exec kitchen create                                                                                                                             [85/1050]
-----> Starting Kitchen (v1.2.1)
-----> Creating <default-ubuntu-1204>...
>>>>>> ------Exception-------
>>>>>> Class: Kitchen::ActionFailed
>>>>>> Message: Failed to complete #create action: [Expected process to exit with [0], but received '1'
---- Begin output of vagrant up --no-provision --provider=lxc ----
STDOUT: 
STDERR: /home/mike/.vagrant.d/gems/gems/json-1.8.1/lib/json/common.rb:155:in `encode': "\xC3" on US-ASCII (Encoding::InvalidByteSequenceError)
        from /home/mike/.vagrant.d/gems/gems/json-1.8.1/lib/json/common.rb:155:in `initialize'
        from /home/mike/.vagrant.d/gems/gems/json-1.8.1/lib/json/common.rb:155:in `new'
        from /home/mike/.vagrant.d/gems/gems/json-1.8.1/lib/json/common.rb:155:in `parse'
        from /opt/vagrant/embedded/gems/gems/vagrant-1.6.3/lib/vagrant/box.rb:68:in `initialize'
        from /opt/vagrant/embedded/gems/gems/vagrant-1.6.3/lib/vagrant/box_collection.rb:299:in `new'
        from /opt/vagrant/embedded/gems/gems/vagrant-1.6.3/lib/vagrant/box_collection.rb:299:in `block (3 levels) in find'
        from /opt/vagrant/embedded/gems/gems/vagrant-1.6.3/lib/vagrant/box_collection.rb:284:in `each'
        from /opt/vagrant/embedded/gems/gems/vagrant-1.6.3/lib/vagrant/box_collection.rb:284:in `block (2 levels) in find'
        from /opt/vagrant/embedded/gems/gems/vagrant-1.6.3/lib/vagrant/box_collection.rb:277:in `each'
        from /opt/vagrant/embedded/gems/gems/vagrant-1.6.3/lib/vagrant/box_collection.rb:277:in `block in find'
        from /opt/vagrant/embedded/gems/gems/vagrant-1.6.3/lib/vagrant/box_collection.rb:416:in `block in with_collection_lock'
        from /opt/vagrant/embedded/lib/ruby/2.0.0/monitor.rb:211:in `mon_synchronize'
        from /opt/vagrant/embedded/gems/gems/vagrant-1.6.3/lib/vagrant/box_collection.rb:415:in `with_collection_lock'
        from /opt/vagrant/embedded/gems/gems/vagrant-1.6.3/lib/vagrant/box_collection.rb:263:in `find'
        from /opt/vagrant/embedded/gems/gems/vagrant-1.6.3/lib/vagrant/vagrantfile.rb:157:in `block in machine_config'
        from /opt/vagrant/embedded/gems/gems/vagrant-1.6.3/lib/vagrant/vagrantfile.rb:190:in `call'
        from /opt/vagrant/embedded/gems/gems/vagrant-1.6.3/lib/vagrant/vagrantfile.rb:190:in `machine_config'
        from /opt/vagrant/embedded/gems/gems/vagrant-1.6.3/lib/vagrant/vagrantfile.rb:45:in `machine'
        from /opt/vagrant/embedded/gems/gems/vagrant-1.6.3/lib/vagrant/environment.rb:497:in `machine'
        from /opt/vagrant/embedded/gems/gems/vagrant-1.6.3/lib/vagrant/plugin/v2/command.rb:168:in `block in with_target_vms'
        from /opt/vagrant/embedded/gems/gems/vagrant-1.6.3/lib/vagrant/plugin/v2/command.rb:192:in `call'
        from /opt/vagrant/embedded/gems/gems/vagrant-1.6.3/lib/vagrant/plugin/v2/command.rb:192:in `block in with_target_vms'
        from /opt/vagrant/embedded/gems/gems/vagrant-1.6.3/lib/vagrant/plugin/v2/command.rb:174:in `each'
        from /opt/vagrant/embedded/gems/gems/vagrant-1.6.3/lib/vagrant/plugin/v2/command.rb:174:in `with_target_vms'
        from /opt/vagrant/embedded/gems/gems/vagrant-1.6.3/plugins/commands/up/command.rb:67:in `block in execute'
        from /opt/vagrant/embedded/gems/gems/vagrant-1.6.3/lib/vagrant/environment.rb:238:in `block (2 levels) in batch'
        from /opt/vagrant/embedded/gems/gems/vagrant-1.6.3/lib/vagrant/environment.rb:236:in `tap'
        from /opt/vagrant/embedded/gems/gems/vagrant-1.6.3/lib/vagrant/environment.rb:236:in `block in batch'
        from /opt/vagrant/embedded/gems/gems/vagrant-1.6.3/lib/vagrant/environment.rb:235:in `synchronize'
        from /opt/vagrant/embedded/gems/gems/vagrant-1.6.3/lib/vagrant/environment.rb:235:in `batch'
        from /opt/vagrant/embedded/gems/gems/vagrant-1.6.3/plugins/commands/up/command.rb:58:in `execute'
        from /opt/vagrant/embedded/gems/gems/vagrant-1.6.3/lib/vagrant/cli.rb:42:in `execute'
        from /opt/vagrant/embedded/gems/gems/vagrant-1.6.3/lib/vagrant/environment.rb:252:in `cli'
        from /opt/vagrant/bin/../embedded/gems/gems/vagrant-1.6.3/bin/vagrant:166:in `<main>'
---- End output of vagrant up --no-provision --provider=lxc ----
Ran vagrant up --no-provision --provider=lxc returned 1]
>>>>>> ----------------------
>>>>>> Please see .kitchen/logs/kitchen.log for more details
>>>>>> Also try running `kitchen diagnose --all` for configuration
