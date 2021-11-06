# 搭建一个blog

## 运行环境

Linux系统



## 具体步骤

#### 步骤一：环境配置
1. 安装一个node.js软件，设置好环境变量。

2. 使用npm指定淘宝镜像

   ```
   npm install -g cnpm --registry=https://registry.npm.taobao.org
   ```

3. 运行上述命令后就可以用cnpm安装hexo

   ```
   cnpm install -g hexo-cli
   ```

   

#### 步骤二：创建一个blog项目

1. 在桌面创建一个文件夹用于放置项目，如：C:\Users\Sealevel\Desktop\blog
2. cd进blog，然后使用hexo init克隆相应项目的文件
3. 使用hexo s会在本地的4000端口启动服务



#### 步骤三：远程部署（这里部署到GitHub的仓库）

1. 在GitHub中新建一个仓库（repository），注意仓库名为昵称+.github.io

2. 安装hexo-deployer-git插件用于向github推送文件

   ```
   cnpm install --save hexo-deployer-git
   ```

3. 配置_config.yml文件内容

   ```
   ...
   deploy:
     type:git
     repo:https://github.com/hexo/hexo.github.io.git
     或者 https://<username>:<token>@github.com/hexo/hexo.github.io.git
     branch:master
   ```

4. 部署到远端

   ```
   hexo clean
   hexo g/generate
   hexo d/deploy
   ```

   

