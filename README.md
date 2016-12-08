# check_jenkins

# Overview
A bash shell script for use in nagios as a service check for 
Jenkins build queue health.  It is used in an environment
where Jenkins dynamically creates slave VMs to run jobs.

This rather custom service check reports on Jenkins queue
health based on these metrics:

* age of old job in queue (waiting to start)
* number of jobs in queue
* number of slaves currently running jobs

# Usage 

check_nagios -w WARNMINUTES -c CRITMINUTES -j JENKINSURL
             -m MAXMINIONS

Returns: OK, WARN, or CRITCAL with status, ie:
OK - Build queue is empty and 5 minions are active

# Dependencies

The script requires the python API to jenkins in the
python-jenkins package.
