# 2024-Playground Project

Welcome to the `2024-Playground` repository! This document will guide you through the setup process and understanding the contribution guidelines, which is essential for participating in this project.

## Steps for Contributing

* [Setting Up SSH Keys](./#setting-up-ssh-keys)
  * [Generating a New SSH Key](./#generating-a-new-ssh-key)
  * [Adding Your SSH Key to the ssh-agent](./#adding-your-ssh-key-to-the-ssh-agent)
  * [Adding the SSH Key to Your GitHub Account](./#adding-the-ssh-key-to-your-github-account)
* [Setting Up Your Own Copy of the Repository (Forked Repository)](./#setting-up-your-own-copy-of-the-repository)
* [Organizing Your Work](./#organizing-your-work)
* [Adding Changes](./#adding-changes)
* [Making a Pull Request](./#making-a-pull-request)



### Setting Up SSH Keys

Setting up SSH keys allows you to securely connect to GitHub without needing to enter your username and password every time you interact with your repository from the command line.

#### **Generating a New SSH Key**

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

#### **Adding Your SSH Key to the ssh-agent**

1.  Start the ssh-agent in the background.

    ```bash
    eval "$(ssh-agent -s)"
    ```
2.  Add your SSH private key to the ssh-agent.

    ```bash
    ssh-add ~/.ssh/id_rsa
    ```

#### **Adding the SSH Key to Your GitHub Account**

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
3.  Then, click on  **Settings**.

    <figure><img src=".gitbook/assets/Adding the SSH Key to Your GitHub Account 2.png" alt=""><figcaption></figcaption></figure>
4.  In the user settings sidebar, click **SSH and GPG keys,** then click on "**New SSH key**"

    <figure><img src=".gitbook/assets/Adding the SSH Key to Your GitHub Account 3.png" alt=""><figcaption></figcaption></figure>
5.  In the "Title" field, add a descriptive label for the new key. For example, if you're using a Linux on Virtual Machine, you might call this key "Linux on Virtual Machine". Then, Paste your public key into the "Key" field.

    <figure><img src=".gitbook/assets/Adding the SSH Key to Your GitHub Account 4.png" alt=""><figcaption></figcaption></figure>

After inserting all the details, click 'Add SSH key' button. If it prompted for the password, confirm it by using your GitHub password. You will then receive a successful message, something like `You have successfully added the key 'Linux on Virtual Machine'`.

<figure><img src=".gitbook/assets/Adding the SSH Key to Your GitHub Account 5.png" alt=""><figcaption></figcaption></figure>

### Setting Up Your Own Copy of the Repository

1.  **Fork the repo on GitHub to your personal account.** Click the `Fork` button on the `gajabaar/2024-playground` Public page. (This needs to be done only once.)

    <figure><img src=".gitbook/assets/Setting Up Your Own Copy of the Repository 0.png" alt=""><figcaption></figcaption></figure>
2.  After clicking the **Fork button**, we will be redirected to a page where we can customize our forked repository. Here, we don't need to make any changes, as everything looks fine. So, we processed by clicking on `Create fork` button.

    <figure><img src=".gitbook/assets/Setting Up Your Own Copy of the Repository 1.png" alt=""><figcaption></figcaption></figure>
3.  &#x20;**Clone the repository:** Click on the green `Code` button. It will open a small window. Then click on `SSH` and copy the repository's URL using the copy button or by manually selecting the URL. This URL will be copied to your clipboard. You can use this URL to clone the repository onto your local machine.

    <figure><img src=".gitbook/assets/Setting Up Your Own Copy of the Repository 2.png" alt=""><figcaption></figcaption></figure>

    Now, we have the SSH URL of our forked repository, we can use it to clone our forked repo onto our local machine using the command `git clone <repo URL>`.

    <figure><img src=".gitbook/assets/Setting Up Your Own Copy of the Repository 3.png" alt=""><figcaption></figcaption></figure>

### Organizing your Work

When working on a specific challenge, ensure your contributions are organized as follows:

* Create a directory named after the challenge name directory (e.g., `learning_Git` for learngitbranching, `cryptopals` for cryptopals writeups), etc...
* Within the challenge directory, create a subdirectory named after your Name or username.
* Place all your work for that challenge within our subdirectory.

Example structure:

```bash
/learning_Git/our_username/our_files_and_folders_here
# Example: 
# /learning_Git/GajendraMahato/1.1.introduction-sequence-write-up.md
# /learning_Git/GajendraMahato/1.2.ramping-up-write-up.md
```

### Adding Changes

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



### Making a Pull Request

1.  **Switch to the branch where you made changes.**

    ```bash
    git checkout your_branch_name
    ```
2. **Open a pull request.** Go to your fork on GitHub, and you should see a button to create a pull request from your branch.
3. **Review and submit.** Double-check to ensure you are making a pull request against the right branch. Enter a descriptive title in the title field.
