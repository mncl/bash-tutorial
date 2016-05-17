# Common Tasks

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

# Remove top








