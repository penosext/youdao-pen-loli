# youdao-pen-loli

有道词典笔第三方应用 **loli** 的安装包与文档归档。

loli 是由社区开发者为有道词典笔打造的扩展应用，支持在词典笔上运行_。

> ⚠️ 本项目为第三方社区项目，与有道 / 网易官方无关。

---

## 版本说明

安装包位于 `app/` 目录，分两个硬件分支：

| 分支 | 适用芯片 | 多媒体框架 |
|------|----------|------------|
| 'rk-gst' | RK 系列 | GStreamer |
| `cvi-ffmpeg` | CVI 系列 | FFmpeg |

安装前请先确认自己的设备属于哪个分支，方法见下方"设备兼容性检测"。

## 设备兼容性检测

通过 adb 执行以下五条指令，将输出结果发到社群中询问：

```bash
uname -m
cat /proc/device-tree/compatible
ls -la /usr/bin/
ls /dev
gst-launch-1.0
```

也可以直接报设备型号在群里问（不一定有结论）。

---

## 安装方法

> 有道词典笔虽支持 adb，但并非标准 Android 系统，不能使用常规 adb 工具箱，请通过命令行操作。

**前置条件**

- 已安装 adb 命令行工具
- 已获取词典笔的 adb 密码
- 数据线连接电脑与词典笔

**第一步：连接并认证**

```bash
adb shell auth success
```

**第二步：推送安装包到设备**

```bash
adb push <本地文件路径> /userdisk/<文件名>.amr
```

示例：

```bash
adb push C:\Users\hdh\Desktop\loli_v1.5.amr /userdisk/loli_v1.5.amr
```

**第三步：安装**

```bash
adb shell miniapp_cli install /userdisk/<文件名>.amr
```

示例：

```bash
adb shell miniapp_cli install /userdisk/loli_v1.5.amr
```

解除词典笔 adb 限制的教程：https://m.bilibili.com/opus/1041644000127221764

---

## 社群

本项目由 QQ 群社区维护，欢迎有编程能力的开发者加入参与开发。

- 群精华消息（请加入群聊后，在QQ/TIM中打开）：https://qun.qq.com/essence/index?gc=961114239

---

## 免责声明

本项目为社区爱好者自发维护，与有道 / 网易官方无任何关联。使用前请自行评估风险，因使用本软件导致的设备问题由用户自行承担。
