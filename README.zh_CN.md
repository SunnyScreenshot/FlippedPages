<div align="center">
  <p>
      <h1>
      <a href="https://github.com/XMuli/FlippedPages">
          <img src="docs/snapshot/Flipped.svg"  alt="FLIPPED" />
      </a>
      <br/>
      FLIPPED
    </h1>
    <br/>
    <h4>漂亮且简易的跨平台截图贴图的软件。</h4>
  </p>
  <p>
      <a href="https://github.com/XMuli/FlippedPages/releases">
      <img src="https://img.shields.io/github/languages/code-size/XMuli/FlippedPages" alt="code-size" />
    </a>
    <a href="https://github.com/XMuli/FlippedPackage/releases">
      <img src="https://img.shields.io/github/downloads/XMuli/FlippedPages/total" alt="Total Downloads" />
    </a>
  <a href="https://github.com/XMuli/FlippedPackage">
      <img src="https://img.shields.io/github/release/XMuli/FlippedPages.svg?label=docs" alt="Docs" />
    </a>
    </a>
  </p>
  <p align="right"><br><a href="README.md">English</a> | <a href="README.zh_CN.md">简体中文</a></p>
</div>

[TOC]

<br>

## 特性

- 贴图（钉图）
- 多屏截图，延时截图，自定义截图
- 智能识别窗口矩形（Windows & Linux）
- 矩形、椭圆、箭头、画笔、马赛克、文本、序号
- 撤销、重做（多级）、保存、取消、拷贝到剪切板
- 截图框样式三套，且主题色提供自定义；屏幕十字线样式自定义
- 国际化：英文、简体中文、繁体中文；字体和字号自定义
- 更新中

<br>

## 运行预览

### 视频演示

