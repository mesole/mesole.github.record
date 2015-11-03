# mesole.github.record

bf  记住些什么




# 控件篇
<h5> 初识控件


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
- (BOOL)isAnimating; // 是否正在执⾏行动画<p><p>


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
● 直接将数据直接写在代码⾥里⾯面,不是⼀一种合理的做法。如果数据经常改,就<p>
● 因此,可以考虑将经常变的数据放在⽂文件中进⾏行存储,程序启动后从⽂文件中<p><p> 读取最新的数据。如果要变动数据,直接修改数据⽂文件即可,不⽤用修改代码<p>
● ⼀一般可以使⽤用属性列表⽂文件存储NSArray或者NSDictionary之类的数据,这<p> 种“属性列表⽂文件”的扩展名是plist,因此也称为“plist⽂文件”<p>

<p><p><p>
instancetype<p>
● instancetype在类型表⽰示上,跟id⼀一样,可以表⽰示任何对象类型<p>
● instancetype只能⽤用在返回值类型上,不能像id⼀一样⽤用在参数类型上<p>
● instancetype⽐比id多⼀一个好处:编译器会检测instancetype的真实类型<p>

<p><p><p>
类前缀<p>
● 使⽤用Objective-C开发iOS程序时,最好在每个类名前⾯面加⼀一个前缀,⽤用来标识这个类的“⽼老家”在哪<p>
● ⽬目的是防⽌止N个⼈人开发了⼀一样的类,冲突了<p><p><p>
● ⽐比如Jake Will、Kate Room在同⼀一个项⽬目中都各⾃自开发了个Button类,这样的程序是不能运⾏行起来的<p><p>
● 解决⽅方案:Jake Will的类名叫做JWButton,Kate Room的类名叫做KRButton<p>


view的封装<p>
● 如果⼀一个view内部的⼦子控件⽐比较多,⼀一般会考虑⾃自定义⼀一个view,把它内部<p>
● 外界可以传⼊入对应的模型数据给view,view拿到模型数据后给内部的⼦子控件 设置对应的数据<p>
● 封装控件的基本步骤<p>
● 在initWithFrame:⽅方法中添加⼦子控件,提供便利构造⽅方法<p>
● 在layoutSubviews⽅方法中设置⼦子控件的frame(⼀一定要调⽤用super的 layoutSubviews)<p>
● 增加模型属性,在模型属性set⽅方法中设置数据到⼦子控件上<p>


<p><p><p>
UITextField – ⽂文本输⼊入框<p>
● ⽂文本输⼊入框可以弹出键盘,让⽤用户输⼊入⽂文本内容<p>

<p>
UITextView – 能滚动的⽂文字显⽰示控件 <p>
● 如果⽂文字内容⽐比较多,需要换⾏行显⽰示,并且需要编辑<p>
<p><p>

UIProgressView – 进度条<p>
● ⽔水平进度条,⽐比如显⽰示⽂文件的下载进度,程序的启动进度<p>

<p><p><p>

UISlider – 滑块<p>
● 在2个数值之间滑动选择,⽐比如调节⾳音量⼤大⼩小<p>
<p><p><p>

UIActivityIndicator – 圈圈 <p>
● ⼀一直在转圈圈,表⽰示让⽤用户等待<p>
<p><p><p>


UIActionSheet – 底部弹框 <p>
● 从底部弹出⼀一个框提⽰示⽤用户下⼀一步该做什么<p>
<p><p><p>

UIAlertView – 对话框(中间弹框) <p>
● 从中间弹出⼀一个框提⽰示⽤用户下⼀一步该做什么<p>

<p><p><p>
UIScrollView – 滚动的控件<p>
● 如果内容⽐比较多,超出了⼀一个屏幕,就可以⽤用它来显⽰示<p>
<p><p>
UIScrollView⽆无法滚动的解决办法<p>
● 如果UIScrollView⽆无法滚动,可能是以下原因: ➢ 没有设置contentSize<p>
➢ scrollEnabled = NO<p>
➢ 没有接收到触摸事件:userInteractionEnabled = NO<p>
<p>
代理方法<p>
// scrollview正在滚动的时候调用<p>
- (void)scrollViewDidScroll:(UIScrollView *)scrollView<p>
{<p>
    int Pa =  (int)(scrollView.contentOffset.x / scrollView.frame.size.width+0.5);<p>
    page.currentPage = Pa;<p>
    <p>
    NSLog(@"正在滚动");<p>
}<p>
// 将要开始拖拽<p>
- (void)scrollViewWillBeginDragging:(UIScrollView *)scrollView<p>
{<p>
    NSLog(@"将要开始拖拽");<p>
}<p>
// 将要结束拖拽<p>
- (void)scrollViewWillEndDragging:(UIScrollView *)scrollView withVelocity:(CGPoint)velocity<p> targetContentOffset:(inout CGPoint *)targetContentOffset<p>
{<p>
    NSLog(@"将要结束拖拽");<p>
}<p>
// 结束拖拽<p>
- (void)scrollViewDidEndDragging:(UIScrollView *<p>)scrollView willDecelerate:(BOOL)decelerate<p>
{<p>
    NSLog(@"结束拖拽");<p>
}<p>
// 停止滚动时候调用<p>
- (void)scrollViewDidEndDecelerating:(UIScrollView *)scrollView<p>
{<p>
    NSLog(@"停止滚动");<p>
}<p>
<p><p><p>
UIScrollView的常见属性<p>
● @property(nonatomic)CGPointcontentOffset; ➢ 这个属性⽤用来表⽰示UIScrollView滚动的位置<p> (其实就是内容左上⾓角与scrollView左上⾓角的间距值)<p>
● @property(nonatomic)CGSizecontentSize;<p>
➢ 这个属性⽤用来表⽰示UIScrollView内容的尺⼨寸,滚动范围(能滚多远)<p>
● @property(nonatomic)UIEdgeInsetscontentInset;<p>
➢ 这个属性能够在UIScrollView的4周增加额外的滚动区域,⼀一般⽤用来避免scrollView的内容被 其他控件挡住<p>
<p><p>
● @property(nonatomic) BOOL bounces;<p>
● 设置UIScrollView是否需要弹簧效果<p>
● @property(nonatomic,getter=isScrollEnabled)BOOLscrollEnabled;<p>
➢ 设置UIScrollView是否能滚动<p>
● @property(nonatomic) BOOL showsHorizontalScrollIndicator;<p>
➢ 是否显⽰示⽔水平滚动条<p>
● @property(nonatomic) BOOL showsVerticalS<p>crollIndicator; <p><p>
➢ 是否显⽰示垂直滚动条<p><p>

UIScrollView的缩放原理<p><p>
￼实现 ● 当⽤用户在UIScrollView⾝身上使⽤用捏合⼿手势时,UIScrollView会给代理发送⼀一条消息,询问 理<p><p>
相 代理究竟要缩放⾃自⼰己内部的哪⼀一个⼦子控件(哪⼀一块内容)<p><p>
<p><p>
• 当⽤用户在UIScrollView⾝身上使⽤用捏合⼿手势时,UIScrollView会调⽤用代理的<p><p> viewForZoomingInScrollView:⽅方法,这个⽅方法返回的控件就是需要进⾏行缩放的 控件<p><p>

<p><p>
缩放实现步骤<p><p>
1. 设置UIScrollView的id<UISCrollViewDelegate> de<p><p>legate代理对象<p><p>
2. 设置minimumZoomScale :缩⼩小的最⼩小⽐比例<p><p>
3. 设置maximumZoomScale :放⼤大的最⼤大⽐比例<p><p>
4. 让代理对象实现下⾯面的⽅方法,返回需要缩放的视图控件<p>
- (UIView *)viewForZoomingInScrollView:(UIScrollView *)scrollView;<p>
 跟缩放相关的其他代理⽅方法<p>
  缩放完毕的时候调⽤用<p>
- (void)scrollViewWillBeginZooming:(UIScrollView *)scrollView<p>
withView:(UIView *)view<p>
正在缩放的时候调⽤用<p>
- (void)scrollViewDidZoom:(UIScrollView *)scrollView<p>
<p>
<p>
UIPageControl – 分页控件 <p>
● 能显⽰示当前的页码<p>
● 只要将UIScrollView的pageEnabled属性设置为YES,UIScrollView会被分割成多个独⽴立页⾯面,⾥里⾯面的内容就能进⾏行分页展⽰示<p>
● ⼀一般会配合UIPageControl增强分页效果,UIPageControl常⽤用属性如下<p>
➢ ⼀一共有多少页<p>
@property(nonatomic) NSInteger numberOfPages; ➢ 当前显⽰示的页码<p>
@property(nonatomic) NSInteger currentPage;<p>
➢ 只有⼀一页时,是否需要隐藏页码指⽰示器<p>
@property(nonatomic) BOOL hidesForSinglePage;<p>
➢ 其他页码指⽰示器的颜⾊色<p>
@property(nonatomic,retain) UIColor *pageIndicatorTintColor; ➢ 当前页码指⽰示器的颜⾊色<p>
@property(nonatomic,retain) UIColor *currentPageIndicatorTintColor<p>
<p><p><p>
NSTimer<p><p>
● NSTimer叫做“定时器”,它的作⽤用如下 ➢ 在指定的时间执⾏行指定的任务<p><p>
➢ 每隔⼀一段时间执⾏行指定的任务<p><p>
● 调⽤用下⾯面的⽅方法就会开启⼀一个定时任务<p><p>
+ (NSTimer *)scheduledTimerWithTimeInterval:(NSTimeInterval)ti<p><p>
     target:(id)aTarget<p><p>
   selector:(SEL)aSelector<p><p>
   userInfo:(id)userInfo<p><p>
   repeats:(BOOL)yesOrNo;<p><p>
每隔ti秒,调⽤用⼀一次aTarget的aSelector⽅方法,yesOrNo决定了是否重复执⾏行这个任 务<p><p>
● 通过invalidate⽅方法可以停⽌止定时器的⼯工作,⼀一旦定时器被停⽌止了,就不能再次执⾏行任<p><p> 务。只能再创建⼀一个新的定时器才领能先执业⾏行内I新T教的育任培务训⾏行业<p><p>
<p><p>
NSTimer<p><p>
● 解决定时器在主线程不⼯工作的问题<p><p>
NSTimer *timer = [NSTimer timerWithTimeInterval:2 target:self<p><p>
selector:@selector(next) userInfo:nil repeats:YES];<p>
[[NSRunLoop mainRunLoop] addTimer:timer<p>
forMode:NSRunLoopCommonModes];<p>
<p>
<p>

UITableView – 表格<p>
● 如果每⼀一⾏行显⽰示的内容格式差不多,就⽤用这个表格控件<p>
<p>
UITabBarController<p>
● UITabBarController的使⽤用步骤<p>
➢ 初始化UITabBarController<p>
➢ 设置UIWindow的rootViewController为UITabBarController<p>
➢ 根据具体情况,通过addChildViewController⽅方法添加对应个数的⼦子控制器<p>
<p>
● UITabBarController添加控制器的⽅方式有2种 ➢ 添加单个⼦子控制器<p>
- (void)addChildViewController:(UIViewController<p>
*)childController;<p>
➢ 设置⼦子控制器数组<p>
@property(nonatomic,copy) NSArray *viewControllers;<p>
<p>
UITabBar<p>
● 如果UITabBarController有N个⼦子控制器,那么UITabBar内部就会有N 个UITabBarButton作为⼦子控件<p>
<p><p>
UITabBarButton<p><p>
● UITabBarButton⾥里⾯面显⽰示什么内容,由对应⼦子控制器的tabBarItem属性决定<p><p>
<p><p>
● UITabBarItem有以下属性影响着UITabBarButton的内容 <p><p>
➢ 标题⽂文字<p><p>
@property(nonatomic,copy) NSString *title;<p><p>
➢ 图标<p><p>
@property(nonatomic,retain) UIImage *image;<p><p>
➢ 选中时的图标<p><p>
@property(nonatomic,retain) UIImage *selectedImage<p><p>
<p><p>
<p><p>
UICollectionView – 九宫格<p><p>
● 如果显⽰示的东西是⼀一块⼀一块、⼀一格⼀一格的,⽽而且每个格⼦子长的差不多,就可以 ⽤用它<p><p>
<p><p>
<p><p>
UIWebView – ⽹网页显⽰示控件<p><p>
● ⼀一般⽤用来显⽰示⽹网页,使⽤用它,就可以在⼿手机上浏览⽹网页<p><p>
<p><p>
<p><p>

UISwitch – 开关 <p><p>
● 要么打开,要么关上<p><p>

<p>
<p>
UISegmentControl – 选项卡 <p>
● 在固定的⼏几个选项之间进⾏行选择<p>

