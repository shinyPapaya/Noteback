#### ssh拉取代码出错
问题:
> Connection closed by 28.0.0.69 port 22 fatal: Could not read from remote repository.  Please make sure you have the correct access rights

"思考了一下近期的操作，使用新的梯子，设置了TUN模式代理了全局， 有可能造成了端口变化， 导致了git基于SSH拉取出了问题。"
**解决方法:**
1. 可以放弃SSH方式， 换用HTTPS方式来读取和拉取代码。
2. 坚持使用SSH方式，在 {用户}/.ssh/ 目录下建立config文本文档，输入以下代码，端口指向443即可。
```bash
	Host githup.com
	Hostname ssh.githup.com
	Port 443
```

