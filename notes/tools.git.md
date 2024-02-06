---
id: 8zmz5ikhasjxxderkey7xv5
title: Git
desc: ''
updated: 1669131630469
created: 1661958066834
---

Welcome to salitomeyo **git command library**! This will be used to store the git commands i have learn and how to use them.

- > Disclaimer: This is not a tutorial nor does it give a complete understanding of `git` or `github`. This are personal notes with no additional purpose.

## General notes

Keep in mind that if part of a command starts with **-** it means we are using an abbreviation of the command

```bash
git -v
```

But if instead it starts with **--** it means we are usign the complete word for the command

```bash
git --version
```

During this notes i will use **<>** to indicate that this must be replace with something that fullfills the request

```bash
git <command>
```

Means that we can replace **<command>** with any command we want to use because its use is transversal so i wont use a single example, rather i will show that it is util accross all posible examples

## Initial commands

* This will let us know which git version is currently installed

```bash
git --version
```

* This will allow us to start a new repository inside the folder where the command is called

```bash
git init
```
* This will give us a general overview of the possible most used commands

```bash
git help
```

We can also call this command with a certain command to enter a most extensive command description

```bash
git help <command>
```

Commit without changes

```bash
git commit --allow-empty -m "mensajito"
```

## SSH

Working with ssh in github first use the console window to create an ssh key on your computer

```bash
ssh-keygen -t rsa -C "correo@correo.com"
```

Then go to github configurations and add your public key as an SSH new key, once you have done that connect ssh with github

```bash
ssh -t git@github.com
```

If it doesn't work follow the [official documentation](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)

If yarn install is not working for "permission denied" when usign ssh it means the **agent** hasnt the ssh key assigned, we can fix it usign the following command to make sure the agent is currently working and configured correctly

```bash
eval $(ssh-agent)
```

And then we assign the generated key to the agent using 

```bash
ssh-add ~/.ssh/id_ed25519
```

Make sure to change "id_ed25519" to the name of the ssh key generated and your computer and linked to your github account