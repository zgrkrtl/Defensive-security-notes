# Log Analysis with CLI

Search for failed SSH attempts
grep "Failed password" /var/log/auth.log

Case-insensitive search
grep -i "error" /var/log/app.log

Search recursively
grep -r "admin" /var/log/

Count IP occurrences in access log
awk '{print $1}' access.log | sort | uniq -c | sort -nr

Show logs for SSH service
journalctl -u ssh

Show logs from last hour
journalctl --since "1 hour ago"

Follow live logs
journalctl -f