- [P1] [FlippedPages-MACOS 运行演示](https://www.bilibili.com/video/BV1rX4y1D7EZ?p=1)
- [P2] [FlippedPages-WINDOWS 运行演示](https://www.bilibili.com/video/BV1rX4y1D7EZ?p=2)
- [P3] [FlippedPages-MACOS_WINDOWS_LINUX 运行演示](https://www.bilibili.com/video/BV1rX4y1D7EZ?p=3)

<br>

### 截图演示

**MACOS**

<img src="https://fastly.jsdelivr.net/gh/XMuli/xmuliPic@pic/2022/202303121457071.jpg" width="100%"/>

<img src="https://fastly.jsdelivr.net/gh/XMuli/xmuliPic@pic/2022/202303121524707.jpg" width="100%"/>

**WINDOWS**

<img src="https://fastly.jsdelivr.net/gh/XMuli/xmuliPic@pic/2022/202303121616530.jpg" width="100%"/>

<img src="https://fastly.jsdelivr.net/gh/XMuli/xmuliPic@pic/2022/202303121524281.jpg" width="100%"/>

**LINUX**

<img src="https://fastly.jsdelivr.net/gh/XMuli/xmuliPic@pic/2022/202303121447431.jpg" width="100%"/>

<br>

<font color=#D0087E size=4 face="幼圆"> **其它：** 更多截图效果可 → [在此](docs/snapshot) 预览 </font>

<br>

## 快捷键

| 按键                                                         | 描述                   | 模式 |
| ------------------------------------------------------------ | ---------------------- | ---- |
| <kbd>←</kbd>, <kbd>↓</kbd>, <kbd>↑</kbd>, <kbd>→</kbd> ( <kbd>A</kbd>, <kbd>S</kbd>, <kbd>W</kbd>, <kbd>D</kbd> ) | 移动选中框位置 1 像素  | 局部 |
| <kbd>Ctrl</kbd> + <kbd>←</kbd>, <kbd>↓</kbd>, <kbd>↑</kbd>, <kbd>→</kbd> | 扩展选中框尺寸 1 像素  | 局部 |
| <kbd>Alt</kbd> + <kbd>←</kbd>, <kbd>↓</kbd>, <kbd>↑</kbd>, <kbd>→</kbd> | 收缩选中框尺寸 1 像素  | 局部 |
| <kbd>Shift</kbd> + <kbd>←</kbd>, <kbd>↓</kbd>, <kbd>↑</kbd>, <kbd>→</kbd> | 移动选中框位置 10 像素 | 局部 |
| <kbd>Shift</kbd> + <kbd>Ctrl</kbd> + <kbd>←</kbd>, <kbd>↓</kbd>, <kbd>↑</kbd>, <kbd>→</kbd> | 扩展选中框尺寸 10 像素 | 局部 |
| <kbd>Shift</kbd> + <kbd>Alt</kbd> + <kbd>←</kbd>, <kbd>↓</kbd>, <kbd>↑</kbd>, <kbd>→</kbd> | 收缩选中框尺寸 01 像素 | 局部 |
| <kbd>Shift</kbd> + <kbd>F4</kbd>                             | 快速保存图片           | 局部 |
| <kbd>Esc</kbd>                                               | 退出                   | 局部 |
|                                                              |                        |      |
| <kbd>F6</kbd>           | 窗口智能截图           | 全局 |
| <kbd>F7</kbd>           | 延时截图               | 全局 |
| <kbd>F8</kbd>           | 全屏截图               | 全局 |

<br>

## 编译

### 依赖

- Qt >= 5.15.2
- CMake >= 3.16
- MSVC >= 2019 | MinGW >=  8.1.0 | GCC >= 9.4 | Clang >= 12.0

​	备注: 这是已经成功编译的一些版本，在更低的版本未经过测试。

<br>

### Windows

- **工具链:** Windows 10 & Qt 5.15.2 & CMake 3.24.1 & MSVC 2019 ( or MinGW 8.1.0)

- **编译步骤:**

  ```bash
  # ******************** MSVC 2019 ********************
  #『Step1』
  # x86:
  # 添加 "C:\Qt\5.15.2\msvc2019\bin" 到 path 后，终端执行 echo %PATH% 使其立即生效
  "C:\Program Files (x86)\Microsoft Visual Studio\2019\Professional\VC\Auxiliary\Build\vcvarsall.bat" x86
  cmake -G "Visual Studio 16 2019" -A Win32 ..
  devenv Flipped.sln /Build "Release|Win32"
  
  # x64:
  # 添加 "C:\Qt\5.15.2\msvc2019_64\bin" 到 path 后，终端执行 echo %PATH% 使其立即生效
  "C:\Program Files (x86)\Microsoft Visual Studio\2019\Professional\VC\Auxiliary\Build\vcvarsall.bat" x64
  cmake -G "Visual Studio 16 2019" -A x64 ..
  devenv Flipped.sln /Build "Release|x64"
  
  #『Step2』
  Visual Studio 2019 open `Flipped.sln`
  
  #『Step3』
  windeployqt  bin/Flipped.exe --no-translations
  
  # ******************** MinGW 8.1.0 ********************
  QtCreator opens the `CMakeLists.txt` file in the root directory of the source code
  ```

<br>

### MacOS / Linux

- **工具链:** 

  - **MacOS:** MacOS 10.15 & Qt 5.15.2 & CMake 3.24 & Clang 12.0
  - **Linux:** Ubuntu 20.04 & Qt 5.15.2 & CMake 3.24 & GCC 9.4

- **编译步骤:**

  ```bash
  git clone --recursive https://github.com/XMuli/Flipped.git
  cd Flipped
  mkdir build & cd build
  cmake ..
  make -j16
  ```

<br>

## 作者

| [![alt text](https://img.shields.io/badge/GitHub-XMuli-brightgreen)](https://github.com/XMuli) : 我的主页 | [![alt text](https://img.shields.io/badge/Blog-%E5%81%95%E8%87%A7%E7%9A%84%E5%B0%8F%E7%AB%99-ff69b4)](https://ifmet.cn/) : 好奇我的小窝 |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| [![alt text](https://img.shields.io/badge/QQ-XMuli-brightgreen)](https://sighttp.qq.com/authd?IDKEY=31f3ef7312b39e2c8dc822ae2f4c3b3118e1a6f31cc83373) : 直接和我聊天~ | [![alt text](https://img.shields.io/badge/Blog-国内镜像-ff69b4)](https://blog.csdn.net/qq_33154343) ：浏览量 100W+ |

<br>

## 贡献者

若是帮助到了你，或者觉得有用，<font color=#FE7207  size=4 face="幼圆">可以点击该项目的的 <font color=#D0087E size=4 face="幼圆">**⭐Star** </font>和<font color=#D0087E size=4 face="幼圆">**🍴 Fork**</font> 的两个图标，方便抬手之间，表示点个赞，手有余香，</font>其次才是一份冰的肥宅快乐水。

<br>

<details>
    <summary> <b>当然也可以赠与一杯冰阔落[捐赠/打赏  ← 点击展开二维码]</b></summary>
  <p> - 若是此项目帮助到了你，或者觉得有用，或是想帮助此项目的发展，你也能够邀请我喝一杯杯肥仔快乐水。 - </p>
  <pre><img src="https://fastly.jsdelivr.net/gh/XMuli/xmuliPic@pic/2022/202302282339037.png" width="80%"/></pre>
</details>
<br>

## 反馈 & 贡献

非常欢迎你的加入！对于此软件有任何缺陷、建议、功能想法、都可 [提一个 Issue](https://github.com/XMuli/FlippedPages/issues) ；或者帮助此项目的完善，提交一个 Pull Request。

<br>

## 版本下载

<font color=#D0087E>→ 离线安装包下载 [Releases](https://flipped.xmuli.tech/); </font>

<font color=#D0087E>→ **反馈 BUG/SUGGEST，用户划水交流等，和最新版本安装包获取 → [![alt text](https://img.shields.io/badge/QQ_Groups-418103279-brightgreen)](https://qm.qq.com/cgi-bin/qm/qr?k=jsD03QzMohGZm0TqYAFh3BvKOpCGlTcT&jump_from=webapi&authKey=DMUwiCQ6ta95PoH8JmtZ+Jz9y7Ozg3yinEsxmm92rNXZRVeMPD7NRgjU+dmUI8Xu) ** </font>

<br>

## 系列地址

[QtExamples](https://github.com/XMuli/QtExamples)     欢迎 `star` ⭐ 和 `fork` 🍴这个系列的 `C++ / QT / DTK` 学习，附学习由浅入深的目录

