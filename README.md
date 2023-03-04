By GitHub Actions, Package a Noll site.

# 快速开始

## 创建站点 Repository

你首先需要一个用于部署网站的 Repository（仓库），这里推荐直接 Fork [`NollAction`](https://github.com/NollGo/NollAction) 仓库并重命名。

![image](https://user-images.githubusercontent.com/11867809/222881878-7c48231a-1000-4d38-aeaf-b0ded5e00934.png)

你也可以创建一个空仓库，并添加 `NollAction` 的 [`noll.yml`](https://github.com/NollGo/NollAction/blob/main/.github/workflows/noll.yml) workflow。这个 workflow 是一个用于自动编译，打包和发布网站到线上的 Action。

这个仓库可以命名为：`noll.github.io`（`noll` 替换为你的 `github` 用户名），也可以是其他名字，比如 `blog` 等。如果你的仓库名是前者，那么你的网站最终地址是 `https://noll.github.io`，如果是后者，那么你的网站地址是 `https://noll.github.io/blog`。

## 开启 GitHub Pages 并设置 `Source` 为 `Github Actions`

> 如果会，可以跳过此步骤。

在 Repository 的设置页的左边栏里，点击`Pages` 菜单，进入 `GitHub Pages` 页面。然后设置 `Build and deployment` 的 `Source` 为 `Github Actions`（`workflow` 里面用到了发布到 `GitHub Pages` 的框架和自定义构建过程）。

![image](https://user-images.githubusercontent.com/11867809/220971700-5bc6946e-970b-46d3-a53a-1b1e754fdfc2.png)

## 开启 GitHub Discussions

> 如果会，可以跳过此步骤。

Noll 采用 GitHub Discussions 作为发布和保存文章的数据源，所以需要开启 Repository Discussions。

在 Repository 的设置页，下滑找到 `Features` 列表，找到 `Discussions` 功能，勾选开启，如下：

![image](https://user-images.githubusercontent.com/11867809/220903391-80a0d084-6c88-425f-8ff8-e61c95532dc6.png)

## 创建文章

创建文章就是创建一个讨论（`Discussion`）的过程，比如我们要创建一个 `Hello world` 的文章。

首先进入你的 Repository Discussions 页面，点击右边的 `New Discussion` 按钮，选择一个 `Category`（分类），进入编辑页，输入 `Hello world` 标题并随便写点什么，然后点击下方的 `Start discussion` 按钮，即可发布文章了。

发布新文章会触发 GitHub Action，然后执行我们的 `workflow`——`noll.yml`，然后`noll.yml` 会编译打包我们的网站，并最终会布网站到你的站点。

浏览器里访问：<https://nollgo.github.io/Noll/> （假如你的用户名是 `NollGo`，仓库名是 `Noll`）

可在 GitHub Action 的最近一次构建里看到具体地址，如下：

![image](https://user-images.githubusercontent.com/11867809/221553629-676af9b7-d9da-4937-a99a-e12eae44a868.png)

# 更新 Noll

为了获得更好的体验，我们建议你保持较新版本的 Noll，这不会花费你太多时间即可更新到最新的版本。

## 通过 `Sync Fork` 方式更新 Noll

如果你的站点仓库是通过 Fork `NollAction` 的方式创建的，那么请使用此方法。

1. 在 GitHub 上，导航到您与 [NollAction](https://github.com/NollGo/NollAction) 仓库同步的 Fork 仓库页面（即站点仓库页面）；
2. 选择 “Sync Fork” 下拉菜单；

![image](https://user-images.githubusercontent.com/11867809/222360984-23dea64a-2495-4bd0-9ab7-d4e5938b9735.png)

3. 如果出现了 "Update branch" 按钮，则表示有更新，请点击 “Update branch” 即可完成更新。
   如果没有，则表示当前版本为最新版本，无需更新。

![image](https://user-images.githubusercontent.com/11867809/222360389-a94f4680-de45-468e-bf19-659ea7dee968.png)

最后别忘了 `Re-run all jobs` 你的 Action。

## 通过更新 workflow 的方式更新 Noll

如果你的站点仓库是手动创建的，那么请使用此方法。

手动创建的站点仓库，需要手动更新 workflow。

1. 进入 [NollAction](https://github.com/NollGo/NollAction) 仓库页面，打开 [`.github/workflows/noll.yml`](https://github.com/NollGo/NollAction/tree/main/.github/workflows/noll.yml) 文件，复制 `noll.yml` 文件内容；
2. 进入你的站点仓库，打开并编辑你的 `.github/workflows/noll.yml` 文件，粘贴刚刚复制的内容，完成更新。

最后别忘了 `Re-run all jobs` 你的 Action。

-----

如有问题，请查看[快速使用](https://nollgo.github.io/Noll/post/29.html)，或[创建一个 Issue](https://github.com/NollGo/Noll/issues/new)。

谢谢。