<p>
<p>
UIPickerView – 选择器 <p>
● 在多⾏行数据之间只选择⼀一⾏行<p>
1> 注意点:PickerView的高度不能改,默认162,PickerView里面每行的高度 可以改,不要弄混淆了<p>
1> 如何使用PickerView展示数据? 进入PickerView头文件,有数据源和代理,联想到UITableView,模仿 UITableView的用法。<p>
2> 让控制器作为PickerView的数据源,控制器遵守PickerView的数据源方法<p>
2.1>两种方式:1.拖线 2.代码 2.2>系统自带的控件,数据源和代理属性不需要IBOutlet,也能拖<p> 线。自己的属性,想要拖线,必须写IBOutlet。<p>
3> PickerView的数据源方法<p>
1> numberOfComponentsInPickerView: 返回多少列<p>
2> pickerView:numberOfRowsInComponent: 返回第component列有多少 行<p>
3> 和UITableView的区别,每一行长什么样,是由PickerView的代理决 定的。<p>
4> 注意:如果没有返回每一行长什么样子,每行就会显示?,看见?,就 知道没有实现每一行长什么样子的方法。<p>
4> PickerView的代理方法<p>
1> 返回第component列第row行长什么样。<p>
第component列第row行的展示标题<p>
- (NSString *)pickerView:(UIPickerView *)pickerView titleForRow:(NSInteger)row forComponent:(NSInteger)component<p><p><p><p>
第component列第row行带属性的标题<p><p><p><p>
- (NSAttributedString *)pickerView:(UIPickerView *)pickerView attributedTitleForRow:(NSInteger)row<p><p><p><p> forComponent:(NSInteger) component<p><p><p><p>
第component列第row行展示的视图<p><p><p><p>
- (UIView *)pickerView:(UIPickerView *)pickerView viewForRow:(NSInteger)row forComponent:(NSInteger)component reusingView:(UIView *)view;<p><p><p><p>
- 2> 返回第component列每一行的高度和宽度<p><p><p><p>
- (CGFloat)pickerView:(UIPickerView *)pickerView widthForComponent:(NSInteger)component;<p><p><p><p>
- (CGFloat)pickerView:(UIPickerView *)pickerView rowHeightForComponent:(NSInteger)component;<p><p><p><p>
3> 选中第component列第row行调用<p><p><p><p>
- (void)pickerView:(UIPickerView *)pickerView didSelectRow:(NSInteger)row inComponent:(NSInteger)component;<p><p><p><p>
- <p><p><p><p>
<p><p><p><p>
<h3>随机选中某一列的某一行<p><p><p><p>
1> 如何选中某一行 [self.pickerView selectRow:row inComponent:component<p><p><p><p>
animated:YES];<p><p><p><p>
2> 先随机选中第0列的某一行,随机数取值范围看第0列总共有多少行,<p><p><p><p>
arc4random_uniform(x)随机0~x-1的数<p><p><p><p>
3> 避免随机出来的行数都一样,需要判断下,随机出来的行数和当前选中<p><p><p><p> 的是否一样,一样就重新随机,用while判断,直到随机到不一样,才行。 3> 问题:label没有显示最新选中的一行。<p><p><p>
原因:手动调用pickview滚动,选中某一行,不会触发代理,我们自己 主动调用代理,让lebel显示选中哪一行.<p><p><p>
注意:只有用户手动滚动才可以触发pickview的代理方法。 4> 每一列都要随机选中,弄个for循序,遍历每一列都随机选中<p><p><p>
<p><p><p>
<h4> 二级联动的问题<p><p><p>
两列同时滚动,会报角标越界错误 原因:返回每一行的样子的代理方法会经常调用,只要有新的一行<p><p><p> 出现就会调用。这里每次都会获取最新选中的省,而第0列展示的<p><p><p> 是之前选中的省会,如果最新选中的省会的城市总数小于之前选中 的省会。<p><p><p> 假设:最新选中的城市只有有4个,但是之前选中的省会城市有10 行,当第1列滚到5就会报角标越界错误。<p><p><p> 解决方式:这里不能获取最新的选中省会,需要记录之前选中的, 且只需要记录一次,在选中一行的代理方法里记录。<p><p><p> 注意:在刷新城市之前记住省会角标,应该刷新的城市,是当前选 中的省会的城市。<p><p><p>
4.8 监听城市选择,选中新的省会。 1> 记录选中的省会<p><p><p>
2> 刷新第1列<p><p><p>
3> 第一列默认选中第一个城市<p><p>
4> 把选中的省会和获取选中的城市显示到文本框<p><p>
<p><p>
<p><p>
UIDatePicker – ⽇日期选择器 <p><p>
● 选择⽇日期<p><p>
<p><p>
<p><p>

UIToolbar – ⼯工具条<p><p>
● ⼀一般显⽰示在底部或者键盘顶部,⾥里⾯面有⼏几个⼩小按钮<p><p>
<p><p>
<p><p>

UINavigationBar – 导航条 <p><p>
● 显⽰示在顶部的条<p><p>

UINavigationController的简单使⽤用<p>
● UINavigationController的使⽤用步骤<p>
➢ 初始化UINavigationController<p>
➢ 设置UIWindow的rootViewController为UINavigationController ➢ 根据具体情况,通过push⽅方法添加对应个数的⼦子控制器<p>
<p>
UINavigationController的⼦子控制器<p>
● UINavigationController以栈的形式保存⼦子控制器 @property(nonatomic,copy) NSArray *viewControllers;<p> @property(nonatomic,readonly) NSArray *childViewControllers;<p>
● 使⽤用push⽅方法能将某个控制器压⼊入栈<p>
- (void)pushViewController:(UIViewController *)viewController<p>
animated:(BOOL)animated;<p>
● 使⽤用pop⽅方法可以移除控制器<p>
➢ 将栈顶的控制器移除<p>
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




# UIApplication
什么是UIApplication
● UIApplication对象是应⽤用程序的象征
● 每⼀一个应⽤用都有⾃自⼰己的UIApplication对象,⽽而且是单例的
● 通过[UIApplication sharedApplication]可以获得这个单例对象
● ⼀一个iOS程序启动后创建的第⼀一个对象就是UIApplication对象
● 利⽤用UIApplication对象,能进⾏行⼀一些应⽤用级别的操作


UIApplication的常⽤用属性 
● 设置应⽤用程序图标右上⾓角的红⾊色提醒数字
@property(nonatomic) NSInteger applicationIconBadgeNumber;
● 设置联⽹网指⽰示器的可见性 @property(nonatomic,getter=isNetworkActivityIndicatorVisible)
BOOL networkActivityIndicatorVisible;


iOS7中的状态栏
● 从iOS7开始,系统提供了2种管理状态栏的⽅方式
➢ 通过UIViewController管理(每⼀一个UIViewController都可以拥有⾃自⼰己不同的状 态栏)
➢ 通过UIApplication管理(⼀一个应⽤用程序的状态栏都由它统⼀一管理) ● 在iOS7中,默认情况下,状态栏都是由UIViewController管理
的,UIViewController实现下列⽅方法就可以轻松管理状态栏的可见性和样式 ➢ 状态栏的样式
- (UIStatusBarStyle)preferredStatusBarStyle;
➢ 状态栏的可见性
- (BOOL)prefersStatusBarHidden;


openURL:
● UIApplication有个功能⼗〸十分强⼤大的openURL:⽅方法 - (BOOL)openURL:(NSURL*)url;
● openURL:⽅方法的部分功能有
➢ 打电话
UIApplication *app = [UIApplication sharedApplication]; [app openURL:[NSURL URLWithString:@"tel://10086"]];
➢ 发短信
[app openURL:[NSURL URLWithString:@"sms://10086"]];
➢ 发邮件
[app openURL:[NSURL URLWithString:@"mailto://12345@qq.com"]]



# UIWindow

● UIWindow是⼀一种特殊的UIView,通常在⼀一个app中只会有⼀一个UIWindow
● iOS程序启动完毕后,创建的第⼀一个视图控件就是UIWindow,接着创建控制器的view,
最后将控制器的view添加到UIWindow上,于是控制器的view就显⽰示在屏幕上了 ● ⼀一个iOS程序之所以能显⽰示到屏幕上,完全是因为它有UIWindow
● 也就说,没有UIWindow,就看不见任何UI界⾯面

UIWindow
● 添加UIView到UIWindow中两种常见⽅方式:
➢ -(void)addSubview:(UIView*)view; 直接将view添加到UIWindow中,但并不会理会view对应的UIViewController
➢ @property(nonatomic,retain)UIViewController*rootViewController; ⾃自动将rootViewController的view添加到UIWindow中,负责管理rootViewController
的⽣生命周期
● 常⽤用⽅方法
➢ -(void)makeKeyWindow; 让当前UIWindow变成keyWindow(主窗⼜口)
￼￼￼➢ -(void)makeKeyAndVisible;让当前UIWindow变成keyWindow,并显⽰示出来


UIWindow的获得
● [UIApplicationsharedApplication].windows 在本应⽤用中打开的UIWindow列表,这样就可以接触应⽤用中的任何⼀一个UIView对象 (平时输⼊入⽂文字弹出的键盘,就处在⼀一个新的UIWindow中)
● [UIApplicationsharedApplication].keyWindow
⽤用来接收键盘以及⾮非触摸类的消息事件的UIWindow,⽽而且程序中每个时刻只能有⼀一 个UIWindow是keyWindow。如果某个UIWindow内部的⽂文本框不能输⼊入⽂文字,可能是因为这 个UIWindow不是keyWindow
● view.window 获得某个UIView所在的UIWindow



# 程序启动原理
1.创建UIApplication对象 2.创建UIApplication的代理对象，并且设置为UIApplication的代理. 3.开启一个主运行循环，处理事件 4.加载info.plist文件，判断是否有Main.storyboard,如果有就会去加载。 有Main.storyboard才会执行第5步 5.加载Main.storyboard， 5.1 创建窗口 5.2 加载Main.storyboard，初始化storyboard描述的控制器 5.3 设置窗口的根控制器，并且显示窗口

二、窗口，应用程序创建的第一个控件。 1.添加子控件，一般把窗口的根控制器添加上去，通过设置rootViewController就可以把根控制器的view添加到窗口上。 2.介绍窗口如何显示。 2.1 设置窗口的hiddle属性 3.应用程序是有主窗口，通常调用makeKeyAndVisible 4.windons属性，可以识别应用程序中哪些控件还是窗口，有一个比较特殊，状态栏。 5.window层级，alert(2000) > statusBar(1000) > normal(0)





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




Modal
● 除了push之外,还有另外⼀一种控制器的切换⽅方式,那就是Modal
● 任何控制器都能通过Modal的形式展⽰示出来
● Modal的默认效果:新控制器从屏幕的最底部往上钻,直到盖住之前的控制器为⽌止
● 以Modal的形式展⽰示控制器
- (void)presentViewController:(UIViewController
*)viewControllerToPresent animated: (BOOL)flag completion:(void
(^)(void))completion
● 关闭当初Modal出来的控制器
- (void)dismissViewControllerAnimated: (BOOL)flag completion:
(void (^)(void))completion;


# 触摸事件
响应者对象
● 在iOS中不是任何对象都能处理事件,只有继承了UIResponder的对象才能接收并处理事 件。我们称之为“响应者对象”
● UIApplication、UIViewController、UIView都继承⾃自UIResponder,因此它们都 是响应者对象,都能够接收并处理事件

UIResponder
● UIResponder内部提供了以下⽅方法来处理事件
➢ 触摸事件
- (void)touchesBegan:(NSSet *)touches withEvent:(UIEvent *)event;
- (void)touchesMoved:(NSSet *)touches withEvent:(UIEvent *)event;
- (void)touchesEnded:(NSSet *)touches withEvent:(UIEvent *)event;
- (void)touchesCancelled:(NSSet *)touches withEvent:(UIEvent *)event;
➢ 加速计事件
- (void)motionBegan:(UIEventSubtype)motion withEvent:(UIEvent *)event;
- (void)motionEnded:(UIEventSubtype)motion withEvent:(UIEvent *)event;
- (void)motionCancelled:(UIEventSubtype)motion withEvent:(UIEvent *)event;
➢ 远程控制事件
- (void)remoteControlReceivedWithEvent:(UIEvent *)event;
- 

UIView的触摸事件处理
● UIView是UIResponder的⼦子类,可以覆盖下列4个⽅方法处理不同的触摸事件
➢ ⼀一根或者多根⼿手指开始触摸view,系统会⾃自动调⽤用view的下⾯面⽅方法
- (void)touchesBegan:(NSSet *)touches withEvent:(UIEvent *)event
➢ ⼀一根或者多根⼿手指在view上移动,系统会⾃自动调⽤用view的下⾯面⽅方法(随着⼿手指的移动,会 持续调⽤用该⽅方法)
- (void)touchesMoved:(NSSet *)touches withEvent:(UIEvent *)event ➢ ⼀一根或者多根⼿手指离开view,系统会⾃自动调⽤用view的下⾯面⽅方法
- (void)touchesEnded:(NSSet *)touches withEvent:(UIEvent *)event
➢ 触摸结束前,某个系统事件(例如电话呼⼊入)会打断触摸过程,系统会⾃自动调⽤用view的下⾯面
⽅方法
- (void)touchesCancelled:(NSSet *)touches withEvent:(UIEvent *)event 提⽰示:touches中存放的都是UITouch对象
- 
UITouch的属性 ● 触摸产⽣生时所处的窗⼜⼝口
@property(nonatomic,readonly,retain) UIWindow *window; ● 触摸产⽣生时所处的视图
@property(nonatomic,readonly,retain) UIView *view; ● 短时间内点按屏幕的次数,可以根据tapCount判断单击、双击或更多的点击
@property(nonatomic,readonly) NSUInteger tapCount; ● 记录了触摸事件产⽣生或变化时的时间,单位是秒
@property(nonatomic,readonly) NSTimeInterval      timestamp;

● 当前触摸事件所处的状态
@property(nonatomic,readonly) UITouchPhase phase;

UITouch的⽅方法
● -(CGPoint)locationInView:(UIView*)view; 返回值表⽰示触摸在view上的位置 这⾥里返回的位置是针对view的坐标系的(以view的左上⾓角为原点(0, 0)) 调⽤用时传⼊入的view参数为nil的话,返回的是触摸点在UIWindow的位置
- (CGPoint)previousLocationInView:(UIView *)view; 该⽅方法记录了前⼀一个触摸点的位置
- 

UIEvent
● 每产⽣生⼀一个事件,就会产⽣生⼀一个UIEvent对象
● UIEvent:称为事件对象,记录事件产⽣生的时刻和类型
● 常见属性
➢ 事件类型
@property(nonatomic,readonly) UIEventType type; @property(nonatomic,readonly) UIEventSubtype subtype;
➢ 事件产⽣生的时间
@property(nonatomic,readonly) NSTimeInterval timestamp;

● UIEvent还提供了相应的⽅方法可以领获先得业在内某IT个教育vi培e训w⾏行上业⾯面w的ww触.5摸20i对t.co象m(UITouch)

touches和event参数
● ⼀一次完整的触摸过程,会经历3个状态:
￼➢ ➢ ➢ ➢
触摸开始:- (void)touchesBegan:(NSSet *)touches withEvent:(UIEvent *)event
触摸移动:- (void)touchesMoved:(NSSet *)touches withEvent:(UIEvent *)event
触摸结束:- (void)touchesEnded:(NSSet *)touches withEvent:(UIEvent *)event
触摸取消(可能会经历):- (void)touchesCancelled:(NSSet *)touches withEvent:(UIEvent *)event
4个触摸事件处理⽅方法中,都有NSSet *touches和UIEvent *event两个参数
➢ 如果两根⼿手指同时触摸⼀一个view,那么view只会调⽤用⼀一次touchesBegan:withEvent:
●
➢ ⼀一次完整的触摸过程中,只会产⽣生⼀一个事件对象,4个触摸⽅方法都是同⼀一个event参数
￼⽅方法,touches参数中装着2个UITouch对象


事件的产⽣生和传递
● 发⽣生触摸事件后,系统会将该事件加⼊入到⼀一个由UIApplication管理的事件队列中
● UIApplication会从事件队列中取出最前⾯面的事件,并将事件分发下去以便处理,通
常,先发送事件给应⽤用程序的主窗⼜⼝口(keyWindow)
● 主窗⼜⼝口会在视图层次结构中找到⼀一个最合适的视图来处理触摸事件,这也是整个事件处理
过程的第⼀一步


UIView不接收触摸事件的三种情况 . 不接收⽤用户交互
userInteractionEnabled = NO . 隐藏
hidden = YES . 透明
alpha = 0.0 ~ 0.01 提⽰示:UIImageView的userInteractionEnabled默认就是NO,因此UIImageView以
  及它的⼦子控件默认是不能接收触摸事件的
  
  touches⽅方法的默认做法是将事件顺着响应者链条向上传递,将事件交给上⼀一个响 应者进⾏行处理
  
  
  <h4>事件传递的完整过程
