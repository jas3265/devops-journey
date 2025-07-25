---

# 🐛 Export Bug Report – Day 2 DevOps Drills

## ❌ Buggy Script: `broken-export.sh`

```bash
#!/bin/bash
export STAGE : testing
echo "STAGE: $STAGE"

🧪 Error Output

./broken-export.sh: line 2: export: ` : ': not a valid identifier
./broken-export.sh: line 2: export: `testing': not a valid identifier

🕵️ Root Cause

The script uses incorrect syntax when exporting an environment variable.

❗ Problem

export STAGE : testing

This line is invalid because:

export expects the format VARIABLE=VALUE

The use of a colon (:) instead of an equals sign (=) causes Bash to interpret this as three separate arguments:

STAGE

:

testing


: and testing are not valid variable names, so Bash throws errors.


✅ Fixed Script

#!/bin/bash
export STAGE=testing
echo "STAGE: $STAGE"

✅ Output After Fix

STAGE: testing

💡 Lesson

When exporting environment variables in Bash, always use the correct assignment syntax:

export VARIABLE=VALUE

Any other format will result in errors due to invalid identifiers.


---
