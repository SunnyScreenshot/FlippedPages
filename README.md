# Flipped Package
FLIPPED Install packages offline



简介： https://xmuli.blog.csdn.net/article/details/130033621



<br>



<!-- more -->

[TOC]

<br>

> <font color=#D0087E size=4 face="STFangsong">本文初发于 "[**偕臧的小站**](https://ifmet.cn)"，同步转载于此。</font>

<br>

## FLIPPED



<div align="center">
  <p>
      <h1>
      <a href="https://github.com/XMuli/Flipped">
          <img src="https://fastly.jsdelivr.net/gh/XMuli/xmuliPic@pic/2022/202303121608051.svg"  alt="FLIPPED" />
      </a>
      <br/>
      FLIPPED
    </h1>
    <br/>
    <h4>Simple and beautiful cross-platform screenshot software.</h4>
  </p>
</div>
<br>

## 运行预览

### 视频演示

- [P1] [FLIPPED-MACOS 运行演示](https://www.bilibili.com/video/BV1rX4y1D7EZ?p=1)
- [P2] [FLIPPED-WINDOWS 运行演示](https://www.bilibili.com/video/BV1rX4y1D7EZ?p=2)
- [P3] [FLIPPED-LINUX 运行演示](https://www.bilibili.com/video/BV1rX4y1D7EZ?p=3)

<br>

### 截图演示

**MACOS**

<img src="https://fastly.jsdelivr.net/gh/XMuli/xmuliPic@pic/2022/202303121457071.jpg" width="100%"/>



**WINDOWS**

<img src="https://fastly.jsdelivr.net/gh/XMuli/xmuliPic@pic/2022/202303121616530.jpg" width="100%"/>

**LINUX**

<img src="https://fastly.jsdelivr.net/gh/XMuli/xmuliPic@pic/2022/202303121447431.jpg" width="100%"/>

<br>

## 特性

- 贴图（钉图）
- 多屏截图，延时截图，自定义截图
- 智能识别窗口矩形（Windows & Linux）
- 矩形、椭圆、箭头、画笔、马赛克、文本、序号
- 撤销、重做（多级）、保存、取消、拷贝到剪切板
- 截图框样式三套，且主题色提供自定义；屏幕十字线样式自定义
- 国际化：英文、简体中文、繁体中文；字体和字号自定义
- 等，，，更新中

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
| <kbd>Shift</kbd> + <kbd>F4</kbd>                             | 快速保存截图           | 局部 |
| <kbd>Esc</kbd>                                               | 退出                   | 局部 |
|                                                              |                        |      |
| <kbd>F6</kbd>                                                | 窗口智能截图           | 全局 |
| <kbd>F7</kbd>                                                | 延时截图               | 全局 |
| <kbd>F8</kbd>                                                | 全屏截图               | 全局 |

<br>

## 架构思路

技术架构属初看觉着很简单，耗时几天就能写一个 Demo 级的截图，如很早写的 [ShotX](https://github.com/XMuli/ShotX)。

但后来心心念念，准备正式写一个具有高级/商业的软件时候，就属于有点规模。其属细节点超级多；

<br>

### 思路

1. 创建一个 QWidget 窗口，去掉标题栏后，全屏且置顶
2. 捕获此刻多屏幕状态保存为 QPixamp，然后绘画在 QWidget 最底层
3. 再绘画一层透明黑色作为遮罩
4. 将 QWidget 放于虚拟桌面的左上角；后面注意相对坐标和绝对坐标的转换
5. 判断当前所处模式：Wait / Select / Move /  Draw / Stretch，标记
6. 根据模式标记，对鼠标的  Press / Move / Release 事件进行对应的操作；重点是鼠标放下和松开时的 QPoint 
   - 捕获模式：智能窗口 / 全屏截图 / 延时截图 / 自定义截图 等
   - 绘画模式则细分：一级绘画栏和二级绘画栏（愈加精确的参数）
   - 拉伸可为：拉伸已绘图形 / 选中框 / ... ，操作是可见区域的任意一个图案
   - 移动同上类似
7. 重复迭代步骤 6，进行标注等功能
8. 导出图片保存到本机路径 / 剪切板。
9. 亦可直接贴图（钉住）在屏幕上，然后进行缩放和透明度等操作，作为写作时的参照。

<br>

## 编译

### 依赖

- Qt >= 5.15.2
- CMake >= 3.16
- MSVC >= 2019 | MinGW >=  8.1.0 | GCC >= 9.4 | Clang >= 12.0

	备注: 这是已经成功编译的一些版本，在更低的版本未经过测试。

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

- **代码构成:**

   <img src="https://fastly.jsdelivr.net/gh/XMuli/xmuliPic@pic/2022/202303121626081.png" width="70%"/>

<br>

## 运行效果

构建各个平台后的包，附上另外一些实际运行图。**Other** 更多截图效果可 → 在此预览

<img src="https://fastly.jsdelivr.net/gh/XMuli/xmuliPic@pic/2022/202303121524707.jpg" width="100%"/>

<img src="https://fastly.jsdelivr.net/gh/XMuli/xmuliPic@pic/2022/202303121441470.jpg" width="100%"/>

<img src="https://fastly.jsdelivr.net/gh/XMuli/xmuliPic@pic/2022/202303121623966.png" width="100%"/>

<br>

<img src="https://fastly.jsdelivr.net/gh/XMuli/xmuliPic@pic/2022/202303121524281.jpg" width="100%"/>

<img src="https://fastly.jsdelivr.net/gh/XMuli/xmuliPic@pic/2022/202303121447407.jpg" width="100%"/>

<img src="https://fastly.jsdelivr.net/gh/XMuli/xmuliPic@pic/2022/202303121621557.png" width="100%"/>

<img src="https://fastly.jsdelivr.net/gh/XMuli/xmuliPic@pic/2022/202303121621671.png" width="100%"/>

<img src="https://fastly.jsdelivr.net/gh/XMuli/xmuliPic@pic/2022/202304081932040.png" width="50%"/><img src="https://fastly.jsdelivr.net/gh/XMuli/xmuliPic@pic/2022/202303121514627.jpg" width="50%"/><img src="https://fastly.jsdelivr.net/gh/XMuli/xmuliPic@pic/2022/202304081931040.png" width="50%"/><img src="https://fastly.jsdelivr.net/gh/XMuli/xmuliPic@pic/2022/202303121514907.jpg" width="50%"/><img src="https://fastly.jsdelivr.net/gh/XMuli/xmuliPic@pic/2022/202304081930048.png" width="50%"/><img src="https://fastly.jsdelivr.net/gh/XMuli/xmuliPic@pic/2022/202304081932046.png" width="50%"/>

 <img src="https://fastly.jsdelivr.net/gh/XMuli/xmuliPic@pic/2022/202303121515818.jpg" width="30%"/> <img src="https://fastly.jsdelivr.net/gh/XMuli/xmuliPic@pic/2022/202303121522838.jpg" width="30%"/>

<br>

## 作者

[![alt text](https://img.shields.io/badge/QQ-%E5%81%95%E8%87%A7-brightgreen)](https://sighttp.qq.com/authd?IDKEY=31f3ef7312b39e2c8dc822ae2f4c3b3118e1a6f31cc83373) : 直接和我聊天~           |    [![alt text](https://img.shields.io/badge/GitHub-XMuli-brightgreen)](https://github.com/XMuli) : 查看我的主页

[![alt text](https://img.shields.io/badge/Blog-%E5%81%95%E8%87%A7%E7%9A%84%E5%B0%8F%E7%AB%99-ff69b4)](https://ifmet.cn/) : 好奇我的小窝    |    [![alt text](https://img.shields.io/badge/Blog-国内镜像-ff69b4)](https://blog.csdn.net/qq_33154343) ：浏览量 100W+

<br>

## 贡献者

若是帮助到了你，或者觉得有用，<font color=#FE7207  size=4 face="幼圆">可以点击该项目的的 <font color=#D0087E size=4 face="幼圆">**⭐Star** </font>和<font color=#D0087E size=4 face="幼圆">**🍴 Fork**</font> 的两个图标，方便抬手之间，表示点个赞，手有余香，</font>其次才是一份冰的肥宅快乐水。 → [project-flipped](https://github.com/XMuli/FlippedPackage)

<br>

<details>
    <summary> <b>当然也可以赠与一杯冰阔落[捐赠/打赏  ← 点击展开二维码]</b></summary>
  <p> - 若是此项目帮助到了你，或者觉得有用，或是想帮助此项目的发展，你也能够邀请我喝一杯杯肥仔快乐水。 - </p>
  <pre><img src="https://fastly.jsdelivr.net/gh/XMuli/xmuliPic@pic/2022/202302282339037.png" width="80%"/></pre>
</details>
<br>

## 反馈 & 贡献

非常欢迎你的加入！对于此软件有任何缺陷、建议、功能想法、都可 [提一个 Issue](https://github.com/XMuli/FlippedPackage/issues) ；或者帮助此项目的完善，提交一个 Pull Request。

请遵循 [Contributor Covenant](http://contributor-covenant.org/version/1/3/0/) 行为规范。

<br>

## 下载安装包

→ 离线安装包下载 [Releases](https://github.com/XMuli/FlippedPackage/releases) ；

→ **反馈 BUG/SUGGEST，用户社区等，和最新版本安装包获取，在QQ群:[418103279](https://qm.qq.com/cgi-bin/qm/qr?k=jsD03QzMohGZm0TqYAFh3BvKOpCGlTcT&jump_from=webapi&authKey=DMUwiCQ6ta95PoH8JmtZ+Jz9y7Ozg3yinEsxmm92rNXZRVeMPD7NRgjU+dmUI8Xu)**

<br>

## 系列地址

[QtExamples](https://github.com/XMuli/QtExamples)     欢迎 `star` ⭐ 和 `fork` 🍴这个系列的 `C++ / QT / DTK` 学习，附学习由浅入深的目录

[ExCMake](https://github.com/XMuli/ExCMake)          欢迎 `star` ⭐ 和 `fork` 🍴这个系列的 `CMake` 学习，附学习由浅入深的目录



