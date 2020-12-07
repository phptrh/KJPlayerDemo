# KJPlayer

#### <a id="功能介绍"></a>功能介绍
KJPlayer 是一款视频播放器，AVPlayer的封装，继承UIView    
1.支持播放网络和本地视频  ☑️  
2.播放多种格式mp4  ☑️  m3u8、3gp、mov等等暂未完成  
3.视频边播边下，缓存完成视频保存本地  ☑️  
4.缓存离线观看  ☑️    
5.重力感应切换横竖屏  ☑️  
6.手势滑动改变播放进度和音量和亮度  ☑️  
7.视频支持播放完之后播放下一集  ☑️  
8.随机播放、顺序播放、重复播放  ☑️  
9.小窗口播放、锁定控制面板等等  
10.缓存管理、清除长时间不再观看的视频  
11.免费试看几分钟  
12.音频功能  
13.音频和视频混合播放  

----------------------------------------
### 框架整体介绍
* [作者信息](#作者信息)
* [功能介绍](#功能介绍)
* [更新日志](#更新日志)
* [效果图](#效果图)
* [KJPlayer 功能区](#KJPlayer)
* [KJPlayerView 展示区](#KJPlayerView)
* [打赏作者 &radic;](#打赏作者)

#### <a id="作者信息"></a>作者信息
[![Language](https://img.shields.io/badge/Language-%20Objective%20C%20-blue.svg)](https://github.com/yangKJ/KJPlayerDemo)
> Github地址：https://github.com/yangKJ  
> 简书地址：https://www.jianshu.com/u/c84c00476ab6  
> 博客地址：https://blog.csdn.net/qq_34534179  

#### <a id="作者其他库"></a>作者其他Pod库
```
/*
*********************************************************************************
*
*⭐️⭐️⭐️ ----- 本人其他库 ----- ⭐️⭐️⭐️
*
粒子效果、自定义控件、自定义选中控件
pod 'KJEmitterView'
pod 'KJEmitterView/Control' # 自定义控件
 
扩展库 - Button图文混排、点击事件封装、扩大点击域、点赞粒子效果，
手势封装、圆角渐变、倒影、投影、内阴影、内外发光、渐变色滑块等，
图片压缩加工处理、滤镜渲染、泛洪算法、识别网址超链接等等
pod 'KJExtensionHandler'
pod 'KJExtensionHandler/Foundation'
pod 'KJExtensionHandler/Language' # 多语言模块

基类库 - 封装整理常用，采用链式处理，提炼独立工具
pod 'KJBaseHandler'
pod 'KJBaseHandler/Tool' # 工具相关
pod 'KJBaseHandler/Router' # 路由相关

播放器 - KJPlayer是一款视频播放器，AVPlayer的封装，继承UIView
视频可以边下边播，把播放器播放过的数据流缓存到本地，下次直接从缓冲读取播放
pod 'KJPlayer' # 播放器功能区
pod 'KJPlayer/KJPlayerView' # 自带展示界面

轮播图 - 支持缩放 多种pagecontrol 支持继承自定义样式 自带网络加载和缓存
pod 'KJBannerView'  # 轮播图，网络图片加载 支持网络GIF和网络图片和本地图片混合轮播

加载Loading - 多种样式供选择 HUD控件封装
pod 'KJLoading' # 加载控件

菜单控件 - 下拉控件 选择控件
pod 'KJMenuView' # 菜单控件

工具库 - 推送工具、网络下载工具、识别网页图片工具等
pod 'KJWorkbox' # 系统工具
pod 'KJWorkbox/CommonBox'

异常处理库 - 包含基本的防崩溃处理（数组，字典，字符串）
pod 'KJExceptionDemo'

* 如果觉得好用,希望您能Star支持,你的 ⭐️ 是我持续更新的动力!
*
*********************************************************************************
*/
```

#### <a id="使用方法(支持cocoapods/carthage安装)"></a>Pod使用方法
```
pod 'KJPlayer'  # 播放器功能区
pod 'KJPlayer/KJPlayerView'  # 自带展示界面
```

#### <a id="更新日志"></a>更新日志
```
####版本更新日志:
#### Add 1.0.8
1.引入头文件 KJPlayerHeader
2.修复切换视频清晰度之后从头播放
3.扩大按钮点击域KJPlayerButtonTouchAreaInsets

#### Add 1.0.6
1.重构KJDefinitionView清晰度面板
2.配置信息类KJPlayerViewConfiguration新增属性 continuePlayWhenAppReception 控制是否后台返回播放
3.工具类KJPlayerTool 新增 kj_playerValidateUrl 判断当前URL是否可用

#### Add 1.0.5
1.重新更新KJPlayer播放方式
2.新增清晰度选择

#### Add 1.0.4
1.新增 KJFileOperation 文件操作类
2.KJPlayerView 重新布局添加控件
3.修复不能播放长视频BUG

#### Add 1.0.3
1.增加播放类型功能 重复播放、随机播放、顺序播放、仅播放一次
2.优化提高播放器稳定性和降低性能消耗
3.新增 KJPlayerViewConfiguration 类用来管理设置默认属性
4.完善全屏布局 完善 KJFastView 快进倒退展示区
5.完成手势快进快退、手势改变音量、完成重力感应改变屏幕方向

#### Add 1.0.2
1.完善 KJPlayerView 展示界面
2.修改bug

#### Add 1.0.0
1.第一次提交项目
2.完善 KJPlayer 功能区
```

#### <a id="效果图"></a>效果图
横屏展示效果图：

![培训活动-视频全屏](https://upload-images.jianshu.io/upload_images/1933747-3d64de1b9d073891.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

竖屏目前展示效果：

![WechatIMG10.jpeg](https://upload-images.jianshu.io/upload_images/1933747-537dbd09082b0153.jpeg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

#### <a id="KJPlayer"></a>KJPlayer

- KJPlayerTool：主要提供一些播放器的工具  判断是否含有视频轨道  获取视频第一帧图片和总时长等等  
- KJRequestTask：网络缓存类   网络请求结束的时候，如果数据完整，则把数据缓存到指定的路径，储存起来，如果不完整，则删除缓存的临时文件数据
- KJPlayerURLConnection：网络和Player的中转类   把网络请求缓存到本地的临时数据`offset`和`videoLength`传递给播放器

<!--爱学习-->

##### 代码事例
```
UIButton *button = [UIButton buttonWithType:(UIButtonTypeCustom)];
button.frame = CGRectMake(0, 0, 120, 30);
button.center = CGPointMake(self.view.frame.size.width/2, self.view.frame.size.height/2+50);
[button setTitle:@"自带展示区控制器" forState:(UIControlStateNormal)];
button.titleLabel.font = [UIFont systemFontOfSize:12];
button.backgroundColor = UIColor.greenColor;
[self.view addSubview:button];
[button addTarget:self action:@selector(butAction:) forControlEvents:(UIControlEventTouchUpInside)];

UIView *view = [[UIView alloc] initWithFrame:CGRectMake(0, 20, [UIScreen mainScreen].bounds.size.width, [UIScreen mainScreen].bounds.size.width*9/16)];
view.backgroundColor = UIColor.cyanColor;
[self.view addSubview:view];

NSURL *url = [NSURL URLWithString:@"https://mp4.vjshi.com/2018-03-30/1f36dd9819eeef0bc508414494d34ad9.mp4"];

KJPlayer *player = [KJPlayer sharedInstance];
self.player = player;
player.delegate = self;
AVPlayerLayer *playerLayer = [player kj_playerPlayWithURL:url];
[player kj_playerSeekToTime:0];
playerLayer.frame = view.bounds;
[view.layer addSublayer:playerLayer];
```
##### 委托代理
```
#pragma mark - KJPlayerDelegate
- (void)kj_player:(nonnull KJPlayer *)player LoadedProgress:(CGFloat)loadedProgress LoadComplete:(BOOL)complete SaveSuccess:(BOOL)saveSuccess {
    NSLog(@"Load:%.2f==%d==%d",loadedProgress,complete,saveSuccess);
}
- (void)kj_player:(nonnull KJPlayer *)player Progress:(CGFloat)progress CurrentTime:(CGFloat)currentTime DurationTime:(CGFloat)durationTime {
    NSLog(@"Time:%.2f==%.2f==%.2f",progress,currentTime,durationTime);
}
- (void)kj_player:(nonnull KJPlayer *)player State:(KJPlayerState)state ErrorCode:(KJPlayerErrorCode)errorCode {
    NSLog(@"State:%ld==%ld",state,errorCode);
}
- (void)butAction:(UIButton*)sender{
    PlayViewController *vc = [PlayViewController new];
    vc.view.backgroundColor = UIColor.whiteColor;
    UINavigationController *nav = [[UINavigationController alloc]initWithRootViewController:vc];
    nav.navigationBar.hidden = YES;
    [self presentViewController:nav animated:YES completion:^{
        [self.player kj_playerStop];
    }];
}
```

#### <a id="KJPlayerView"></a>KJPlayerView
提供一套完整的布局界面，视图属性我全部暴露在外界，这样方便修改和重新布局 `pod 'KJPlayer/KJPlayerView'` 

- KJPlayerViewConfiguration：配置信息  
- KJPlayerViewHeader：宏文件  
- KJLightView：亮度管理  
- KJFastView：快进倒退管理  
- KJDefinitionView：清晰度展示面板 

#### 获取当前播放视频地址的算法
如果你们需要不同的算法方式，请修改就完事

```
/// 得到当前播放的视频地址
- (NSString*)kj_getCurrentURL{
    return ({
        NSString *name;
        switch (_videoModel.priorityType) {
            case KJPlayerViewModelPriorityTypeSD:
                name = kj_getPlayURL(_videoModel.sd,_videoModel.cif,_videoModel.hd);
                break;
            case KJPlayerViewModelPriorityTypeCIF:
                name = kj_getPlayURL(_videoModel.cif,_videoModel.sd,_videoModel.hd);
                break;
            case KJPlayerViewModelPriorityTypeHD:
                name = kj_getPlayURL(_videoModel.hd,_videoModel.cif,_videoModel.sd);
                break;
            default:
                break;
        }
        name;
    });
}
static inline NSString * kj_getPlayURL(NSString*x,NSString*y,NSString*z){
    return (x || y) == 0 ? z : (x?:y);
}
``` 

##### 展示区代码事例
```
@interface ViewController ()<KJPlayerViewDelegate>
@property(nonatomic,strong) KJPlayerView *playerView;
@end

@implementation ViewController

/// 电池状态栏管理
- (BOOL)prefersStatusBarHidden{
    if (self.playerView) {
        return _playerView.configuration.fullScreen;
    }else{
        return NO;
    }
}

- (void)viewDidLoad {
    [super viewDidLoad];

    // Do any additional setup after loading the view.
    [self.view addSubview:self.playerView];
}

- (KJPlayerView*)playerView{
    if (!_playerView) {
        KJPlayerViewConfiguration *configuration = [[KJPlayerViewConfiguration alloc]init];
        configuration.autoHideTime = 0.0;
        configuration.playType = KJPlayerPlayTypeOrder;
        KJPlayerView *view = [[KJPlayerView alloc] initWithFrame:CGRectMake(0, 20, [UIScreen mainScreen].bounds.size.width, [UIScreen mainScreen].bounds.size.width*9/16) Configuration:configuration];
        _playerView = view;
        view.backgroundColor = UIColor.blackColor;
        view.delegate = self;

        NSArray *temp = @[@"https:apps.winpow.com/attached/media/mp4/1559550527183.mp4",
                        @"http:appit.winpow.com/attached/media/MP4/1567585643618.mp4",
                        @"https:devstreaming-cdn.apple.com/videos/streaming/examples/bipbop_4x3/gear1/prog_index.m3u8",
                        @"https:mp4.vjshi.com/2018-08-31/3ba67e58deb45fefe7f7d3d16dbf2b16.mp4",
                        @"https:mp4.vjshi.com/2017-07-02/0cbbf21c6003f7936f4086dd10e7ebf5.mp4",
                        @"https:mp4.vjshi.com/2018-03-30/1f36dd9819eeef0bc508414494d34ad9.mp4",
                        ];
        NSMutableArray *array = [NSMutableArray array];
        for (NSInteger i=0; i<2; i++) {
            KJPlayerViewModel *model = [KJPlayerViewModel new];
            if (i==0) {
                model.sd = temp[0];
                model.cif = temp[1];
            }else if (i==1) {
                model.hd = temp[2];
            }else{
                model.sd = temp[3];
                model.hd = temp[4];
            }
            [array addObject:model];
        }
        view.videoIndex = 0;
        view.videoModelTemps = array;
    }
    return _playerView;
}
```
#### 委托代理
```
#pragma mark - KJPlayerViewDelegate
- (BOOL)kj_PlayerView:(KJPlayerView *)playerView DeviceDirection:(KJPlayerDeviceDirection)direction{
    /// 重置电池状态
    [self setNeedsStatusBarAppearanceUpdate];
    return NO;
}
/// Bottom按钮事件  tag:520收藏、521下载、522清晰度
- (void)kj_PlayerView:(KJPlayerView*)playerView BottomButton:(UIButton*)sender{
    
}
```

----------------------------------------

#### <a id="打赏作者"></a>打赏作者
* 如果你觉得有帮助，还请为我Star
* 如果在使用过程中遇到Bug，希望你能Issues，我会及时修复
* 大家有什么需要添加的功能，也可以给我留言，有空我将补充完善
* 谢谢大家的支持 - -！

[![谢谢老板](https://upload-images.jianshu.io/upload_images/1933747-879572df848f758a.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)](https://github.com/yangKJ/KJPlayerDemo)

#### 救救孩子吧，谢谢各位老板～～～～
