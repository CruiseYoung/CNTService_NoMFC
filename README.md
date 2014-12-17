CNTService_NoMFC
================

CNTService_NoMFC v1.80 A class framework for developing NT services in C++

modify by CruiseYoung


原官网：http://www.naughter.com/serv.html



随着V1.80的，默认情况下该代码不依赖于MFC的了。如果你还是喜欢在课堂上的MFC框架的使用，然后定义预处理值“CNTSERVICE_MFC_EXTENSIONS”



历史
V1.0（1998年7月17日）

首次公开发行。
1998年8月24日

次要更新的演示程序（app.cpp）摆脱一个编译错误的。
V1.01（1999年5月17日）

另外的一些ASSERT的语句来帮助调试。
修正了CNTEventLogSource ::报告错误报告的马林Kunev
修正了一个编译器警告时，用VC编写6。
V1.02（1999年9月5日）

增加更多的ASSERT的语句来帮助调试。
V1.03（1999年10月3日）

加入GetProfileStringArray，WriteProfileStringArray，GetProfileBinary和WriteProfileBinary方法的CNTService类。
更名为一些模块名称。
V1.04（1999年10月5日）

修正了一个问题，编制发布和Unicode生成配置MC的文件。
修正了4级警告时，采用VC + + 6建成。
V1.05（1999年10月10日）

增加了对现场的描述哪些服务可以在Windows 2000的支持。
增加了访问功能的服务名称，友好的名称和说明文字。
V1.06（2000年1月24日）

修改后的MC文件纳入TestSrv.exe示例服务的方式。在MC文件被编译进，这是“包含（#include）”到最后的rc文件“testsrv.rc”中间“ntserv_msg.rc”文件。这样做，使“testsrc.rc”文件可以由内而外的Visual C + +的资源设计进行编辑。在CNTService以前的版本中，如果您尝试编辑rc文件（这是由MC命令行编译器生成的），你最终会破坏文件。如果您使用的是CNTService开发自己的服务，那么我会建议你采取这种方法。你需要做的是建立内部的VC + +资源脚本，加入任何资源，你想在你的服务资源（如版本信息的，字符串等），然后调出的资源，包括对话框，修改“编译时指令”，以“＃包括”ntserv_msg.rc“还是你这是由MC生成的编译.mc文件rc文件的版本。您还应该检查出带有CNTService演示服务项目设置，看看它是如何处理的汇编。通过一个批处理文件MC文件（鼠标右键点击“ntserv_msg.mc”，然后选择设置）。
V1.07（2000年4月10日）

修正了缓冲区大小的计算错误时CNTEventLogSource编译UNICODE :: SetStringArrayIntoRegistry
V1.1（2000年5月21日）

CNTEventLogSource添加2个新的重写版本::报告
以下评论这本书“专业新台币服务”的CNTService :: ReportStatusToSCM调整和设置默认参数
不允许接受任何控件时，该服务目前正在处理同一控制在ReportStatusToSCM
改变在ReportStatusToSCM参数的排序。你应该检查你的代码，以确保如果您有现有的代码是正确的
现在默认的类框架使用相同的名称为其NT事件日志将目光转向了​​MC字符串项的消息文件的DLL。这意味着，你应该检查你的代码，以确保如果您有现有的代码是正确的
CNTEventLogSource ::报告，现在不打扰自动创建一个SID，因为这应该用于服务，做模拟客户端
改变CNTEventLog的构造函数，现在把它需要的值，调用注册
CNTEventLog ::报告方法有改变，因为现在不再是常量以上。
SCM数据库现在是在锁定的安装和卸载服务
现在支持Windows 2000中所规定的服务，同时保持与NT 3.x和NT 4服务二进制兼容所有新功能。
框架现在要求的2000年1月的平台SDK或更高版本的存在。这是因为点的上方。
改变现有的CNTScmService :: QueryStatus函数的原型。
作出的typedef为枚举函数专用于各自的类别，而不是污染全局命名空间
V1.11（2000年6月19日）

添加一个ASSERT来ReportStatusToSCM的状态手柄== 0
修正了一些在ReportStatusToSCM其他逻辑问题
去掉不必要的保持断言CNTEventLogSource ::报告
示例服务的应用程序现在使用的，而不是PC喇叭的声音声卡默认的声音
V1.12（2000年6月21日）

微小的变化在RegisterCtrlHandler一丝声明
RegisterCtrlHandler被自动调用你现在不需要调用它的ServiceMain的派生版本
增加了一个布尔CNTEventLogSource ::报告（WORD w类型，LPCTSTR lspszString）方法
修正了一个示例服务没有正确地报告其关机状态给SCM的错误。
V1.13（2000年7月28日）

修正了一个项目设置错误，结果造成了以下编译器错误 “致命错误C1083：无法打开包含文件：”ntserv_msg.h'：没有那个文件或目录“。
V1.14（2000年12月21日）

修正了CNTService ::卸载（），它是导致它失败有时服务正在运行时的错误。
取得了CNTService类公共的所有成员变量，但把它们放在楼下的“执行”行翼标准的MFC类中声明的方法。
加入CNTEventLogSource的新版本覆写::报告。
V1.15（2001年1月8日）

