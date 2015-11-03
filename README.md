# mesole.github.record

bf  记住些什么




# 控件篇
<h4> 初识控件


UILabel – ⽂文本标签<p>
● ⽂文本标签的作⽤用是显⽰示⼀一串固定的⽂文字<p>
UILabel的常见属性 @property(nonatomic,copy) NSString<p>
➢显⽰示的⽂文字 @property(nonatomic,retain) UIFont<p>
➢字体<p>
@property(nonatomic,retain) UIColor<p>
➢⽂文字颜⾊色<p>
@property(nonatomic) NSTextAlignment<p>
➢对齐模式(⽐比如左对齐、居中对齐、右对齐) @property(nonatomic) NSInteger numberOfLines;<p>
➢⽂文字⾏行数<p>
@property(nonatomic) NSLineBreakMode ➢换⾏行模式<p>
*text;<p>
*font;<p>
*textColor;<p>
textAlignment;<p>
lineBreakMode;<p>

UIFont<p>
● UIFont代表字体,常见创建⽅方法有以下⼏几个:<p>
➢ + (UIFont *)systemFontOfSize:(CGFloat)fontSize; 系统默认字体 <p>
➢ + (UIFont *)boldSystemFontOfSize:(CGFloat)fontSize; 粗体<p>
➢ +(UIFont*)italicSystemFontOfSize:(CGFloat)fontSize;斜体<p>

● 要想让UILabel⾃自动换⾏行,设置Lines为0即可<p>





UIImageView<p>
● UIImageView极其常⽤用,功能⽐比较专⼀一:显⽰示图⽚片<p>
UIImageView的常见属性 @property(nonatomic,retain) UIImage *image;<p>
➢显⽰示的图⽚片<p>
@property(nonatomic,copy) NSArray *animationImages;<p>
➢显⽰示的动画图⽚片<p>
@property(nonatomic) NSTimeInterval animationDuration;<p>
➢动画图⽚片的持续时间<p>
@property(nonatomic) NSInteger animationRepeatCount;<p>
➢动画的播放次数(默认是0,代表⽆无限播放)<p>

UIImageView的常见⽅方法<p>
- (void)startAnimating; // 开始动画<p>
- (void)stopAnimating; // 停⽌止动画<p>
- (BOOL)isAnimating; // 是否正在执⾏行动画<p>


<p><p><p><p><p><p>


UIButton – 按钮<p>
● 按钮的作⽤用是:监听⽤用户的点击事件,在⽤用户点击后做出响应<p>
UIButton的状态<p>
● normal(普通状态)<p>
➢ 默认情况(Default)<p>
➢ 对应的枚举常量:UIControlStateNormal<p>
● highlighted(⾼高亮状态)<p>
➢ 按钮被按下去的时候(⼿手指还未松开)<p>
➢ 对应的枚举常量:UIControlStateHighlighted<p>
● disabled(失效状态,不可⽤用状态)<p>
➢ 如果enabled属性为NO,就是处于disable状态,代表按钮不可以被点击 ➢ 对应的枚举常量:UIControlStateDisabled<p>
<p><p><p><p><p>
● 在⽤用代码创建按钮的同时指定按钮样式<p>
UIButton *btn = [UIButton buttonWithType:UIButtonTypeCustom];<p>
➢ UIButtonTypeCustom:⽆无类型,按钮的内容需要⾃自定义<p>
➢ UIButtonTypeDetailDisclosure:<p>
➢ UIButtonTypeInfoLight:<p>
➢ UIButtonTypeInfoDark:<p>
➢ UIButtonTypeContactAdd:<p>

