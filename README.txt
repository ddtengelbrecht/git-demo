# Demo Git Repository

This is the first file in this repo.

## Ipsum Below
If dev is still in a broken state (can't activate the DB), can you please send me the db cfg output along with the SQLOGCTL.LFH/GLFH files from one of the databases?  You can determine which SQL0000X directory to collect them from by running
'db2 list db directory on <path>'
where <path> is the path from the 'db2 list db directory" command. 

A couple more things.   I am beginning to think that the OFF may be part of the issue here.  The LOGARCHMETHx path is stored in two places (the  dbcfg and the GLFH file) and I suspect it's not getting changed in both places.  Which is why I want to collect the db dfg output and the LFH/GLFH files to review after you run the "update db cfg using LOGARCHMETH2 OFF IMMEDIATE" and it subsequently fails to work.  

I believe that if instead of OFF you change it to "DISK:<some local path>  IMMEDIATE" that it may actually work.  Changing LOGARCHMETHx to OFF could change the logging method if it's the only one set (from archival to circular logging), so I think it's interfering with the OFF change working as desired.