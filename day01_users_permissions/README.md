# Day 1 – Users, Groups, and File Permissions (XK0-005)

## 🧠 Core Concepts

| Term         | Description |
|--------------|-------------|
| User         | Individual account on system |
| Group        | Collection of users with shared permissions |
| File Owner   | Creator of the file |
| Permissions  | Control who can read/write/execute files |

---

## 🔧 Key Commands

| Command                        | Description |
|--------------------------------|-------------|
| `useradd <name>`              | Add a new user |
| `passwd <name>`               | Set user password |
| `groupadd <name>`             | Create new group |
| `usermod -aG <group> <user>`  | Add user to a group |
| `chown user:group file`       | Change ownership of file |
| `chmod 755 file`              | Change file permissions |
| `ls -l`                       | View file permission string |
| `id <user>`                   | Show UID, GID, group info |
| `groups <user>`               | List group memberships |

---

## 🧪 Permission Mode Breakdown

| Mode | Symbol | Meaning |
|------|--------|---------|
| 7    | rwx    | Full access |
| 6    | rw-    | Read/write |
| 5    | r-x    | Read/execute |
| 4    | r--    | Read only |
| 0    | ---    | No access |

---

## 🔨 Practice Lab

```bash
# Create user and group
sudo useradd richie
sudo groupadd devs
sudo usermod -aG devs richie

# Create file and assign permissions
touch /tmp/secure.txt
sudo chown richie:devs /tmp/secure.txt
sudo chmod 770 /tmp/secure.txt

# View permission details
ls -l /tmp/secure.txt