现在，包括源代码和文档的版权信息。
CNTEventLogSource ::报告现在允许你指定的错误代码是否应显示在十六进制或十进制
示例服务有时不显示停止事件。这已经弥补了在事件日志中报告之前，我们的供应链管理报告。
框架现已作出独立的需要的最新的平台SDK的头文件。现在，您可以编译在VC 5的代码，而平台SDK不必安装。
V1.16（2001年5月16日）

螺纹保护的代码CNTEventLogSource ::报告。
V1.17（2001年5月27日）

添加的方法框架，以支持新的命令行选项 - 启动，-pause， - 继续和-stop。感谢斯特凡尼迈耶为这个伟大的补充。
在CEventLogSource类的app.cpp测试修正了一个小问题。
V1.18（2001年7月15日）

CreateService函数调用与包含空格的路径名时出现的问题。
V1.19（2001年7月18日）

次要更新的代码示例演示类的框架。
由于VC的6送货与Winsvc.h（主要的NT服务的头文件），其中包括了一些，但它的类需要你需要定义一些预处理的定义并不是所有定义获取代码干净编译特定的设置。设置“ntserv.cpp”为细节的顶部。
V1.20（2001年8月9日）

更新SetStringArrayIntoRegistry和GetStringArrayIntoRegistry能与我的其他类CHKLM V1.11一致。
V1.21（2001年11月27日）

固定在那里的类不能读该只读任何键的问题。这是因为Win2000的默认访问HKLM为“正常”的用户只读出了问题。由于汉斯 - 格奥尔格·乌尔里希为察觉这个问题。
V1.22（2002年8月27日）

取得更多的功能的虚拟，让更多的最终用户定制。
呼叫所有有用的属性，在CreateService函数CNTService ::安装现在可以无需获得CNTService的定制版本修改::安装在你的派生类。
一个布尔值，现在提供使能/禁用事件日志整合
V1.23（2002年8月28日）

回顾所有跟踪报表的正确性码
增加了一个参数CNTService ::安装，以便等待服务停止的时间来指定
添加一个CString参数的CNTService ::安装和卸载方法返回一个描述性的错误来电。
另外一个新的布尔变量的CNTService类的，让服务来决定是否应该使用GUI或控制台来电显示状态消息
CNTService :: ProcessShellCommand现在会显示错误信息到控制台或通过一个消息框时发生错误的安装，卸载，启动，停止，重启和暂停服务。
V1.24（2002年九月二十日）

固定在调用ReportStatusToSCM，你的服务，应要求在您的的ServiceMain一个“问题”。特别呼吁ReportStatusToSCM（SERVICE_STOPPED）看起来像它引发了单片机强行终止你的工作线程的行为。当其他代码这个调用，它使用被分配的工作线程堆栈的东西后，执行这可能会导致问题。为了解决这个“问题”（我找不到这种行为的任何文件），你应该删除它使用的值“SERVICE_STOPPED”从服务的ServiceMain函数的底部ReportStatusToSCM单一通话。要强迫你这样做，我已经改变了功能“ReportStatusToSCM”只是“ReportStatus”的名称。这将意味着，编译器会强迫你检查每个调用该函数，如上述取出一个电话。这个类的框架，现在看起来报告您的服务已停止向供应链管理后。由于“吉姆”为察觉这一点。
V1.25（2002年11月20日）

修正了3级用VC.Net编译代码时4警告。感谢埃德Eichman为察觉这个问题。
V1.26（2003年3月12日）

由于固定用户代码出了问题不能打电话ReportStatus（SERVICE_STOPPED）有没有办法报经dwWin32ExitCode或dwServiceSpecificExitCode启动或关机的错误。这已经解决了通过添加新的被保护的函数TerminateService在严重故障的情况下关闭该服务。这将引发包括其受困于_ServiceMain框架（或DebugService情况ProcessShellCommand的）的退出代码的私人例外。_ServiceMain然后通过_ReportStatus传递的代码。也因为不能被用于ReportStatus的dwWin32ExitCode和dwServiceSpecificExitCode参数这些参数已经被删除。由于乔恩Baggott这些2补充。
由框架进行了包括头文件的一些轻微的起伏整齐
V1.27（2003年5月8日）

更新的安装和卸载方法从GetLastError函数返回值（）。因为它可以被重置函数返回之前这是为客户机代码是有用的。
命令行现在支持A / T：参数允许你指定一个超时使用做一个卸载的时候。这个超时用于指定该代码将等待多长时间，如果服务需要被停止。
打破了所有的类放到自己的模块。这可以让你拉，你只需要，如果你不使用主类CNTService类。
去掉所有不必要的跟踪语句在整个框架由GetLastError函数的返回，因为他们有时会重置价值。
V1.28（2003年5月17日）

进一步调整，以_ReportStatus避免间断性死机。看到20-09-2002第1项有关问题的详细信息。
去掉了一些不必要的调用锁定临界区
V1.29（2003年5月22日）

更新示例服务的消息DLL项目集成创建MC文件的方式。有关如何MC文件集成到Visual Studio中的详细信息，请参阅CodeProject上的文章 http://www.codeproject.com/useritems/MCTutorial.asp。请注意，我没有按照建议的设置，在这篇文章中确切地概括为信息文件的头文件需要被纳入NT服务exe文件在编译时。
V1.30（2003年8月3日）

