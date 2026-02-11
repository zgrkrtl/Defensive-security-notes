1. ls
The ls command in Linux is used to list files and directories present in the current working directory.

Displays files and folders in a directory.
Helps users quickly understand directory contents.
Syntax:

->ls [options] [directory]

2. pwd
The pwd command in Linux is used to display the present working directory.

Shows the full path of the current directory.
Helps users know their current location.
Syntax:

->pwd

3. mkdir
The mkdir command in Linux is used to create new directories.

Creates new folders in the file system.
Helps organize files and directories.
Syntax:

->mkdir directory_name

4. cd
The cd command in Linux is used to change the current working directory.

Allows navigation between directories.
Moves the user to the home directory when used without arguments.
Syntax:

->cd directory_name

5. rmdir
The rmdir command in Linux is used to delete empty directories.

Removes directories that do not contain files.
Helps clean up unused folders.
Syntax:

->rmdir directory_name

6. cp
The cp command in Linux is used to copy files or directories.

Copies files from one location to another.
Useful for creating backups.
Syntax:

->cp source destination
Example:

->cp file1.txt file2.txt

7. mv
The mv command in Linux is used to move or rename files and directories.

Renames files easily.
Moves files between directories.
Syntax:

->mv old_name new_name

Example:

->mv old.txt new.txt

8. rm
The rm command in Linux is used to delete files permanently.

Removes unwanted files.
Frees disk space.
Syntax:

->rm file_name
Example:

->rm demo.txt
Output:

The rm command deletes the file demo.txt.
9. uname
The uname command in Linux is used to display system information.

Shows operating system details.
Helps identify the system.
Syntax:

->uname

Output:

Linux

The uname command displays the operating system name.
10. locate
The locate command in Linux is used to find files using a database.

Searches files quickly.
Faster than manual searching.
Syntax:

->locate file_name
Example:

->locate demo.txt
Output:
/dir1/dir2/dir3

The locate command shows the path of the searched file.
11. touch
The touch command in Linux is used to create empty files.

Creates new files instantly.
Updates file timestamps.
Syntax:

->touch file_name
Example:

->touch test.txt

The touch command creates an empty file named test.txt.
12. ln
The ln command in Linux is used to create links between files.

Creates shortcuts to files.
Supports hard and soft links.
Syntax:

ln -s source link_name
Example:

ln -s file1.txt link1.txt

ln
The ln command creates a symbolic link.
13. cat
The cat command in Linux is used to display file contents.

Reads file content.
Combines multiple files.
Syntax:

->cat file_name
Example:

->cat test.txt

The cat command displays the content of the file.
14. clear
The clear command in Linux is used to clear the terminal screen.

Removes previous outputs.
Keeps the terminal clean.
Syntax:

->clear
Example:

The terminal screen is cleared.
15. ps
The ps command in Linux is used to display running processes.

Shows active processes.
Helps monitor system activity.
Syntax:

->ps

16. man
The man command in Linux is used to display command manuals.

Provides command documentation.
Explains options and usage.
Syntax:

->man command_name

Example:

->man ls

The manual page of the command is displayed.
17. grep
The grep command in Linux is used to search text patterns.

Finds specific strings.
Filters output.
Syntax:

->grep "text" file_name
Example:

->grep "Python" notes.txt
Output:

The grep command displays matching lines.
18. echo
The echo command in Linux is used to display text in the terminal.

Prints messages.
Writes text into files.
Syntax:

->echo "text"
Example:

->echo "Hello Linux"

19. wget
The wget command in Linux is used to download files from the internet.

Downloads files via URL.
Works in the background.
Syntax:

->wget url
Example:

->wget http://example.com/file.zip%3C/span>

The file is downloaded successfully.
20. whoami
The whoami command in Linux is used to display the current user.

Shows logged-in username.
Useful in multi-user systems.
Syntax:

->whoami
Example:

->whoami

The current username is displayed.
21. sort
The sort command in Linux is used to sort file contents.

Sorts data alphabetically.
Supports numeric sorting.
Syntax:

->sort file_name
Example:

->sort test.txt

The file content is displayed in sorted order.
22. cal
The cal command in Linux is used to display the calendar.

Shows month calendar.
Useful for date reference.
Syntax:

->cal
Example:

->cal
Output:


23. whereis
The whereis command in Linux is used to locate command files.

Shows binary location.
Finds command paths.
Syntax:

->whereis command_name
Example:

->whereis ls

The location of the command is displayed.
24. df
The df command in Linux is used to display disk space usage.

Shows file system usage.
Helps monitor storage.
Syntax:

->df [options]
Example:

->df -h

Disk usage details are displayed.
25. wc
The wc command in Linux is used to count words, lines, and characters.

Counts file statistics.
Useful for text analysis.
Syntax:

->wc option file_name
Example:

->wc -w test.txt

The number of words in the file is displayed.