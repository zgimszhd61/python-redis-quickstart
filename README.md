在Mac系统下本地部署Redis主要有两种方法：通过Homebrew安装和通过源码安装。以下是这两种方法的详细步骤。

## 通过Homebrew安装Redis

Homebrew是MacOS的包管理器，可以简化安装过程。

1. **检查Homebrew是否已安装**：首先，你需要确认你的Mac上是否已经安装了Homebrew。可以通过在终端运行`brew --version`来检查。如果未安装，可以通过运行以下命令来安装Homebrew：
   ```bash
   /bin/bash -c "$(curl -fsSL https://gitee.com/cunkai/HomebrewCN/raw/master/Homebrew.sh)"
   ```
2. **安装Redis**：一旦安装了Homebrew，就可以通过运行以下命令来安装Redis：
   ```bash
   brew install redis
   ```
3. **启动Redis服务**：安装完成后，可以通过Homebrew服务启动Redis，使用以下命令：
   ```bash
   brew services start redis
   ```
   或者，直接使用Redis自带的命令启动：
   ```bash
   redis-server /usr/local/etc/redis.conf
   ```
4. **验证Redis是否正在运行**：可以通过运行`redis-cli ping`命令来测试Redis服务器是否启动。如果返回`PONG`，则表示Redis服务器正在运行。

## 通过源码安装Redis

如果你更倾向于从源码安装Redis，可以按照以下步骤操作：

1. **下载Redis**：访问Redis官网(http://redis.io/)下载最新稳定版本的Redis。
2. **解压Redis**：下载完成后，使用以下命令解压Redis压缩包：
   ```bash
   tar -zxf redis-*.tar.gz
   ```
3. **编译Redis**：解压后，进入Redis目录，并使用`make`命令编译Redis：
   ```bash
   cd redis-*
   make
   ```
   你也可以运行`make test`来测试编译结果。
4. **安装Redis**：编译完成后，使用以下命令安装Redis：
   ```bash
   sudo make install
   ```
5. **启动Redis服务**：安装完成后，可以通过以下命令启动Redis服务：
   ```bash
   redis-server
   ```
6. **连接到Redis**：可以通过`redis-cli`命令连接到Redis服务器，例如：
   ```bash
   redis-cli
   ```

无论是通过Homebrew安装还是通过源码安装，安装完成后都可以通过`redis-cli`命令与Redis服务器交互，例如设置键值对和获取键值对[1][3][5][6]。

Citations:
[1] https://www.runoob.com/redis/redis-install.html
[2] https://blog.csdn.net/realize_dream/article/details/106227622
[3] https://juejin.cn/post/7099771580812623902
[4] https://cloud.tencent.com/developer/article/1506991
[5] https://developer.aliyun.com/article/1148552
[6] https://blog.csdn.net/HIHE_i/article/details/108834803
[7] https://juejin.cn/s/mac%20%E6%9C%AC%E5%9C%B0%E5%90%AF%E5%8A%A8redis
[8] https://www.cnblogs.com/chocolatexll/p/12964812.html
