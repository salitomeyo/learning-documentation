---
id: q19twh59ztqlgfx109sn8l9
title: Script Repo Tutorial
desc: ''
updated: 1669850513112
created: 1669850509269
---

## How to install docker

First of all we need to install WSL. This is needed because we dont have access to docker desktop, the only way for us to use it is through the command line

[WSL installing guide](https://learn.microsoft.com/en-us/windows/wsl/install)

We need to make sure the versione installed is wsl2, we can check this usign the following command

```bash
wsl -l -v
```

Now we can install the [windows terminal](https://www.microsoft.com/store/productId/9N0DX20HK701) (Even though this is not a necessary step we highly recommend it)

Then we have to install docker inside the WSL (ubuntu) terminal this is needed because docker engine only runs on linux

[Docker Engine installing guide](https://docs.docker.com/engine/install/ubuntu/)

If you can run the hello-world test at the end of the guide it probably means you havent started your docker service, you can fix that and see the current docker service status using

```bash
sudo service docker status
```

```bash
sudo service docker start
```

To finallize the docker installation you must follow the post-installation guide as well

[Docker post-installation guide](https://docs.docker.com/engine/install/linux-postinstall/)


## Configuring github

Because the repositories are private you need to make sure you are performing the following steps with an account with access, and we are going to configure an ssh key as our cloning method (make sure no one has access to your private ssh key, this is extremely dangerous, never share it with ANYONE)

[Github ssh guide](https://docs.github.com/es/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)

Once the ssh key is vinculated with your github account use the following command to authenticate your with github

```bash
ssh -T git@github.com
```

## Running our project 

You need to install the github repository inside the wsl ubuntu console (make sure you are using your ssh key generated in the last step)

[Lighthouse scripts](https://github.com/pslcorp/lighthouse-scripts)

This project uses poetry as a dependency manager for python 

[Poetry installation guide](https://python-poetry.org/docs/)

We are working on a different branch in the project, so we must use 

```bash
git checkout evaluations-migration
```

We will be working inside a folder called "evaluations_migration" which will act as our "root", once we are inside this folder on the command line we use 

```bash
poetry install
```

In order to tell poetry to install all the dependencies configured in the project, and finally to run the scripts we use

```bash
poetry run pytest -vv
```
