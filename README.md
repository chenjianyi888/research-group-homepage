# 课题组网站部署指南

这是一个多页面的课题组网站，采用简洁的学术风格设计，参考了日式实验室网站的设计风格。所有内容均为英文，每个部分都是独立的HTML页面。

## 📁 网站结构

- `index.html` - 首页（HOME）
- `faculty.html` - 教师信息页面（FACULTY），包含详细的教师个人信息
- `research.html` - 研究方向页面（RESEARCH）
- `publications.html` - 论文发表页面（PUBLICATIONS）
- `presentations.html` - 学术报告页面（PRESENTATIONS）
- `members.html` - 团队成员页面（MEMBERS）
- `gallery.html` - 图片库页面（GALLERY）
- `access.html` - 联系方式和地址页面（ACCESS）
- `links.html` - 相关链接页面（LINKS）

所有页面共享同一个导航栏和样式文件（`css/styles.css`）。

这个网站可以部署到 GitHub Pages，让任何人都可以通过网址访问！

## 📦 快速部署步骤

### 方法一：使用 GitHub Desktop（最简单，推荐）

1. **下载 GitHub Desktop**
   - 访问 https://desktop.github.com/ 下载并安装

2. **创建 GitHub 仓库**
   
   **重要提示：** 如果你想直接在 `research-group-homepage` 文件夹里创建仓库（推荐），有两种方法：
   
   **方法 A：使用 GitHub Desktop**
   - 打开 GitHub Desktop，登录你的 GitHub 账号
   - 点击 `File` → `New Repository`
   - **Repository name:** 填写仓库名（例如：`research-group-homepage`）
   - **Local path:** 点击 "Choose..." 按钮，选择 `research-group-homepage` 文件夹的**上一级文件夹**
   - ⚠️ **关键：** 这样 GitHub Desktop 会在上一级文件夹里创建 `research-group-homepage` 子文件夹，**然后你需要把所有网站文件移动到那个新文件夹里**
   
   **方法 B：直接在现有文件夹初始化（推荐）**
   - 在终端中执行以下命令（或使用 GitHub Desktop 的菜单）
   - 打开终端，进入 `research-group-homepage` 文件夹
   - 运行：`git init`
   - 然后在 GitHub Desktop 中点击 `File` → `Add Local Repository`，选择 `research-group-homepage` 文件夹
   - 在 GitHub Desktop 中，点击 `Repository` → `Repository Settings` → `Remote` → 添加远程仓库地址

3. **推送代码到 GitHub**
   - 在 GitHub Desktop 中，填写 Summary（例如：Initial commit）
   - 点击 `Commit to main`
   - 点击 `Publish repository`

4. **启用 GitHub Pages**
   
   ⚠️ **重要：如果看不到 "Source" 部分**
   
   如果你在 `Settings` → `Pages` 页面看到 "Upgrade or make this repository public to enable Pages" 提示，说明你的仓库是私有的，需要先做以下操作之一：
   
   **选项 A：将仓库设为公开（免费，推荐）**
   - 在仓库页面，点击 `Settings`（设置）
   - 向下滚动到 `Danger Zone`（危险区域）
   - 点击 `Change visibility`（更改可见性）
   - 选择 `Make public`（设为公开）
   - 确认操作
   - 然后返回 `Settings` → `Pages`，就能看到 "Source" 部分了
   
   **选项 B：升级到 GitHub Pro（付费，可保持私有）**
   - 点击 "Upgrade" 按钮升级账户
   - 升级后即可为私有仓库启用 GitHub Pages
   
   **启用步骤（完成上述操作后，或如果你已经能看到 "Source" 部分）：**
   
   如果你看到页面显示 "GitHub Pages is currently disabled"（GitHub Pages 当前已禁用），这很正常，说明还没有配置部署源。按以下步骤操作：
   
   - 访问你的仓库页面（https://github.com/你的用户名/仓库名）
   - 点击 `Settings`（设置）
   - 在左侧菜单找到 `Pages`
   - 在 `Source` 部分，下拉菜单应该显示 "Deploy from a branch"，保持这个选项
   - 在 `Branch` 部分的下拉菜单中，选择 `main`（或 `master`，取决于你的默认分支名）
   - 在同一个下拉菜单右侧，选择 `/ (root)` 文件夹
   - 点击 `Save`（保存）按钮
   - ⚠️ **重要：** 保存后页面会刷新，可能还会显示 "disabled"，这是正常的。等待 1-2 分钟，页面会自动更新
   - 📍 **如何找到你的网站地址：**
     - 保存并等待 1-2 分钟后，在 Pages 设置页面的**顶部**通常会显示："Your site is live at"（你的网站已上线于）
     - 点击这个链接就能访问你的网站
     - 如果没有显示，可以直接访问：`https://你的用户名.github.io/仓库名/`
     - 例如：如果你的用户名是 `chenjianyi888`，仓库名是 `research-group-homepage`，网址就是：`https://chenjianyi888.github.io/research-group-homepage/`
   - ⚠️ **注意：** "Custom domain" 部分是用来设置**你自己的域名**（需要单独购买），不是用来显示默认的 GitHub Pages 网址的
   - 网站通常会在 5-10 分钟内可用，你可以点击链接查看

