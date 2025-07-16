# git-find-commit.sh

Recursively searches all Git repositories inside a specified path for those that contain a commit with a specific message.

## **What is it for?**

This script is useful when you have **many Git repositories** scattered across your system and need to quickly find in which one(s) there's a commit with a certain message (e.g., to locate a specific change or an old project).

## **How to use it**

### **Basic syntax**

```bash
./git-find-commit.sh "commit message" [search_directory]
```

- **"commit message"**: The exact message (or part of it) you want to search for in the commits.
- **[search_directory]**: (Optional) The path where the search should begin. If not specified, the current directory (`.`) will be used.

### **Examples**

- Search in the current directory:
  ```bash
  ./git-find-commit.sh "v.0 Exploring Ebay"
  ```
- Search in a specific path:
  ```bash
  ./git-find-commit.sh "fix login bug" /home/user/projects
  ```

## **How it works**

1. **Recursively searches** for all `.git` directories within the specified path.
2. For each found repository, it **checks** whether at least one commit exists whose message matches the provided text.
3. **Displays the path** of each repository where the commit was found.

## **Requirements**

- **Bash** (most modern Linux/macOS systems include it).
- **Git** installed and accessible from the command line.
- **Read permissions** on the directories being inspected.

## **Customization**

You can modify the script to, for example, show additional commit information (hash, date, etc.), or to allow partial matches (using `--grep` without quotes).

## **Notes**

- **Case-sensitive**: The search distinguishes between uppercase and lowercase letters.
- **Performance**: On systems with many large repositories, the search may take several seconds or even minutes.
- **Safety**: The script only reads Git data — it does not modify any repository.

**Any issues or suggestions?**  
Feel free to open an issue or contribute to the project!

---