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
   - 访问你的仓库页面（https://github.com/你的用户名/仓库名）
   - 点击 `Settings`（设置）
   - 在左侧菜单找到 `Pages`
   - 在 `Source` 部分，选择 `Deploy from a branch`
   - 选择 `main` 分支和 `/ (root)` 文件夹
   - 点击 `Save`
   - 等待几分钟，GitHub 会给你一个网址：`https://你的用户名.github.io/仓库名/`

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

然后在 GitHub 仓库的 Settings → Pages 中启用（步骤同方法一的第4步）

### 方法三：直接上传文件（最简单但不够优雅）

1. 在 GitHub 上创建新仓库
2. 点击 `Upload files`
3. 将项目文件夹中的所有文件拖拽上传
4. 提交后，在 Settings → Pages 中启用（步骤同方法一的第4步）

## 🌐 自定义域名（可选）

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

每次修改网站后：

**使用 GitHub Desktop：**
1. 修改文件后，在 GitHub Desktop 中看到修改的文件
2. 填写 Summary，点击 `Commit to main`
3. 点击 `Push origin` 推送更改
4. 几分钟后网站自动更新

**使用命令行：**
```bash
git add .
git commit -m "更新内容"
git push
```

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

**Q: 部署后网站显示 404？**
A: 等待 5-10 分钟，GitHub Pages 需要时间构建。确保 `index.html` 在根目录。

**Q: 图片显示不出来？**
A: 检查图片路径是否正确，确保 `images` 文件夹中的文件都已上传。

**Q: 修改后网站没更新？**
A: 清空浏览器缓存（Ctrl+F5 或 Cmd+Shift+R），或等待几分钟。

**Q: 可以私有仓库吗？**
A: GitHub Pages 免费版只支持公开仓库。如需私有，需要 GitHub Pro。

---

需要帮助？查看 [GitHub Pages 官方文档](https://docs.github.com/en/pages)