1> 先将事件对象由上往下传递(由⽗父控件传递给⼦子控件),找到最合适的控件 来处理这个事件。
￼2> 调⽤用最合适控件的touches....⽅方法
3> 如果调⽤用了[super touches....];就会将事件顺着响应者链条往上传递,传递
给上⼀一个响应者
4> 接着就会调⽤用上⼀一个响应者的touches....⽅方法
如何判断上⼀一个响应者
1> 如果当前这个view是控制器的view,那么控制器就是上⼀一个响应者
2> 如果当前这个view不是控制器的view,那么⽗父控件就是上⼀一个响应者

<h3>响应者链的事件传递过程
如果view的控制器存在,就传递给控制器;如果控制器不存在,则将其传递给它 的⽗父视图
在视图层次结构的最顶级视图,如果也不能处理收到的事件或消息,则其将事件 或消息传递给window对象进⾏行处理
如果window对象也不处理,则其将事件或消息传递给UIApplication对象 如果UIApplication也不能处理该事件或消息,则将其丢弃



<h5>UIGestureRecognizer
● 为了完成⼿手势识别,必须借助于⼿手势识别器----UIGestureRecognizer
● 利⽤用UIGestureRecognizer,能轻松识别⽤用户在某个view上⾯面做的⼀一些常见⼿手势
● UIGestureRecognizer是⼀一个抽象类,定义了所有⼿手势的基本⾏行为,使⽤用它的⼦子类才能 处理具体的⼿手势
➢ UITapGestureRecognizer(敲击)
➢ UIPinchGestureRecognizer(捏合,⽤用于缩放) ➢ UIPanGestureRecognizer(拖拽)
➢ UISwipeGestureRecognizer(轻扫)
➢ UIRotationGestureRecognizer(旋转)
➢ UILongPressGestureRecognizer(长按)

// 点击手势
    UITapGestureRecognizer *tap = [[UITapGestureRecognizer alloc] initWithTarget:self action:@selector(tap)];
    [self.image addGestureRecognizer:tap];

# 数据存储

iOS应⽤用数据存储的常⽤用⽅方式
● XML属性列表(plist)归档 ● Preference(偏好设置)
● NSKeyedArchiver归档(NSCoding) ● SQLite3
● Core Data




应⽤用沙盒
● 每个iOS应⽤用都有⾃自⼰己的应⽤用沙盒(应⽤用沙盒就是⽂文件系统⽬目录),与其 他⽂文件系统隔离。应⽤用必须待在⾃自⼰己的沙盒⾥里,其他应⽤用不能访问该沙 盒


应⽤用沙盒结构分析
应⽤用程序包:(上图中的Layer)包含了所有的资源⽂文件和可执⾏行⽂文件 Documents:保存应⽤用运⾏行时⽣生成的需要持久化的数据,iTunes同步设备时会
备份该⽬目录。例如,游戏应⽤用可将游戏存档保存在该⽬目录
tmp:保存应⽤用运⾏行时所需的临时数据,使⽤用完毕后再将相应的⽂文件从该⽬目录删 除。应⽤用没有运⾏行时,系统也可能会清除该⽬目录下的⽂文件。iTunes同步设备时 不会备份该⽬目录
Library/Caches:保存应⽤用运⾏行时⽣生成的需要持久化的数据,iTunes同步设 备时不会备份该⽬目录。⼀一般存储体积⼤大、不需要备份的⾮非重要数据
Library/Preference:保存应⽤用的所有偏好设置,iOS的Settings(设置) 应⽤用会在该⽬目录中查找应⽤用的设置信息。iTunes同步设备时会备份该⽬目录


应⽤用沙盒⽬目录的常见获取⽅方式
● 沙盒根⽬目录:NSString *home = NSHomeDirectory(); ● Documents:(2种⽅方式)
● 利⽤用沙盒根⽬目录拼接”Documents”字符串
NSString *home = NSHomeDirectory();
NSString *documents = [home stringByAppendingPathComponent:@"Documents"]; // 不建议采⽤用,因为新版本的操作系统可能会修改⽬目录名
● 利⽤用NSSearchPathForDirectoriesInDomains函数
// NSUserDomainMask 代表从⽤用户⽂文件夹下找
// YES 代表展开路径中的波浪字符“~”
NSArray *array = NSSearchPathForDirectoriesInDomains(NSDocumentDirectory, NSUserDomainMask, NO); // 在iOS中,只有⼀一个⽬目录跟传⼊入的参数匹配,所以这个集合⾥里⾯面只有⼀一个元素
￼￼￼领先业内IT教育培训⾏行业 www.520it.com NSString *documents = [array objectAtIndex:0];





● tmp:NSString *tmp = NSTemporaryDirectory();
● Library/Caches:(跟Documents类似的2种⽅方法)
● 利⽤用沙盒根⽬目录拼接”Caches”字符串
● 利⽤用NSSearchPathForDirectoriesInDomains函数(将函数的第2个参数改 为:NSCachesDirectory即可)
● Library/Preference:通过NSUserDefaults类存取该⽬目录下的设置信息




属性列表-归档NSDictionary
● 将⼀一个NSDictionary对象归档到⼀一个plist属性列表中 // 将数据封装成字典
NSMutableDictionary *dict = [NSMutableDictionary dictionary]; [dict setObject:@"母鸡" forKey:@"name"];
[dict setObject:@"15013141314" forKey:@"phone"]; [dict setObject:@"27" forKey:@"age"];
// 将字典持久化到Documents/stu.plist⽂文件中
[dict writeToFile:path atomically:YES];


属性列表-恢复NSDictionary
● 读取属性列表,恢复NSDictionary对象
// 读取Documents/stu.plist的内容,实例化NSDictionary
NSDictionary *dict = [NSDictionary dictionaryWithContentsOfFile:path]; NSLog(@"name:%@", [dict objectForKey:@"name"]); NSLog(@"phone:%@", [dict objectForKey:@"phone"]); NSLog(@"age:%@", [dict objectForKey:@"age"]);




偏好设置
● 读取上次保存的设置
NSUserDefaults *defaults = [NSUserDefaults standardUserDefaults]; NSString *username = [defaults stringForKey:@"username"];
float textSize = [defaults floatForKey:@"text_size"];
BOOL autoLogin = [defaults boolForKey:@"auto_login"];
● 注意:UserDefaults设置数据时,不是⽴立即写⼊入,⽽而是根据时间戳定时地把缓存中 的数据写⼊入本地磁盘。所以调⽤用了set⽅方法之后数据有可能还没有写⼊入磁盘应⽤用程序 就终⽌止了。出现以上问题,可以通过调⽤用synchornize⽅方法强制写⼊入
[defaults synchornize];



NSKeyedArchiver-归档对象的注意
● 如果⽗父类也遵守了NSCoding协议,请注意:
● 应该在encodeWithCoder:⽅方法中加上⼀一句 [super encodeWithCode:encode]; 确保继承的实例变量也能被编码,即也能被归档 ● 应该在initWithCoder:⽅方法中加上⼀一句
self = [super initWithCoder:decoder];
确保继承的实例变量也能被解码,即也能被恢复


NSData-归档2个Person对象到同⼀一⽂文件中
● 归档(编码)
// 新建⼀一块可变数据区
NSMutableData *data = [NSMutableData data];
// 将数据区连接到⼀一个NSKeyedArchiver对象
NSKeyedArchiver *archiver = [[[NSKeyedArchiver alloc] initForWritingWithMutableData:data] autorelease];
// 开始存档对象,存档的数据都会存储到NSMutableData中 [archiver encodeObject:person1 forKey:@"person1"]; [archiver encodeObject:person2 forKey:@"person2"];
// 存档完毕(⼀一定要调⽤用这个⽅方法)
￼￼[archiver finishEncoding]; // 将存档的数据写⼊入⽂文件


NSData-从同⼀一⽂文件中恢复2个Person对象
● 恢复(解码)
// 从⽂文件中读取数据
NSData *data = [NSData dataWithContentsOfFile:path];
// 根据数据,解析成⼀一个NSKeyedUnarchiver对象
NSKeyedUnarchiver *unarchiver = [[NSKeyedUnarchiver alloc] initForReadingWithData:data];
Person *person1 = [unarchiver decodeObjectForKey:@"person1"]; Person *person2 = [unarchiver decodeObjectForKey:@"person2"]; // 恢复完毕
[unarchiver finishDecoding];


利⽤用归档实现深复制
eDaO● ⽐比如对⼀一个Person对象进⾏行深复制
tbja //临时存储person1的数据
eWNSData *data = [NSKeyedArchiver archivedDataWithRootObject:person1];
ict // 解析data,⽣生成⼀一个新的Person对象
hWStudent *person2 = [NSKeyedUnarchiver unarchiveObjectWithData:data];
iR // 分别打印内存地址 to
oh NSLog(@"person1:0x%x", person1); // person1:0x7177a60
￼NSLog(@"person2:0x%x", person2); // person2:0x7177cf0




<h5>�>创建、打开、关闭数据库

● 创建或打开数据库
// path为:~/Documents/person.db
sqlite3 *db;
int result = sqlite3_open([path UTF8String], &db);
￼● 代码解析:
● sqlite3_open()将根据⽂文件路径打开数据库,如果不存在,则会创建⼀一个新的数据
￼库。如果result等于常量SQLITE_OK,则表⽰示成功打开数据库
● sqlite3 *db:⼀一个打开的数据库实例
● 数据库⽂文件的路径必须以C字符串(⽽而⾮非NSString)传⼊入
￼● 关闭数据库:sqlite3_close(db);


带占位符插⼊入数据
char *sql = "insert into t_person(name, age) values(?, ?);"; sqlite3_stmt *stmt;
if (sqlite3_prepare_v2(db, sql, -1, &stmt, NULL) == SQLITE_OK) {
sqlite3_bind_text(stmt, 1, "母鸡", -1, NULL);
sqlite3_bind_int(stmt, 2, 27); }
if (sqlite3_step(stmt) != SQLITE_DONE) { NSLog(@"插⼊入数据错误");
} sqlite3_finalize(stmt);



查询数据
char *sql = "select id,name,age from t_person;";
sqlite3_stmt *stmt;
if (sqlite3_prepare_v2(db, sql, -1, &stmt, NULL) == SQLITE_OK) {
while (sqlite3_step(stmt) == SQLITE_ROW) {
int _id = sqlite3_column_int(stmt, 0);
char *_name = (char *)sqlite3_column_text(stmt, 1); NSString *name = [NSString stringWithUTF8String:_name]; int _age = sqlite3_column_int(stmt, 2);
NSLog(@"id=%i, name=%@, age=%i", _id, name, _age);
￼￼} }
sqlite3_finalize(stmt);




# Core Data
搭建Core Data上下⽂文环境 
● 从应⽤用程序包中加载模型⽂文件
NSManagedObjectModel *model = [NSManagedObjectModel mergedModelFromBundles:nil];
● 传⼊入模型,初始化NSPersistentStoreCoordinator NSPersistentStoreCoordinator *psc = [[[NSPersistentStoreCoordinator alloc]
initWithManagedObjectModel:model] autorelease];
● 构建SQLite⽂文件路径
NSString *docs = [NSSearchPathForDirectoriesInDomains(NSDocumentDirectory, NSUserDomainMask, YES) lastObject];
NSURL *url = [NSURL fileURLWithPath:[docs stringByAppendingPathComponent:@"person.data"]];


● 添加持久化存储库,这⾥里使⽤用SQLite作为存储库
NSError *error = nil;
NSPersistentStore *store = [psc addPersistentStoreWithType:NSSQLiteStoreType configuration:nil URL:url options:nil error:&error];
if (store == nil) { // 直接抛异常
[NSException raise:@"添加数据库错误" format:@"%@", [error localizedDescription]];
}
● 初始化上下⽂文,设置persistentStoreCoordinator属性 NSManagedObjectContext *context = [[NSManagedObjectContext alloc] init]; context.persistentStoreCoordinator = psc;
// ⽤用完之后,还是要[context release];


<h4>添加数据
● 传⼊入上下⽂文,创建⼀一个Person实体对象 NSManagedObject *person = [NSEntityDescription
insertNewObjectForEntityForName:@"Person" inManagedObjectContext:context]; ● 设置简单属性
[person setValue:@"MJ" forKey:@"name"];
[person setValue:[NSNumber numberWithInt:27] forKey:@"age"];
● 传⼊入上下⽂文,创建⼀一个Card实体对象 NSManagedObject *card = [NSEntityDescription
insertNewObjectForEntityForName:@"Card" inManagedObjectContext:context]; [card setValue:@"4414241933432" forKey:@"no"];
● 设置Person和Card之间的关联关系
￼￼￼[person setValue:card forKey:@"card"];



<h4>查询数据
● 初始化⼀一个查询请求
NSFetchRequest *request = [[[NSFetchRequest alloc] init] autorelease];
● 设置要查询的实体
NSEntityDescription *desc = [NSEntityDescription entityForName:@"Person" inManagedObjectContext:context];
● 设置排序(按照age降序)
NSSortDescriptor *sort = [NSSortDescriptor sortDescriptorWithKey:@"age"
ascending:NO];
request.sortDescriptors = [NSArray arrayWithObject:sort];
● 设置条件过滤(name like '%Itcast-1%')
NSPredicate *predicate = [NSPredicate predicateWithFormat:@"name like %@",
￼￼@"*Itcast-1*"]; request.predicate = predicate;


