# :beers: PCB_BusinessCard <a href="https://github.com/SummerFalls/PCB_BusinessCard/blob/master/LICENSE"><img alt="License" src="https://img.shields.io/github/license/SummerFalls/PCB_BusinessCard.svg?style=flat"></a> <a title="Hits" target="_blank" href="https://github.com/SummerFalls/PCB_BusinessCard"><img src="https://hits.b3log.org/b3log/hits.svg"></a>

<div align="center">

<br/>

![PCB_BusinessCard.32][PCB_BusinessCard.32]

<hr/>
</div>

## :closed_book: 简介

基于 `Altium Designer 21` 和 `KeyShot 8` 的个人 PCB 名片工程，本工程演示了如何使用 Altium Designer 导出 3D 模型并用 KeyShot 进行渲染的操作。

<hr/>

## :gear: 软件需求

- Altium Designer 21
- KeyShot 8
- Adobe Photoshop 2020
- Adobe Acrobat DC

## :framed_picture: 其它渲染图

|                                             |                                             |
|---------------------------------------------|---------------------------------------------|
| ![PCB_BusinessCard.22][PCB_BusinessCard.22] | ![PCB_BusinessCard.28][PCB_BusinessCard.28] |
| ![PCB_BusinessCard.41][PCB_BusinessCard.41] | ![PCB_BusinessCard.42][PCB_BusinessCard.42] |

## :speech_balloon: 渲染简要步骤

1. `Altium Designer` 导出 `PARASOILD (.x_t)` 格式的 3D 模型文件
   > :warning: `.x_t` 格式可导出线路，而如果导出为 `STEP` 格式，会发现线路是缺失的。
   > ![AD导出3D模型][AD导出3D模型]
2. 使用 `KeyShot` 打开 `.x_t` 文件，此时发现 PCB 表面和元器件表面的丝印缺失，故需要分别使用两种不同方法，采用贴图的方式，将丝印分别贴到 PCB 表面和元器件表面。
   - **PCB 丝印导出 & 贴图**
     1. ![AD导出PCB丝印][AD导出PCB丝印]
     2. 用 `Photoshop` 打开刚刚导出的 PDF 文件，将导出后的 PCB 丝印 PDF 做些处理，将不必要的线路 P 掉，因为线路在 3D 文件中已经有了，之后另存为 `PNG 文件`
        > ![PCB丝印处理][PCB丝印处理]
     3. 将刚刚导出的 `PNG 文件` 作为贴图，添加到 `PCB 主板` 上，并调整位置、角度等，如下图所示
        1. 双击 `PCB 主板` 项目进入材质
           > ![双击PCB主板][双击PCB主板]
        2. 添加标签，并如图添加 `PNG 文件` 或者 `PSD 文件`，之后进行如图所示的调整
           > ![材质_添加标签并设置][材质_添加标签并设置]
        3. 使用箭头进行丝印位置的平移细调
           > ![丝印位置进一步调整][丝印位置进一步调整]
   - **元器件丝印导出 & 贴图**
     1. 下载对应芯片的数据手册，用 `Acrobat DC` 打开数据手册 PDF 文件后，找到对应封装的 package marking，并进入编辑模式进行编辑，编辑完成后保存，如图
        > ![元器件丝印导出1][元器件丝印导出1]
        > :warning: 若电脑中没有对应芯片丝印使用的字体，需要自行去下载字体文件，本例中的芯片丝印字体已经提供，右键安装即可，安装后需要重启 `Acrobat DC`
     2. 进入 `组织页面` 功能，将刚刚的一页进行单独提取导出为 PDF 文件
        > ![元器件丝印导出2][元器件丝印导出2]
     3. 将刚刚单独提取导出的 PDF 文件再次编辑，删去无关内容，如图
        > ![元器件丝印导出3][元器件丝印导出3]
     4. 用 `Photoshop` 打开该 PDF 文件，之后进行修改，再导出为 `PNG 文件`，如图
        > ![元器件丝印导出4][元器件丝印导出4]
     5. 将刚刚导出的 `PNG 文件` 作为贴图，添加到 `芯片主体` 上，并调整位置、角度等，具体操作与之前的 PCB 丝印的贴图操作类似
3. 之后，依个人喜好以及实际情况，再进行 `材质`、`颜色`、`纹理`、`环境`、`背景` 相关的调整，便能有不同的实时渲染效果，案例如图
   > ![KeyShot][KeyShot]
4. 最后，将调整好角度的实时渲染效果导出为图片
   > ![渲染导出][渲染导出]

---

## :star: License

MIT License

Copyright © 2021 SummerFalls

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

[KeyShot]: ./2.Pics/KeyShot.png
[AD导出3D模型]: ./2.Pics/AD导出3D模型.png
[AD导出PCB丝印]: ./2.Pics/AD导出PCB丝印.png
[PCB丝印处理]: ./2.Pics/PCB丝印处理.png
[双击PCB主板]: ./2.Pics/双击PCB主板.png
[材质_添加标签并设置]: ./2.Pics/材质_添加标签并设置.png
[丝印位置进一步调整]: ./2.Pics/丝印位置进一步调整.png
[元器件丝印导出1]: ./2.Pics/元器件丝印导出1.png
[元器件丝印导出2]: ./2.Pics/元器件丝印导出2.png
[元器件丝印导出3]: ./2.Pics/元器件丝印导出3.png
[元器件丝印导出4]: ./2.Pics/元器件丝印导出4.png
[渲染导出]: ./2.Pics/渲染导出.png
[PCB_BusinessCard.32]: ./2.Pics/PCB_BusinessCard.32.png
[PCB_BusinessCard.22]: ./2.Pics/PCB_BusinessCard.22.png
[PCB_BusinessCard.28]: ./2.Pics/PCB_BusinessCard.28.png
[PCB_BusinessCard.41]: ./2.Pics/PCB_BusinessCard.41.png
[PCB_BusinessCard.42]: ./2.Pics/PCB_BusinessCard.42.png