改进了错误处理和报告中CNTService :: SetServiceToStatus。由于乔恩·波利报告此问题。
V1.31（2003年8月15日）

优化CEventLogRecord :: CEventLogRecord（常量EVENTLOGRECORD * pRecord）字符串复制。一个错误报告在这一领域的Jeroen沃尔特但看起来这是在MSDN的当前版本文档错误。这种结构在MSDN的一些早期版本的正确定义。
V1.32（2003年9月8日）

感动了所有该框架需要到一个单独的头文件中定义。由于迪马波利亚科夫指点出，当你没有安装的SDK平台的必要这一变化发生的编译问题。
改变用于编译在MC文件的命令行的顺序。这避免了一个问题，因为在VC 7使用框架时，报告罗德里戈·奥利维拉·费尔南德斯
修正了一个编译错误与使用预处理器的定义NTSERV_EXCLUDE_VC6_WINSVC_DEFINES
v1.33中（2003年10月4日）

更新了自定义生成步骤编译在MC文件。现在，采用VC宏“$（InputPath）”，而不是“$（InputDir）\ $（InputName）的.mc”。
去掉了一些未引用变量的4级警告，当用VC.Net 2003编译。
要干净编出来与Visual Studio.Net 2000或Visual Studio.Net 2003盒提供一个特定的工作区（TESTSRV的视觉Studio.Net.dsw），它允许示例服务的问题是，各种版本的格式宏如$（InputDir）已经从VC的6改变只需选择文件 - >打开项目VS.Net，然后选择“TESTSRV的视觉Studio.Net.dsw”。
v1.34（2003年10月5日）

更新了在Visual Studio.Net工作区移除“没有平台SDK”的配置，因为他们是不适用的。
V1.35（2003年十一月十二日）

现在包括一个Unicode文件管委会感谢布罗迪Thiesfield。要使用此文件，只需复制ntserv_msgU.mc多年来在TestSrvMsg的ntserv_msg.mc文件，并修改了TestSrvMsg项目的MC文件的自定义生成步骤包括-u命令行选项。该文件还包括示例服务使用默认的服务事件日志字符串的日语翻译。
v1.36毒素（2003年11月14日）

其中该服务的消息DLL所在的位置，现在可以在运行时通过填写CNTService :: m_sMessageDll变量调整了。由于布罗迪Thiesfield此更新。
审查了使用一个CString参数的所有跟踪语句。现在明确地把CString的一个LPCTSTR。由于布罗迪Thiesfield此更新。
增加了一个新CNTService :: m_LoggingDetail变量。这种结合被称为CNTService :: Win32ErrorToString新方法能更灵活地控制错误记录到事件日志。由于布罗迪Thiesfield的暗示此更新。
比“-debug”参数的其他命令行参数是通过在调试模式下运行时传递给的ServiceMain（）。由于布罗迪Thiesfield的暗示此更新。
V1.37（2003年11月19日）

重做功能Win32ErrorToString来包含字符串资源ID。由于布罗迪Thiesfield的暗示这一点。
固定CNTS_MSG_SERVICE_FAIL_PAUSE，CNTS_MSG_SERVICE_FAIL_CONTINUE并没有使用新的Win32ErrorToString方法CNTS_MSG_SERVICE_FAIL_STOP事件日志条目。由于布罗迪Thiesfield报告此。
Win32ErrorToString现在包括一个“bEventLog”参数。如果这是真函数被调用以获得被显示在事件日志中的错误，为FALSE时，它被用来显示给最终用户或跟踪窗口
V1.38（2003年11月23日）

修正了CNTService ::调试内存泄漏时，该服务使用TerminateService来关闭该服务提前。
v1.39（2003年11月26日）

现在支持/无声的命令行选项。结合使用此设置，例如/安装将确保在发生错误时的框架，不显示任何消息框或控制台输出。感谢Metrich弗雷德里克这个加法。
从布尔到一个DWORD改为从ProcessShellCommand的返回值。这个值现在使用从服务的exe退出时返回错误代码。与/ silent命令行选项的组合，这使如安装控制通过服务的退出代码服务实例第三方程序。再次感谢Metrich弗雷德里克这个加法。
更新提供了框架来说明如何为现在ProcessShellCommand返回客户端服务可以返回的Win32错误代码的示例应用程序。
2004年1月13日

更新示例服务的“m_bWantStop”变量的声明到现在是一个变量。没有变化的实际CNTService模块（巴版权更新为2004年新的一年）
V1.40（2004年1月22日）

修正了CNTScmService :: EnumDependents和CNTServiceControlManager :: EnumServices在枚举将继续甚至当回调函数返回FALSE的错误。感谢爱德华·利文斯通为察觉这一点。
2004年2月21日

Unicode版本的MC文件已经被更新，包括韩国资源。由于布罗迪Thiesfield此更新。
1.41（2004年3月18日）

固定在CNTScmService :: WaitForServiceStatus功能，导致它返回TRUE即使服务失败返回所需的状态（如果待处理状态不是预期的未决居留制的错误。
还确保CNTScmService :: WaitForServiceStatus不会等待过去请求超时时间。由于布罗迪Thiesfield这些bug报告和修复。
V1.42（2004年4月9日）