● 执⾏行请求
NSError *error = nil;
NSArray *objs = [context executeFetchRequest:request error:&error]; if (error) {
[NSException raise:@"查询错误" format:@"%@", [error localizedDescription]]; }
● 遍历数据
for (NSManagedObject *obj in objs) {
NSLog(@"name=%@", [obj valueForKey:@"name"] }





<h4>删除数据
● 传⼊入需要删除的实体对象
[context deleteObject:managedObject]; ● 将结果同步到数据库
NSError *error = nil;
[context save:&error];
if (error) {
[NSException raise:@"删除错误" format:@"%@", [error localizedDescription]];
}



# Autolayout
● 代码实现Autolayout的步骤
● 利⽤用NSLayoutConstraint类创建具体的约束对象
● 添加约束对象到相应的view上
- (void)addConstraint:(NSLayoutConstraint *)constraint; - (void)addConstraints:(NSArray *)constraints;
● 代码实现Autolayout的注意点
● 要先禁⽌止autoresizing功能,设置view的下⾯面属性为NO
view.translatesAutoresizingMaskIntoConstraints = NO; ● 添加约束之前,⼀一定要保证相关控件都已经在各⾃自的⽗父控件上
● 不⽤用再给view设置frame

NSLayoutConstraint
● ⼀一个NSLayoutConstraint对象就代表⼀一个约束 ● 创建约束对象的常⽤用⽅方法
+(id)constraintWithItem:(id)view1 attribute:(NSLayoutAttribute)attr1
relatedBy:(NSLayoutRelation)relation toItem:(id)view2 attribute:
(NSLayoutAttribute)attr2 multiplier:(CGFloat)multiplier constant:
(CGFloat)c;
● view1 :要约束的控件
● attr1 :约束的类型(做怎样的约束)
● relation :与参照控件之间的关系
● view2 :参照的控件
● attr2 :约束的类型(做怎样的约束)
● multiplier :乘数
● c:常量

● ⾃自动布局的核⼼心计算公式
obj1.property1 =(obj2.property2 * multiplier)+ constant value


# VFL语⾔言
● VFL全称是Visual Format Language,翻译过来是“可视化格式语⾔言” 
● VFL是苹果公司为了简化Autolayout的编码⽽而推出的抽象语⾔言

VFL示例
● H:[cancelButton(72)]-12-[acceptButton(50)]
● canelButton宽72,acceptButton宽50,它们之间间距12 ● H:[wideView(>=60@700)]
● wideView宽度⼤大于等于60point,该约束条件优先级为700(优先级最⼤大值为1000,优先级越⾼高的约束越先 被满⾜足)
● V:[redBox][yellowBox(==redBox)]
● 竖直⽅方向上,先有⼀一个redBox,其下⽅方紧接⼀一个⾼高度等于redBox⾼高度的yellowBox
● H:|-10-[Find]-[FindNext]-[FindField(>=20)]-|
● ⽔水平⽅方向上,Find距离⽗父view左边缘默认间隔宽度,之后是FindNext距离Find间隔默认宽度;再之后是宽度 不⼩小于20的FindField,它和FindNext以及⽗父view右边缘的间距都是默认宽度。(竖线“|” 表⽰示superview的边 缘)


VFL的使⽤
● 使⽤用VFL来创建约束数组
+ (NSArray *)constraintsWithVisualFormat:(NSString
*)format options:(NSLayoutFormatOptions)opts metrics:
(NSDictionary *)metrics views:(NSDictionary *)views;
● format :VFL语句
● opts :约束类型
● metrics :VFL语句中⽤用到的具体数值 ● views :VFL语句中⽤用到的控件
● 创建⼀一个字典(内部包含VFL语句中⽤用到的控件)的快捷宏定义 NSDictionaryOfVariableBindings(...)


基于Autolayout的动画
● 在修改了约束之后,只要执⾏行下⾯面代码,就能做动画效果 
[UIView animateWithDuration:1.0 animations:^{
[添加了约束的view layoutIfNeeded]; }];


# Quartz2D
● Quartz 2D能完成的⼯工作
➢ 绘制图形 : 线条\三⾓角形\矩形\圆\弧等
➢ 绘制⽂文字
➢ 绘制\⽣生成图⽚片(图像)
➢ 读取\⽣生成PDF
➢ 截图\裁剪图⽚片
➢ ⾃自定义UI控件


<h4>图形上下⽂(Bitmap Graphics Context/PDF Graphics Context/Window Graphics Context/Layer Graphics Context/Printer Graphics Context)
● 图形上下⽂文(Graphics Context):是⼀一个CGContextRef类型的数据
● 图形上下⽂文的作⽤用
➢ 保存绘图信息、绘图状态
➢ 决定绘制的输出⽬目标(绘制到什么地⽅方去?) (输出⽬目标可以是PDF⽂文件、Bitmap或者显⽰示器的窗⼜⼝口上)


drawRect:中取得的上下⽂文
● 在drawRect:⽅方法中取得上下⽂文后,就可以绘制东西到view上
● View内部有个layer(图层)属性,drawRect:⽅方法中取得的是⼀一个Layer Graphics Context,因此,绘制的东西其实是绘制到view的layer上去了
● View之所以能显⽰示东西,完全是因为它内部的layer


<h4>绘图的代码步骤 1. 获得图形上下⽂文
CGContextRef ctx = UIGraphicsGetCurrentContext();
2. 拼接路径(下⾯面代码是搞⼀一条线段) CGContextMoveToPoint(ctx, 10, 10); CGContextAddLineToPoint(ctx, 100, 100);
3. 绘制路径
CGContextStrokePath(ctx); // CGContextFillPath(ctx);



常⽤用拼接路径函数
● 新建⼀一个起点
void CGContextMoveToPoint(CGContextRef c, CGFloat x, CGFloat y)
● 添加新的线段到某个点
void CGContextAddLineToPoint(CGContextRef c, CGFloat x, CGFloat y)
● 添加⼀一个矩形
void CGContextAddRect(CGContextRef c, CGRect rect)
● 添加⼀一个椭圆
void CGContextAddEllipseInRect(CGContextRef context, CGRect rect)
● 添加⼀一个圆弧
void CGContextAddArc(CGContextRef c, CGFloat x, CGFloat y,



常⽤用绘制路径函数
● Mode参数决定绘制的模式
void CGContextDrawPath(CGContextRef c, CGPathDrawingMode mode)
● 绘制空⼼心路径
void CGContextStrokePath(CGContextRef c)
● 绘制实⼼心路径
void CGContextFillPath(CGContextRef c)
一般以CGContextDraw、CGContextStroke、CGContextFill开头的函数, 都是⽤用来绘制路径的



图形上下⽂文栈的操作
● 将当前的上下⽂文copy⼀一份,保存到栈顶(那个栈叫做”图形上下⽂文栈”) void CGContextSaveGState(CGContextRef c)
● 将栈顶的上下⽂文出栈,替换掉当前的上下⽂文
void CGContextRestoreGState(CGContextRef c)


矩阵操作
● 利⽤用矩阵操作,能让绘制到上下⽂文中的所有路径⼀一起发⽣生变化
➢ 缩放
void CGContextScaleCTM(CGContextRef c, CGFloat sx, CGFloat sy)
➢ 旋转
void CGContextRotateCTM(CGContextRef c, CGFloat angle)
➢ 平移
void CGContextTranslateCTM(CGContextRef c, CGFloat tx, CGFloat ty)



Quartz2D的内存管理
● 使⽤用含有“Create”或“Copy”的函数创建的对象,使⽤用完后必须释放,否则将导致内存泄
露
● 使⽤用不含有“Create”或“Copy”的函数获取的对象,则不需要释放
● 如果retain了⼀一个对象,不再使⽤用时,需要将其release掉
● 可以使⽤用Quartz 2D的函数来指定retain和release⼀一个对象。例如,如果创建了⼀一 个CGColorSpace对象,则使⽤用函数CGColorSpaceRetain和CGColorSpaceRelease来retain 和release对象。
● 也可以使⽤用Core Foundation的CFRetain和CFRelease。注意不能传递NULL值给这些函数



图⽚片⽔水印
● 有时候,在⼿手机客户端app中也需要⽤用到⽔水印技术
● ⽐比如,⽤用户拍完照⽚片后,可以在照⽚片上打个⽔水印,标识这个图⽚片是属于哪个⽤用户的 ● 实现⽅方式:利⽤用Quartz2D,将⽔水印(⽂文字、LOGO)画到图⽚片的右下⾓角
水印PPT简介
    *  图片水印作用：防止他人盗取图片，加一些Logo，生成一张新的图片。
    *  怎么生成新的图片?和绘图一样的，需要拿到上下文做事情，这里也需要拿到上下文，生成一个新的图片。
    *  什么上下文？位图上下文，在这个上下文画东西，就能输出到新的图片上。
    *  怎么获取？之前用的都是图层上下文，系统会自动创建，但是我们位图上下文，需要我们手动创建
    *  总结：只要不和view有关系的上下文，都需要我们手动创建。
    *  在哪获取图像上下文，viewDidLoad, 不需要拿到系统创建的图层上下文，没必要在drawRect方法里写,直接viewDidLoad就行了。
    *  怎么创建图像上下文了？之前说过跟上下文有关的以什么开头，UIGraphics
    *  UIGraphicsBeginImageContextWithOptions:看注释,create bitmap，创建一个位图上下文,而且这种方法得到的图片最清晰。
    *  解释参数（size:新图片尺寸 opaque: YES:不透明 NO:透明 scale:0.0 不伸缩）
    *  绘制内容(图片，文字)
    *  获取图片：把位图上下文的内容生成一个图片给你。
    *  关闭上下文，不关闭一直占用着内存。
    *  显示UIImageView上
    *  保存图片，写到文件，UIImage不能写，需要转换成NSData二进制数据
    *  UIImageJPEGRepresentation:可以设置图片质量
    *  UIImagePNGRepresentation：把图片转换成png格式的二进制数据,png格式默认是最高清的。
    *  写到桌面


<h3>图⽚片裁剪
￼● 核⼼心代码
// 图片
    UIImage *image =[ UIImage imageNamed:@"1"];
    
    // 首先开启一个位图上下文
    UIGraphicsBeginImageContextWithOptions(image.size, NO, 0);
    
    // 画一个源
    UIBezierPath *path = [UIBezierPath bezierPathWithOvalInRect:CGRectMake(0, 0, image.size.height, image.size.height)];
    
    // 圆形剪裁
    [path addClip];
    
    // 图片绘制到上下文
    [image drawAtPoint:CGPointZero];
    
    // 获取图片
    image = UIGraphicsGetImageFromCurrentImageContext();
    // 关闭上下文
    UIGraphicsEndImageContext();
    
    
    // 输出
    NSData *data = UIImagePNGRepresentation(image);
    
    [data writeToFile:@"/Users/JS/Desktop/dd2.png" atomically:YES];


<h3>屏幕截图
 核⼼心代码
// 开启位图上下文
    UIGraphicsBeginImageContextWithOptions(self.view.frame.size, NO, 0);
    
    // 获取当前上下文
    CGContextRef ctr = UIGraphicsGetCurrentContext();
    
    //  渲染到上下文(图层只能用渲染)
    [self.view.layer renderInContext:ctr];
    
    
    
    // 生成一张新的图片
    UIImage *image = UIGraphicsGetImageFromCurrentImageContext();
    
    // 关闭上下文
    UIGraphicsEndImageContext();
    
    // 输出
    NSData *data = UIImagePNGRepresentation(image);
    
    [data writeToFile:@"/Users/JS/Desktop/2c97690e72365e38e3e2ab934b8dd2.png" atomically:YES];
    
    
    
   


# CALayer
● 在iOS中,你能看得见摸得着的东西基本上都是UIView,⽐比如⼀一个按钮、⼀一个⽂文本标签、 ⼀一个⽂文本输⼊入框、⼀一个图标等等,这些都是UIView
● 其实UIView之所以能显⽰示在屏幕上,完全是因为它内部的⼀一个图层
● 在创建UIView对象时,UIView内部会⾃自动创建⼀一个图层(即CALayer对象),通过UIView
的layer属性可以访问这个层 @property(nonatomic,readonly,retain) CALayer *layer;
● 当UIView需要显⽰示到屏幕上时,会调⽤用drawRect:⽅方法进⾏行绘图,并且会将所有内容绘制在 ⾃自⼰己的图层上,绘图完毕后,系统会将图层拷贝到屏幕上,于是就完成了UIView的显⽰示
● 换句话说,UIView本⾝身不具备显⽰示的功能,是它内部的层才有显⽰示功能

CALayer的基本使⽤
● 通过操作CALayer对象,可以很⽅方便地调整UIView的⼀一些外观属性,⽐比如: ➢ 阴影
➢ 圆⾓角⼤大⼩小
➢ 边框宽度和颜⾊色


CALayer的属性 
● 宽度和⾼高度
@property CGRect bounds;
● 位置(默认指中点,具体由anchorPoint决定)
@property CGPoint position;
● 锚点(x,y的范围都是0-1),决定了position的含义
@property CGPoint anchorPoint; 
● 背景颜⾊色(CGColorRef类型)
@property CGColorRef backgroundColor;
￼￼● 形变属性
@property CATransform3D transform;
● 边框颜⾊色(CGColorRef类型)
@property CGColorRef borderColor; 
● 边框宽度
@property CGFloat borderWidth; 
● 圆⾓角半径
@property CGColorRef borderColor; 
● 内容(⽐比如设置为图⽚片CGImageRef)
@property(retain) id contents;


CALayer的疑惑
● ⾸首先
➢ CALayer是定义在QuartzCore框架中的
➢ CGImageRef、CGColorRef两种数据类型是定义在CoreGraphics框架中的
➢ UIColor、UIImage是定义在UIKit框架中的
● 其次
➢ QuartzCore框架和CoreGraphics框架是可以跨平台使⽤用的,在iOS和Mac OS X上都能使⽤用
➢ 但是UIKit只能在iOS中使⽤用
● 为了保证可移植性,QuartzCore不能使⽤用UIImage、UIColor,只能使 ⽤用CGImageRef、CGColorRef



UIView和CALayer的选择
● 通过CALayer,就能做出跟UIImageView⼀一样的界⾯面效果
● 既然CALayer和UIView都能实现相同的显⽰示效果,那究竟该选择谁好呢?
➢ 其实,对⽐比CALayer,UIView多了⼀一个事件处理的功能。也就是说,CALayer不能
处理⽤用户的触摸事件,⽽而UIView可以
➢ 所以,如果显⽰示出来的东西需要跟⽤用户进⾏行交互的话,⽤用UIView;如果不需要跟⽤用户
进⾏行交互,⽤用UIView或者CALayer都可以
➢ 当然,CALayer的性能会⾼高⼀一些,因为它少了事件处理的功能,更加轻量级



position和anchorPoint
● CALayer有2个⾮非常重要的属性:position和anchorPoint
● @propertyCGPointposition; ➢ ⽤用来设置CALayer在⽗父层中的位置
➢ 以⽗父层的左上⾓角为原点(0, 0)
● @propertyCGPointanchorPoint; ➢ 称为“定位点”、“锚点”
➢ 决定着CALayer⾝身上的哪个点会在position属性所指的位置 ➢ 以⾃自⼰己的左上⾓角为原点(0, 0)
➢ 它的x、y取值范围都是0~1,默认值为(0.5,0.5)


隐式动画
● 可以通过动画事务(CATransaction)关闭默认的隐式动画效果 [CATransaction begin];
[CATransaction setDisableActions:YES]; 
self.myview.layer.position = CGPointMake(10, 10); 
[CATransaction commit];


 # Core Animation 核心动画
 使⽤用步骤
 ● 1.⾸首先得有CALayer
● 2.初始化⼀一个CAAnimation对象,并设置⼀一些动画相关属性
● 3.通过调⽤用CALayer的addAnimation:forKey:⽅方法,增加CAAnimation对 象到CALayer中,这样就能开始执⾏行动画了
● 4.通过调⽤用CALayer的removeAnimationForKey:⽅方法可以停⽌止CALayer 中的动画

● duration:动画的持续时间
● repeatCount:重复次数,⽆无限循环可以设置HUGE_VALF或者MAXFLOAT ● repeatDuration:重复时间
● removedOnCompletion:默认为YES,代表动画执⾏行完毕后就从图层上移除,图形会 恢复到动画执⾏行前的状态。如果想让图层保持显⽰示动画执⾏行后的状态,那就设置 为NO,不过还要设置fillMode为kCAFillModeForwards
● fillMode:决定当前对象在⾮非active时间段的⾏行为。⽐比如动画开始之前或者动画结束 之后
● beginTime:可以⽤用来设置动画延迟执⾏行时间,若想延迟2s,就设置 为CACurrentMediaTime()+2,CACurrentMediaTime()为图层的当前时间
● timingFunction:速度控制函数,控制动画运⾏行的节奏 ● delegate:动画代理


CAAnimation——速度控制函数
● 速度控制函数(CAMediaTimingFunction)
kCAMediaTimingFunctionLinear(线性):匀速,给你⼀一个相对静态的感觉
kCAMediaTimingFunctionEaseIn(渐进):动画缓慢进⼊入,然后加速离开
kCAMediaTimingFunctionEaseOut(渐出):动画全速进⼊入,然后减速的到达⽬目 的地
kCAMediaTimingFunctionEaseInEaseOut(渐进渐出):动画缓慢的进⼊入,中间 加速,然后减速的到达⽬目的地。这个是默认的动画⾏行为。



# CALayer上动画的暂停和恢复
#pragma mark 暂停CALayer的动画 -(void)pauseLayer:(CALayer*)layer {
   CFTimeInterval pausedTime = [layer
convertTime:CACurrentMediaTime() fromLayer:nil];
// 让CALayer的时间停⽌止⾛走动 layer.speed = 0.0;
// 让CALayer的时间停留在pausedTime这个时刻
   layer.timeOffset = pausedTime;
}

#pragma mark 恢复CALayer的动画 -(void)resumeLayer:(CALayer*)layer {
CFTimeInterval pausedTime = layer.timeOffset; // 1. 让CALayer的时间继续⾏行⾛走
layer.speed = 1.0;
// 2. 取消上次记录的停留时刻
layer.timeOffset = 0.0; // 3. 取消上次设置的时间
     layer.beginTime = 0.0;
// 4. 计算暂停的时间(这⾥里也可以⽤用CACurrentMediaTime()-pausedTime)
   CFTimeInterval timeSincePause = [layer convertTime:CACurrentMediaTime()
fromLayer:nil] - pausedTime;
// 5. 设置相对于⽗父坐标系的开始时间(往后退timeSincePause) layer.beginTime = timeSincePause;
}
￼￼




