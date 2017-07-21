Cinder Quota Sync
=================

What is it?
-----------
cinder-quota-sync is a simple script that compares for a Cinder database
the quota usage with the actual usage (on a per resource and project basis).

It also allows to synchronize quotas in case of mismatches.


How to use it?
--------------

python cinder-quota-sync --help

usage: cinder-quota-sync [-h] [--sync] [--nosync] [--config CONFIG] project_id

positional arguments:
  project_id       project to check

optional arguments:
  -h, --help       show this help message and exit
  --sync           always sync resources (no interactive check)
  --nosync         never sync resources (no interactive check)
  --config CONFIG  configuration file


Examples
--------

Check a project (with interactive check before syncing):
cinder-quota-sync ed189d6c-5356-4378-8e98-14b7f7153607

Check a project (don't sync, just display):
cinder-quota-sync --nosync ed189d6c-5356-4378-8e98-14b7f7153607

Check a project (sync, don't ask for confirmation):
cinder-quota-sync --sync ed189d6c-5356-4378-8e98-14b7f7153607


Nova versions supported
-----------------------

Tested with Ocata.


Bugs and Disclaimer
-------------------
Bugs? Oh, almost certainly.

This tool was written to be used in the CERN Cloud Infrastructure and
it has been tested only in our environment.

Since it updates the Cinder database: use with extreme caution.