进一步的工作，以CNTScmService :: WaitForServiceStatus。现在忽略待定状态。此外，它忽略了等待提示，因为我们要求QueryServiceStatus而不是调用ControlService功能与SERVICE_CONTROL_INTERROGATE控制代码。它也允许一个可选的第三个参数指定的轮询间隔。由于爱德华·利文斯通和“勇”报告此问题。请注意，由于第三个参数给这个函数意味着不同的东西以前，你应该检查你的所有通话WaitForServiceStatus，以确保其继续正常运行。
V1.43（2004年4月12日）

除去CNTScmService :: WaitForServiceStatus未使用的变量。感谢爱德华·利文斯报告此问题。
V1.44（2004年5月5日）

修正了CNTService :: GetDependencies和CNTEventLogSource :: SetStringArrayIntoRegistry一些警告使用“强制一致性的For循环范围”VC编译选项编译代码时（/ ZC：forScope）。感谢阿列克谢库兹涅佐夫报告此问题。
V1.45（2004年6月20日）

修正了CEventLogRecord :: CEventLogRecord错误（常量EVENTLOGRECORD * ..）做跨弦空值的记录的结尾处理。由于“勇”报告此问题。
优化CEventLogRecord :: CEventLogRecord代码（常量EVENTLOGRECORD * ..）。
v1.46（2004年6月20日）

提供了一个新的虚拟实现CNTService :: _的ServiceMain的。为了实现这一目标之前的静态_ServiceMain现在被称为“_SDKServiceMain”。这使您的服务代码完全定制你的服务的启动。例如，如果你的服务并不需要积极的工作线程做任何工作（例如，它永远只能响应救援人员到场使用OnUserDefinedRequest单片机的客户端请求），那么你可以实现你自己的版本_ServiceMain的不叫_ReportStatus（SERVICE_STOPPED ..这将允许您使用RegisterWaitForSingleObject实现您服务清理代码。欲了解更多有关这种类型的服务，请参阅MSDN文档中的“RegisterWaitForSingleObject”和“的ServiceMain”。感谢豪格Leuschner报告此。
v1.47（2004年6月24日）

补发我忘了申报_ServiceMain虚，卫生署最后更新！
也取得了在全局命名空间中的类CNTServiceTerminateException可见。这是你实现自己的_ServiceMain要求。
v1.48（2004年10月15日）

框架现在会自动安装在调试模式下运行时，控制台CTRL处理。这意味着，在调试模式下运行的，如果你的服务是建立一个控制台应用程序，你按Ctrl + C或Ctrl + Break或打在控制台窗口的关闭按钮时，框架将自动调用您的服务的onStop方法。这可以帮助您验证服务关闭的代码，而无需运行代码的服务。由于控制台CTRL处理程序是在一个单独的线程来执行的ServiceMain，这种仿真模式下调用你在一个单独的线程，就像单片机做的onStop方法。当你需要在你的服务，这是线程相关的调试关机问题，这证明非常有帮助。
增加了一些检查，以不同的头文件警告如果各种头文件还没有被列入，例如Afxmt.h。这有助于避免简单的编译问题，当框架被添加到一个新的项目开始。
示例应用程序现在使用的，而不是一个关键部分InterlockedExchange功能，能够连续访问多个线程使用的变量。此外，“m_bPaused”示例应用程序的变量，现在也被标记为volatile
修正了CNTEventLogSource“dwTypesSupported”双重声明::安装。在此过程中修复了该代码生成4级警告。
v1.49（2004年10月18日）

修正了一些水平的框架4的警告时，“检测64位可移植性问题，”在Visual Studio .NET启用
V1.50（2004年11月11日）

修正了CNTEventLogSource :: SetStringArrayIntoRegistryà再论64位的问题，当在Visual Studio .NET编译。
加入CNTSERVICE_EXT_CLASS预处理宏，允许类可以很容易地加入到扩展DLL的
V1.51（2005年2月11日）

另外一个虚拟GetEventLogSourceName方法，允许事件日志源的名称在运行时进行定制。由于巴拉CEK请求这个加法。
更新了所有模块的版权资料。
除了真正的Visual Studio NET 2003文件示例服务（Testsrv.sln和Testsrv.vcproj）
v1.52（2005年3月26日）

加入m_bProfileWriteFlush变量，这就决定如果注册表设置，应立即提交，而不是依靠惰性写入器的CNTService类。
V1.53（2005年4月21日）

CNTService :: GetProfileInt和GetProfileString功能现在包括一个可选的DWORD输出参数的设置时，允许从GetLastError函数的值被返回给客户端的代码。这使得代码的返回，因为它实际上是存储，而不是返回一个默认值，因为某些注册表的API失败的默认值进行区分。感谢托尼·罗南报告此问题。
V1.54（2005年7月31日）

提供了一个重写版本CNTEventLogSource ::报告的有3字符串参数
CNTEventLogSource :: GetStringArrayFromRegistry和SetStringArrayIntoRegistry方法现在公众，因为他们有提供外部帮助。
v1.55（2005年8月14日）

修正了SID和二进制值没有被正确设置，在重载的构造函数CEventLogRecord这需要一个EVENTLOGRECORD指针的问题。感谢布赖恩·李报告此问题。另外此信息被复制到阵列现预分配来提高性能。
V1.56（2006年1月11日）