CABasicAnimation——基本动画 ● 基本动画,是CAPropertyAnimation的⼦子类
● 属性说明:
● fromValue:keyPath相应属性的初始值 ● toValue:keyPath相应属性的结束值
● 动画过程说明:
● 随着动画的进⾏行,在长度为duration的持续时间内,keyPath相应属性的值从
● keyPath内容是CALayer的可动画Animatable属性
● 如果fillMode=kCAFillModeForwards同时removedOnComletion=NO,那么在 动画执⾏行完毕后,图层会保持显⽰示动画执⾏行后的状态。但在实质上,图层 的属性值还是动画执⾏行前的初始值,并没有真正被改变。
    <h3>CABasicAnimation
    // 创建一个基本动画
    CABasicAnimation *cab = [CABasicAnimation animationWithKeyPath:@"position"];
    
    // 修改的值
    cab.toValue = [NSValue valueWithCGPoint:CGPointMake(200, 400)];
    
    // 取消反弹
    cab.removedOnCompletion = NO;
    cab.duration = 3;
    cab.repeatCount = MAXFLOAT;
    cab.autoreverses = YES;
    
    //  动画保存最新效果
    cab.fillMode = kCAFillModeForwards;
    
    [self.vie.layer addAnimation:cab forKey:nil];
    
    
    
    
   <h3> CAKeyframeAnimation
   CAKeyframeAnimation——关键帧动画
● 关键帧动画,也是CAPropertyAnimation的⼦子类,与CABasicAnimation的区别是:
● CABasicAnimation只能从⼀一个数值(fromValue)变到另⼀一个数值(toValue), ⽽而CAKeyframeAnimation会使⽤用⼀一个NSArray保存这些数值
● 属性说明:
● values:上述的NSArray对象。⾥里⾯面的元素称为“关键帧”(keyframe)。动画对象会在指
定的时间(duration)内,依次显⽰示values数组中的每⼀一个关键帧
● path:可以设置⼀一个CGPathRef、CGMutablePathRef,让图层按照路径轨迹移 动。path只对CALayer的anchorPoint和position起作⽤用。如果设置了path,那么values将 被忽略
● keyTimes:可以为对应的关键帧指定对应的时间点,其取值范围为0到1.0,keyTimes 中的每⼀一个时间值都对应values中的每⼀一帧。如果没有设置keyTimes,各个关键帧的 时间是平分的
● CABasicAnimation可看做是只有2个关键帧的CAKeyframeAnimation
    // 创建一个帧动画
    CAKeyframeAnimation *cak = [CAKeyframeAnimation animation];
    
    cak.keyPath = @"transform.rotation";
    
    cak.values = @[@0.1,@0,@-0.1,@0.1];
    
    
    cak.duration = 0.3;
    cak.repeatCount = MAXFLOAT;
    
    [self.image.layer addAnimation:cak forKey:nil];
    
    
    <h4>CATransition
    转场动画——CATransition
● CATransition是CAAnimation的⼦子类,⽤用于做转场动画,能够为层提供 移出屏幕和移⼊入屏幕的动画效果。iOS⽐比Mac OS X的转场动画效果少 ⼀一点
● UINavigationController就是通过CATransition实现了将控制器的视图推 ⼊入屏幕的动画效果
● 动画属性:
● type:动画过渡类型
● subtype:动画过渡⽅方向
● startProgress:动画起点(在整体动画的百分⽐比) ● endProgress:动画终点(在整体动画的百分⽐比)

    static int i = 1;
    
    if (i == 4) {
        i =1;
    }
    
    // 转场动画必须先进行判断,在写动画,这样才会执行
    
    self.image.image = [UIImage imageNamed:[NSString stringWithFormat:@"%d",i]];
    
    i++;
    
    // 添加转场动画
    CATransition *cat = [CATransition animation];
    
    
    // 设置转场样式
    // 立体反转效果
    cat.type = @"cube";
    
//    // 水滴效果
//    cat.type = @"rippleEffect";
    
    // 抽布效果
//    cat.type = @"suckEffect";
    
    // 相机关闭效果
//    cat.type = @"cameraIrisHollowOpen";
    
    
    [self.image.layer addAnimation:cat forKey:nil];
    
    
    
    
CAAnimationGroup——动画组
● 动画组,是CAAnimation的⼦子类,可以保存⼀一组动画对象,
￼将CAAnimationGroup对象加⼊入层后,组中所有动画对象可以同时并发运⾏行
● 属性说明:
● animations:⽤用来保存⼀一组动画对象的NSArray
● 默认情况下,⼀一组动画对象是同时运⾏行的,也可以通过设置动画对象的 beginTime属性来更改动画的开始时间


使⽤用UIView动画函数实现转场动画——单视 图
● + (void)transitionWithView:(UIView *)view duration:(NSTimeInterval)duration options: (UIViewAnimationOptions)options animations:(void (^)(void))animations completion:(void (^)(BOOL finished))completion;
● 参数说明:
● duration:动画的持续时间
● view:需要进⾏行转场动画的视图
● options:转场动画的类型
● animations:将改变视图属性的代码放在这个block中 ● completion:动画结束后,会⾃自动调⽤用这个block



使⽤用UIView动画函数实现转场动画——双视 图
● + (void)transitionFromView:(UIView *)fromView toView:(UIView *)toView duration: (NSTimeInterval)duration options: (UIViewAnimationOptions)options completion:(void (^)(BOOL finished))completion;
● 参数说明:
● duration:动画的持续时间
● options:转场动画的类型
● animations:将改变视图属性的代码放在这个block中 ● completion:动画结束后,会⾃自动调⽤用这个block




CADisplayLink
● CADisplayLink是⼀一种以屏幕刷新频率触发的时钟机制,每秒钟执⾏行 ⼤大约60次左右
● CADisplayLink是⼀一个计时器,可以使绘图代码与视图的刷新频率保 持同步,⽽而NSTimer⽆无法确保计时器实际被触发的准确时间
● 使⽤用⽅方法:
● 定义CADisplayLink并制定触发调⽤用⽅方法 ● 将显⽰示链接添加到主运⾏行循环队列


# 源代码管理⼯工具


● SVN
● 全称是Subversion,集中式版本控制之王者
● 是CVS的接班⼈人,速度⽐比CVS快,功能⽐比CVS多且强⼤大 ● 在国内软件企业中使⽤用最为普遍(70%~90%)
● GIT
● ⼀一款伟⼤大的分布式源代码管理⼯工具 ● ⽬目前被越来越多的开源项⽬目使⽤用
● 不过在国内企业尚未⼤大范围普及


SVN 是集中式源代码管理工具

概念：
1> Repository   代码仓库，保存代码的仓库
2> Server       服务器，保存所有版本的代码仓库
3> Client       客户端，只保存当前用户的代码仓库
4> 用户名&密码   访问代码仓库需要使用自己的"用户名和密码"，从而可以区分出不同的人对代码做的修改

使⽤用环境

要想利⽤用SVN管理源代码,必须得有2套环境
服务器
⽤用于存储客户端上传的源代码 可以在Windows上安装Visual SVN Server ⼤大部分情况下,公司的开发⼈人员不必亲⾃自搭建SVN服务器
客户端
上传本地的源代码到服务器,或者更新服务器的代码到本地,保持同步 可以在Mac上使⽤用命令⾏行、Versions、Cornerstone、Xcode 开发⼈人员就属于客户端这个⾓角⾊色
￼

SVN客户端命令
● svn checkout :下载服务器的代码到本地 (简写svn co)
● svn commit :将改动的⽂文件提交到服务器(简写svn ci)
● svn update :更新服务器的代码到本地 (简写svn up)
● svn add :向本地的版本控制库中添加新⽂文件
● svn delete、svn remove :从本地的版本控制库中删除⽂文件(简写svn del、svn rm)
● svn move :移动⽂文件或者⽬目录或⽂文件更名
● svn mkdir :创建纳⼊入版本控制下的新⽬目录
● svn revert :撤销之前的⼀一切修改
● svn merge :将两个版本之间的差异合并到当前⽂文件


SVN客户端命令
● svn info :查看⽂文件的详细信息
● svn diff :查看不同版本的区别
● svn log :查看⽇日志信息
● svn list :列出版本库下的⽂文件和⽬目录列表
● svn status :查看⽂文件状态(简写svn st)
● svn help :获取帮助信息(⽐比如svn help ci)
● svn lock :加锁
● svn unlock :解锁


提交
● 将改动过的⽂文件提交⾄至服务器
● svn commit -m "注释" [PATH]
● svn ci -m "注释" [PATH] 注意:⼀一定要养成写注释的良好习惯
● ⽰示例
svn commit -m “修改了User.m⽂文件”
/Users/Desktop/workspace/Weibo/branches/User.m
● 橙⾊色代表的是:提交哪个⽂文件到服务器
● 如果省略橙⾊色的路径,就将命令⾏行所在路径中所有改动过的⽂文件提交 到服务器



添加
● 提交⼀一个新建的⽂文件到服务器,需要2个步骤
● 添加新建的⽂文件到本地的版本控制库中:svnadd
● 提交刚才的添加操作到服务器:svncommit
● 如果直接提交⼀一个没有添加到本地版本控制库中的⽂文件,会报下⾯面的错误
● is not a working copy

删除
● 删除服务器上的某个⽂文件,需要做2个步骤
● 将⽂文件从本地的版本控制库中移除:svndelete、svnremove
● 提交刚才的删除操作到服务器:svncommit
● 将⽂文件从本地的版本控制库中移除
● svn delete PATH
● ⽰示例
svn delete /Users/Desktop/workspace/Weibo/branches/User.m 
● 橙⾊色代表的是:将哪个⽂文件从版本控制库中移除


更新
● 将服务器的最新代码更新到本地
● svn update [PATH]
● ⽰示例
svn update /Users/lnj/Desktop/workspace/Weibo/branches/User.m
● 橙⾊色代表的是:更新哪个⽂文件的内容
● 如果省略橙⾊色的路径,就更新命令⾏行所在路径的所有内容
● 将⽂文件恢复⾄至某个版本
● svn update -r 版本号 [PATH]


常见问题总结
● 去到公司的第⼀一天,下载公司的代码到电脑上
● svn checkout
● 修改了某个早已存在的旧⽂文件,然后提交到服务器
● svn commit
● 提交⼀一个⾃自⼰己新建的⽂文件到服务器
● svn add ! svn commit
● 删除⼀一个早已存在的旧⽂文件,然后同步到服务器上
● svn delete ! svn commit
● 将其他同事提交的新代码更新到⾃自⼰己电脑上
● svn update


常见问题总结
● 不⼩小⼼心写错了很多东西,想撤销所写的东西(还未把修改提交到服务 器)
● svn revert
● 不⼩小⼼心删错了⽂文件,想把⽂文件恢复回来(还未把删除提交到服务器)
● svn revert
● 不⼩小⼼心写错了很多东西,想撤销所写的东西(已经把修改提交到服务
器)
● svn update -r 版本号
● 不⼩小⼼心删错了⽂文件,想把⽂文件恢复回来(已经把删除提交到服务器)
● svn update -r 版本号


注意!!!
● 注意
● .svn这个隐藏⽬目录记录着⾮非常关键的信息
● 千万不要⼿手⼯工修改或删除这个.svn隐藏⽬目录和⾥里⾯面的⽂文件!否则将会 导致本地的⼯工作副本被破坏,⽆无法再进⾏行操作



操作：
1> checkout     将服务器上最新的代码仓库下载到本地，"只需要做一次"
2> update       从服务器上将其他人所做的修改下载到本地，"每天上班必须要做的事情"
3> commit       将工作提交到服务器，"每天下班之前至少做一次"

03.	SVN服务器安装 Visual SVN Server

# checkout服务器上的代码仓库
$ svn co http://192.168.1.103/svn/weibo --username=manager --password=manager

提示：checkout(co)之后，命令行会记录用户名和密码，后续操作不用再另行指定


# 查看工作目录状态
$ svn st
# 将文件添加到本地版本库中
$ svn add main.c
# 将文件提交到服务器的版本库中
$ svn ci -m "添加了main.c文件"




# 多线程

创建和启动线程
● ⼀一个NSThread对象就代表⼀一条线程 ● 创建、启动线程
NSThread *thread = [[NSThread alloc] initWithTarget:self
selector:@selector(run) object:nil];
[thread start];
// 线程⼀一启动,就会在线程thread中执⾏行self的run⽅方法
● 主线程相关⽤用法
+ (NSThread *)mainThread; // 获得主线程 - (BOOL)isMainThread; // 是否为主线程
+ (BOOL)isMainThread; // 是否为主线程


