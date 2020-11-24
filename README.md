# JPG-and-PNG-to-MNIST

将任意大小的jpg格式或者png格式转换为MINST格式数据集 (基于python3.6.9，运行于Linux系统或者WSL中)

[源码地址](https://github.com/gskielian/JPG-PNG-to-MNIST-NN-Format)


## 准备操作:

安装必须的python包pliiow和非必须软件imagemagick:

```bash
sudo apt install imagemagick // 如果需要同一图片大小则安装imagemagick
pip3 install pillow
```

## 将图片转换为MINST数据集格式


1\. 将您的jpg或png图像复制粘贴到一个类文件夹中，如所示（例如，狗-> 0，猫-> 1，...长颈鹿-> 9）

2\. 将训练集的标签写至 `batches.meta.txt`

3\. 运行rename-script.sh脚本将所有图片转换为png格式

`./resize-script.sh`

4\. 如果需要则运行resize-script.sh脚本将图片大小设置为指定格式（默认为256×256）

`./resize-script.sh`

5\. 最后，运行以下python命令将所有图片和类别折叠为单个ble二进制文件；二进制文件将以ubyte文件的形式压缩至tar中

`python3 convert-images-to-mnist-format.py`

6\. 现在，您可以用自己的数据替换任何标准mnist教程中的常规数据

## 文件关系树

文件出现的位置/png的位置的示例（忽略placeholder.txt，这只是在那里，以便git可以检入其父文件夹-由于无法提交空文件夹）
```

.
├── batches.meta.txt
├── convert-images-to-mnist-format.py
├── LICENSE
├── README.md
├── resize-script.sh
├── test-images
│   ├── 0
│   │   ├── home-cat.png
│   │   └── placeholder.txt
│   ├── 1
│   │   ├── dog-07.png
│   │   └── placeholder.txt
│   ├── 2
│   │   └── placeholder.txt
│   ├── 3
│   │   └── placeholder.txt
│   ├── 4
│   │   └── placeholder.txt
│   ├── 5
│   │   └── placeholder.txt
│   ├── 6
│   │   └── placeholder.txt
│   ├── 7
│   │   └── placeholder.txt
│   ├── 8
│   │   └── placeholder.txt
│   └── 9
│       └── placeholder.txt
└── training-images
    ├── 0
    │   ├── home-cat.png
    │   └── placeholder.txt
    ├── 1
    │   ├── dog-07.png
    │   └── placeholder.txt
    ├── 2
    │   └── placeholder.txt
    ├── 3
    │   └── placeholder.txt
    ├── 4
    │   └── placeholder.txt
    ├── 5
    │   └── placeholder.txt
    ├── 6
    │   └── placeholder.txt
    ├── 7
    │   └── placeholder.txt
    ├── 8
    │   └── placeholder.txt
    └── 9
        └── placeholder.txt
```