该服务使用入手现在可以通过一个新的/ SCL命令行选项，例如TestSrv.exe /安装“：/参数1 / SomeOtherParam：XYZ / SCL”中指定的命令行选项。这种额外的灵活性是由布尔CNTService :: m_bAllowCommandLine它默认为FALSE控制。
更新的详细信息，版权为所有模块
该服务使用了安装服务显示名称字符串现在可以通过一个新的/ SDN命令行选项指定。“：PJ的第二个测试服务/ SDN”这是通过支持新的命令行选项，例如TestSrv.exe /安装完成。这种额外的灵活性是由布尔CNTService :: m_bAllowDisplayNameChange它默认为FALSE控制。
该服务使用安装说明字符串现在可以通过一个新的/ SD命令行选项指定。“：一些说明/标清”，这是支持一个新的命令行选项，例如TestSrv.exe /安装完成。这种额外的灵活性是由布尔CNTService :: m_bAllowDescriptionChange它默认为FALSE控制。
该服务使用安装的服务名称字符串现在可以通过一个新的/ SN命令行选项指定。这是通过支持新的命令行选项，例如TestSrv.exe /安装“：PJSERVICE2 / SN”来实现的。这种额外的灵活性是由布尔CNTService :: m_bAllowNameChange它默认为FALSE控制。
除去这将事件写入日志条目时，该服务正在卸载代码。没有太多的意义在登录你已经卸载该服务，当你还卸载事件日志源的条目。
去掉了ANSI MC文件。相反，现在包含在zip文件中的MC文件是由布罗迪Thiesfield（见历史记录列表V1.35）所提供的Unicode的MC文件。
更新为使用相同的样式的Web站点上的文档。
当注册该服务时，路径名的引用要使用的服务在CNTService现在做:: ProcessShellCommand代替CNTScmService ::创建。
在CNTServiceCommandLineInfo :: CNTServiceCommandLineInfo优化的代码。
去掉不必要的CNTServiceCommandLineInfo析构函数。
去除CNTService :: GetEventLogSourceName方法。相反，现在你可以调用m_EventLogSource.SetSourceName（）来定制这个值。
提供CNTService :: SetUseConsole和CNTService :: GetUseConsole方法。
默认设置为CNTService :: m_bUseConsole根据标准_CONSOLE预处理器定义是否被宣告现在设置
辗转于CNTService构造函数中不必要的临界区锁
提供CNTService的:: SetControlsAccepted和CNTService :: GetControlsAccepted方法。
提供一个默认的构造函数CNTService的
另外一个默认的构造函数CNTEventLogSource
加入CNTEventLogSource :: SetServerName，CNTEventLogSource :: GetServerName，CNTEventLogSource :: SetSourceName和CNTEventLogSource :: GetSourceName方法
提供CNTService :: SetServiceName，CNTService :: SetInstanceServiceName，CNTService :: SetMasterServiceName，CNTService :: GetInstanceServiceName，CNTService :: GetMasterServiceName，CNTService :: SetDisplayName，CNTService :: SetMasterDisplayName，CNTService :: SetInstanceDisplayName，CNTService :: GetMasterDisplayName，CNTService :: GetInstanceDisplayName，CNTService :: SetDescription，CNTService :: SetMasterDescription，CNTService :: SetInstanceDescription方法，CNTService :: GetMasterDescription和CNTService :: GetInstanceDescription。最让此版本的框架的工作是支持CNTService“实例”的新概念。在此之前版本的CNTService框架，你可以永远只在一台机器上安装任何一个服务的一个副本。现在引进的/ SDN，/标清的，哪些是用来在安装和卸载你可以注册该服务多次，使用不同的服务名称，显示名称和描述/ SN命令行选项。原始值，你构建你的CNTService实例被称为主的价值观和是你的服务的所有实例的生命周期中修改。在“实例”的值修改（如果你让他们通过CNTService :: m_bAllowNameChange，CNTService :: m_bAllowDisplayNameChange和CNTService :: m_bAllowDescriptionChange如此），在运行时。在注册过程中提供的命令行中这些值，该服务是建立在供应链管理后，推出使用命令行进行定制，使这些相同的命令行选项传递给它。这使得当它作为服务运行的同一个实例的值提供给该服务。如果没有这个绝招，就没有简单的方法为服务，以检测其下的实例详细介绍它应该运行。
另外的2个新的命令行选项，即“/应用程序”或“/应用程序”。这些行为相同的方式为现有的“/调试”命令行选项。
另外一个DWORD *参数的CNTEventLogSource :: GetStringArrayFromRegistry和CNTEventLogSource :: SetStringArrayFromRegistry功能。这让最后一个错误的详细信息返回给客户端代码。
加入CNTService :: WriteProfileString，CNTService :: WriteProfileInt，CNTService :: WriteProfileStringArray，CNTService :: WriteProfileBinary，CNTService :: GetProfileString，CNTService :: GetProfileInt，CNTService :: GetProfileStringArray和CNTService :: GetProfileBinary的仿制版本。这些实现允许指定以及其隐藏在其他实施方式中的冲洗设定的服务名称。这些功能的实现存在的，现在只是把这些新的实现。提供这些实现现在允许客户端代码，而无需创建一个新的CNTService实例来读取和写入的任何服务（包括同一服务的其他实例）的设置。
CNTServiceControlManager :: EnumServices方法，现在使用的void *参数的项目数据，而不是一个DWORD。
另外一个CNTService :: EnumerateInstances方法，它可以让你列举已使用新的主/实例添加到该版本的框架安装服务的所有实例。你在哪里写配置型的小程序为您安装服务的所有实例配置设置，这可能证明是有用的。
又多了一个新的/ U命令行选项，它允许服务运行下配置的用户帐户。
又多了一个新/ P命令行选项，允许该服务是与要配置运行密码。
为安全起见，一旦用户名和密码字符串被用于安装，它们覆盖在内存中。
v1.57（2006年1月13日）

