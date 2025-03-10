# 小卓寻回网站部署指南

这个指南将帮助您将小卓寻回网站部署到公网上，使任何人都可以通过不同设备访问。

## 方案一：使用GitHub Pages（推荐）

GitHub Pages是一个免费的静态网站托管服务，非常适合部署这类简单的HTML网站。

### 步骤：

1. **创建GitHub账号**
   - 如果您还没有GitHub账号，请前往 [GitHub官网](https://github.com) 注册一个账号

2. **创建新仓库**
   - 登录GitHub后，点击右上角的"+"按钮，选择"New repository"
   - 仓库名称填写：`find-xiaozuo`（或您喜欢的名称）
   - 选择"Public"（公开）
   - 点击"Create repository"创建仓库

3. **上传网站文件**
   - 在新创建的仓库页面，点击"uploading an existing file"链接
   - 将您电脑上的所有网站文件（index.html、qrcode.html和照片文件夹）拖拽到上传区域
   - 在页面底部添加提交信息，如"初始网站文件上传"
   - 点击"Commit changes"按钮提交

4. **启用GitHub Pages**
   - 在仓库页面，点击顶部的"Settings"选项卡
   - 在左侧菜单中找到并点击"Pages"
   - 在"Source"部分，选择"main"分支，文件夹选择"/(root)"，然后点击"Save"
   - 等待几分钟，GitHub会显示您的网站URL（通常格式为`https://您的用户名.github.io/find-xiaozuo/`）

5. **更新二维码生成代码**
   - 打开qrcode.html文件
   - 找到JavaScript部分（第118-150行左右）
   - 将`const targetUrl = baseUrl + 'index.html';`这一行替换为：
     ```javascript
     const targetUrl = 'https://您的用户名.github.io/find-xiaozuo/index.html';
     ```
   - 请将上面的URL替换为您实际获得的GitHub Pages URL
   - 保存文件并重新上传到GitHub仓库

完成以上步骤后，您的网站就已经部署到公网上了，任何人都可以通过您的GitHub Pages URL访问，也可以通过扫描二维码访问。

## 方案二：使用Netlify（备选）

Netlify也是一个免费的静态网站托管服务，操作更简单。

### 步骤：

1. **创建Netlify账号**
   - 前往 [Netlify官网](https://www.netlify.com) 注册账号（可以使用GitHub账号直接登录）

2. **部署网站**
   - 登录后，点击"New site from Git"按钮
   - 选择"Deploy manually"选项
   - 将您的网站文件打包成ZIP文件并上传
   - 或者直接拖拽您的网站文件夹到上传区域

3. **获取网站URL**
   - 部署完成后，Netlify会自动分配一个URL（如`https://random-name.netlify.app`）
   - 您可以在网站设置中自定义这个URL

4. **更新二维码生成代码**
   - 与GitHub Pages方案类似，更新qrcode.html中的targetUrl为您的Netlify URL

## 注意事项

1. 确保照片文件夹的路径正确，特别是在index.html中引用的图片路径
2. 部署后请测试网站的所有功能，确保二维码正确指向公网URL
3. 如果您的网站需要频繁更新，建议学习使用Git进行版本控制

通过以上方法部署后，您的寻宠网站将可以在公网上访问，任何人都可以通过电脑、手机等不同设备查看网站内容，帮助您寻找爱宠小卓。