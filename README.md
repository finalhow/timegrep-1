# timegrep.py

by Dennis Williamson 20100113
in response to http://serverfault.com/questions/101744/fast-extraction-of-a-time-range-from-syslog-logfile
Improvements by Fabrice FACORAT 20110914

Perform a binary search through a log file to find a range of times
and print the corresponding lines
Supported Log Formats:
- W3C Extended: %Y-%m-%d %H:%M:%S
- Syslog: %b %d %H:%M:%S
- NSCA Common/Apache: host rfc931 username [%d/%b/%Y:%H:%M:%S +TZ]
- Bind8: %d-%b-%Y %H:%M:%S.
- Nginx Error logs: %Y/%m/%d %H:%M:%S.
Tested with Python 2.6

You can install it using :

    pip install timegrep

---
TODO: Make sure that it works if the seek falls in the middle of
      the first or last line

TODO: Make sure it's not blind to a line where the sync read falls
      exactly at the beginning of the line being searched for and
      then gets skipped by the second read

DONE: Support more log time format

TODO: Support case when log files may not be properly sorted ( remove superfluous lines )

DONE: Support on the fly log format definition with --log-regexp