又多了一个新的/自动命令行选项使您可以指定该服务应自动启动。
v1.58（2006年4月27日）

代码现在消灭了用户名和密码字符串时使用SecureZeroMemory。这将进一步改善这些值的安全性，当他们由类框架操作。
V1.59（2006年5月12日）

次要更新ntservEventLogRecord.cpp模块现在去掉不必要的包括AfxPriv.h的。由于马丁·里希特报告此问题。
还更新了本文档中的使用说明来描述如何使用复制和粘贴，以加快作业。再次感谢马丁·里希特报告此问题。
V1.60（2006年5月18日）

小更新来重新命名它是用来保存函数指针类型_NTSERV_SERVICCONTROLMANAGER_DATA的局部变量。由于弗雷德里克Metrich报告此问题。
小更新来重新命名它是用来保存函数指针类型_NTSERV_SCMSERVICE_DATA的局部变量。由于弗雷德里克Metrich报告此问题。
v1.61（2006年5月31日）

更新为VC 6没有被安装Platform SDK中正常工作的代码。我个人用VC 6安装2003年2平台SDK，这是怎么了我大部分的代码主要是进行测试。看来我的一些最新更新CNTService已经打破了VC 6自身的兼容性。也改名是当你在编译的Visual C + + 6类无框架平台SDK是“CNTSERVICE_MISSING_PLATFORMSDK”所需的界定“NTSERV_DO_NEW_WINSVC_DEFINES”。请注意，我会建议所有的开发人员来安装平台SDK（2003年2月这是用VC 6兼容的最新版本），因为我可能会下降支持VC 6没有在未来的平台SDK的CNTService。它正在成为太多的工作来支持它被运用VC 6和我的大多数其他开源代码是迈向需要平台SDK旧的头文件。由于马蒂亚斯·米勒报告此问题。在“NTSERV_EXCLUDE_VC6_WINSVC_DEFINES”定义现在已经不存在，而不再由CNTService代码中使用。
v1.62（2006年6月3日）

如果CNTEventLogSource ::卸载无法删除的HKLM \ SYSTEM \ CURRENTCONTROLSET \服务\事件日志\“显示名称”的注册表项，然后将它做任何其他工作之前，将中止。由于马蒂亚斯·米勒报告此问题。
修正了CNTService :: SetServiceToStatus小错字。由于马蒂亚斯·米勒报告此问题。
v1.63（2006年6月7日）

除去3 unreferrenced变量从CNTService :: ProcessShellCommand。由于弗雷德里克Metrich报告此问题。
次要更新的CNTService某些功能的声明在其功能的实现采用“WINAPI”。由于弗雷德里克Metrich报告此问题。
更新了CNTService ::调试代码排除“/调试”，“-app”，“/应用程序”，“ - 应用”和“/应用程序”，除了“-debug”值的命令行选项。再次感谢弗雷德里克Metrich报告此问题。
更新提供了CNTService下载建立一个控制台应用程序，而不是一个Windows应用程序的示例服务。这使您可以检查出控制台处理程序支持，CNTService包括。
v1.64（2006年6月9日）

制造CNTService ::初始化非虚。这个改变是因为它被称为由CNTService构造函数，你不能调用从C + +类的构造函数（或析构函数）虚函数。有关此问题的详细信息，请参阅在网上的文章 http://www.artima.com/cppsource/nevercall.html 从书“有效的C + +”斯科特迈尔斯。由于弗雷德里克Metrich为察觉这个问题。这种变化的原因，你应该检查一下你自己的代码，它使用CNTService ::初始化，以确保这种改变对你的代码没有任何副作用。
v1.65（2006年6月13日）

加入LOGNAME参数的构造函数CNTEventLogSource支持，而不是记录到标准的“应用程序”事件日志的用户定义的事件日志。请注意，该代码仅加入使得CNTService框架使用非“应用程序”的事件日志，但它不包含代码以创建自定义事件日志。您将需要处理，在你的应用程序的安装。感谢扬巴特尔斯这个加法。
还优化了成员变量在CNTEventLogSource构造施工
要允许定制的客户项目，资源ID和邮件ID值现在可以通过两个新的虚拟功能，即CNTService :: MapResourceID和CNTService :: MapMessageID定制。感谢扬巴特尔斯此更新。
CNTService :: SetServiceToStatus现在公开等作为参数，以及轮询间隔作为参数的时间间隔。除了命令行超时间隔，现在传递到CNTService :: ProcessShellCommand所有调用SetServiceToStatus。被传递的超时值的额外的命令行操作包括启动，停止，暂停和继续服务，除卸载它时，它在V1.27导入的服务是在能得到的超时值的运转。
修正了v1.64其中样品的服务进行了更新，作为一个控制台应用程序运行引入的错误。我忘了做决策时，这种变化是摆在呼叫AfxWinInit。
V1.66（2006年6月24日）

