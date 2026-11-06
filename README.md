# .github

> 本组织的「门面」仓库，没有业务代码，只放给 GitHub 看的文件。

这是 [cayzlh](https://github.com/cayzlh) 组织的**特殊配置仓库**。名字固定叫 `.github`，
GitHub 会按约定从这里读取组织的公开资料，所以它和普通的项目仓库不是一回事。

## 目录结构

| 路径 | 作用 |
| --- | --- |
| `profile/README.md` | 组织主页 <https://github.com/cayzlh> 上渲染的自我介绍 |
| `README.md` | 本文件。只在仓库页面展示，**不影响**组织主页 |
| `LICENSE` | 许可证。组织内公开仓库统一使用 MIT |

## 关于 profile/README.md

`profile/` 这个目录名是 GitHub 的硬约定，写别的名字不会被识别。
组织主页顶部那段自我介绍就是 `profile/README.md` 的内容，
它在组织主页和仓库文件页两处都能看到，但只有前者是「对外的样子」。

想改组织主页，改这个文件就够了。

## 修改后怎么生效

GitHub 只读**默认分支**（`main`）上的内容，本地改完不推等于没改：

```bash
# 1. 改完 profile/README.md
git add -A && git commit -m "docs: 更新组织主页自我介绍"
git push origin main

# 2. 打开组织主页确认（缓存通常在几秒内刷新）
open https://github.com/cayzlh
```

注意两点：

- **没有本地预览。** 组织主页的渲染结果只有推上去才看得到，
  相对链接、HTML 标签的可见性问题都得推完再验。
- **相对路径不可靠。** 组织主页上的 README 不是从文件页渲染的，
  相对链接的解析基准容易踩坑。指向本仓库文件的链接请写**绝对 URL**，
  例如 `https://github.com/cayzlh/.github/blob/main/LICENSE`。

## 许可证

本仓库使用 [MIT License](LICENSE)。
