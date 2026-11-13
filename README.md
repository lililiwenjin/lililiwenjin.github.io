# 技术随记 · Hexo + Butterfly

主站：<https://lililiwenjin.github.io/>  
生活手帐：<https://lililiwenjin.github.io/life-journal/>

这个项目是一个独立的 Hexo + Butterfly 技术博客，顶部导航和示例文章都提供通往「生活拾遗」的链接。

## 在 Windows / macOS 上本地启动

安装 Node.js LTS、Git，然后在项目根目录运行：

```bash
npm install
npm run build
npm run server
```

本地预览：<http://localhost:4000/>。如果端口占用：

```bash
npm run server -- -p 4001
```

## 第一次提交到 GitHub

先确保这个空仓库存在：<https://github.com/lililiwenjin/lililiwenjin.github.io>

在当前项目目录（不是 life-journal 目录）执行：

```bash
git init
git branch -M main
git remote add origin https://github.com/lililiwenjin/lililiwenjin.github.io.git
git add .
git commit -m "Initialize main site with Hexo Butterfly"
git push -u origin main
```

如果 `git remote add` 提示 `origin already exists`，先执行 `git remote -v` 核查仓库地址，不要覆盖生活手帐的 remote。

然后打开 <https://github.com/lililiwenjin/lililiwenjin.github.io/settings/pages>，在 `Build and deployment → Source` 选择 `GitHub Actions`。检查 Actions 绿勾后访问主站。

## 平时写博客

```bash
npx hexo new "我的第一篇技术笔记"
# 编辑 source/_posts/ 下的新文章
npm run build
git add .
git commit -m "Add technical note"
git push origin main
```

## 配置位置

- `_config.yml`：主站 URL 为 `https://lililiwenjin.github.io/`，`root: /`
- `_config.butterfly.yml`：顶部「生活拾遗」指向 `https://lililiwenjin.github.io/life-journal/`
- `source/_posts/`：技术文章 Markdown
- `source/images/`：图片
- `.github/workflows/pages.yml`：GitHub Actions 部署配置

两个网站完全独立；主站提交不会覆盖 `life-journal` 仓库。此项目**不包含旧技术博客文章**。