加入CNTService :: Win32ErrorToString缺少MapResourceID电话。
更新样本DSP和vcproj文件产生的，而不是ASCII的Unicode MC资源。
框架现在接受命令行/控制台的意思是一样的/调试，即不与服务控制管理器进行交互运行的程序作为一个正常的（控制台）的应用程序。
更新后的代码使用VC 2005编译干净。
在ntservEventLogSource.cpp包括信息如何找到所需要创建用户定义的事件日志中的各种注册表值进一步的信息。
v1.67（2006年6月25日）

结合_NTSERV_SERVICCONTROLMANAGER_DATA类的功能进入主CNTServiceControlManager类。
代码现在使用较新的c + +风格的转换，而不是C风格的转换。
结合_NTSERV_SCMSERVICE_DATA类的功能进入主CNTScmService类。
在该项目的数据参数CNTScmService :: EnumDependents一个void *，而不是当前的DWORD。
优化CEventLogRecord构造
结合_NTSERV_DATA类的功能进入主CNTService类。
该类框架，现在需要的平台SDK，如果编译用VC 6。
固定码这是不牢固复位，使用后，他们在命令行中的用户名和密码的字符串
v1.68（2006年7月2日）

优化收拾的DllMain代码TestSrvMsg.cpp
所有来电m_EventLogSource.Report现在保护与“如果（m_bRegisterEventLogSource）”检查
现在去除未使用的项目配置从VC 6工作区文件。
v1.69（2006年7月27日）

在CNTService配置文件功能的静态版本，现在已经更名为包含单词“服务”中的方法名。这修正了编译器错误代码时采用的是2005年的VC。
V1.70（2006年8月1日）

使用新_tcscpy_s功能，在CNTEventLogSource 1 :: SetStringArrayIntoRegistry和其他在CNTService :: GetDependencies定出两个缓冲大小计算。由于DmityShm在CodeProject上论坛上报告此问题。
v1.71（2006年9月21日）

小更新以各种跟踪语句和CNTEventLogSource ::举报电话使用％x而不是％X。
二○○六年十一月二十○日

次要更新使用控制台I / O中的示例应用程序，而不是在CMyService ::使用showHelp一个MessageBox。
优化的成员变量建设CMyService :: CMyService。
v1.72（2007年2月2日）

更新版权的细节。
优化CNTEventLog构造函数代码。
返工CNTService :: SetServiceToStatus让最后一个错误值报告给客户端代码。由于马蒂亚斯·米勒报告此问题。
优化呼叫Win32ErrorToString。
v1.73（2007年3月22日）

CNTService :: SetServiceToStatus和CNTService ::卸载不再指定其需要连接到SCM的SC_MANAGER_LOCK访问权。这种变化有助于让服务启动和超级用户帐户停止。由于马蒂亚斯·米勒报告此问题。
CNTService :: SetServiceToStatus不再打开控制服务时指定STANDARD_RIGHTS_REQUIRED访问权限。这种变化有助于让服务启动和超级用户帐户停止。由于马蒂亚斯·米勒报告此问题。
v1.74（2007年11月19日）

小更新以显示正确的HRESULT的。
v1.75（2008年1月12日）

更新版权的细节。
提供与VC 6编译的HTML文档中有详细信息的链接到我的博客。
CNTService :: Win32ErrorToString方法已被修改，以现在使用的FORMAT_MESSAGE_IGNORE_INSERTS标志。欲了解更多信息，请参阅Raymond Chen的博客在 http://blogs.msdn.com/oldnewthing/archive/2007/11/28/6564257.aspx。感谢阿列克谢库兹涅佐夫报告此问题。
更新了示例应用程序来清理编译VC的2008。
SecureEmptyString方法现在被定义为“FORCEINLINE”。
v1.76（2008年6月1日）

代码现在完全编译使用代码分析（/分析）
该代码已经被更新，以支持VC 2005或更高版本。
v1.77（2010年8月1日）