其他⽤用法
● 获得当前线程
NSThread *current = [NSThread currentThread];
● 线程的名字
- (void)setName:(NSString *)n; - (NSString *)name;
- 

其他创建线程⽅方式
● 创建线程后⾃自动启动线程
[NSThread detachNewThreadSelector:@selector(run)
toTarget:self withObject:nil]; ● 隐式创建并启动线程
[self performSelectorInBackground:@selector(run)
withObject:nil];
● 上述2种创建线程⽅方式的优缺点
● 优点:简单快捷
● 缺点:⽆无法对线程进⾏行更详细的设置


控制线程状态
● 启动线程
- (void)start;
// 进⼊入就绪状态 -> 运⾏行状态。当线程任务执⾏行完毕,⾃自动进⼊入死亡状态
● 阻塞(暂停)线程
+ (void)sleepUntilDate:(NSDate *)date;
+ (void)sleepForTimeInterval:(NSTimeInterval)ti; // 进⼊入阻塞状态
● 强制停⽌止线程 + (void)exit; // 进⼊入死亡状态
注意:⼀一旦线程停⽌止(死亡)了,就不能再次开启任务


安全隐患解决 – 互斥锁
● 互斥锁使⽤用格式
@synchronized(锁对象) { // 需要锁定的代码 } 注意:锁定1份代码只⽤用1把锁,⽤用多把锁是⽆无效的
● 互斥锁的优缺点
● 优点:能有效防⽌止因多线程抢夺资源造成的数据安全问题 ● 缺点:需要消耗⼤大量的CPU资源
● 互斥锁的使⽤用前提:多条线程抢夺同⼀一块资源


原⼦子和⾮非原⼦子属性
● OC在定义属性时有nonatomic和atomic两种选择
● atomic:原⼦子属性,为setter⽅方法加锁(默认就是atomic) ● nonatomic:⾮非原⼦子属性,不会为setter⽅方法加锁



<h4>线程间通信
● 什么叫做线程间通信
● 在1个进程中,线程往往不是孤⽴立存在的,多个线程之间需要经常进⾏行通信
● 线程间通信的体现
● 1个线程传递数据给另1个线程
● 在1个线程中执⾏行完特定任务后,转到另1个线程继续执⾏行任务
● 线程间通信常⽤用⽅方法
- (void)performSelectorOnMainThread:(SEL)aSelector
withObject:(id)arg waitUntilDone:(BOOL)wait;
- (void)performSelector:(SEL)aSelector onThread:(NSThread
*)thr withObject:(id)arg waitUntilDone:(BOOL)wait;




# GCD
● GCD的优势
● GCD是苹果公司为多核的并⾏行运算提出的解决⽅方案
● GCD会⾃自动利⽤用更多的CPU内核(⽐比如双核、四核)
● GCD会⾃自动管理线程的⽣生命周期(创建线程、调度任务、销毁线程)
● 程序员只需要告诉GCD想要执⾏行什么任务,不需要编写任何线程管理代码

● 将任务添加到队列中
• GCD会⾃自动将队列中的任务取出,放到对应的线程中执⾏行 • 任务的取出遵循队列的FIFO原则:先进先出,后进后出


执⾏行任务
● GCD中有2个⽤用来执⾏行任务的常⽤用函数 ● ⽤用同步的⽅方式执⾏行任务
dispatch_sync(dispatch_queue_t queue, dispatch_block_t
block);
• queue:队列 • block:任务
● ⽤用异步的⽅方式执⾏行任务
dispatch_async(dispatch_queue_t queue, dispatch_block_t
block);
● 同步和异步的区别
● 同步:只能在当前线程中执⾏行任务,不具备开启新线程的能⼒
● 异步:可以在新的线程中执⾏行任务,具备开启新线程的能⼒


执⾏行任务
● GCD中还有个⽤用来执⾏行任务的函数: dispatch_barrier_async(dispatch_queue_t queue,
dispatch_block_t block); 在前⾯面的任务执⾏行结束后它才执⾏行,⽽而且它后⾯面的任务等它执⾏行完成之后才会执
⾏
● 这个queue不能是全局的并发队列



<h4>队列的类型
● GCD的队列可以分为2⼤大类型
● 并发队列(Concurrent Dispatch Queue)
• 可以让多个任务并发(同时)执⾏行(⾃自动开启多个线程同时执⾏行任务) • 并发功能只有在异步(dispatch_async)函数下才有效
● 串⾏行队列(Serial Dispatch Queue)
• 让任务⼀一个接着⼀一个地执⾏行(⼀一个任务执⾏行完毕后,再执⾏行下⼀一个任务)


<h3>并发队列
● 使⽤用dispatch_queue_create函数创建队列 dispatch_queue_t
dispatch_queue_create(const char *label, // 队列名称 dispatch_queue_attr_t attr); // 队列的类型
● 创建并发队列
dispatch_queue_t queue = dispatch_queue_create("com.520it.queue",
DISPATCH_QUEUE_CONCURRENT);
● 获得全局并发队列 dispatch_queue_t queue =
dispatch_get_global_queue(DISPATCH_QUEUE_PRIORITY_DEFAULT, 0);(和并发队列要区分)



<h3>串⾏行队列
● GCD中获得串⾏行有2种途径
● 使⽤用dispatch_queue_create函数创建串⾏行队列
// 创建串⾏行队列(队列类型传递NULL或者DISPATCH_QUEUE_SERIAL)
dispatch_queue_t queue = dispatch_queue_create("com.520it.queue", NULL);
● 使⽤用主队列(跟主线程相关联的队列)
• 主队列是GCD⾃自带的⼀一种特殊的串⾏行队列
• 放在主队列中的任务,都会放到主线程中执⾏行
• 使⽤用dispatch_get_main_queue()获得主队列 dispatch_queue_t queue = dispatch_get_main_queue();




<h4>线程间通信⽰示例
● 从⼦子线程回到主线程
dispatch_async( dispatch_get_global_queue(DISPATCH_QUEUE_PRIORITY_DEFAULT, 0), ^{
// 执⾏行耗时的异步操作... dispatch_async(dispatch_get_main_queue(), ^{
// 回到主线程,执⾏行UI刷新操作
}); })



