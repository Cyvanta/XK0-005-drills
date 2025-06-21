# 🧠 Day 5 – Bash Scripting (Linux+ XK0-005)

---

## 🔍 What is Bash Scripting?

Bash scripting is when you write a list of terminal commands into a file (usually ending with `.sh`) and run them as a script — instead of typing each command one by one. It makes tasks faster and repeatable.

---

## 🧾 Basic Structure

Every bash script should start with this:

```bash
#!/bin/bash


🧪 Creating a Bash Script (Step by Step)

# Step 1: Create the file
touch script.sh

# Step 2: Open the file to edit
nano script.sh

# Step 3: Add this inside
#!/bin/bash
echo "Hello from Cyvanta script"

# Step 4: Save and exit nano (Ctrl + O, Enter, Ctrl + X)

# Step 5: Make it executable
chmod +x script.sh

# Step 6: Run it
./script.sh

📦 Bash Variables

#!/bin/bash
name="Richie"
echo "My name is $name"
Use variable to store value you want use later

✅ Conditions (if statements)

#!/bin/bash
if [ "$USER" = "root" ]; then
  echo "You're root"
else
  echo "You're not root"
fi

🔁 Loops

For Loop:

#!/bin/bash
for i in 1 2 3
do
  echo "Loop number $i"
done

While loop 

#!/bin/bash
count=1
while [ $count -le 3 ]
do
  echo "Count is $count"
  ((count++))
done


🧑‍💻 User Input

#!/bin/bash
echo "What’s your name?"
read name
echo "Nice to meet you, $name"

This script asks for input from the user and responds.

💬 Script with Arguments

#!/bin/bash
echo "The first argument is $1"

Run it like this:

./script.sh Cyvanta

It will print: The first argument is Cyvanta


🔐 Simple Backup Script (Real Use)

#!/bin/bash

echo "Starting backup..."

# Create tar archive of a folder
tar -czvf backup.tar.gz /home/kali/Documents

echo "Backup completed."

🧠 Note: Change the path to any folder you want to back up.


🔧 Practice Task

Create a script called cyvanta_backup.sh with the following features:
    •    Print current date
    •    Check if user is root
    •    Back up a folder

Here’s the full script:

#!/bin/bash

echo "Today's date: $(date)"

if [ "$EUID" -ne 0 ]; then
  echo "Please run as root."
  exit 1
fi

tar -czvf /tmp/cyvanta_backup.tar.gz /home/kali/Documents
echo "Backup saved in /tmp"

🧠 Summary Table

Concept
Example
Shebang
#!/bin/bash
Variable
name="Richie"
If condition
if [ "$USER" = "root" ]; then ...
Loop
for i in 1 2 3; do ... done
Input
read name
Argument
$1, $2, etc
Make executable
chmod +x script.sh
Run script
./script.sh
