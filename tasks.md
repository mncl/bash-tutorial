# Common Tasks

Execute in bash-tutorial folder.

```bash
#/bin/bash

# files owned by by alice (dot is CWD)
find . -type f -user alice

# directories owned by by alice
find . -type d -user alice

# files and dirs but not .git folders
find /path/to/dir -type d -name '.git' -prune -o -print

# Renaming all .js files to .ts (uses bash suffix removal)
find . -name '*.js' | while read f; do mv -v $f ${f%.js}.ts; done

# Pretty print xml files with xml lint
find . -name "*.xml" -type f -exec xmllint --output '{}.pretty' --format '{}' \;

# Remove all pretty printed files
find . -name "*.xml.pretty" -type f |xargs rm

# Show first 10 lines of file
head -10 ssl-access.log

# Show last 10 lines of file
tail -10 ssl-access.log

# Show last few lines of log file (append to file from other terminal)
tail -f mylog.log

# Remove all but some files
ls |grep -v '^keep-this-file.txt$'|xargs rm

# HTTP 404 in apache access log
cat ssl-access.log | awk -F'[ "]+' '{print $9 " " $7}' | grep '^404'

# Number of request by HTTP status
cat ssl-access.log | awk -F'[ "]+' '{print "with status " $9}' | sort | uniq -c

# top 10 ips
cat ssl-access.log | awk -F'[ "]+' '{print $1}' |sort | uniq -c |sort -r | head -10















