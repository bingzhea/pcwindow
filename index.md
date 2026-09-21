# 隐私政策 / Privacy Policy

**应用名称 / App name：** pc之窗（pc window）
**发布者 / Publisher：** bingzhe
**生效日期 / Effective date：** 2026-09-21
**最近更新 / Last updated：** 2026-09-21
**联系方式 / Contact：** pcwindow@163.com
**本政策公开地址 / Public URL：** https://bingzhea.github.io/pcwindow/

> 提交 Microsoft Store 前，必须把上面四处 `<待填写>` 替换成真实内容，并把本文
> 档发布到一个任何人都能匿名访问的 https 地址；Partner Center 的「隐私政策 URL」
> 填的就是那个地址。

---

## 中文

### 一、总述

pc之窗是一个纯本地运行的 Windows 桌面工具，用于整理并快速打开桌面上已有的入口。

**我们不收集、不上传、不出售你的任何个人信息。** 程序没有账号体系，不做用户
识别，不接入任何统计、广告或第三方 SDK。

### 二、程序会读取哪些内容

为了展示桌面入口，程序会在本机读取：

| 读取内容 | 用途 |
| --- | --- |
| 当前用户桌面和公共桌面第一层的文件、文件夹、快捷方式的名称与路径 | 在界面上列出并分类 |
| `.lnk` 快捷方式的目标路径、启动参数、工作目录 | 判断类别，并按原样启动 |
| Windows Shell 为上述项目提供的默认图标 | 在界面上显示图标 |

程序**不会**读取任何文件的内容，也**不会**修改、移动、重命名或删除桌面上的任何
项目。

### 三、数据存放在哪里

所有数据只保存在本机当前用户目录下，不会离开你的电脑：

```
%LOCALAPPDATA%\DesktopQuickLauncher\
├── scan_cache.json          桌面扫描结果缓存
├── manual_sections.json     你手动创建的自定义栏目
├── icons\                   提取出来的图标缓存（PNG）
└── logs\app.log             运行日志（轮转，最多 4 个文件、每个 1 MiB）
```

运行日志记录启动/退出时间、扫描结果数量、被打开的入口名称与路径，以及异常堆栈，
用于你自己排查问题。日志不记录任何文件内容，也不会被自动上传。

**删除方式：** 直接删除上面的目录即可。使用安装包卸载时，程序会询问你是否一并
删除这些数据；Microsoft Store 版本在卸载时由系统自动清除。

### 四、网络访问

程序默认**不进行任何网络通信**。

唯一可能的例外是「检查更新」功能，它满足全部以下条件才会发起请求：

1. 你使用的是独立安装包版本（Microsoft Store 版本不含此功能，更新由商店负责）；
2. 该版本已配置更新清单地址；
3. **你主动点击了侧边栏的「检查更新」**（程序不会在后台自动检查）。

当前版本未配置更新清单地址，因此「检查更新」功能处于关闭状态，不会发起上述请求。
如果未来启用该功能，程序会向公开披露的 HTTPS 更新清单地址发起一次 GET 请求，读取
一个只包含版本号和下载链接的 JSON 文件。请求中除 HTTP 协议本身必需的信息（如
User-Agent，内容为应用名和版本号）外，不包含任何你的个人信息、机器标识或桌面内容。
服务器的访问日志可能按常规记录你的 IP 地址和时间。

### 五、第三方

程序不使用任何第三方分析、广告、崩溃上报或数据处理服务。程序基于 Python 标准库
构建，不引入网络相关的第三方运行时依赖。

### 六、儿童隐私

本程序不面向 13 岁以下儿童，也不会有意收集任何年龄段用户的个人信息。

### 七、权限说明

Microsoft Store 版本声明了 `runFullTrust`（完全信任）受限权限。这是因为枚举桌面
快捷方式并以其原有参数启动对应的本机程序，无法在 AppContainer 沙箱内完成。该权限
仅用于上述用途。

### 八、政策变更

本政策如有修改，会更新顶部的「最近更新」日期并发布在同一地址。

### 九、联系我们

如对本政策有疑问，请联系：`pcwindow@163.com`

---

## English

### 1. Overview

pc window is a purely local Windows desktop utility that organises and launches
shortcuts that already exist on your desktop.

**We do not collect, transmit, or sell any personal information.** The app has no
accounts, performs no user identification, and integrates no analytics,
advertising, or third-party SDKs.

### 2. What the app reads

To display your desktop entries, the app reads the following locally:

| Data read | Purpose |
| --- | --- |
| Names and paths of top-level files, folders and shortcuts on the current user's Desktop and the Public Desktop | List and categorise them in the UI |
| Target path, arguments and working directory of `.lnk` shortcuts | Determine category and launch them unchanged |
| Default icons provided by the Windows Shell for those entries | Display icons in the UI |

The app does **not** read the contents of any file, and does **not** modify, move,
rename or delete anything on your desktop.

### 3. Where data is stored

All data stays on your machine, under the current user's profile:

```
%LOCALAPPDATA%\DesktopQuickLauncher\
├── scan_cache.json          Cached desktop scan results
├── manual_sections.json     Custom sections you created
├── icons\                   Extracted icon cache (PNG)
└── logs\app.log             Rotating application log (max 4 files, 1 MiB each)
```

The log records start/exit times, the number of scanned entries, the name and path
of entries you open, and exception tracebacks — for your own troubleshooting. It
never records file contents and is never uploaded automatically.

**Deletion:** simply delete the folder above. The installer asks whether to remove
this data during uninstall; the Microsoft Store version has it removed by Windows
automatically.

### 4. Network access

The app makes **no network requests** by default.

The only possible exception is the "Check for updates" action, which runs only when
all of the following hold:

1. you are running the standalone installer build (the Microsoft Store build does
   not include this feature — updates are handled by the Store);
2. an update manifest URL has been configured in that build;
3. **you explicitly click "Check for updates" in the sidebar** (there is no
   background or automatic check).

No update manifest URL is configured in the current version, so the "Check for
updates" feature is disabled and no such request is made. If this feature is
enabled in a future version, the app will issue a single HTTPS GET to a publicly
disclosed update manifest URL and read a small JSON file containing a version
number and a download link. Beyond what the HTTP protocol itself requires (a
User-Agent consisting of the app name and version), the request will contain no
personal information, machine identifier, or desktop content. The server's access
log may record your IP address and timestamp as is customary.

### 5. Third parties

No third-party analytics, advertising, crash-reporting or data-processing services
are used. The app is built on the Python standard library and has no third-party
networking dependencies at runtime.

### 6. Children's privacy

The app is not directed at children under 13 and does not knowingly collect
personal information from users of any age.

### 7. Capability disclosure

The Microsoft Store build declares the `runFullTrust` restricted capability. This
is required because enumerating desktop shortcuts and launching the corresponding
native programs with their original arguments cannot be done inside the
AppContainer sandbox. The capability is used for nothing else.

### 8. Changes to this policy

Any change will be reflected in the "Last updated" date above and published at the
same URL.

### 9. Contact

Questions about this policy: `pcwindow@163.com`
