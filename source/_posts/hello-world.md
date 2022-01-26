title: Quick Start
categories:
  - Hexo
tags:
  - hexo
  - tips
date: 2020-04-30 00:01:15
---
Welcome to [Hexo](https://hexo.io/)! This is your very first post. Check [documentation](https://hexo.io/docs/) for more info. If you get any problems when using Hexo, you can find the answer in [troubleshooting](https://hexo.io/docs/troubleshooting.html) or you can ask me on [GitHub](https://github.com/hexojs/hexo/issues).
<!--more-->
## Quick Start

### Create a new post

``` bash
$ hexo new "My New Post"
```

More info: [Writing](https://hexo.io/docs/writing.html)

### Run server

``` bash
$ hexo server
or
$ hexo server
```
Then preview the website in [http://localhost:4000](http://localhost:4000)

### Edit in GUI
Add `/admin` behind the URL above
[http://localhost:4000/admin/](http://localhost:4000/admin/)


More info: [Server](https://hexo.io/docs/server.html)

### Generate static files

``` bash
$ hexo generate
```

More info: [Generating](https://hexo.io/docs/generating.html)

### Deploy to remote sites
To do this, you have to first shut down the server by pressing CTRT+C.

Then deploy to github

``` bash
$ hexo cl  //清除之前建立的靜態檔案，也可以輸入 hexo clean
$ hexo g  //建立靜態檔案，也可以輸入 hexo generate
$ hexo d  //部署至 Github Pages，也可以輸入 hexo deploy
```

### Backup

```bash
$ git add .
$ git commit
$ git push
```

### Editor
##### Color
<font color=#66A5B4>I am blue</font>

<u> underscore </u>



More info: [Deployment](https://hexo.io/docs/one-command-deployment.html)