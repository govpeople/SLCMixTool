# SLCMixTool

iOS 代码混淆(生成无用的代码和内部属性及函数)

## 设置变量
在执行文件`main.m`内修改变量.
```
SLCMixManager *mix = [SLCMixManager shared];
mix.fileHeader = @"SQZ"; //header
mix.fileName = @"QuizProject"; //文件夹名称
mix.fileNum = 150; //文件个数
[mix fire];
```
![Alt text](https://github.com/WeiKunChao/SLCMixTool/raw/master/screenShort/1.png).

## 运行
command + r 运行,文件夹(不设置的情况下，默认在桌面)生成.

![Alt text](https://github.com/WeiKunChao/SLCMixTool/raw/master/screenShort/2.png).

## 调用
代码拉进项目(或设置路径直接在工程生成)后,有一个默认调用类.
`#import "设置的fileHeader + Bullets.h"`,例如`#import "SQZBullets.h"`.

通过此类,关联工程的相对路径后调用.所有的类会生成一个对象,并且简单操作其内的属性和方法,执行完成后会立即被释放.
```
SQZBullets *buleets = [SQZBullets shared];
buleets.fullPath = @"aa/aa/QuizProject";
[buleets fire];
```

![Alt text](https://github.com/WeiKunChao/SLCMixTool/raw/master/screenShort/3.png).