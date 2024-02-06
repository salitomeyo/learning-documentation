---
id: rsfu9zzuenjtxnr12iw8l37
title: Docker
desc: ''
updated: 1674846525902
created: 1674846490400
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

