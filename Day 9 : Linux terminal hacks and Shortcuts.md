🐧 Day 9 — Linux Terminal Hacks & Shortcuts

Today is Day 9 of my Linux learning journey.

Today I learned some useful Linux terminal hacks, shortcuts, directory navigation tricks, aliases, and command-history shortcuts that can make working in the terminal much faster.

📁 1. "cd" Directory Navigation Hacks

When working inside a long directory path, these shortcuts can help us move around quickly.

Go up two directories

cd ../..

Example:

/home/user/projects/linux/day9

Running:

cd ../..

moves up two levels.

Go up three directories

cd ../../..

This moves up three directory levels.

Go to the previous directory

cd -

This takes you back to the previous working directory.

For example:

cd /home/user/Documents
cd /var/log
cd -

The last command takes you back to:

/home/user/Documents

"$OLDPWD"

The environment variable "$OLDPWD" contains the previous working directory.

echo $OLDPWD

"$PWD"

The "$PWD" environment variable shows the current working directory.

echo $PWD

You can also simply use:

pwd

to display your current directory.

⚡ 2. Quick "ls" Hacks

Long listing

ls -l

Shows detailed information about files and directories, such as:

- Permissions
- Owner
- Group
- File size
- Modification time
- File name

Show hidden files

ls -al

This combines:

-a → show hidden files
-l → long listing format

So:

ls -al

shows detailed information including hidden files.

"ll"

On many Linux distributions, you can use:

ll

as a shortcut for a long listing such as:

ls -l

However, "ll" is usually an alias, not a universal Linux command. Its exact definition can vary between systems.

You can check it with:

alias ll

🏷️ 3. Create Your Own Commands with Aliases

An alias allows us to create a shortcut for a longer command.

For example:

alias la="ls -al"

Now instead of typing:

ls -al

we can simply type:

la

To see the aliases currently defined in your shell:

alias

To check a specific alias:

alias la

Make an Alias Permanent

Normally, an alias created with:

alias la="ls -al"

only lasts for the current shell session.

To make it available in future Bash sessions, add the alias to:

nano ~/.bashrc

Add:

alias la="ls -al"

Then reload the ".bashrc" file:

source ~/.bashrc

Now the alias will be available in new Bash sessions.

«💡 Note: The correct file is "~/.bashrc", not "nano .bashrc".»

⌨️ 4. Useful Keyboard Shortcuts

Linux terminal keyboard shortcuts can make command-line work much faster.

"Ctrl + A"

Moves the cursor to the beginning of the current command line.

Ctrl + A → Beginning

"Ctrl + E"

Moves the cursor to the end of the current command line.

Ctrl + E → End

"Ctrl + U"

Deletes everything from the cursor back to the beginning of the line.

Ctrl + U → Delete before cursor

"Ctrl + Y"

Pastes/yanks back text that was removed using shortcuts such as "Ctrl + U", "Ctrl + K", etc.

Ctrl + Y → Paste previously killed text

"Ctrl + K"

Deletes everything from the cursor to the end of the command line.

Ctrl + K → Delete after cursor

"Ctrl + X", then "Ctrl + E"

This opens the current command in your configured text editor so you can edit a long or complex command more easily.

Ctrl + X → Ctrl + E

After editing, save/exit the editor and the command can be returned to the shell for execution.

🔎 5. Search Command History with "Ctrl + R"

Instead of manually searching through previous commands, we can use:

Ctrl + R

This starts a reverse incremental search through the shell history.

For example, press:

Ctrl + R

Then type:

docker

The terminal searches previous commands containing "docker".

Press "Ctrl + R" again to search further backward through matching commands.

When you find the command you want, you can press:

Enter

to execute it, or use the arrow keys to edit it before running it.

🧠 Important Commands & Shortcuts Learned

Command / Shortcut| Purpose
"cd ../.."| Go up two directories
"cd ../../.."| Go up three directories
"cd -"| Return to the previous directory
"echo $OLDPWD"| Show the previous working directory
"echo $PWD"| Show the current working directory
"pwd"| Show the current working directory
"ls -l"| Long listing of files
"ls -al"| Long listing including hidden files
"ll"| Common alias for "ls -l"
"alias"| Display aliases
"alias la="ls -al""| Create a command shortcut
"nano ~/.bashrc"| Edit Bash configuration
"source ~/.bashrc"| Reload Bash configuration
"Ctrl + A"| Move to beginning of command
"Ctrl + E"| Move to end of command
"Ctrl + U"| Delete from cursor to beginning
"Ctrl + Y"| Paste previously deleted text
"Ctrl + K"| Delete from cursor to end
"Ctrl + X", "Ctrl + E"| Edit current command in an editor
"Ctrl + R"| Reverse-search command history

⭐ Quick Memory Trick

DIRECTORY
cd ../..       → Go up 2 levels
cd ../../..    → Go up 3 levels
cd -           → Previous directory
$PWD           → Current directory
$OLDPWD        → Previous directory

LISTING
ls -l          → Detailed listing
ls -al         → Detailed + hidden files
ll             → Common shortcut for ls -l

ALIASES
alias la="ls -al" → Create shortcut
~/.bashrc         → Make alias persistent
source ~/.bashrc  → Reload configuration

KEYBOARD
Ctrl + A       → Beginning
Ctrl + E       → End
Ctrl + U       → Delete before cursor
Ctrl + Y       → Paste killed text
Ctrl + K       → Delete after cursor
Ctrl + X, Ctrl + E → Edit command
Ctrl + R       → Search command history

🎓 Day 9 Summary

Today I learned several Linux terminal hacks and shortcuts that can make command-line work faster and more efficient.

I learned how to quickly navigate directories using "cd ../..", "cd ../../..", and "cd -"; check directories using "$PWD" and "$OLDPWD"; use "ls" shortcuts; create custom commands with aliases; make aliases permanent using "~/.bashrc"; and use powerful keyboard shortcuts such as "Ctrl + A", "Ctrl + E", "Ctrl + U", "Ctrl + K", and "Ctrl + R".

These shortcuts will help me become faster and more comfortable with the Linux terminal as I continue learning.
