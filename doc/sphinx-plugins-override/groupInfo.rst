Usage examples
==============

Show info about a specific group::

    --osh groupInfo --group mygroup2

Gather info about all groups, with no extra data except their keys::

    --osh groupInfo --all --without-everything --with-keys --json

Gather info about all groups, including all extra data (and possibly future options)::

    --osh groupInfo --all --with-everything --json

Output example
==============

::

  | Group mygroup's Owners are: user1
  | Group mygroup's GateKeepers (managing the members/guests list) are: user2
  | Group mygroup's ACLKeepers (managing the group servers list) are: user3
  | Group mygroup's Members (with access to ALL the group servers) are: user4
  | Group mygroup's Guests (with access to SOME of the group servers) are: user5
  |
  | The public key of this group is:
  |
  | fingerprint: SHA256:r/PQS4wLdSWqjYsDca8ReKjhq0l9EX+zQgiUR5qKdlc (ED25519-256) [2018/04/16]
  | keyline follows, please copy the *whole* line:
  from="203.0.113.4/32,192.0.2.0/26" ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAILdD60bA3NgaOpRLgcACWfKcAMRQQRyFMppwp5GpHLTB mygroup@testbastion:1523886640

The first paragraph of the output lists the different roles along with the people having these roles.

You can also see the public egress key of this group, i.e. the key that needs to be added to the remote servers' ``authorized_keys`` files, so that ``members`` of this group can access these servers.

Note that if you want to see the list of servers pertaining to this group, you can use the command ``groupListServers``.