### 方法二：使用命令行（如果你熟悉 Git）

```bash
# 1. 在项目文件夹中初始化 Git
cd research-group-homepage
git init

# 2. 添加所有文件
git add .

# 3. 提交
git commit -m "Initial commit"

# 4. 在 GitHub 上创建新仓库（通过网页），然后连接
git remote add origin https://github.com/你的用户名/仓库名.git
git branch -M main
git push -u origin main
```

然后在 GitHub 仓库的 Settings → Pages 中启用（详细步骤见方法一的第4步，注意如果仓库是私有的需要先设为公开）

### 方法三：直接上传文件（最简单但不够优雅）

1. 在 GitHub 上创建新仓库
2. 点击 `Upload files`
3. 将项目文件夹中的所有文件拖拽上传
4. 提交后，在 Settings → Pages 中启用（详细步骤见方法一的第4步，注意如果仓库是私有的需要先设为公开）

## 🌐 自定义域名（可选）

⚠️ **关于费用：**
- **GitHub Pages 服务本身完全免费**，你可以使用 `你的用户名.github.io/仓库名` 这样的默认地址
- **自定义域名需要单独购买**（费用与 GitHub 无关，是域名注册商收取的，通常每年几十到几百元不等，取决于域名类型）
- 如果你只是想测试网站，**无需设置自定义域名**，使用免费的 `github.io` 地址即可

如果你想使用自己的域名（如 `research.yourschool.edu.cn`）：

1. 在项目根目录创建 `CNAME` **(不带扩展名)**，内容是你的域名：
   ```
   research.yourschool.edu.cn
   ```

2. 在你的域名 DNS 设置中添加 CNAME 记录：
   - 类型：CNAME
   - 名称：research（或你想要的子域名）
   - 值：你的用户名.github.io

3. 在 GitHub Pages 设置中也输入你的域名

## 📝 更新网站内容

✅ **是的，完全可以！** 你在本地修改的任何文件都可以同步到 GitHub，GitHub Pages 会自动更新你的网站。

### 方法一：使用 GitHub Desktop（最简单，推荐）

1. **在本地修改文件**
   - 用任何编辑器（VS Code、记事本等）打开并修改 `index.html`、`faculty.html` 等文件
   - 保存文件

2. **在 GitHub Desktop 中提交更改**
   - 打开 GitHub Desktop，它会自动检测到修改的文件
   - 在左侧会显示所有修改过的文件，点击可以看到具体改动
   - 在左下角的 `Summary` 框填写本次更新的描述（例如："更新教师信息"、"添加新成员"等）
   - （可选）在 `Description` 框中添加更详细的说明
   - 点击 `Commit to main`（提交到 main 分支）

3. **推送到 GitHub**
   - 点击右上角的 `Push origin`（推送到远程）按钮
   - 等待推送完成（通常几秒钟）

4. **网站自动更新**
   - 推送成功后，GitHub Pages 会自动开始构建新版本
   - 通常 1-3 分钟后，访问你的网站就能看到更新后的内容
   - 如果没看到更新，尝试强制刷新浏览器（Ctrl+F5 或 Cmd+Shift+R）

### 方法二：使用命令行（如果你熟悉 Git）

```bash
# 1. 进入项目文件夹
cd research-group-homepage

# 2. 查看修改了哪些文件（可选）
git status

# 3. 添加所有修改的文件
git add .

# 或者只添加特定文件：
# git add index.html faculty.html

# 4. 提交更改（写一个描述性的提交信息）
git commit -m "更新教师信息"

# 5. 推送到 GitHub
git push

# 推送成功后，等待 1-3 分钟，网站就会自动更新
```

### 📌 重要提示

