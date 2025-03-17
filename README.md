# **GitHub Repository Deletion Script**

This Bash script automates the deletion of all repositories in a GitHub account using the GitHub API.

## **Prerequisites**
- **GitHub Personal Access Token (PAT)** with `repo` and `delete_repo` permissions.  
- `curl` and `jq` installed on your system.

### **Installation**
Install dependencies if they are not already installed:
sudo apt install curl jq -y    # Ubuntu/Debian  
brew install curl jq           # macOS  
**Usage****
**Clone the Repositor**

git clone https://github.com/your-username/repo-name.git  
cd repo-name
**Generate a GitHub PAT**
Go to GitHub Token Settings
Generate a Personal Access Token (PAT) with repo and delete_repo permissions.
** Configure and Run the Script**
**Edit the script to add your credentials:**
nano delete_github_repos.sh
Replace the placeholders:

TOKEN="your_github_personal_access_token"
USERNAME="your_github_username"
**Make the script executable:**

chmod +x delete_github_repos.sh  
**Run the script:**

./delete_github_repos.sh  
**Warnings**
⚠ This action is irreversible—deleted repositories CANNOT be recovered.
⚠ Ensure you're using a PAT instead of a password.

**License**
MIT License.
