可关注 江苏宇桐科技有限责任公司 公众号 下载  https://mp.weixin.qq.com/s/OAHydGyyVGVBybB9ABR98A
本系统可以限制客户使用的账号、策略名 ，到期日期
可以有效防止EA被倒卖，无序扩散，随时可以授权，延期。大大提高客户的管理效率  

程序支持  网络加密 与 单机加密
本软件优势，源码无需外泄即可自行加密
图片


软件包比较大 可以关注公众号回复 “账号管理 ”下载

图片


我们程序支持  网络加密 与 单机加密 下面 2 3
我们程序支持  网络加密 与 单机加密 下面 2 3
本软件优势，源码无需外泄即可自行加密

图片



单机模式目前免费使用，可以给EA指标生成秘钥，程序无需二次编译，只需要再次发送秘钥即可实现EA延期
加密包已打包好，无需给作者发送源码，按案例即可自行编译，傻瓜案例，保姆教程，小白也能学会


//---文字表达来源于网络
1.传统方法： 单机加密，在源码内部增加时间判断/账号判断。
                    优点：代码简单，成本低。
                    缺点：每次添加账号或者修改到期时间都要去源码里面修改然后编译，最后再发给用户，操作繁琐，客户体验差。

2.网络加密： 在源码内部增加网络API接口，提交数据返回数据后再进行时间判断/账号判断。
                    优点：不用反复编译源码文件。
                    缺点：需要租用服务器，成本高，部署也麻烦，网络不稳定就无法使用。

3.现代方法：  在EA参数输入秘钥码。EA解析出授权账号和此账号的到期时间。
                     优点：不用反复修改源码，不用读取网络API接口，只需生成秘钥，发送给客户，即可实现授权，追加授权等。效率高，体验好。




图片
单机模式           免费生成秘钥(认证ID，免费使用 ,免费生成秘钥(认证ID，免费使用
单机模式           适合个人 与 小团队

服务端:
       
        复制文件（MTx_acc_admin_server_client_20260329.exe）到桌面双击

        账号:my0622     ==> 账号公开的,仅供测试，请勿作为业务开展

        账号: 123456       //你要加密的MT5 MT4账号
        程序: 123456_M5EA

        点击  认证ID/单机复制


MT5MT4客户端:

        1.encrypted_library_mt5_mt4.ex5 与 EA指标文件放一起
            EA文件放MQL5-> Experts  ,指标文件放MQL5-> Indicators

        2.客户端加载,参数输入 认证ID 即可

        //---mt4 操作流程与上述操作一致


网络模式    有偿使用，适合一定规模公司
网络模式
网络模式

服务端:

        准备一个香港(境外也可以)服务器，推荐阿里云
        复制文件（MTx_acc_admin_server_client_20260329.exe）到桌面双击

        账号:my0622     ==> 账号公开的,仅供测试，请勿作为业务开展

        登录后点击tcp通讯，启动监听即可  

MT5MT4客户端:

        1.双击打开案例(M5EA 客户端 后缀为mql5 的文件

        2.仿案例把代码植入自己的源码，ip格式(127.0.0.1)换成自己的(即你购买的服务器地址，点击编写即可

        3.encrypted_library_mt5_mt4.ex5 与 EA指标文件放一起
            EA文件放MQL5-> Experts  ,指标文件放MQL5-> Indicators

        4.客户端加载后后与服务器通讯，并自动建立档案,可在tcp通讯日志查看

        //---mt4 操作流程与上述操作一致


//--单机模式加密案例
//--单机模式加密案例
//--单机模式加密案例



//---以下是引入加密函数
#import "encrypted_library_mt5_mt4.ex5"
boolauthid_root(string _authid,string _EAZB_tag,string _EAZB_name,bool _allow_alert =true);
#import
//---以上是引入加密函数

inputstring authid = "请输入认证ID";

intOnInit()//---入口函数每个程序都会有 且 唯一 旧版本为Init()
  {
//---依次 认证ID ，标识("EA" 或者 "ZB")，策略名称(全英文)， 弹窗提醒
   authid_root(authid,"EA","M5EA",true);

   return(INIT_SUCCEEDED);
  }
//+------------------------------------------------------------------+
voidOnTick()//---主函数每个程序都会有 且 唯一 旧版本为start()
  {
//---依次 认证ID ，标识("EA" 或者 "ZB")，策略名称(全英文)， 弹窗提醒
   authid_root(authid,"EA","M5EA",true);

  }
//+------------------------------------------------------------------+


//---指标加密
/*
int OnInit()//---入口函数每个程序都会有 且 唯一 旧版本为Init()
  {
//---依次 认证ID ，标识("EA" 或者 "ZB")，策略名称(全英文)， 弹窗提醒
   authid_root(authid,"EA","M5EA",true);

   return(INIT_SUCCEEDED);
  }

//+------------------------------------------------------------------+
int OnCalculate(const int rates_total,
                const int prev_calculated,
                const datetime& time[],
                const double& open[],
                const double& high[],
                const double& low[],
                const double& close[],
                const long& tick_volume[],
                const long& volume[],
                const int& spread[])
  {

//---依次 认证ID ，标识("EA" 或者 "ZB")，策略名称(全英文)， 弹窗提醒
   authid_root(authid,"EA","M5EA",true);
   
return rates_total;
  };

//+------------------------------------------------------------------+
*/
图片
//---下面是网络模式
//---下面是网络模式
//---下面是网络模式

//---以下是引入加密函数

#import "encrypted_library_mt5_mt4.ex5"

boolEAZB_oninit(string _address,ushort _port,string _EAZB_tag,string _EAZB_name,bool _alert=true)
;
boolEAZB_ontick(bool _alert=true)
;
#import

//---以上是引入加密函数


input string ip = "127.0.0.1";

intOnInit()//---入口函数每个程序都会有 且 唯一 旧版本为Init()
  
{

//---依次ip ，端口， 标识， 策略名称， 弹窗提醒

//---ip(换成你自己的服务器) 标识("EA" 或者 "ZB")  策略名称(全英文)

   EAZB_oninit(ip,443,"EA","M5EA",true);
   return(INIT_SUCCEEDED);
  }
//+------------------------------------------------------------------+



//+------------------------------------------------------------------+

voidOnTick()//---主函数每个程序都会有 且 唯一 旧版本为start()
  
{
//---

   EAZB_ontick(true);
  }
//+------------------------------------------------------------------+



//---指标加密

/*
int OnInit()//---入口函数每个程序都会有 且 唯一 旧版本为Init()
  {

//---依次ip ，端口， 标识， 策略名称， 弹窗提醒
//---ip(换成你自己的服务器) 标识("EA" 或者 "ZB")  策略名称(全英文)
   EAZB_oninit(ip,443,"ZB","M5EA",true);
   return(INIT_SUCCEEDED);
  }

//+------------------------------------------------------------------+
int OnCalculate(const int rates_total,
                const int prev_calculated,
                const datetime& time[],
                const double& open[],
                const double& high[],
                const double& low[],
                const double& close[],
                const long& tick_volume[],
                const long& volume[],
                const int& spread[])
  {

   EAZB_ontick(true);

 return rates_total;
  };

//+------------------------------------------------------------------+
*/

图片
