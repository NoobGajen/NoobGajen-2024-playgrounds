# 2024-Playground Project

## 2024-Playground Project

Welcome to the `2024-Playground` repository! This document will guide you through the setup process and understanding the contribution guidelines which is essential for participating in this project.

### Steps for Contributing

* Setting Up SSH Keys
  * Generating a New SSH Key
  * Adding Your SSH Key to the ssh-agent
  * Adding the SSH Key to Your GitHub Account
* Setting Up Your Own Copy of the Repository (Forked Repository)
* Organizing Your Work
* Adding Changes
* Making a Pull Request
* Pushing Additional Changes
* Making a Pull Request

#### Setting Up SSH Keys

Setting up SSH keys allows you to securely connect to GitHub without needing to enter your username and password every time you interact with your repository from the command line.

**Generating a New SSH Key**

1.  Open a terminal and paste the following command with your email address:

    ```bash
    ssh-keygen -t rsa -b 4096 -C "sudogajendra@gmail.com"
    ```

    This creates a new SSH key, using the provided email as a label.
2.  When prompted to "Enter a file in which to save the key," press Enter. This accepts the default file location.

    ```bash
    > Enter file in which to save the key (/home/gajen/.ssh/id_rsa): [Press enter]
    ```

    That's it! Now your system has its own SSH keys ready to go.

<figure><img src=".gitbook/assets/Generating a New SSH Key 0.png" alt=""><figcaption></figcaption></figure>

**Adding Your SSH Key to the ssh-agent**

1.  Start the ssh-agent in the background.

    ```bash
    eval "$(ssh-agent -s)"
    ```
2.  Add your SSH private key to the ssh-agent.

    ```bash
    ssh-add ~/.ssh/id_rsa
    ```

**Adding the SSH Key to Your GitHub Account**

1.  Copy the SSH key to your clipboard.

    ```bash
    sudo apt-get install xclip
    xclip -sel clip < ~/.ssh/id_rsa.pub
    ```

    Or, if `xclip` is not available:

    ```bash
    cat ~/.ssh/id_rsa.pub
    ```

    And then manually copy the output.
2.  In the upper-right corner of any page, click your **profile photo**, 

    <figure><img src=".gitbook/assets/Adding the SSH Key to Your GitHub Account 1.png" alt=""><figcaption></figcaption></figure>
3. In the user settings sidebar, click **SSH and GPG keys**.
4. Click **New SSH key** or **Add SSH key**.
5. In the "Title" field, add a descriptive label for the new key. For example, if you're using a personal Mac, you might call this key "Personal MacBook Air".
6. Paste your key into the "Key" field.
7. Click **Add SSH key**.
8. If prompted, confirm your GitHub password.

For detailed instructions, refer to the [GitHub documentation](https://docs.github.com/en/authentication/connecting-to-github-with-ssh).

#### Setting Up Your Own Copy of the Repository

1. **Fork the repo on GitHub to your personal account.** Click the `Fork` button on the `gajabaar/2024-playground` Public page. (This needs to be done only once.)
2.  **Clone the repository.** Click the green "Clone or download" button, copy the repository's URL, and type `git clone repo-url` in the terminal:

    ```bash
    git clone git@github.com:your_username/2024-playground.git
    ```

#### Organizing Your Work

When working on a specific challenge, ensure your contributions are organized as follows:

* Create a directory named after the challenge (e.g., `learning_Git` for learngitbranching, `cryptopals` for cryptopals writeups).
* Within the challenge directory, create a subdirectory named after your GitHub username or handle.
* Place all your work for that challenge within your subdirectory.

Example structure:

```
/learning_Git/
  /your_username/
    your_files_and_folders_here
/cryptopals/
  /your_username/
    your_files_and_folders_here
```

#### Adding Changes

1.  **Update main.** Before you make any changes, first checkout main:

    ```bash
    git checkout main
    git pull
    ```
2.  **Create a new branch or switch to your branch.** After cloning the repository, create a new branch:

    ```bash
    git branch your_branch_name
    git checkout your_branch_name
    ```
3.  **Make your changes and commit them.** Once you have created your branch, make your changes and commit them:

    ```bash
    git add -A
    git commit -m "Descriptive message of what you did"
    ```
4.  **Push up your changes.** Push your changes to your fork:

    ```bash
    git push origin your_branch_name
    ```

#### Making a Pull Request

1. **Create a pull request.** Go to your fork on GitHub, and you should see a button to create a pull request from your branch.
2. **Review and submit.** Double-check to ensure you are making a pull request against the right branch. Enter a descriptive title in the title field.

#### Pushing Additional Changes

If additional changes are necessary after creating the pull request, **do not create a new pull request**. Instead, make more commits to your branch and push them up:

```bash
git add -A
git commit -m "Additional changes"
git push origin your_branch_name
```

These changes will be added to the pull request automatically.

#### Making a Pull Request

1.  **Switch to the branch where you made changes.**

    ```bash
    git checkout your_branch_name
    ```
2. **Open a pull request.** Go to your fork on GitHub, and you should see a button to create a pull request from your branch.
3. **Review and submit.** Double-check to ensure you are making a pull request against the right branch. Enter a descriptive title in the title field.
