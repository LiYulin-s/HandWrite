# **HandWrite Generator**
> 使用 PyQt5 编写的手写字生成器，旨在完成一些无用的手写作业任务
>本项目提供了丰富的参数设置，以满足您在生成手写字时的个性化需求
>[下载链接](https://github.com/kivvi3412/HandWrite/releases)
> 
## **功能介绍**

1. **纸张设置**：可自定义纸张宽度和高度
2. **字体选择**：支持多种字体选择
3. **字体大小**：可自由调整字体大小
4. **行距字距**：提供行距和字距调整功能
5. **留白设置**：可分别设置上下左右留白
6. **颜色选择**：支持自定义字体颜色、背景颜色、透明色（transparent）和白色（white）
7. **输入文本框**：方便输入需要生成的文字内容
8. **扰动设置**：包括行间距扰动、字体大小扰动、字间距扰动、横向笔画扰动、纵向笔画扰动和旋转笔划扰动，以模拟手写字体的自然特点
9. **bilibili教学**: [bilibili_link](https://www.bilibili.com/video/BV1324y1P7pV/?share_source=copy_web&vd_source=8f4728ca528c4f3b362697c9193278ff)

## **使用说明**
从 [releases](https://github.com/kivvi3412/HandWrite/releases/tag/Release) 中下载本软件
1. **界面如下**
![main_window.png](docs%2Fmain_window.png)
   (1 和 2)是纸张大小的宽度和高度，可以根据实际情况确定，接下来会有例子进行讲解  
   (3) 背景色选择透明色可以更方便的将输出文件覆盖在其他图片上进行打印  
   (4) 如果文本过长会被自动切分为多个页面, 这里可以选择页码进行预览  
   (5) 这里可以选择渲染精度，倍率越高，输出的文件越清晰，但是渲染速度会变慢(PNG)  
   (6) 按下export进行导出，默认导出到当前文件夹`output`目录下
2. **其他字体**
   默认字体文件夹在当前目录的`ttf_library`文件夹下，可以自行添加字体文件，但是字体文件必须是`.ttf`格式的，字体文件夹不能为空！
3. **使用例子**
![example_page.png](docs%2Fexample_page.png)  
   截图后，外围绿色方框为宽度和高度，可以用工具测量距离  
   (1, 2, 3, 4)为上下左右留白
   两根黑线之间为行距，两个字之间的距离为字距, 字体大小为粉色方框处
   字体大小不能超过行距否则会报错  
   扰动设为0，可以得到一个比较整齐的手写字体，例:
![example_parm_0.png](docs%2Fexample_parm_0.png)
   扰动设为较大，可以得到一个比较潦草的手写字体，例:
![example_parm_1.png](docs%2Fexample_parm_1.png)  
实际情况可根据实际需求进行调整

## **手动启动说明**
1. 安装依赖库
```shell
uv sync
```
2. 运行`main.py`
```shell
python main.py
```

> 若报错，`qt.qpa.plugin: Could not find the Qt platform plugin "cocoa" in`
> 
> 原因是 "同一进程里混入了两套不同签名/不同路径的 Qt 库"
> 例如 Homebrew 安装的裸 Qt （/opt/homebrew/…/libQt6…）
> 
> 解决方案：卸载homebrew的QT