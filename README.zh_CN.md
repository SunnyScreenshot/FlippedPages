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



## Update 2023.10.24

We recommend and use the new version of `Sunny Screenshot`, with its new architecture and UI design.

更推荐和使用新版 `Sunny Screenshot`，全新架构和 UI 设计，Winks~

**官网：** [https://sunny.xmuli.tech](https://sunny.xmuli.tech/)

**GitHub：**  [https://github.com/XMuli/SunnyPages](https://github.com/XMuli/SunnyPages)





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

## 截图作品系列

很久之前就想些一个软件截图的软件，目前一共写如下三个层级的难度作品，提供大家参考

- **Ⅰ. 新手之作 ShotX**
  - 项目地址：[ShotX](https://github.com/XMuli/ShotX)   \|   [镜像](https://gitee.com/XMuli/ShotX)
  - 功       能：①基本的截图功能，复制和保存，②右键托盘及菜单，③支持 Window，MacOS，Linux，④攥写 Github-Action 的 CI/CD 自动脚本 .yml；实现自动打包和发布，⑤更多见 README 和 源码
  - 描        述：新手级的截图，适合初学 Qt/C++ 入门者
- **Ⅱ. 高级之作 FLIPPED**
  - 官       网：[flipped.xmuli.tech](https://flipped.xmuli.tech/)
  - 项目地址：[FLIPPED](https://github.com/XMuli/FlippedPages)  \|  [镜像](https://gitee.com/XMuli/FlippedPages)
  - 功       能：①贴图和钉图，②多屏截图，延时截图，自定义截图，③智能检测窗口矩形（Windows & Linux），④矩形、椭圆、箭头、画笔、马赛克、文本、序号，⑤撤销、重做（多级）、保存、取消、拷贝到剪切板，⑥截图框样式三套，且主题色提供自定义；屏幕十字线样式自定义，⑦国际化：英文、简体中文、繁体中文；字体和字号自定义，⑧支持设置窗口，托盘，截图区域之间的流畅切换，⑨更多见 README 和 源码
  - 描        述：高级难度，适合已学习 Qt/C++ 数年经验进阶，需同类型软件的代码借鉴，但可探索中独立写一个大的软件。出发于隐私安全，无任何联网功能。
- **Ⅲ. 商业级别的成熟之作 Sunny (推荐)**
  - 官       网：[sunny.xmuli.tech](https://sunny.xmuli.tech/)
  - 项目地址：[Sunny](https://github.com/XMuli/sunnypages)  \|  [镜像](https://gitee.com/XMuli/SunnyPages)
  - 功       能：是 FLIPPED 作品的超集合，常见截图功能都都包含。还包含额外的功能：① "图片翻译" (中/英/日/韩/俄等)，和"OCR 提取文字"，也支持用户私人token 的额度使用 ，② .iss 脚本和 CMake 来提供便携版，安装版，③ 绘画工具栏的亚克力效果，且支持跨平台（毛玻璃效果），④编辑文本支持富文本，同一个注释可采用多个字体和颜色等（暂未遇到其它同类软件也能做到），⑤全新的 UI/UE 设计交互，“设置窗口” 无任何缝隙拼接感，颜值达到简约美观，⑥优化截屏完成后的内存释放；⑦国际化翻译更方便，⑧CMake 重写拆分为 EXE + DLL 隔离，⑨进行代码签名，方便下载校验和防篡改，⑩成功上架 Window 的微软商店，Linux 的 深度/统信商店，以及三方的星火商店等；麒麟商店也在上架待审核
  - 描        述：基于前两个的项目经验和不足，直接重写了一套新的框架和UI界面；目前个人从代码功能和产品体验来说，已经达到 工程代码整洁、规范、稳定和健壮性，优秀的解耦机制，漂亮简约得 UI / UX 设计，可以随时应对变化的实际需求，很久之内都无需重构了。定位为 漂亮和简洁，功能实用为主。

|  项目   |                             描述                             |                           开发经验                           |
| :-----: | :----------------------------------------------------------: | :----------------------------------------------------------: |
|  ShotX  |                      功能极简的截图工具                      |           简易，新手级的截图，适合初学 Qt/C++ 入门           |
| FLIPPED |   简洁且漂亮，功能完整的截图软件；隐私安全，无任何联网功能   | 高级难度，属 Qt/C++ 数年经验的进阶作品，在借鉴同类作品的代码时，可于探索中独立完成的一个大的软件 |
|  Sunny  | 一款简洁且漂亮的截图的软件工具。亦支持图片翻译和OCR；已上架微软商店，深度/统信商店，及三方的星火商店等 | 专业级作品，适合已多年沉浸研究 Qt/C++ 经验，随心所欲写任意所需功能，**属于商业级的成熟作品，是本截图系列的最高水准之作** |



> **注：** ShotX，FLIPPED，Sunny 这三款均支持跨平台 Windows / MacOS / Linux。
>
> **笔记：** Sunny  =  FLIPPED的功能重构 + 代码重构 + UI重构 + 网络功能（图片翻译+OCR）+ 上架应用商店 + 后续新功能；而 ShotX 是最早的练手探索

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

