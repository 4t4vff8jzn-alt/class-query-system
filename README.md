# 学生成绩查询网站部署说明

这个网站已经是一个静态页面：

- `index.html`
- `style.css`
- `student_data.js`

要实现“无需同一网络即可访问”，需要把它发布到公网。下面给出两种常用方法：

## 方案 1：使用 GitHub Pages（推荐）

1. 注册或登录 GitHub。
2. 创建一个新的仓库。
3. 将当前文件夹中的 `index.html`、`style.css`、`student_data.js` 上传到仓库根目录。
4. 在仓库设置中开启 GitHub Pages，选择 `main` 分支的根目录作为发布目录。
5. 等待几分钟后，GitHub Pages 会生成一个链接，如：
   `https://<你的用户名>.github.io/<仓库名>/`
6. 手机直接打开该链接即可访问。

> 这种方法免费、稳定，适合静态网站。

## 方案 2：使用隧道服务（立即可用）

如果你不想马上部署到 GitHub，可以使用 `ngrok`、`cloudflared` 或 `localtunnel`。

### ngrok 示例

1. 下载并安装 `ngrok`。
2. 在终端进入 `d:\vscode\fk`。
3. 运行：
   `python -m http.server 8000`
4. 另开一个终端，运行：
   `ngrok http 8000`
5. ngrok 会返回一个公网地址，例如：
   `https://abc1234.ngrok.io`
6. 手机打开该地址即可访问网站。

### cloudflared 示例

1. 下载并安装 `cloudflared`。
2. 在终端运行：
   `cloudflared tunnel --url http://localhost:8000`
3. 得到的 URL 也可以直接在手机上打开。

## 方案说明

- GitHub Pages：适合长期使用，网站地址固定。
- 隧道服务：适合临时演示，地址可能会变化。

## 注意

- 如果你希望我直接帮你生成一个 GitHub Pages 部署脚本或 `ngrok` 运行脚本，我也可以继续帮你完成。
