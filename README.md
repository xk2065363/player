# SBPlayer_iOS

#### 基于AVPlayer封装的轻量级播放器,可以播放本地网络视频,易于定制

##### SBPlayer结构简单,可以`横屏竖屏`,支持`M3u8、mp4`等格式视频本地播放或者网络播放,通过masonry约束，适配各种尺寸iPhone。


![3](https://github.com/shibiao/SBPlayer_iOS/blob/master/Images/23.gif)


***
#### 使用方法：
##### 拖拽SBPlayer文件夹到项目中，并添加[Masonry](https://github.com/SnapKit/Masonry)约束第三方库，然后导入`SBPlayer.h`即可

##### 导入` #import "SBPlayer" `,用xib更简单，使用如下：

```
//纯代码请用此种方法
    //http://ivi.bupt.edu.cn/hls/cctv1hd.m3u8 直播网址
    //初始化播放器
    self.player = [[SBPlayer alloc]initWithUrl:[NSURL URLWithString:@"http://download.3g.joy.cn/video/236/60236937/1451280942752_hd.mp4"]];
    //设置标题
    [self.player setTitle:@"这是一个标题"];
    //设置播放器背景颜色
    self.player.backgroundColor = [UIColor blackColor];
    //设置播放器填充模式 默认SBLayerVideoGravityResizeAspectFill，可以不添加此语句
    self.player.mode = SBLayerVideoGravityResizeAspectFill;
    //添加播放器到视图
    [self.view addSubview:self.player];
    //约束，也可以使用Frame
    [self.player mas_makeConstraints:^(MASConstraintMaker *make) {
        make.top.right.left.mas_equalTo(self.view);
        make.height.mas_equalTo(@250);
    }];
    
    /**
     使用xib请用第二种方法
     [self.player assetWithURL:[NSURL URLWithString:@"http://download.3g.joy.cn/video/236/60236937/1451280942752_hd.mp4"]];
     [self.player setTitle:@"这是一个标题"];
     */

```

SBPlayer macOS版 : http://www.jianshu.com/p/1ad52c702190
* github: [github](https://github.com/shibiao)
* 详细请看简书： [iOS通过AVPlayer打造自己的视频播放器](http://www.jianshu.com/p/ffe1bd598bf2)
# player