UIButton的常见设置<p>
● - (void)setTitle:(NSString *)title forState:(UIControlState)state;<p>
➢ 设置按钮的⽂文字<p>
● - (void)setTitleColor:(UIColor *)color forState:(UIControlState)state;<p>
➢ 设置按钮的⽂文字颜⾊色<p>
● -(void)setImage:(UIImage*)imageforState:(UIControlState)state;<p>
➢ 设置按钮内部的⼩小图⽚片<p>
● - (void)setBackgroundImage:(UIImage *)image forState:(UIControlState)state; ➢ 设置按钮的背景图⽚片<p>
<p><p>
● 设置按钮的⽂文字字体(需要拿到按钮内部的label来设置)<p>
➢ btn.titleLabel.font=[UIFontsystemFontOfSize:13]; ● -(NSString*)titleForState:(UIControlState)state;<p>
➢ 获得按钮的⽂文字<p>
● - (UIColor *)titleColorForState:(UIControlState)state;<p>
➢ 获得按钮的⽂文字颜⾊色<p>
● - (UIImage *)imageForState:(UIControlState)state;<p>
➢ 获得按钮内部的⼩小图⽚片<p>
● - (UIImage *)backgroundImageForState:(UIControlState)state; ➢ 获得按钮的背景图⽚片<p>
￼
￼<p><p>
UIButton、UIImageView、UILabel的选择<p>
● 特点<p>
● UIButton<p>
- 既能显⽰示⽂文字,又能显⽰示图⽚片(能显⽰示2张图⽚片,背景图⽚片、内容图⽚片)<p>
- 长按⾼高亮的时候可以切换图⽚片\⽂文字<p>
- 直接通过addTarget...⽅方法监听点击<p>
● UIImageView<p>
- 能显⽰示图⽚片,不能直接通过addTarget...⽅方法监听点击<p>
- <p><p><p>
● UILabel<p>
- 能显⽰示⽂文字,不能直接通过addTarget...⽅方法监听点击<p>
- <p><p><p>
UIButton、UIImageView、UILabel的选择<p>
选择<p>
仅仅是显⽰示数据,不需要点击 建议选择UIImageView、UILabel<p>
不仅显⽰示数据,还需要监听点击<p>
建议选择UIButton 其实UIImageView、UILabel也可以通过⼿手势识别器来监听(后⾯面课程会学)<p>
长按控件后,会改变显⽰示的内容 不⽤用考虑了,选择UIButton(因为UIButton有highlighted这种状态)<p>
同时显⽰示2张图⽚片:背景图⽚片、内容图⽚片 不⽤用考虑了,选择UIButton<p>
￼
<p><p><p>
Plist⽂文件<p>
● 直接将数据直接写在代码⾥里⾯面,不是⼀一种合理的做法。如果数据经常改,就
● 因此,可以考虑将经常变的数据放在⽂文件中进⾏行存储,程序启动后从⽂文件中 读取最新的数据。如果要变动数据,直接修改数据⽂文件即可,不⽤用修改代码
● ⼀一般可以使⽤用属性列表⽂文件存储NSArray或者NSDictionary之类的数据,这 种“属性列表⽂文件”的扩展名是plist,因此也称为“plist⽂文件”


instancetype
● instancetype在类型表⽰示上,跟id⼀一样,可以表⽰示任何对象类型
● instancetype只能⽤用在返回值类型上,不能像id⼀一样⽤用在参数类型上
● instancetype⽐比id多⼀一个好处:编译器会检测instancetype的真实类型


类前缀
● 使⽤用Objective-C开发iOS程序时,最好在每个类名前⾯面加⼀一个前缀,⽤用来标识这个类的“⽼老家”在哪
● ⽬目的是防⽌止N个⼈人开发了⼀一样的类,冲突了
● ⽐比如Jake Will、Kate Room在同⼀一个项⽬目中都各⾃自开发了个Button类,这样的程序是不能运⾏行起来的
● 解决⽅方案:Jake Will的类名叫做JWButton,Kate Room的类名叫做KRButton


