# Common Tasks

```bash
#/bin/bash

# files owned by by alice
find /path/to/dir -type f -user alice

# directories owned by by alice
find /path/to/dir -type d -user alice

# files and dirs but not .git folders
find /path/to/dir -type d -name '.git' -prune -o -print

# Renaming all .js files to .ts (uses bash suffix removal)
find . -name '*.js' | while read f; do mv -v $f ${f%.js}.ts; done



