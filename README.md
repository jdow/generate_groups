# generate_groups
A script to generate LDAP group memberships out of search filters or other groups

This script helps create LDAP groups, like all users with a certain t-shirt size or all users that
report to a certain manager. It can be used to make somewhat fake nested groups, i.e. a group that
contains all members of 2 or more other groups plus a few extra, or minus a few extra.

The word "nested_groups" in the configuration file means that all members of the nested groups
will be members of the target group, but actual nesting will not occur. The rest of the config
file should be pretty self-explanatory. Exceptions can go in either direction, either add a user that
doesn't match the criteria, or never add a user that does match the criteria.

The groups will be maintained by both adding and removing users every time the script runs. It is
recommended to run it from a cron job on a regular schedule to keep the groups current and valid.