view的封装
● 如果⼀一个view内部的⼦子控件⽐比较多,⼀一般会考虑⾃自定义⼀一个view,把它内部
● 外界可以传⼊入对应的模型数据给view,view拿到模型数据后给内部的⼦子控件 设置对应的数据
● 封装控件的基本步骤
● 在initWithFrame:⽅方法中添加⼦子控件,提供便利构造⽅方法
● 在layoutSubviews⽅方法中设置⼦子控件的frame(⼀一定要调⽤用super的 layoutSubviews)
● 增加模型属性,在模型属性set⽅方法中设置数据到⼦子控件上



UITextField – ⽂文本输⼊入框
● ⽂文本输⼊入框可以弹出键盘,让⽤用户输⼊入⽂文本内容


UITextView – 能滚动的⽂文字显⽰示控件 
● 如果⽂文字内容⽐比较多,需要换⾏行显⽰示,并且需要编辑


UIProgressView – 进度条
● ⽔水平进度条,⽐比如显⽰示⽂文件的下载进度,程序的启动进度



UISlider – 滑块
● 在2个数值之间滑动选择,⽐比如调节⾳音量⼤大⼩小


UIActivityIndicator – 圈圈 
● ⼀一直在转圈圈,表⽰示让⽤用户等待



UIActionSheet – 底部弹框 
● 从底部弹出⼀一个框提⽰示⽤用户下⼀一步该做什么


UIAlertView – 对话框(中间弹框) 
● 从中间弹出⼀一个框提⽰示⽤用户下⼀一步该做什么


UIScrollView – 滚动的控件
● 如果内容⽐比较多,超出了⼀一个屏幕,就可以⽤用它来显⽰示

UIScrollView⽆无法滚动的解决办法
● 如果UIScrollView⽆无法滚动,可能是以下原因: ➢ 没有设置contentSize
➢ scrollEnabled = NO
➢ 没有接收到触摸事件:userInteractionEnabled = NO

代理方法
// scrollview正在滚动的时候调用
- (void)scrollViewDidScroll:(UIScrollView *)scrollView
{
    int Pa =  (int)(scrollView.contentOffset.x / scrollView.frame.size.width+0.5);
    page.currentPage = Pa;
    
    NSLog(@"正在滚动");
}
// 将要开始拖拽
- (void)scrollViewWillBeginDragging:(UIScrollView *)scrollView
{
    NSLog(@"将要开始拖拽");
}
// 将要结束拖拽
- (void)scrollViewWillEndDragging:(UIScrollView *)scrollView withVelocity:(CGPoint)velocity targetContentOffset:(inout CGPoint *)targetContentOffset
{
    NSLog(@"将要结束拖拽");
}
// 结束拖拽
- (void)scrollViewDidEndDragging:(UIScrollView *)scrollView willDecelerate:(BOOL)decelerate
{
    NSLog(@"结束拖拽");
}
// 停止滚动时候调用
- (void)scrollViewDidEndDecelerating:(UIScrollView *)scrollView
{
    NSLog(@"停止滚动");
}

UIScrollView的常见属性
● @property(nonatomic)CGPointcontentOffset; ➢ 这个属性⽤用来表⽰示UIScrollView滚动的位置 (其实就是内容左上⾓角与scrollView左上⾓角的间距值)
● @property(nonatomic)CGSizecontentSize;
➢ 这个属性⽤用来表⽰示UIScrollView内容的尺⼨寸,滚动范围(能滚多远)
● @property(nonatomic)UIEdgeInsetscontentInset;
➢ 这个属性能够在UIScrollView的4周增加额外的滚动区域,⼀一般⽤用来避免scrollView的内容被 其他控件挡住

● @property(nonatomic) BOOL bounces;
● 设置UIScrollView是否需要弹簧效果
● @property(nonatomic,getter=isScrollEnabled)BOOLscrollEnabled;
➢ 设置UIScrollView是否能滚动
● @property(nonatomic) BOOL showsHorizontalScrollIndicator;
➢ 是否显⽰示⽔水平滚动条
● @property(nonatomic) BOOL showsVerticalScrollIndicator; ➢ 是否显⽰示垂直滚动条

