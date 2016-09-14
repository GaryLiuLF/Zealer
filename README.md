###前言
######一位ios程序员我们可以自己高仿一款app项目给自己练习的能力，同样也可以增强自己的本身技术，
- 这里很感[维尼的小熊](http://www.jianshu.com/users/5fe7513c7a57)和[ManoBoo](http://www.jianshu.com/users/232094594d02)两位指导老师的文章，我也跟着做了一份高仿app 评测的一款项目
- 说实话做一款高仿的app还真不是一件容易的事情，基本上所有的事情都是自己来完成，因为没有人会帮助你，只能靠自己有这种想法来完成了。
- 在讲之前我们不着急看app效果，首页我们要做的一些事情有多少，使用到的工具给大家演示一遍，
###首页我们要找到要高仿的项目官网

![Snip20160519_4.png](http://upload-images.jianshu.io/upload_images/1754828-0d5a1f4fccd2b58b.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


![Snip20160519_5.png](http://upload-images.jianshu.io/upload_images/1754828-db439c92d13cbf33.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

上两张图片就是我们动手的原因了，剩下的就开始我们动手做了(`这一步比较痛苦，会很烦躁，都想放弃的念想`)


![Snip20160519_6.png](http://upload-images.jianshu.io/upload_images/1754828-7f8597eba36f4fef.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

我用到了这三个工具来做一款``ps``, ``墨刀``， ``Charles``,这都是神器。``ps``工具这里我不做多介绍，大家都认识，也不陌生，``墨刀``这工具，我也写了有关这个工具的使用文章，我这里强调介绍一下抓包工具怎么用

- 首先第一步打开Charles这个抓包工具，最好破解版版
- 介绍我们用自己的苹果电脑共享一个WIFI，看我的截图介绍


![Snip20160519_7.png](http://upload-images.jianshu.io/upload_images/1754828-405f80af74d30a9c.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


![Snip20160519_8.png](http://upload-images.jianshu.io/upload_images/1754828-9092135b768df53b.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)



![Snip20160519_10.png](http://upload-images.jianshu.io/upload_images/1754828-e7e3134a7f3b3df2.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

- 下一步就开始连接手机了，怎么连接呢？看图步骤，文字很难说明


![Snip20160519_11.png](http://upload-images.jianshu.io/upload_images/1754828-18634ad7bcb4c39e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

- 在WIFI下找到HTTP代理，手动输入服务器的地址，就是我们电脑上的IP地址，
端口就是为8888，这个是固定的

![Snip20160519_13.png](http://upload-images.jianshu.io/upload_images/1754828-ed79ebbe417aafa3.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

##以上的步骤完了，我们到了激动人心的时刻了

![Snip20160519_18.png](http://upload-images.jianshu.io/upload_images/1754828-47ce40252ba69443.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
- 点击我们的Charles工具，你会发现我手机上很多接受到很多的请求
- 我们先来做一个例子，用新浪微博的为例，用手机打开新浪微博app我们看到


![Snip20160519_19.png](http://upload-images.jianshu.io/upload_images/1754828-ef34d6c7248e44c9.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


![Snip20160519_17.png](http://upload-images.jianshu.io/upload_images/1754828-9dbe7f588ef82a39.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
 - 我们点击`json Text` 可以看到很多数据，这些正是我们所要得要的东西
##好了，以上所有步骤都是抓包的工程，不知道你们学会了没有？不懂得可以评论回复我。
- 下面我们开始进入正题了，以上工作都弄好了，怎么样？不难吧，基本全是操作，没有写任何代码，要是换成代码估计人都不想看了。
- 我们开始讲app 开发了，进入代码阶段，先来一张效果演示图

![演示.gif](http://upload-images.jianshu.io/upload_images/1754828-143e856d82657942.gif?imageMogr2/auto-orient/strip)

- 这就是app 高仿评测的项目，我是用了故事版的方法，用纯代码的方法是在是让人头痛



![Snip20160519_21.png](http://upload-images.jianshu.io/upload_images/1754828-fcec621d7a17d388.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


![Snip20160519_22.png](http://upload-images.jianshu.io/upload_images/1754828-ce55104a93ce2d7b.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

- 这是项目大致结构，可以看到我是用了故事版来做这个项目，主要是比较快，方便很多，这个项目很简单，没有太多的代码至于布局当然没有用代码写了
- 开始说说代码吧

```
- (BOOL)application:(UIApplication *)application didFinishLaunchingWithOptions:(NSDictionary *)launchOptions {
    // Override point for customization after application launch.
    LaunchAnimationViewController *launchVC = [[LaunchAnimationViewController alloc] init];
    self.window.rootViewController = launchVC;
    
    //输出调试信息
   // [WeiboSDK enableDebugMode:YES];
    [WeiboSDK registerApp:kAppKey];
    
    [WXApi registerApp:@"wx8011e108b672eee2" withDescription:@"云石管家"];
    return YES;
}
```
- 重第一步开始我们找到`AppDelegate.m`页面中由于找到主控制

```
- (void)viewDidLoad {
    [super viewDidLoad];
    self.view.backgroundColor = [UIColor whiteColor];
    UIImageView *launchAnimationView = nil;
    if (self.view.bounds.size.width == 414.0) {
        launchAnimationView = [[UIImageView alloc] initWithFrame:CGRectMake(0, 100, self.view.bounds.size.width, 260)];
    }else{
        launchAnimationView = [[UIImageView alloc] initWithFrame:CGRectMake(0, 80, self.view.bounds.size.width, 250)];
    }
    UIImage *gifImage = [UIImage sd_animatedGIFNamed:@"iPhone-6-Crop"];
    launchAnimationView.image = gifImage;
    [self.view addSubview:launchAnimationView];
    
    [UIView animateWithDuration:0.3 delay:1.6 options:UIViewAnimationOptionTransitionCrossDissolve animations:^{
        launchAnimationView.alpha = 0;
    } completion:^(BOOL finished) {
        AppDelegate *delegate = (id)[UIApplication sharedApplication].delegate;
        UIStoryboard *storyboard = [UIStoryboard storyboardWithName:@"Main" bundle:[NSBundle mainBundle]];
        delegate.window.rootViewController=[storyboard instantiateInitialViewController];
        [delegate.window makeKeyAndVisible];
    }];
}
```

`UIStoryboard *storyboard = [UIStoryboard storyboardWithName:@"Main" bundle:[NSBundle mainBundle]];`
- 这句就是为了启动故事版，分别来到TabbarController 下主控制器，然后主控制器下分子控制器，故事版一开打界面很清晰，没有太多的代码


![Snip20160519_24.png](http://upload-images.jianshu.io/upload_images/1754828-65a40748c6fa1ba5.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

- 在故事版中，我们直接拖入UITableView控件，我这里就不演示了，故事版相对简单一点，然后实现代理方法

```
#pragma mark - UITableViewDataSource
- (NSInteger)tableView:(UITableView *)tableView numberOfRowsInSection:(NSInteger)section{
    return 5;
}

- (UITableViewCell*)tableView:(UITableView *)tableView cellForRowAtIndexPath:(NSIndexPath *)indexPath{
    static NSString *cellIdentifier = @"cell";
    FirstTableViewCell *cell = [tableView dequeueReusableCellWithIdentifier:cellIdentifier];
    
    if (cell == nil) {
        cell = [[[NSBundle mainBundle] loadNibNamed:@"FirstTableViewCell" owner:self options:nil] objectAtIndex:0];
    }
    [cell setImageForCellWithIndexpath:indexPath];
    cell.backgroundColor = [UIColor clearColor];
    return cell;
}

- (CGFloat)tableView:(UITableView *)tableView heightForRowAtIndexPath:(NSIndexPath *)indexPath{
    return 125;
}

- (void)tableView:(UITableView *)tableView didSelectRowAtIndexPath:(NSIndexPath *)indexPath{
    ZealerVideoWebViewController *zealerVideo = [[ZealerVideoWebViewController alloc] init];
    zealerVideo.type = ScrollViewTableCellRequest;
    [self.navigationController pushViewController:zealerVideo animated:YES];
}
```

 - 当然还没有完，那么开始加入控件了`UICollectionViewDataSource,ScrollViewDelegate`实现这个控件的代理方法

```
#pragma mark - UICollectionViewDataSource
- (NSInteger)collectionView:(UICollectionView *)collectionView numberOfItemsInSection:(NSInteger)section{
    return 4;
}

- (UICollectionViewCell*)collectionView:(UICollectionView *)collectionView cellForItemAtIndexPath:(NSIndexPath *)indexPath{
    FirstCollectionViewCell *cell = [collectionView dequeueReusableCellWithReuseIdentifier:@"cell" forIndexPath:indexPath];
    
    [cell setImageForCellWithIndexPath:indexPath];
    return cell;
}

- (void)collectionView:(UICollectionView *)collectionView didSelectItemAtIndexPath:(NSIndexPath *)indexPath{
    ZealerVideoWebViewController *zealerVideoVC = [[ZealerVideoWebViewController alloc] init];
    zealerVideoVC.index = indexPath.row;
    zealerVideoVC.type = ScrollViewCollectionRequest;
    [self.navigationController pushViewController:zealerVideoVC animated:YES];
}

#pragma mark - SDCycleScrollViewDelegate
- (void)cycleScrollView:(SDCycleScrollView *)cycleScrollView didSelectItemAtIndex:(NSInteger)index{
    ZealerVideoWebViewController *zealerVideoVC = [[ZealerVideoWebViewController alloc] init];
    zealerVideoVC.index = index;
    zealerVideoVC.type = ScrollViewFirstRequest;
    [self.navigationController pushViewController:zealerVideoVC animated:YES];
}
```
- 至于Cell 这个是自己可以自定义，自己想怎么写就怎么写


![Snip20160519_25.png](http://upload-images.jianshu.io/upload_images/1754828-dd5da1c34eeb95e4.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

- 至于的也是一样的方法,这就是首页怎么搭建起来的

- 好的我们看看个人中心是怎么完成的


![Snip20160519_26.png](http://upload-images.jianshu.io/upload_images/1754828-c40d4474835af6c6.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

```
- (UICollectionView*)collectionView{
    if (!_collectionView) {
        UICollectionViewFlowLayout *flowLayout = [[UICollectionViewFlowLayout alloc] init];
        flowLayout.minimumInteritemSpacing = 1;
        flowLayout.minimumLineSpacing = 1;
        flowLayout.itemSize = CGSizeMake(CELL_WIDTH -1 , CELL_WIDTH -1);
        _collectionView = [[UICollectionView alloc] initWithFrame:CGRectMake(0, headBackgroundImage.frame.size.height , SCREEN_WIDTH, SCREEN_WIDTH) collectionViewLayout:flowLayout];
        [_collectionView registerNib:[UINib nibWithNibName:@"MyCollectionViewCell" bundle:[NSBundle mainBundle]] forCellWithReuseIdentifier:@"cell"];
        _collectionView.scrollEnabled = YES;
        _collectionView.backgroundColor = [UIColor clearColor];
        _collectionView.delegate = self;
        _collectionView.dataSource = self;
    }
    return _collectionView;
}

#pragma mark - UICollectionViewDataSource
- (NSInteger)collectionView:(UICollectionView *)collectionView numberOfItemsInSection:(NSInteger)section{
    return 9;
}

- (UICollectionViewCell*)collectionView:(UICollectionView *)collectionView cellForItemAtIndexPath:(NSIndexPath *)indexPath{
    MyCollectionViewCell *cell = [collectionView dequeueReusableCellWithReuseIdentifier:@"cell" forIndexPath:indexPath];
    [cell setImageForCellWithIndexPath:indexPath];
    return cell;
}

- (void)collectionView:(UICollectionView *)collectionView didSelectItemAtIndexPath:(NSIndexPath *)indexPath{
    
    if (user) {
        
        if (indexPath.row == 5) {
            
            [MBProgressHUD showHUDAddedTo:self.view animated:YES];
            
            [[SDImageCache sharedImageCache] cleanDisk];
            
            dispatch_after(dispatch_time(DISPATCH_TIME_NOW, (int64_t)(1.0f * NSEC_PER_SEC)), dispatch_get_main_queue(), ^{
                
                [MBProgressHUD hideHUDForView:self.view animated:YES];
                
            });
        }else {
            
            AboutZealerViewController *aboutZealerVC = [[AboutZealerViewController alloc] init];
            [self.navigationController pushViewController:aboutZealerVC animated:YES];
        }
    }else {
        
        [self performSegueWithIdentifier:@"isLogin" sender:self];
    }
}
```

###结尾
- 这里我说明一下，这项目是用于故事版来完成的，相对于纯代码来写的话，有一定的难度
- 一打开故事版所有的流程全部清晰，没有用代码来写控件剩去了很多时间
- 这款项目做的的不够全面，还有很多的东西都没有实现，毕竟是高仿的，用于自己练习非常好，工作中用到的远远不止这些，在这里真的很谢谢指导老师[维尼的小熊](http://www.jianshu.com/users/5fe7513c7a57)和[ManoBoo](http://www.jianshu.com/users/232094594d02)的文章，我是看了才那种思路设计
- 本项目我会改进，图中看到`其他`的控制器根本就是一片空白，什么都没有写，这是我加入的东西.目的是为了测试
- 有什么问题和源码的可以评论回复我，自己的Github都没有搭建起来，以后时间下载地址我会放在自己的Github中让大家下载，在此抱歉