🗓️ Day 1 Linux Terminal Drills
Date: July 23, 2025
Location: ~/devops-log/day1/drills-log.md
Author: Jasper
Objective: Build muscle memory for Linux CLI navigation and file management. Include real mistakes and how they were fixed.

✅ Drill 1: Basic Directory and File Creation
Command Used:

mkdir lab1 && touch lab1/file1.txt lab1/file2.txt
Outcome: ✅ Success
Lesson: Basic mkdir and touch chaining is intuitive. No errors.

✅ Drill 2: View and Navigate
Commands:

ls -l lab1
cd lab1
pwd
cd ..
Outcome: ✅ Success
Lesson: Used pwd to verify location. Learned the structure and behavior of relative paths.

✅ Drill 3: Rename and Move Files
Commands:

mv lab1/file1.txt lab1/renamed.txt
Outcome: ✅ Success
Lesson: Renamed file1.txt inside the same directory. Understood mv works both for moving and renaming.

✅ Drill 4: Directory Tree View
Command Attempted:

tree lab1
❌ Problem:
tree: command not found

🔧 Fix Option (not installed yet):

sudo apt install tree
Lesson: Realized tree is not installed by default. Added to future setup checklist.

✅ Drill 5: File Deletion
Commands:

rm lab1/file2.txt
Outcome: ✅ Success
Lesson: Simple file deletion with no issues. Confirmed with ls.

✅ Drill 6: Directory Deletion
Command Attempted:

rmdir lab1
❌ Problem:
Directory not empty — rmdir only works on empty directories.

🔧 Fix:

rm lab1/renamed.txt
rmdir lab1
Lesson: Understood the strict behavior of rmdir. Must clear contents manually unless using rm -r.

✅ Drill 7: Safe Recursive Delete
Command:

rm -r lab2
Outcome: ✅ Success
Lesson: Learned rm -r can delete entire directories with contents. Powerful — must use caution.

✅ Drill 8: Nested Directories + Files
Command:

mkdir -p lab3/lab4/lab5 && touch lab3/lab4/lab5/notes.txt
Outcome: ✅ Success
Lesson: Practiced creating deeply nested directory trees. Confirmed with ls -R.

✅ Drill 9: Simulate Failure Then Fix
Command Attempted:

mkdir lab6 && touch lab6/fail.txt
❌ Problem:
Touch failed due to nonexistent directory when mkdir failed.

Error:

touch: cannot touch 'lab6/fail.txt': No such file or directory

🔧 Fixed Command:

mkdir -p lab6 && touch lab6/fail.txt
Cleanup:

rm lab6/fail.txt
rmdir lab6
Lesson: Chains break if one part fails. Using -p ensures directory creation succeeds.

✅ Drill 10: Absolute Path Handling
Command:

mkdir -p ~/devops-log/day1/lab10 && touch ~/devops-log/day1/lab10/final.txt
Outcome: ✅ Success
Lesson: Mastered full path targeting using ~ and absolute structure.

🔁 Reflection
Mistakes were valuable — they clarified how Linux reacts to failures.
Used cat, ls -R, and rmdir to confirm results and trace state.
Learned importance of building commands with && only when the previous is guaranteed to succeed.