UIScrollView的缩放原理
￼实现 ● 当⽤用户在UIScrollView⾝身上使⽤用捏合⼿手势时,UIScrollView会给代理发送⼀一条消息,询问 理
相 代理究竟要缩放⾃自⼰己内部的哪⼀一个⼦子控件(哪⼀一块内容)

• 当⽤用户在UIScrollView⾝身上使⽤用捏合⼿手势时,UIScrollView会调⽤用代理的 viewForZoomingInScrollView:⽅方法,这个⽅方法返回的控件就是需要进⾏行缩放的 控件


缩放实现步骤
1. 设置UIScrollView的id<UISCrollViewDelegate> delegate代理对象
2. 设置minimumZoomScale :缩⼩小的最⼩小⽐比例
3. 设置maximumZoomScale :放⼤大的最⼤大⽐比例
4. 让代理对象实现下⾯面的⽅方法,返回需要缩放的视图控件
- (UIView *)viewForZoomingInScrollView:(UIScrollView *)scrollView;
 跟缩放相关的其他代理⽅方法
  缩放完毕的时候调⽤用
- (void)scrollViewWillBeginZooming:(UIScrollView *)scrollView
withView:(UIView *)view
正在缩放的时候调⽤用
- (void)scrollViewDidZoom:(UIScrollView *)scrollView


UIPageControl – 分页控件 
● 能显⽰示当前的页码
● 只要将UIScrollView的pageEnabled属性设置为YES,UIScrollView会被分割成多个独⽴立页⾯面,⾥里⾯面的内容就能进⾏行分页展⽰示
● ⼀一般会配合UIPageControl增强分页效果,UIPageControl常⽤用属性如下
➢ ⼀一共有多少页
@property(nonatomic) NSInteger numberOfPages; ➢ 当前显⽰示的页码
@property(nonatomic) NSInteger currentPage;
➢ 只有⼀一页时,是否需要隐藏页码指⽰示器
@property(nonatomic) BOOL hidesForSinglePage;
➢ 其他页码指⽰示器的颜⾊色
@property(nonatomic,retain) UIColor *pageIndicatorTintColor; ➢ 当前页码指⽰示器的颜⾊色
@property(nonatomic,retain) UIColor *currentPageIndicatorTintColor

NSTimer
● NSTimer叫做“定时器”,它的作⽤用如下 ➢ 在指定的时间执⾏行指定的任务
➢ 每隔⼀一段时间执⾏行指定的任务
● 调⽤用下⾯面的⽅方法就会开启⼀一个定时任务
+ (NSTimer *)scheduledTimerWithTimeInterval:(NSTimeInterval)ti
     target:(id)aTarget
   selector:(SEL)aSelector
   userInfo:(id)userInfo
   repeats:(BOOL)yesOrNo;
每隔ti秒,调⽤用⼀一次aTarget的aSelector⽅方法,yesOrNo决定了是否重复执⾏行这个任 务
● 通过invalidate⽅方法可以停⽌止定时器的⼯工作,⼀一旦定时器被停⽌止了,就不能再次执⾏行任 务。只能再创建⼀一个新的定时器才领能先执业⾏行内I新T教的育任培务训⾏行业

NSTimer
● 解决定时器在主线程不⼯工作的问题
NSTimer *timer = [NSTimer timerWithTimeInterval:2 target:self
selector:@selector(next) userInfo:nil repeats:YES];
[[NSRunLoop mainRunLoop] addTimer:timer
forMode:NSRunLoopCommonModes];



UITableView – 表格
● 如果每⼀一⾏行显⽰示的内容格式差不多,就⽤用这个表格控件

<!--UITabBarController的简单使⽤用-->
<!--● UITabBarController的使⽤用步骤-->
<!--➢ 初始化UITabBarController-->
<!--➢ 设置UIWindow的rootViewController为UITabBarController-->
<!--➢ 根据具体情况,通过addChildViewController⽅方法添加对应个数的⼦子控制器-->


