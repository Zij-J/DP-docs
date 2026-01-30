# Git Cheatsheet

### Untrack tracked files
1. add them to `.gitignore`
2. remove them from Git's index
    ```bash
    git rm --cached <file-name>
    # or for a directory
    git rm -r --cached <directory-name>
    ```
3. stage and commit them all, done!