- ✅ **所有修改都会同步**：HTML 文件、CSS 样式、图片、任何文件都会被同步
- ✅ **自动更新**：推送到 GitHub 后，GitHub Pages 会自动重新构建网站
- ⏱️ **更新时间**：通常 1-3 分钟，最多 10 分钟
- 🔄 **刷新浏览器**：如果看不到更新，尝试强制刷新（Ctrl+F5 或 Cmd+Shift+R）
- 📍 **确认同步**：推送后可以在 GitHub 网页上查看仓库，确认文件已经更新

## 🔍 本地预览

在部署前，你可以本地预览网站：

1. **简单方法**：直接双击 `index.html` 文件在浏览器中打开

2. **使用 Python（推荐，避免某些路径问题）**：
   ```bash
   # Python 3
   python3 -m http.server 8000
   
   # 然后在浏览器访问 http://localhost:8000
   ```

3. **使用 VS Code**：安装 "Live Server" 插件，右键 `index.html` 选择 "Open with Live Server"

## ⚙️ 仓库名称建议

- `research-group-homepage`
- `lab-website`
- `课题组主页`
- `你的课题组英文名-homepage`

注意：如果仓库名是 `你的用户名.github.io`，那么网站地址就是 `https://你的用户名.github.io`（不需要仓库名后缀）

## 📚 参考示例

参考网站的 GitHub 地址：https://github.com/fupeng-sun/homepage

你可以查看他的仓库结构，了解如何组织文件。

## ❓ 常见问题

**Q: 在 Pages 设置中找不到 "Source" 部分？**
A: 这说明你的仓库是私有的。GitHub Pages 免费版只支持公开仓库。解决方法：
   - **推荐**：将仓库设为公开（Settings → 滚动到底部 → Danger Zone → Change visibility → Make public）
   - **或者**：升级到 GitHub Pro 账户（付费，可保持私有）
   设为公开后，返回 Pages 设置页面就能看到 "Source" 部分了。

**Q: 看到 "GitHub Pages is currently disabled" 提示是什么意思？**
A: 这个提示很正常，表示你还没有选择用于部署的分支。按以下步骤操作：
   1. 在 `Branch` 下拉菜单中选择 `main`（或你的默认分支名）
   2. 在右侧选择 `/ (root)` 文件夹
   3. 点击 `Save` 按钮
   4. 等待 1-2 分钟，页面会自动更新显示你的网站地址
   5. 通常在 5-10 分钟内，你的网站就可以通过 `https://你的用户名.github.io/仓库名/` 访问了

**Q: 如何找到我的网站网址？Custom domain 部分会显示吗？**
A: 
   - **Custom domain 部分不会显示默认网址**，它是用来设置你自己购买的域名的
   - 保存设置后，等待 1-2 分钟，在 Pages 设置页面**顶部**通常会显示 "Your site is live at"（你的网站已上线于），点击链接即可访问
   - 你也可以直接访问：`https://你的用户名.github.io/仓库名/`
   - 如果仓库名是 `你的用户名.github.io`，则网址是：`https://你的用户名.github.io`

**Q: GitHub Pages 是免费的吗？**
A: **是的，完全免费！**
   - GitHub Pages 服务本身完全免费，你可以免费使用 `github.io` 子域名
   - 如果你要使用自定义域名（如 `yourwebsite.com`），需要单独购买域名（通常每年几十到几百元），但 GitHub Pages 服务本身仍然是免费的
   - **只要使用免费的 `github.io` 地址，就完全不需要花任何钱**

**Q: 部署后网站显示 404？**
A: 等待 5-10 分钟，GitHub Pages 需要时间构建。确保 `index.html` 在根目录。

**Q: 图片显示不出来？**
A: 检查图片路径是否正确，确保 `images` 文件夹中的文件都已上传。

**Q: 本地修改文件后如何同步到 GitHub？**
A: 
   - **使用 GitHub Desktop**：修改文件后，在 GitHub Desktop 中填写 Summary，点击 `Commit to main`，然后点击 `Push origin`
   - **使用命令行**：`git add .` → `git commit -m "描述"` → `git push`
   - 推送成功后，GitHub Pages 会在 1-3 分钟内自动更新网站
   - 详细步骤见"📝 更新网站内容"部分

**Q: 修改后网站没更新？**
A: 
   - 确认你已经执行了 `git push` 推送更改到 GitHub
   - 等待 3-5 分钟，GitHub Pages 需要时间构建
   - 强制刷新浏览器缓存（Ctrl+F5 或 Cmd+Shift+R）
   - 检查 GitHub 仓库，确认文件已经成功上传

**Q: 可以私有仓库吗？**
A: GitHub Pages 免费版只支持公开仓库。如需私有，需要 GitHub Pro。

---

需要帮助？查看 [GitHub Pages 官方文档](https://docs.github.com/en/pages)

