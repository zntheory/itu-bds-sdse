---
description: "SSH and GitHub"
title: "Connecting to GitHub via SSH keys"
keywords:
  - Software engineering
  - Git
---

## Connecting to GitHub via SSH keys

Before getting into SSH keys, we need to understand what **git** and **GitHub** are and how they are different.

</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>

### Git vs. GitHub

**Git** is a piece of software that you can install and run locally. It is a version control system (VCS) for tracking changes in, primarily, code files that are within the same directory, which then constitutes a repository.

**GitHub** is an online website that functions as a storage and collaboration platform for **git** repositories. It essentially hosts your code on their servers, and provides a graphical user interface as well as features for easing code collaboration, e.g. pull requests.

</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>

### Why SSH keys for GitHub?

In short, it's a secure way to identify yourself (so people know it's really you who sent a pull request with 10,000+ changed lines in one commit), and it saves you from having to log in each time you want to store files on GitHub.

In GitHub's own words:
> Using the SSH protocol, you can connect and authenticate to remote servers and services. With SSH keys, you can connect to GitHub without supplying your username and personal access token at each visit. You can also use an SSH key to sign commits.

**But for it to be secure, you should *never* give out your *private* key to anyone**, though the public key is fine to give out.

See the private key as your ID card, and the public key as your full name. It's generally fine to give out your name to other people, and in this case, GitHub will ask for your ID to confirm you are whom you claim to be, that you are allowed to work in this repository, etc.

</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>

---

## Guide to generate and add SSH keys for GitHub (terminal)

To the fun part.

### Step 0 - Check for existing SSH keys
```bash
ls -al ~/.ssh
```

**If you already have a key pair and don't want to overwrite them**, make a new file for the new secret key:

```bash
touch ~/.ssh/<new_secret_key>
```

... where `<new_secret_key>` could for example be `id_github`.

Know that private, rsa-based SSH keys per default are written to the file `~/.ssh/id_rsa`, so the above command creates the new file in that same folder (`~/.ssh/`), so you can easily find all of your SSH key pairs in there (if you save them there).

Thus, for future steps, remember to replace `id_rsa` with `<new_secret_key>`, so that even `~/.ssh/id_rsa.pub` turns into `~/.ssh/<new_secret_key>.pub`.

Don't worry about creating a file for the public key. The generator takes care of that.

**If you already have a key pair, and you are *really* sure about overwriting them**, then just follow the guide as if you didn't have a key pair.

</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>

### Step 1 - Create SSH key pair

Replace `<your_email@example.com>` below with your actual e-mail address.  See it as metadata to help you differentiate between multiple key pairs, as you might have multiple GitHub accounts (personal: `username@proton.me`, study: `username@itu.dk`, work: `username@novonordisk.com`).

``` bash
ssh-keygen -t rsa -b 4096 -C "<your_email@example.com>"
```

Then, it will prompt you for where to write the secret key.

**If you didn't have any key pairs**, press `ENTER`. This will write the generated secret key to a new file `~/.ssh/id_rsa`, and the public key to a new file `~/.ssh/id_rsa.pub`.

**Else, if you have a key pair and don't want to overwrite them**, type the location of the new secret key file you created earlier.

This will write the generated secret key to the specified file, and the public key to a new file `~/.ssh/<new_secret_key>.pub`.

</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>

### Step 1.5: Add a passphrase to the key pair (Optional)

**No, thanks?** Press `ENTER`, and continue to the next step.

**Yes, please?** Ensure that you will remember it: Once lost, it cannot be recovered, and you'll just have to replace your SSH key pair with new ones.

When typing in your passphrase, you will not see any characters being typed --- that's just security by obscurity.

Afterward, it will prompt you to type in the same passphrase again...

</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>

### Step 2: Start the SSH agent

```bash
eval "$(ssh-agent -s)"
```

</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>

### Step 3: Add SSH key to SSH agent

```bash
ssh-add ~/.ssh/id_rsa
```

*If you didn't use the default location, remember to specify the location to your new secret key file.*

</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>

### Step 4: Display the contents of your public key
```bash
cat ~/.ssh/id_rsa.pub
```

... which outputs a string with the content: `ssh-rsa <long gibberish>= <computer_name>`, or something similar to that.

*Didn't use the default location? Remember to specify your new secret key file's location.*

</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>

### Step 5: Add SSH key to GitHub
1. Copy the contents of the SSH public key.
2. Access your GitHub account settings.
3. Navigate to **SSH and GPG keys**.
4. Click on **New SSH key**.
5. Give it a title, and ensure that **Key type** is set to 'Authentication Key'.
6. Paste your SSH public key into the provided **Key** field.
7. Click **Add SSH key**.

</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>

### Step 6: Start cloning repositories via SSH, not HTTPS links

You might have tried cloning git repositories from GitHub using HTTPS links:

```bash
git clone https://github.com/<repo_owner>/<repo_name>
```

But to use the new SSH keys to clone and skip manually logging into GitHub, run:

```bash
git clone git@github.com:<repo_owner>/<repo_name>.git
```

**To find this string...**
1. Go to the repository you want to clone from GitHub.
2. Click on the green **<> Code** button.
3. Clicon on the **SSH** tab.
4. Copy the SSH URL to the clipboard.

Enjoy.

</br>
</br>