<h4>延时执⾏行
● iOS常见的延时执⾏行
● 调⽤用NSObject的⽅方法
[self performSelector:@selector(run) withObject:nil
afterDelay:2.0];
// 2秒后再调⽤用self的run⽅方法 ● 使⽤用GCD函数
dispatch_after(dispatch_time(DISPATCH_TIME_NOW, (int64_t)(2.0 *
NSEC_PER_SEC)), dispatch_get_main_queue(), ^{
// 2秒后执⾏行这⾥里的代码... });
● 使⽤用NSTimer
[NSTimer scheduledTimerWithTimeInterval:2.0 target:self
selector:@selector(test) userInfo:nil repeats:NO]



<h4>一次性代码
● 使⽤用dispatch_once函数能保证某段代码在程序运⾏行过程中只被执⾏行1次 static dispatch_once_t onceToken;
dispatch_once(&onceToken, ^{
// 只执⾏行1次的代码(这⾥里⾯面默认是线程安全的) });



<h4>快速迭代
● 使⽤用dispatch_apply函数能进⾏行快速迭代遍历 dispatch_apply(10, dispatch_get_global_queue(0, 0), ^(size_t
index){
// 执⾏行10次代码,index顺序不确定 });



<h4>队列组
● 有这么1种需求
● ⾸首先:分别异步执⾏行2个耗时的操作
● 其次:等2个异步操作都执⾏行完毕后,再回到主线程执⾏行操作
● 如果想要快速⾼高效地实现上述需求,可以考虑⽤用队列组 dispatch_group_t group = dispatch_group_create();
dispatch_group_async(group,
dispatch_get_global_queue(DISPATCH_QUEUE_PRIORITY_DEFAULT, 0),
^{
// 执⾏行1个耗时的异步操作 });
dispatch_group_async(group,
dispatch_get_global_queue(DISPATCH_QUEUE_PRIORITY_DEFAULT, 0),
^{
￼￼// 执⾏行1个耗时的异步操作 });
dispatch_group_async(group, dispatch_get_main_queue(),
^{
// 最后面执行的操作 });



<h4>单例模式
● ARC中,单例模式的实现
● 在.m中保留⼀一个全局的static的实例 static id _instance;
● 重写allocWithZone:⽅方法,在这⾥里创建唯⼀一的实例(注意线程安全) + (instancetype)allocWithZone:(struct _NSZone *)zone
{
   static dispatch_once_t onceToken;
   dispatch_once(&onceToken, ^{
       _instance = [super allocWithZone:zone];
   });
   return _instance;
}


● 提供1个类⽅方法让外界访问唯⼀一的实例 + (instancetype)sharedInstance {
   static dispatch_once_t onceToken;
   dispatch_once(&onceToken, ^{
       _instance = [[self alloc] init];
   });
   return _instance;
}
● 实现copyWithZone:⽅方法
- (id)copyWithZone:(struct _NSZone *)zone {
￼￼   return _instance;
}



# NSOperation

● 创建NSInvocationOperation对象
- (id)initWithTarget:(id)target selector:(SEL)sel object:
(id)arg;
● 调⽤用start⽅方法开始执⾏行操作
- (void)start; ⼀一旦执⾏行操作,就会调⽤用target的sel⽅方法
￼● 注意
● 默认情况下,调⽤用了start⽅方法后并不会开⼀一条新线程去执⾏行操作,⽽而是在当
￼前线程同步执⾏行操作
● 只有将NSOperation放到⼀一个NSOperationQueue中,才会异步执⾏行操作


NSBlockOperation
● 创建NSBlockOperation对象
+ (id)blockOperationWithBlock:(void (^)(void))block;
● 通过addExecutionBlock:⽅方法添加更多的操作
- (void)addExecutionBlock:(void (^)(void))block;
注意:只要NSBlockOperation封装的操作数 > 1,就会异步执⾏行操作


NSOperationQueue
● NSOperationQueue的作⽤用
● NSOperation可以调⽤用start⽅方法来执⾏行任务,但默认是同步执⾏行的
● 如果将NSOperation添加到NSOperationQueue(操作队列)中,系统会 ⾃自动异步执⾏行NSOperation中的操作
● 添加操作到NSOperationQueue中
- (void)addOperation:(NSOperation *)op;
- (void)addOperationWithBlock:(void (^)(void))block;
- 

最⼤大并发数
● 什么是并发数
● 同时执⾏行的任务数
● ⽐比如,同时开3个线程执⾏行3个任务,并发数就是3
● 最⼤大并发数的相关⽅方法
- (NSInteger)maxConcurrentOperationCount;
- (void)setMaxConcurrentOperationCount:(NSInteger)cnt;
- 


队列的取消、暂停、恢复
● 取消队列的所有操作
- (void)cancelAllOperations; 提⽰示:也可以调⽤用NSOperation的- (void)cancel⽅方法取消单个操作
● 暂停和恢复队列
- (void)setSuspended:(BOOL)b; // YES代表暂停队列,NO代表恢复队列 - (BOOL)isSuspended;
- 


<h4>操作依赖
● NSOperation之间可以设置依赖来保证执⾏行顺序
● ⽐比如⼀一定要让操作A执⾏行完后,才能执⾏行操作B,可以这么写 [operationB addDependency:operationA]; // 操作B依赖于操作A
● 可以在不同queue的NSOperation之间创建依赖关系


<h4>操作的监听
● 可以监听⼀一个操作的执⾏行完毕
- (void (^)(void))completionBlock;
- (void)setCompletionBlock:(void (^)(void))block;
- 



<h4>自定义NSOperation
● ⾃自定义NSOperation的步骤很简单
● 重写- (void)main⽅方法,在⾥里⾯面实现想执⾏行的任务
● 重写- (void)main⽅方法的注意点
● ⾃自⼰己创建⾃自动释放池(因为如果是异步操作,⽆无法访问主线程的⾃自动释放池)
● 经常通过- (BOOL)isCancelled⽅方法检测操作是否被取消,对取消做出响应



# 网络

<h5>NSURLConnection

NSURLConnection的使⽤用步骤
● 使⽤用NSURLConnection发送请求的步骤很简单
● 创建⼀一个NSURL对象,设置请求路径
● 传⼊入NSURL创建⼀一个NSURLRequest对象,设置请求头和请求体 ● 使⽤用NSURLConnection发送请求


NSURLConnection发送请求
● NSURLConnection常见的发送请求⽅方法有以下⼏几种 ● 同步请求
+ (NSData *)sendSynchronousRequest:(NSURLRequest *)request
returningResponse:(NSURLResponse **)response error:(NSError
**)error;
● 异步请求:根据对服务器返回数据的处理⽅方式的不同,又可以分为2种
• block回调
+ (void)sendAsynchronousRequest:(NSURLRequest*) request
                     queue:(NSOperationQueue*) queue
 completionHandler:(void (^)(NSURLResponse* response,
NSData* data, NSError* connectionError)) handler;
￼
• 代理
- (id)initWithRequest:(NSURLRequest *)request delegate:(id)delegate;
+ (NSURLConnection*)connectionWithRequest:(NSURLRequest *)request
delegate:(id)delegate;
- (id)initWithRequest:(NSURLRequest *)request delegate:(id)delegate
startImmediately:(BOOL)startImmediately;
● 在startImmediately = NO的情况下,需要调⽤用start⽅方法开始发送请求 - (void)start;
● 成为NSURLConnection的代理,最好遵守NSURLConnectionDataDelegate协议


NSURLConnectionDelegate
● NSURLConnectionDataDelegate协议中的代理⽅方法 ● 开始接收到服务器的响应时调⽤用
- (void)connection:(NSURLConnection *)connection
didReceiveResponse:(NSURLResponse *)response;
● 接收到服务器返回的数据时调⽤用(服务器返回的数据⽐比较⼤大时会调⽤用多次)
- (void)connection:(NSURLConnection *)connection didReceiveData:
(NSData *)data;
● 服务器返回的数据完全接收完毕后调⽤用
- (void)connectionDidFinishLoading:(NSURLConnection *)connection; ● 请求出错时调⽤用(⽐比如请求超时)
- (void)connection:(NSURLConnection *)connection didFailWithError:
(NSError *)error;

<h4>获得⽂文件的MIMEType
● 利⽤用NSURLConnection
- (NSString *)MIMEType:(NSURL *)url {
// 1.创建⼀一个请求
NSURLRequest *request = [NSURLRequest
requestWithURL:url];
// 2.发送请求(返回响应)
   NSURLResponse *response = nil;
   [NSURLConnection sendSynchronousRequest:request
returningResponse:&response error:nil];
// 3.获得MIMEType
   return response.MIMEType;
}



NSMutableURLRequest
● NSMutableURLRequest是NSURLRequest的⼦子类,常⽤用⽅方法有
● 设置请求超时等待时间(超过这个时间就算超时,请求失败)
- (void)setTimeoutInterval:(NSTimeInterval)seconds;
● 设置请求⽅方法(⽐比如GET和POST)
- (void)setHTTPMethod:(NSString *)method;
● 设置请求体
- (void)setHTTPBody:(NSData *)data;
● 设置请求头
- (void)setValue:(NSString *)value forHTTPHeaderField:(NSString
*)field;



创建GET和POST请求 ● 创建GET请求
NSString *urlStr = [@"http://120.25.226.186:32812/login?
username=123&pwd=123"
stringByAddingPercentEscapesUsingEncoding:NSUTF8StringEncoding];
NSURL *url = [NSURL URLWithString:urlStr];
NSMutableURLRequest *request = [NSMutableURLRequest
requestWithURL:url];
● 创建POST请求
NSString *urlStr = @"http://120.25.226.186:32812/login";
NSURL *url = [NSURL URLWithString:urlStr];
NSMutableURLRequest *request = [NSMutableURLRequest
requestWithURL:url];
request.HTTPMethod = @"POST";
// 请求体
NSString *bodyStr = @"username=123&pwd=123";
request.HTTPBody = [bodyStr dataUsingEncoding:NSUTF8StringEncoding];



<h5> NSURLSession
获得NSURLSession 
● 获得共享的Session
+ (NSURLSession *)sharedSession; 
+ ● ⾃自定义Session
+ (NSURLSession *)sessionWithConfiguration:
(NSURLSessionConfiguration *)configuration delegate:(id
<NSURLSessionDelegate>)delegate delegateQueue:
(NSOperationQueue *)queue;


NSURLSessionTask
● 常见⽅方法
● - (void)suspend; // 暂停
● - (void)resume; // 恢复
● - (void)cancel; // 取消
● @property (readonly, copy) NSError *error; // 错误
● @property (readonly, copy) NSURLResponse *response; // 响应


NSURLSessionDownloadTask
￼● 常见⽅方法
- (void)cancelByProducingResumeData:(void (^)(NSData
*resumeData))completionHandler; // 取消任务


<h5> AFN

AFHTTPSessionManager
● AFHTTPSessionManager
● 是AFN中最重要的对象之⼀一 ● 封装了HTTP请求的常见处理 • GET\POST请求
• 解析服务器的响应数据
• 创建
AFHTTPSessionManager *mgr = [AFHTTPSessionManager manager];

GET\POST请求
● GET请求
- (NSURLSessionDataTask *)GET:(NSString *)URLString
                  parameters:(id)parameters
                  success:(void (^)(NSURLSessionDataTask *task, id
responseObject))success
                  failure:(void (^)(NSURLSessionDataTask *task,
NSError *error))failure
● POST请求
- (NSURLSessionDataTask *)POST:(NSString *)URLString
                  parameters:(id)parameters
                  success:(void (^)(NSURLSessionDataTask *task, id
responseObject))success
                  failure:(void (^)(NSURLSessionDataTask *task,
NSError *error))failure


<h4>⽂文件上传
- (NSURLSessionDataTask *)POST:(NSString *)URLString
                   parameters:(id)parameters
    constructingBodyWithBlock:(void (^)(id <AFMultipartFormData>
formData))block
                   success:(void (^)(NSURLSessionDataTask *task, id
responseObject))success
                   failure:(void (^)(NSURLSessionDataTask *task,
NSError *error))failure


<h4>监控联⽹网状态
// 创建一个网络监听对象
    AFNetworkReachabilityManager *net = [AFNetworkReachabilityManager sharedManager];
    
    // 设置监听
    [net setReachabilityStatusChangeBlock:^ void(AFNetworkReachabilityStatus status) {
        switch (status) {
           
            case AFNetworkReachabilityStatusNotReachable:
                // 做一些这个网络环境下得操作
                // ..
                 NSLog(@"未识别");
                break;
                
            case AFNetworkReachabilityStatusReachableViaWWAN:
                 NSLog(@"3G");
                break;
                
            case AFNetworkReachabilityStatusReachableViaWiFi:
                 NSLog(@"WIFI");
                break;
                
            default:
                NSLog(@"未连接");
                break;
        }
    }];
    
    // 开始监听
    [net startMonitoring];⽰示:要监控⽹网络连接状态,必须要先调⽤用单例的startMonitoring⽅方法
    
    
    # JSON和XML
JSON解析⽅方案
● 在iOS中,JSON的常见解析⽅方案有4种
● 第三⽅方框架:JSONKit、SBJson、TouchJSON(性能从左到右,越差)
● 苹果原⽣生(⾃自带):NSJSONSerialization(性能最好)
● NSJSONSerialization的常见⽅方法
● JSON数据 -- OC对象
+ (id)JSONObjectWithData:(NSData *)data options:
(NSJSONReadingOptions)opt error:(NSError **)error;
● OC对象 -- JSON数据
+ (NSData *)dataWithJSONObject:(id)obj options:
(NSJSONWritingOptions)opt error:(NSError **)error;

<h4>iOS中的XML解析
● 在iOS中,解析XML的⼿手段有很多
● 苹果原⽣生
• NSXMLParser:SAX⽅方式解析,使⽤用简单
● 第三⽅方框架
• libxml2:纯C语⾔言,默认包含在iOS SDK中,同时⽀支持DOM和SAX⽅方式解析 • GDataXML:DOM⽅方式解析,由Google开发,基于libxml2
● XML解析⽅方式的选择建议
● ⼤大⽂文件:NSXMLParser、libxml2
● ⼩小⽂文件:GDataXML、NSXMLParser、libxml2

NSXMLParser
● 使⽤用步骤
// 传⼊入XML数据,创建解析器
NSXMLParser *parser = [[NSXMLParser alloc] initWithData:data]; // 设置代理,监听解析过程
parser.delegate = self;
// 开始解析
[parser parse];
● NSXMLParser采取的是SAX⽅方式解析,特点是事件驱动,下⾯面情况都会通知代理 ● 当扫描到⽂文档(Document)的开始与结束
● 当扫描到元素(Element)的开始与结束


NSXMLParserDelegate
● 当扫描到⽂文档的开始时调⽤用(开始解析)
- (void)parserDidStartDocument:(NSXMLParser *)parser
● 当扫描到⽂文档的结束时调⽤用(解析完毕)
- (void)parserDidEndDocument:(NSXMLParser *)parser
● 当扫描到元素的开始时调⽤用(attributeDict存放着元素的属性)
- (void)parser:(NSXMLParser *)parser didStartElement:(NSString
*)elementName namespaceURI:(NSString *)namespaceURI qualifiedName:
(NSString *)qName attributes:(NSDictionary *)attributeDict
● 当扫描到元素的结束时调⽤用
- (void)parser:(NSXMLParser *)parser didEndElement:(NSString
*)elementName namespaceURI:(NSString *)namespaceURI qualifiedName:
(NSString *)qName



<h5> RunLoop

RunLoop对象
● iOS中有2套API来访问和使⽤用RunLoop
● Foundation
● NSRunLoop
● Core Foundation
● CFRunLoopRef
● NSRunLoop和CFRunLoopRef都代表着RunLoop对象
RunLoop与线程
● 每条线程都有唯⼀一的⼀一个与之对应的RunLoop对象
● 主线程的RunLoop已经⾃自动创建好了,⼦子线程的RunLoop需要主动创建 ● RunLoop在第⼀一次获取时创建,在线程结束时销毁
● NSRunLoop是基于CFRunLoopRef的⼀一层OC包装,所以要了解RunLoop内部
结构,需要多研究CFRunLoopRef层⾯面的API(Core Foundation层⾯面)



获得RunLoop对象
● Foundation
[NSRunLoop currentRunLoop]; // 获得当前线程的RunLoop对象 [NSRunLoop mainRunLoop]; // 获得主线程的RunLoop对象
● Core Foundation
CFRunLoopGetCurrent(); // 获得当前线程的RunLoop对象 CFRunLoopGetMain(); // 获得主线程的RunLoop对象


RunLoop相关类
● Core Foundation中关于RunLoop的5个类
● CFRunLoopRef
● CFRunLoopModeRef
● CFRunLoopSourceRef
● CFRunLoopTimerRef
● CFRunLoopObserverRef


CFRunLoopModeRef
● CFRunLoopModeRef代表RunLoop的运⾏行模式
● ⼀一个RunLoop包含若⼲干个Mode,每个Mode又包含若⼲干
个Source/Timer/Observer
● 每次RunLoop启动时,只能指定其中⼀一个Mode,这个Mode被称作
CurrentMode
● 如果需要切换Mode,只能退出Loop,再重新指定⼀一个Mode进⼊入
● 这样做主要是为了分隔开不同组的Source/Timer/Observer,让其互不影响

● 系统默认注册了5个Mode:
● NSDefaultRunLoopMode:App的默认Mode,通常主线程是在这个Mode下运⾏行
● UITrackingRunLoopMode:界⾯面跟踪 Mode,⽤用于 ScrollView 追踪触摸滑动, 保证界⾯面滑动时不受其他 Mode 影响
● UIInitializationRunLoopMode: 在刚启动 App 时第进⼊入的第⼀一个 Mode,启动完成后 就不再使⽤用
● GSEventReceiveRunLoopMode: 接受系统事件的内部 Mode,通常⽤用不到
● NSRunLoopCommonModes: 这是⼀一个占位⽤用的Mode,不是⼀一种真正的Mode


CFRunLoopTimerRef
● CFRunLoopTimerRef是基于时间的触发器
● CFRunLoopTimerRef基本上说的就是NSTimer,它受RunLoop的Mode影响 ● GCD的定时器不受RunLoop的Mode影响


CFRunLoopSourceRef
● CFRunLoopSourceRef是事件源(输⼊入源)
● 按照官⽅方⽂文档,Source的分类
● Port-Based Sources
● Custom Input Sources
● Cocoa Perform Selector Sources
● 按照函数调⽤用栈,Source的分类
● Source0:⾮非基于Port的, ⽤用于⽤用户主动触发事件
● Source1:基于Port的,通过内核和其他线程相互发送消息



CFRunLoopObserverRef
● 添加Observer // 创建observer
CFRunLoopObserverRef observer =
CFRunLoopObserverCreateWithHandler(CFAllocatorGetDefault(),
kCFRunLoopAllActivities, YES, 0, ^(CFRunLoopObserverRef observer,
CFRunLoopActivity activity) {
NSLog(@"----监听到RunLoop状态发⽣生改变---%zd", activity); });
// 添加观察者:监听RunLoop的状态 CFRunLoopAddObserver(CFRunLoopGetCurrent(), observer,
kCFRunLoopDefaultMode);
// 释放Observer CFRelease(observer);


RunLoop应⽤用
● NSTimer
● ImageView显⽰
● PerformSelector 
● 常驻线程
 1.源实现造成线程停驻(用当前的runloop添加一个mach事件源)
//    [[NSRunLoop currentRunLoop] addPort:[NSMachPort port] forMode:NSRunLoopCommonModes];
[[NSRunLoop currentRunLoop] run];
// 2.定时器实现线程停驻
    NSTimer *time = [NSTimer scheduledTimerWithTimeInterval:1 target:self selector:@selector(test) userInfo:nil repeats:YES];
    [[NSRunLoop currentRunLoop] run];
● 自动释放池



<h5>视频
● iOS提供了MPMoviePlayerController、MPMoviePlayerViewController两个类, 可以⽤用来轻松播放视频和⽹网络流媒体/⽹网络⾳音频
● 提⽰示:⽹网络⾳音频同样使⽤用此控制器播放
● YouTobe就是⽤用MPMoviePlayerController实现的 
● MPMoviePlayerViewController只能全屏播放视频 
● 上述两个类都定义在了MediaPlayer框架中

MPMoviePlayerController⽀支持的格式

MPMoviePlayerController
● 继承⾃自NSObject
● 内部有个view可以展⽰示视频内容
● 将该视图添加其他控制器的view上,即可显⽰示视频内容
MPMoviePlayerController可以播放的视频格式包括: ● H.264、MPEG-4等
⽀支持的⽂文件扩展名包括:avi,mkv,mov,m4v,mp4等


MPMoviePlayerController的使⽤用
● 加载视频资源(注意,如果url为nil同样可以加载)
NSAssert(self.url, @"URL不能为空");
[[MPMoviePlayerController alloc] initWithContentURL:self.url];
● 显⽰示
[self.view addSubview:self.moviePlayer.view];
通过设置AutoresizingMask属性可以在横竖屏转换时⾃自动调整视图⼤大⼩小
● 播放
  [self.moviePlayer play];
● 全屏
  [self.moviePlayer setFullscreen:YES animated:YES];
● MPMoviePlayerController的播放状态是通过通知中⼼心监听的


常⽤用监听通知事件
● 状态变化 MPMoviePlayerPlaybackStateDidChangeNotification
● 播放结束 MPMoviePlayerPlaybackDidFinishNotification
● 退出全屏 MPMoviePlayerDidExitFullscreenNotification
● 截屏完成 MPMoviePlayerThumbnailImageRequestDidFinishNotification
● 截屏⽅方法 -requestThumbnailImagesAtTimes:timeOption:


<h5>UIWebView

● 什么是UIWebView
● UIWebView是iOS内置的浏览器控件
● 系统⾃自带的Safari浏览器就是通过UIWebView实现的
● UIWebView不但能加载远程的⽹网页资源,还能加载绝⼤大部分的常见⽂文件 ● html\htm
● pdf、doc、ppt、txt
● mp4
●......
● UIWebView常⽤用的加载资源的⽅方法
- (void)loadRequest:(NSURLRequest *)request;
- 
常⽤用属性和⽅方法
● 重新加载(刷新) - (void)reload;
● 停⽌止加载
- (void)stopLoading;
● 回退
- (void)goBack;
● 前进
- (void)goForward;
● 需要进⾏行检测的数据类型
@property(nonatomic) UIDataDetectorTypes dataDetectorTypes

● 是否能回退 @property(nonatomic,readonly,getter=canGoBack) BOOL
canGoBack;
● 是否能前进 @property(nonatomic,readonly,getter=canGoForward) BOOL
canGoForward;
● 是否正在加载中
@property(nonatomic,readonly,getter=isLoading) BOOL loading;
● 是否伸缩内容⾄至适应屏幕当前尺⼨寸 @property(nonatomic) BOOL scalesPageToFit;


监听UIWebView的加载过程
● 成为UIWebView的代理,遵守UIWebViewDelegate协议,就能监
听UIWebView的加载过程
● 开始发送请求(加载数据)时调⽤用这个⽅方法
- (void)webViewDidStartLoad:(UIWebView *)webView;
● 请求完毕(加载数据完毕)时调⽤用这个⽅方法
- (void)webViewDidFinishLoad:(UIWebView *)webView;
● 请求错误时调⽤用这个⽅方法
- (void)webView:(UIWebView *)webView didFailLoadWithError:
(NSError *)error;


监听UIWebView的加载过程
● UIWebView在发送请求之前,都会调⽤用这个⽅方法,如果返回NO,代表停⽌止加载
- (BOOL)webView:(UIWebView *)webView
shouldStartLoadWithRequest:(NSURLRequest *)request
navigationType:(UIWebViewNavigationType)navigationType;




# HTML5
⽹网页的组成
● ⼀一个有具体功能的完整的⽹网页,⼀一般由3部分组成 ● HTML
• ⽹网页的具体内容和结构
● CSS
• ⽹网页的样式(美化⽹网页最重要的⼀一块)
● JavaScript(掌握)
• ⽹网页的交互效果,⽐比如对⽤用户⿏鼠标事件做出响应

常见的HTML标签
● 标题:h1、h2、h3、h4、h5....
● 段落:p
● 换⾏行:br
● 容器:div、span(⽤用来容纳其他标签) ● 表格:table、tr、td
● 列表:ul、ol、li ● 图⽚片:img
● 表单:input
● 链接:a

HTML5新增标签 HTML5新增了27个标签元素,废弃了16个标签元素,主要包括结构
1.结构性标签 负责Web上下⽂文结构的定义,确保HTML⽂文档,包括:
● article ⽂文章主体内容(⼀一篇博客、⼀一篇论坛帖⼦子、⼀一段⽤用户评论、插件)
● header 标记头部区域内容
● footer 标记脚部区域内容
● section 区域章节表述
● nav 菜单导航,链接导航

HTML5新增标签
2.块级性标签 完成Web页⾯面区域的划分,确保内容的有效分隔,包括:
● aside 注记,贴⼠士,侧栏,摘要,插⼊入的引⽤用作为补充主体的内容
● figure 对多个元素组合并展⽰示的元素,常与figcaption联合使⽤用 ● code 表⽰示⼀一段代码块
● dialog ⼈人与⼈人之间对话,包含dt和dd两个组合元素(dt⽤用于表⽰示说话者、dd⽤用 于表⽰示说话者的内容)


HTML5新增标签 3.⾏行内语义性标签
完成Web页⾯面具体内容的引⽤用和表述,丰富展⽰示内容,包括:
● meter 特定范围内的数值,如⼯工资、数量、百分⽐比
● time 时间值
● progress 进度条,可⽤用max、min、step进⾏行控制,完成对进度的表⽰示和监听 ● video 视频元素,⽤用于视频播放,⽀支持缓冲预载和多种视频媒体格式
● audio ⾳音频元素,⽤用于⾳音频播放,⽀支持缓冲预载和多种⾳音频媒体格式

HTML5新增标签 4.交互性标签
功能性内容的表达,有⼀一定的内容和数据的关联,是各种事件的基础,包
括:
● details 表⽰示⼀一段具体的内容,默认不显⽰示,通过某种⽅方式(单击)与legend交互 才会显⽰示
● datagrid 控制客户端数据与显⽰示,可⽤用于动态脚本及时更新 ● menu ⽤用于交互菜单
● command ⽤用来处理命令按钮


<h4>CSS
● 什么是CSS
● CSS的全称是Cascading Style Sheets,层叠样式表
● 它⽤用来控制HTML标签的样式,在美化⽹网页中起到⾮非常重要的作⽤用
● CSS的编写格式是键值对形式的,⽐比如 color: red;
background-color: blue; font-size: 20px;
● 冒号:左边的是属性名,冒号:右边的属性值


CSS的3种书写形式
● CSS有3种书写形式
● ⾏行内样式:(内联样式)直接在标签的style属性中书写 <body style="color: red;">
● 页内样式:在本⽹网页的style标签中书写 <style>
   body {
       color: red;
}
</style>
● 外部样式:在单独的CSS⽂文件中书写,然后在⽹网页中⽤用link标签引⽤用 <link rel="stylesheet" href="index.css">


CSS的两⼤大重点 ● 属性
通过属性的复杂叠加才能做出漂亮的⽹网页
● 选择器 通过选择器找到对应的标签设置样式


CSS选择器 – 选择器优先级 ● 优先级排序
● important > 内联 > id > 类 > 标签 | 伪类 | 属性选择 > 伪元素 > 通配符 > 继承



HTML标签类型
● HTML有N多标签,根据显⽰示的类型,主要可以分为3⼤大类 ● 块级标签
• 独占⼀一⾏行的标签
• 能随时设置宽度和⾼高度(⽐比如div、p、h1、h2、ul、li)
● ⾏行内标签(内联标签)
• 多个⾏行内标签能同时显⽰示在⼀一⾏行
• 宽度和⾼高度取决于内容的尺⼨寸(⽐比如span、a、label)
● ⾏行内-块级标签(内联-块级标签)
• 多个⾏行内-块级标签可以显⽰示在同⼀一⾏行
• 能随时设置宽度和⾼高度(⽐比如input、button)


修改标签的显⽰示类型
● CSS中有个display属性,能修改标签的显⽰示类型 ● none:隐藏标签
● block:让标签变为块级标签
● inline:让标签变为⾏行内标签
● inline-block:让标签变为⾏行内-块级标签(内联-块级标签)


CSS属性
● CSS有N多属性,根据继承性,主要可以分为2⼤大类 ● 可继承属性
• ⽗父标签的属性值会传递给⼦子标签
• ⼀一般是⽂文字控制属性
● 不可继承属性
• ⽗父标签的属性值不能传递给⼦子标签 • ⼀一般是区块控制属性


<h5>盒⼦子模型
● ⽹网页上的每⼀一个标签都是⼀一个盒⼦子
● 每个盒⼦子都有四个属性
● 内容(content)
• 盒⼦子⾥里装的东西
• ⽹网页中通常是指⽂文字和图⽚片
● 填充(padding,内边距)
• 怕盒⼦子⾥里装的(贵重的)东西损坏,⽽而添加的泡沫或者其它抗震的辅料
● 边框(border):盒⼦子本⾝身 ● 边界(margin,外边距)
• 盒⼦子摆放的时候的不能全部堆在⼀一起,盒⼦子之间要留⼀一定空隙保持通风,同时也为了⽅方 便取出




<h5>JavaScript

● JS的常见⽤用途
• HTML DOM操作(节点操作,⽐比如添加、修改、删除节点) • 给HTML⽹网页增加动态功能,⽐比如动画
• 事件处理:⽐比如监听⿏鼠标点击、⿏鼠标滑动、键盘输⼊入


JavaScript的书写⽅方式
● JS常见的书写⽅方式有2种
● 页内JS:在当前⽹网页的script标签中编写 <script type="text/javascript"> </script>
● 外部JS
<script src="index.js"></script>

Canvas
● HTML
<canvas id="canvas"></canvas>
● JS
var canvas = document.getElementById('canvas');
var context = canvas.getContext('2d');
context是⼀一个绘图的上下⽂文环境 2d是⼆二维图形


Canvas绘制直线
● 起点 context.moveTo(100,100);
● 终点 context.lineTo(400, 400);
● 绘制 context.stroke();
● 设置线条颜⾊色和宽度 context.strokeStyle = 'red'; context.lineWidth = 5;
● 设置填充⾊色 context.fillStyle = 'blue';


Canvas绘制弧线
context.arc(
centerX, centerY, radius, startingAngle, endingAngle, anticlockwise=false
)
centerX, centerY: 圆⼼心的坐标
radius: 半径
startingAngle, endingAngle: 开始⾓角度,结束⾓角度 anticlockwise: false顺时针 true逆时针


<h3>OC中调⽤用JavaScipt ● 如何在OC中调⽤用JavaScript代码
使⽤用UIWebView的stringByEvaluatingJavaScriptFromString⽅方法即可


# 真机调试

● 真机调试的主要步骤 登录开发者主页
⽣生成cer证书:cer是⼀一个跟电脑相关联的证书⽂文件,让电脑具备真机调试的功能 添加App ID:调试哪些app?
注册真机设备:哪台设备需要做真机调试? ⽣生成MobileProvision⽂文件:结合2、3、4⽣生成⼀一个⼿手机规定⽂文件 导⼊入cer、MobileProvision⽂文件
● 最终会得到2个⽂文件
➢ Cer⽂文件:让电脑具备真机调试的功能
➢ MobileProvision⽂文件:哪台设备、哪些app、哪台电脑需要做真机调试?


真机调试的步骤01-登录开发者主页 ● 登录开发者主页
https://developer.apple.com/membercenter/index.action
● 管理证书(前提:得花99$或299$加⼊入开发者计划)

真机调试的步骤02-⽣生成cer证书

真机调试的步骤03-添加App ID

真机调试的步骤04-注册真机设备

真机调试的步骤05-⽣生成MobileProvision⽂文件

真机调试的步骤06-导⼊入cer、MobileProvision ⽂文件


#内购
内购的五种产品类别
￼● ⾮非消耗品(Nonconsumable)⼀一旦购买,终⾝身拥有
● 指的是在游戏中⼀一次性购买并拥有永久访问权的物品或服务。⾮非消耗品物
品可以被⽤用户再次下载,并且能够在⽤用户的所有设备上共享 ● 消耗品(Consumable),买了就⽤用,⽤用了就没
● 消耗品购买不可被再次下载,根据其特点,消耗品不能在⽤用户的设备之间 跨设备使⽤用,除⾮非⾃自定义服务在⽤用户的账号之间共享这些信息
● 以下三种类别在iBooks中使⽤用,⽬目前iBooks不⽀支持⼤大陆市场
● ISBN:每本书的⼀一个ID
● 免费订阅(Free subscriptions)
● ⾃自动续费订阅(Auto-renewing subscriptions)
● ⾮非⾃自动续费订阅(Nonrenewing subscriptions)
￼

添加StoreKit框架
● 要使⽤用内购,需要导⼊入StoreKit框架

内购的常⽤用⽅方法
● 请求有效的产品代号集合
● 购买指定产品
● 验证购买(在购买完成之后,验证) ● 恢复购买(针对⾮非消耗品)


请求有效产品集合
// 1) 实例化产品请求
SKProductsRequest *request = [[SKProductsRequest
alloc]initWithProductIdentifiers:identifiers]; // 2) 设置代理
[request setDelegate:self];
// 3) 启动请求 [request start];
提⽰示:
1. 实例化请求时,必须指定有效的identifiers集合,之所以如此处理,主要是为了
确保提交的内购商品真的通过了苹果的审批,处于可⽤用状态! 2. 要想获取到准确的可⽤用产品集合,需要通过代理⽅方法实现
- (void)productsRequest:(SKProductsRequest *)request
didReceiveResponse:(SKProductsResponse *)response
3. 越狱⽤用户⽆无法测试内购,但是可以购买
4. 

购买产品
1. 内购的交易过程是通过SKPaymentTransactionObserver监控的,因此需 要为IAPHelper添加交易观察者:
// 添加交易观察者对象
[[SKPaymentQueue
defaultQueue]addTransactionObserver:sharedInstance]
;
2. 由于发起交易需要使⽤用SKProduct对象,因此需要使⽤用字典记录所 有可⽤用的商品
NSMutableDictionary *_productsDict;

交易队列回调⽅方法
- (void)paymentQueue:(SKPaymentQueue *)queue
updatedTransactions:(NSArray *)transactions
{
   for (SKPaymentTransaction *transaction in
transactions) {
// 购买完成
if (transaction.transactionState ==
SKPaymentTransactionStatePurchased) { NSLog(@"购买完成 %@",
transaction.payment.productIdentifier);
           [queue finishTransaction:transaction];
       } else if (transaction.transactionState ==
SKPaymentTransactionStateFailed) {
 if (transaction.error.code !=￼￼￼SKErrorPaymentCancelled) {..
}

恢复购买
[[SKPaymentQueue
defaultQueue]restoreCompletedTransactions];


购买数据记录问题——系统偏好 [[NSUserDefaults standardUserDefaults]setBool:isPurchased
forKey:productId];
[[NSUserDefaults standardUserDefaults]synchronize];


#广告
● 广告收益三七开
● 添加 iAd.framework 框架
● 添加 ADBannerView 视图,并设置代理⽅方法
●广告条加载完成之前最好隐藏
- (void)bannerViewDidLoadAd:(ADBannerView *)banner {
   self.bannerBottomConstraint.constant = 20.0;
   [UIView animateWithDuration:0.5 animations:^{
       [self.view layoutIfNeeded];
   }];
NSLog(@"加载⼴广告成功"); }
- (void)bannerView:(ADBannerView *)banner didFailToReceiveAdWithError:
(NSError *)error {
NSLog(@"加载⼴广告失败 %@", error); }


#二维码
● 从iOS7开始集成了⼆二维码的⽣生成和读取功能
● 此前被⼴广泛使⽤用的zbarsdk⽬目前不⽀支持64位处理器
● ⽣生成⼆二维码的步骤: 导⼊入CoreImage框架
通过滤镜CIFilter⽣生成⼆二维码
● ⼆二维码的内容(传统的条形码只能放数字): ➢ 纯⽂文本
➢ URL

⽣生成⼆二维码
// 1. 实例化⼆二维码滤镜
CIFilter *filter = [CIFilter
filterWithName:@"CIQRCodeGenerator"]; // 2. 恢复滤镜的默认属性
[filter setDefaults];
// 3. 将字符串转换成NSData NSData *data = [str
dataUsingEncoding:NSUTF8StringEncoding]; // 4. 通过KVO设置滤镜inputMessage数据
[filter setValue:data forKey:@"inputMessage"];
 // 5. 获得滤镜输出的图像
￼￼￼￼￼￼￼￼￼￼CIImage *outputImage = [filter outputImage];
￼

读取二维码
● 读取二维码需要导⼊入AVFoundation框架
● 利⽤用摄像头识别二维码中的内容(模拟器不⾏行)
   输⼊入(摄像头)
   由会话将摄像头采集到的二维码图像转换成字符串数据
   输出(数据)
   由预览图层显⽰示扫描场景
   
   设置拍摄会话
// 1. 实例化拍摄设备
AVCaptureDevice *device = [AVCaptureDevice
defaultDeviceWithMediaType:AVMediaTypeVideo];
// 2. 设置输⼊入设备
AVCaptureDeviceInput *input = [AVCaptureDeviceInput
deviceInputWithDevice:device error:nil];
// 3. 设置元数据输出
// 3.1 实例化拍摄元数据输出
AVCaptureMetadataOutput *output =
[[AVCaptureMetadataOutput alloc] init];
// 3.3 设置输出数据代理
[output setMetadataObjectsDelegate:self
queue:dispatch_get_main_queue()];
￼￼


设置拍摄视频预览图层
// 5. 视频预览图层
// 5.1 实例化预览图层
AVCaptureVideoPreviewLayer *preview =
[AVCaptureVideoPreviewLayer layerWithSession:_session];
preview.videoGravity = AVLayerVideoGravityResizeAspectFill; preview.frame = self.view.bounds;
// 5.2 将图层插⼊入当前视图
[self.view.layer insertSublayer:preview atIndex:100]; self.previewLayer = preview;
// 6. 启动会话
[_session startRunning];
