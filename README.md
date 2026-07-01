# Lumitech Frontend

香港光潮科技有限公司 Lumitech Hong Kong Limited 双语静态官网。

网站定位：AI 与创新科技企业的海外增长伙伴，提供海外市场进入策略、战略伙伴拓展、品牌启动落地与商业化支持。

## 本地预览

直接在浏览器打开 `index.html` 即可预览。

也可以使用任意静态服务器，例如 VS Code Live Server。

## 文件结构

```text
.
├── index.html
├── styles.css
├── script.js
├── README.md
└── assets/
    ├── lumitech-logo.png
    └── lumitech-symbol.png
```

## 文件说明

- `index.html`：页面结构、SEO 基础信息、导航、各内容模块与表单。
- `styles.css`：白底蓝金品牌视觉、响应式布局、卡片样式、滚动入场与悬浮动效。
- `script.js`：中英文切换、导航高亮、返回顶部按钮、滚动动效、3D 地球模型、联系表单邮件生成。
- `assets/lumitech-logo.png`：首页主 Logo。
- `assets/lumitech-symbol.png`：导航栏左上角图标。

## 当前功能

- 中英文切换：按钮显示为 `中 | EN`，会记住用户选择。
- 响应式布局：支持桌面端、平板和移动端。
- 页面动效：首屏加载、滚动入场、卡片悬浮、按钮光泽。
- 导航高亮：滚动到对应区块时自动高亮当前栏目。
- 首页 3D 地球：白底黑线地球、国家轮廓、HK 与目标国家连线、流动光点、鼠标/触摸拖拽旋转。
- 联系表单：提交后通过 `mailto:` 打开用户邮件客户端。

## 外部依赖

项目本身不需要安装 npm 依赖，但首页 3D 地球运行时会从 CDN 加载：

- `three.module.js`：用于渲染 3D 地球。
- `countries.geo.json`：用于绘制全球国家轮廓。

如果 CDN 无法访问，页面会显示基础地球 fallback，不影响其他内容浏览。

## 部署方式

这是纯静态网站，无需安装依赖、无需构建。

部署时上传以下文件即可：

```text
index.html
styles.css
script.js
assets/
```

### Netlify

1. 登录 Netlify。
2. 选择 `Add new site`。
3. 拖拽整个项目文件夹上传。
4. Build command 留空。
5. Publish directory 留空或填写 `/`。

### Vercel

1. 将项目上传到 GitHub。
2. 在 Vercel 选择 `Import Git Repository`。
3. Framework Preset 选择 `Other`。
4. Build Command 留空。
5. Output Directory 填 `.` 或留空。

### GitHub Pages

1. 新建 GitHub 仓库并上传全部文件。
2. 进入仓库 `Settings` > `Pages`。
3. Source 选择 `Deploy from a branch`。
4. Branch 选择 `main`，目录选择 `/root`。

如果是更新已部署的网站：

1. 进入原 GitHub 仓库。
2. 点击 `Add file` > `Upload files`。
3. 上传并覆盖以下文件：

```text
index.html
styles.css
script.js
README.md
assets/
```

4. Commit message 可填写 `Update Lumitech website`。
5. 点击 `Commit changes`。
6. 等待 1-3 分钟后刷新 GitHub Pages 地址。

如果页面未变化，可使用 `Ctrl + F5` 强制刷新浏览器缓存。

### 传统服务器

将项目文件上传到 Nginx / Apache / 宝塔网站根目录，确保 `index.html` 位于网站根目录即可。

## 后续可调整

- 当前联系表单收件邮箱为 `cookiefindu@qq.com`，如需更换可同步修改 `index.html` 和 `script.js`。
- 将项目经验替换为真实案例或匿名案例。
- 如果需要后台收集表单，可将 `script.js` 中的 `mailto:` 改为 Formspree、Netlify Forms 或自建 API。
- 如需完全离线部署，可将 Three.js 和国家轮廓 GeoJSON 下载到本地 `assets/` 后修改 `script.js` 中的 CDN 地址。