UICollectionView – 九宫格
● 如果显⽰示的东西是⼀一块⼀一块、⼀一格⼀一格的,⽽而且每个格⼦子长的差不多,就可以 ⽤用它


UIWebView – ⽹网页显⽰示控件
● ⼀一般⽤用来显⽰示⽹网页,使⽤用它,就可以在⼿手机上浏览⽹网页



UISwitch – 开关 
● 要么打开,要么关上



UISegmentControl – 选项卡 
● 在固定的⼏几个选项之间进⾏行选择



UIPickerView – 选择器 
● 在多⾏行数据之间只选择⼀一⾏行



UIDatePicker – ⽇日期选择器 
● 选择⽇日期



UIToolbar – ⼯工具条
● ⼀一般显⽰示在底部或者键盘顶部,⾥里⾯面有⼏几个⼩小按钮



UINavigationBar – 导航条 
● 显⽰示在顶部的条

UINavigationController的简单使⽤用
● UINavigationController的使⽤用步骤
➢ 初始化UINavigationController
➢ 设置UIWindow的rootViewController为UINavigationController ➢ 根据具体情况,通过push⽅方法添加对应个数的⼦子控制器

UINavigationController的⼦子控制器
● UINavigationController以栈的形式保存⼦子控制器 @property(nonatomic,copy) NSArray *viewControllers; @property(nonatomic,readonly) NSArray *childViewControllers;
● 使⽤用push⽅方法能将某个控制器压⼊入栈
- (void)pushViewController:(UIViewController *)viewController
animated:(BOOL)animated;
● 使⽤用pop⽅方法可以移除控制器
➢ 将栈顶的控制器移除
- (UIViewController *)popViewControllerAnimated:(BOOL)animated;
➢ 回到指定的⼦子控制器
- (NSArray *)popToViewController:(UIViewController *)viewController animated:

修改导航栏的内容
● 导航栏的内容由栈顶控制器的navigationItem属性决定
● UINavigationItem有以下属性影响着导航栏的内容
➢ 左上⾓角的返回按钮
@property(nonatomic,retain) UIBarButtonItem *backBarButtonItem; ➢ 中间的标题视图
@property(nonatomic,retain) UIView *titleView; ➢ 中间的标题⽂文字
@property(nonatomic,copy) NSString *title; ➢ 左上⾓角的视图
@property(nonatomic,retain) UIBarButtonItem *leftBarButtonItem; ➢ UIBarButtonItem *rightBarButtonItem 右上⾓角的视图
@property(nonatomic,retain) UIBarButtonItem *rightBarButtonItem;



# UIView


• 每⼀一个控制器(UIViewController)内部都有个默认的UIView属性
- @property(nonatomic,retain) UIView *view;
- 控制器中管理的其他所有控件都是这个view的⼦子控件(直接或者间接)
- 


- 



UIView的常见属性
@property(nonatomic,readonly) UIView *superview;
➢ 获得⾃自⼰己的⽗父控件对象 @property(nonatomic,readonly,copy) NSArray *subviews;
➢ 获得⾃自⼰己的所有⼦子控件对象 @property(nonatomic) NSInteger tag;
➢ 控件的ID(标识),⽗父控件可以通过tag来找到对应的⼦子控件 @property(nonatomic) CGAffineTransform transform;
➢ 控件的形变属性(可以设置旋转⾓角度、⽐比例缩放、平移等属性) 



常见属性
- (void)addSubview:(UIView *)view;
➢ 添加⼀一个⼦子控件view
- (void)removeFromSuperview;
➢ 从⽗父控件中移除
- (UIView *)viewWithTag:(NSInteger)tag;
➢ 根据⼀一个tag标识找出对应的控件(⼀一般都是⼦子控件)



UIView的常见属性 @property(nonatomic) CGRect frame;
➢ 控件矩形框在⽗父控件中的位置和尺⼨寸(以⽗父控件的左上⾓角为坐标原点) @property(nonatomic) CGRect bounds;
➢ 控件矩形框的位置和尺⼨寸(以⾃自⼰己左上⾓角为坐标原点,所以bounds的x、y⼀一般为0) @property(nonatomic) CGPoint center;
➢ 控件中点的位置(以⽗父控件的左上⾓角为坐标原点)



