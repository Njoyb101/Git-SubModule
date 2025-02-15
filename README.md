## Git Submodule Workflow

### 1. Add a Submodule
```sh
git submodule add <repository-url> <path-to-submodule>
```
Example:
```sh
git submodule add https://github.com/example/repo.git submodule-folder
```

### 2. Clone a Repository with Submodules
```sh
git clone --recursive <repository-url>
```
If already cloned without `--recursive`, initialize submodules:
```sh
git submodule update --init --recursive
```
#### Pull the root repo with submodule
```bash
git pull --recursive-submodules
```

#### Update Git Config to pull submodules always
```bash
git config submodule.recurse true
```

### 3. Pull Latest Changes in Submodules
```sh
cd submodule-folder
git pull origin main
```
Or update all submodules:
```sh
git submodule update --remote --merge
```

### 4. Commit Submodule Changes
```sh
git add submodule-folder
git commit -m "Updated submodule to latest commit"
git push origin main
```

### 5. Remove a Submodule
```sh
git submodule deinit -f -- submodule-folder
rm -rf .git/modules/submodule-folder
rm -rf submodule-folder
```
Commit and push the changes:
```sh
git add .
git commit -m "Removed submodule"
git push origin main
```

### 6. Check Submodule Status
```sh
git submodule status
```

### 7. Update Submodule URL
```sh
git config --file .gitmodules submodule.submodule-folder.url <new-repo-url>
git submodule sync
git submodule update --init --recursive
```

---
This workflow ensures smooth management of submodules in Git repositories.

