Cinder Quota Sync
=================

What is it?
-----------
cinder-quota-sync is a simple script that compares for a Cinder database
the quota usage with the actual usage (on a per resource and project basis).

It also allows to synchronize quotas in case of mismatches.


How to use it?
--------------

$ python cinder-quota-sync --help

usage: cinder-quota-sync [-h] [--config CONFIG] [--nosync] [--sync]
                         (--list_projects | --project_id PROJECT_ID)

optional arguments:

  -h, --help            show this help message and exit

  --config CONFIG       configuration file

  --nosync              never sync resources (no interactive check)

  --sync                always sync resources (no interactive check)

  --list_projects       get a list of all projects in the database

  --project_id PROJECT_ID
                        project to check


Examples
--------

Check a project (with interactive check before syncing):

$ python cinder-quota-sync --project_id ed189d6c-5356-4378-8e98-14b7f7153607

Check a project (don't sync, just display):

$ python cinder-quota-sync --nosync --project_id ed189d6c-5356-4378-8e98-14b7f7153607

Check a project (sync, don't ask for confirmation):

$ python cinder-quota-sync --sync --project_id ed189d6c-5356-4378-8e98-14b7f7153607

List all project which have entries in the Cinder database

$ python cinder-quota-sync --list_projects


Nova versions supported
-----------------------

Tested with Ocata.


Bugs and Disclaimer
-------------------
Bugs? Oh, almost certainly.

This tool was written to be used in the CERN Cloud Infrastructure and
it has been tested only in our environment.

Since it updates the Cinder database: use with extreme caution.