如何创建⼀一个控制器
● 控制器常见的创建⽅方式有以下⼏几种 ➢ 通过storyboard创建
➢ 直接创建
MJViewController *mj = [[MJViewController alloc] init];
➢ 指定xib⽂文件来创建
MJViewController *mj = [[MJViewController alloc]
initWithNibName:@"MJViewController" bundle:nil];

通过storyboard创建控制器 
● 先加载storyboard⽂文件(Test是storyboard的⽂文件名)
UIStoryboard *storyboard = [UIStoryboard
storyboardWithName:@"Test" bundle:nil];
● 接着初始化storyboard中的控制器
➢ 初始化“初始控制器”(箭头所指的控制器)
MJViewController *mj = [storyboard
instantiateInitialViewController];
➢ 通过⼀一个标识初始化对应的控制器 MJViewController *mj = [storyboard
instantiateViewControllerWithIdentifier:@”mj"];

控制器view的延迟加载 ● 控制器的view是延迟加载的:⽤用到时再加载
● 可以⽤用isViewLoaded⽅方法判断⼀一个UIViewController的view是否已经被加载 ● 控制器的view加载完毕就会调⽤用viewDidLoad⽅方法

什么是Segue
● Storyboard上每⼀一根⽤用来界⾯面跳转的线,都是⼀一个UIStoryboardSegue对象(简称Segue)

Segue的属性
● 每⼀一个Segue对象,都有3个属性
➢ 唯⼀一标识
@property (nonatomic, readonly) NSString *identifier;
➢ 来源控制器
@property (nonatomic, readonly) id sourceViewController;
➢ ⽬目标控制器

Segue的类型
● 根据Segue的执⾏行(跳转)时刻,Segue可以分为2⼤大类型
➢ ⾃自动型:点击某个控件后(⽐比如按钮),⾃自动执⾏行Segue,⾃自动完成界⾯面跳转 ➢
⼿手动型:需要通过写代码⼿手动执⾏行Segue,才能完成界⾯面跳转
● 在恰当的时刻,使⽤用perform⽅方法执⾏行对应的Segue
[self performSegueWithIdentifier:@"login2contacts" sender:nil];

performSegueWithIdentifier:sender:
● 利⽤用performSegueWithIdentifier:⽅方法可以执⾏行某个Segue,完成界⾯面跳转
● 接performSegueWithIdentifier:sender:⽅方法的完整执⾏行过程
[self performSegueWithIdentifier:@“login2contacts” sender:nil];
// 这个self是来源控制器
1. 根据identifier去storyboard中找到对应的线,新建UIStoryboardSegue对象 ➢ 设置Segue对象的sourceViewController(来源控制器)
➢ 新建并且设置Segue对象的destinationViewController(⽬目标控制器)

1. 调⽤用sourceViewController的下⾯面⽅方法,做⼀一些跳转前的准备⼯工作并且传⼊入创建好的 Segue对象
 - (void)prepareForSegue:(UIStoryboardSegue *)segue sender:
 (id)sender;
// 这个sender是当初performSegueWithIdentifier:sender:中传⼊入的sender
2. 调⽤用Segue对象的- (void)perform;⽅方法开始执⾏行界⾯面跳转操作
(3) 如果segue的style是push
➢ 取得sourceViewController所在的UINavigationController
➢ 调⽤用UINavigationController的push⽅方法将destinationViewController压⼊入栈中,完成跳转 (4) 如果segue的style是modal
➢ 调⽤用sourceViewController的presentViewController⽅方法将destinationViewController展⽰示出 来

Sender参数的传递
[self performSegueWithIdentifier:@“login2contacts” sender:@“jack”];
- (void)prepareForSegue:(UIStoryboardSegue *)segue sender:(id)sender;


