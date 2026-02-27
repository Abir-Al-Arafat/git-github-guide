# GitHub SSH Setup Guide

This guide explains how to generate an SSH key and connect it to GitHub.

------------------------------------------------------------------------

## 1. Check if SSH Key Already Exists

Open Git Bash or your terminal and run:

``` bash
ls -al ~/.ssh
```

If you see files like:

-   `id_ed25519`
-   `id_ed25519.pub`

Then you already have an SSH key.

------------------------------------------------------------------------

## 2. Generate a New SSH Key (If Not Exists)

Run:

``` bash
ssh-keygen -t ed25519 -C "your_email@example.com"
```

Press **Enter** for default file location.

------------------------------------------------------------------------

## 3. Start SSH Agent

``` bash
eval "$(ssh-agent -s)"
```

------------------------------------------------------------------------

## 4. Add SSH Key to Agent

``` bash
ssh-add ~/.ssh/id_ed25519
```

------------------------------------------------------------------------

## 5. Copy Public Key

``` bash
cat ~/.ssh/id_ed25519.pub
```

Copy the full output.

------------------------------------------------------------------------

## 6. Add SSH Key to GitHub

1.  Go to GitHub → Settings\
2.  Click **SSH and GPG keys**\
3.  Click **New SSH Key**\
4.  Paste the copied key\
5.  Click **Save**

------------------------------------------------------------------------

## 7. Test SSH Connection

``` bash
ssh -T git@github.com
```

If successful, you will see:

    Hi your-username! You've successfully authenticated, but GitHub does not provide shell access.

------------------------------------------------------------------------

## 8. Clone a Repository Using SSH

``` bash
git clone git@github.com:username/repository.git
```

------------------------------------------------------------------------

## Notes

-   Keep `id_ed25519` private. Never share it.
-   Only share `id_ed25519.pub`.
-   SSH allows secure authentication without entering password every
    time.

------------------------------------------------------------------------

**You are now ready to use GitHub with SSH.**
