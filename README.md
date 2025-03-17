# Reporipper
# **GitHub Repository Deletion Script**

This Bash script automates the deletion of all repositories in a GitHub account using the GitHub API.

## **Prerequisites**
- **GitHub Personal Access Token (PAT)** with `repo` and `delete_repo` permissions.  
- `curl` and `jq` installed on your system.

### **Installation**
Install dependencies if they are not already installed:

```bash
sudo apt install curl jq -y    # Ubuntu/Debian  
brew install curl jq           # macOS  
Usage
1️⃣ Generate a GitHub PAT
Go to GitHub Token Settings
Generate a Personal Access Token (PAT) with repo and delete_repo permissions.
2️⃣ Create the Script
Create a file and paste the following script:

bash
Copy
Edit
#!/bin/bash

TOKEN="your_github_personal_access_token"
USERNAME="your_github_username"

# Fetch repositories (handles pagination)
PAGE=1
REPOS=()
while :; do
  RESPONSE=$(curl -s -H "Authorization: token $TOKEN" \
    "https://api.github.com/user/repos?per_page=100&page=$PAGE")

  [[ $(echo "$RESPONSE" | jq length) -eq 0 ]] && break
  REPOS+=($(echo "$RESPONSE" | jq -r '.[].name'))
  ((PAGE++))
done

# Confirmation prompt
echo "Delete ${#REPOS[@]} repositories? (yes/no)"
read CONFIRM
[[ "$CONFIRM" != "yes" ]] && exit 1

# Delete repositories
for REPO in "${REPOS[@]}"; do
  curl -X DELETE -H "Authorization: token $TOKEN" \
    "https://api.github.com/repos/$USERNAME/$REPO"
  echo "Deleted: $REPO"
done

echo "✅ Repositories deleted."
Save the file as delete_github_repos.sh.

3️⃣ Make the Script Executable
bash
Copy
Edit
chmod +x delete_github_repos.sh  
4️⃣ Run the Script
bash
Copy
Edit
./delete_github_repos.sh  
Adding the Script to GitHub via Git Bash
To add and push this script to GitHub, follow these steps:

bash
Copy
Edit
# Initialize Git (if not already initialized)
git init

# Add the script
git add delete_github_repos.sh

# Commit the changes
git commit -m "Add GitHub repository deletion script"

# Add a remote repository (replace with your details)
git remote add origin https://github.com/your-username/your-repo.git

# Push to GitHub
git push -u origin main
If your default branch is master, replace main with master.

Warnings
⚠ This action is irreversible—deleted repositories CANNOT be recovered.
⚠ Ensure you're using a PAT instead of a password.

License
MIT License.
