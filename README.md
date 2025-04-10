
---

# Linux Commands Deep Dive

Now that you have a client terminal and have accessed your remote server, what’s next?  
For the next couple of projects, you will learn a lot about Linux commands. So it's time to get your hands dirty.

---

## 🧠 What is a Linux Command?

A **Linux command** refers to a program or utility that runs in the **command-line interface (CLI)** — a text-based environment where you interact with the system by typing commands.

Linux commands are executed by entering text in the **Terminal** and pressing **Enter**. These commands enable you to:

- Install packages
- Manage users
- Manipulate files and directories
- Configure system settings
- And much more

### 🔧 Syntax

```bash
CommandName [option(s)] [parameter(s)]
```

- **CommandName**: The action you want to perform.  
  Example: To list files, use `ls`

- **Option (or Flag)**: Modifies how the command behaves.  
  Example: `ls -l` (lists files in long format)

- **Parameter (or Argument)**: Provides data to the command.  
  Example: `mkdir photos` (creates a `photos` directory)

> ⚠️ Linux commands are **case-sensitive**, so be careful with your spelling and formatting.

---

## 📁 Manipulating Files and Directories

Working with files and directories is a major part of using Linux. Let’s explore essential commands for this.

---

## 🔐 The `sudo` Command

Some operations require special permissions. That’s where `sudo` comes in.  
**`sudo` = superuser do**

### ✅ Why use `sudo`?

- **Security**: Prevents unauthorized changes
- **Tracking**: Logs actions for accountability

### ⚙️ How `sudo` Works

When you run a command with `sudo`, it temporarily elevates your privileges after entering your password. This lasts about 15 minutes.

### 🛠 Creating a Folder with `sudo`

Let’s try creating a directory in `/root` (a restricted area):

```bash
mkdir /root/example
```

**Expected Output:**
```bash
mkdir: cannot create directory ‘/root/example’: Permission denied
```

Now try with `sudo`:

```bash
sudo mkdir /root/example
```

**To verify:**

```bash
sudo ls /root
```

> ⚠️ Be cautious with `sudo`. It gives access to modify important system files.

---

## 📍 The `pwd` Command

Use `pwd` to print your current working directory.

```bash
pwd
```

**Output Example:**
```
/home/username
```

---

## 🗂 The Linux Directory Structure

Linux organizes everything starting from the **root directory** `/`.

### Common Directories:

| Directory | Purpose |
|----------|---------|
| `/bin`   | Essential user commands |
| `/etc`   | System configuration files |
| `/home`  | User home directories |
| `/root`  | Root user's home |
| `/var`   | Variable files (e.g., logs) |
| `/usr`   | Secondary user data and applications |

Explore using:

```bash
ls /
```

---

## 📂 The `cd` Command

Navigate directories using `cd`.

To go to the root directory:

```bash
cd /
```

To confirm:

```bash
pwd
```

To list contents:

```bash
ls -l
```

To navigate into `/usr`:

```bash
cd /usr
```

---

## 💼 Side Hustle Task 1

1. Create a directory called `photos` inside `/usr`
```bash
sudo mkdir /usr/photos
```

2. Navigate into `photos`:
```bash
cd /usr/photos
```

3. Create 3 random directories:
```bash
mkdir dir1 dir2 dir3
```

4. Show the newly created directories:
```bash
ls
```

5. Navigate into one of them:
```bash
cd dir1
```

6. Show the full path:
```bash
pwd
```

---

## 📋 The `ls` Command

Lists contents of directories.

```bash
ls
```

To view contents of a specific directory:

```bash
ls /home/ubuntu/Documents
```

### Useful `ls` Options:

| Command | Description |
|---------|-------------|
| `ls -R` | Lists contents of all subdirectories |
| `ls -a` | Includes hidden files |
| `ls -lh` | Shows human-readable sizes (MB, GB) |

---

## 📄 The `cat` Command

Displays the content of a file.

```bash
sudo cat /etc/os-release
```

**Example Output:**
```
PRETTY_NAME="Debian GNU/Linux 11 (bullseye)"
VERSION_ID="11"
...
```

---

## 📋 The `cp` Command

Used to **copy** files and directories.

- Copy one file:
```bash
cp filename.txt /home/ubuntu/Documents
```

- Copy multiple files:
```bash
cp file1.txt file2.txt /home/ubuntu/Documents
```

- Copy and rename:
```bash
cp original.txt copy.txt
```

- Copy entire directory:
```bash
cp -R /source/folder /destination/folder
```

---

## 📦 The `mv` Command

Used to **move or rename** files and directories.

- Move a file:
```bash
mv file.txt /home/ubuntu/Documents
```

- Rename a file:
```bash
mv old.txt new.txt
```

---

## 🗑 The `rm` Command

Used to **remove** files.

> ⚠️ Caution: `rm` permanently deletes files without placing them in trash.

- Remove a single file:
```bash
rm file.txt
```

---