更新版权的细节。
更新的项目设置，以更现代的默认值。
在“ELErrorLoggingDetail”枚举的定义固定的结尾“，”
更新了示例应用程序上简洁地编译VC的2010
更新了App.cpp测试代码只连接到单片机或打开一个特定的服务时，使用的必要权限。这样就避免了访问被拒绝在Windows Vista上的错误或更新版本时，启用了UAC。感谢扬巴特尔斯报告此问题。
增加了对以下SERVICE_CONTROL_ *支持定义：SERVICE_CONTROL_SESSIONCHANGE，SERVICE_CONTROL_PRESHUTDOWN，SERVICE_CONTROL_TIMECHANGE＆SERVICE_CONTROL_TRIGGEREVENT。这些控制值表示在Windows Vista和Windows服务的新功能7
添加注释到＃包括告诉用户重新编译TestSrvMsg，如果他们得到一个编译错误“ntserv_msg.h”。感谢保罗PIGNON报告此问题。
更新后的代码正确使用_ATL_CSTRING_EXPLICIT_CONSTRUCTORS定义编译
修正了CNTService一个小问题:: Win32ErrorToString与使用printf格式标识符
重做所有的内部堆内存管理代码使用ATL :: CHeapPtr
重做所有的内部登记管理代码使用ATL :: CRegKey
该CNTService :: m_bRegisterEventLogSource价值已更名为m_bEventLogSource。这是一个重大更改，并且可能需要你的服务代码进行更新，如果你从你的代码中引用该值。
CNTService ::安装已重构。国内现在这个函数调用InstallEventLogSource和InstallServiceConfiguration
在CNTEventLogSource修正了一个小问题::与使用printf格式标识符报告
CNTEventLogSource ::安装方法现在支持的事件源CategoryCount，CategoryMessageFile和ParameterMessageFile设置
在文档中包含注释有关使用微星优先于“/安装”/“/卸载”
增加了对NotifyServiceStatusChange支持
增加了对ControlServiceEx支持
增加了对SERVICE_CONFIG_DELAYED_AUTO_START_INFO支持
增加了对SERVICE_CONFIG_FAILURE_ACTIONS_FLAG支持
增加了对SERVICE_CONFIG_SERVICE_SID_INFO支持
增加了对SERVICE_CONFIG_REQUIRED_PRIVILEGES_INFO支持
增加了对SERVICE_CONFIG_PRESHUTDOWN_INFO支持
增加了对SERVICE_CONFIG_TRIGGER_INFO支持
增加了对SERVICE_CONFIG_PREFERRED_NODE支持
CEventLogRecord :: m_TimeGenerated和CEventLogRecord :: m_TimeWritten值现在简单的DWORD值，而不是CTime的实例。
增加了对GetEventLogInformation支持
进行了彻底的代码审查，以确保所有的功能是正确的和功能在Windows 7和更高版本
v1.78（2010年9月3日）

修正了CNTService :: GetServiceProfileString一个错误的地方，将错误地返回FALSE。
修正了CNTService :: GetServiceProfileInt一个错误的地方，将错误地返回FALSE。
v1.79（2012年11月10日）

更新版权的细节。
更新的示例服务代码清理汇编VC 2012。
返工CNTScmService :: WaitForServiceStatus方法，以避免需要调用的GetTickCount。
修正了CNTEventLogSource :: GetStringArrayFromRegistry一个错误的地方它不能处理空MULTI_SZ字符串。感谢罗尔夫·夏腾报告这个错误。
CNTEventLogSource ::现在安装电话CRegKey ::安装HKLM \ SYSTEM \ CURRENTCONTROLSET \服务\事件日志\“LOGNAME”注册表项时创建的，而不是CRegKey ::打开。这将确保它们与定制LOGNAME的创建事件日志来源将被正确安装。感谢罗尔夫·夏腾报告这个错误。
V1.80（2014年1月1日）

更新版权的细节。
更新后的代码清理编译VC的2013
重新设计的类有选择地编译没有MFC的。默认情况下，类现在使用STL的字符串和数组，但如果你定义CNTSERVICE_MFC_EXTENSIONS，该班将恢复到使用MFC集合类。
更新了代码库支持所有服务功能的Windows高达8.1。支持的新功能包括SERVICE_CONFIG_LAUCH_PROTECTED支持可通过CNTScmService :: QueryLaunchProtected和CNTScmService :: ChangeLaunchProtected和QueryServiceDynamicInformation支持可通过CNTService :: QueryServiceDynamicInformation。






命令行



/install

Installs the service.


/remove | /uninstall

Uninstalls the service.


/help [ /?]

Calls the virtual CNTService::OnHelp function.

/debug | /app | /Application Using this setting bypasses the service SCM start-up code and instead runs your code as a standard application. 
/start Starts the service. 
/stop Stops the service. 
/pause Pauses the service. 
/continue Continues the service. 
/auto Installs the service as an automatic start-up service, as opposed to a manual start-up service which is the default (should be used in conjunction with the /install argument) 
/T:value A timeout value in milliseconds to use when uninstalling, starting, stopping, pausing and continuing the service. 
/SCL:XYZ Provides the command line which the code should use when running as a service by the SCM. (The use of this value on the command line is dependent upon CNTService::m_bAllowCommandLine). 
/SD:WYZ Provides the service description to use. (The use of this value on the command line is dependent upon CNTService::m_bAllowDescriptionChange). 
/SDN:PRQ Provides the service display name to use. (The use of this value on the command line is dependent upon CNTService::m_bAllowDisplayNameChange). 
/SN:STU Provides the service name to use. (The use of this value on the command line is dependent upon CNTService::m_bAllowNameChange). 
/silent Use this command line in conjunction with other command line arguments to suppress any message boxes or console output which the framework generates. 
/U:ABC Allows you to configure the username account under which the service runs. 
/P:DEF Allows you to configure the password for the associated username account under which the service runs. 

Derive a new class from CCommandLineInfo to handle other flags and parameter values.

Please note that Install / Uninstall support via the CNTServiceCommandLineInfo class and the framework in general is considered self-registration. Installation best practices for Windows says that you should use the declarative approach provided by Windows Installer to install / uninstall your service. Please pick the MSI approach if you can.