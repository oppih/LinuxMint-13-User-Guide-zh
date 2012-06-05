##Software Management

### Package Management in Linux Mint

If you have installed Linux for the first time, then you may not be familiar with the concept of organizing software into “packages”. You will soon become familiar with package management and appreciate the advantages it offers in terms of security, control and ease of use.

We have tried to make it so that all or most of your hardware was detected and drivers were installed automatically so that your computer would work out of the box. We have also tried to make it so that you could do many of the things you want to without having to look around for third party software on websites. You may have noticed that your Linux Mint installation already has a full office suite, a professional-quality image-editing solution, an IM and an IRC client, a disk burner, and several media players (as well as many other basic accessories). Relax, it's okay! You haven't stolen anything! This is what free software is all about! And the truly great thing about package management in Linux Mint and generally is that you should never need to look far and wide for extra software, even when the time comes that you do want more functionality from your Linux Mint system. 

This section is intended to explain how this works and the advantages that it can bring to you. It's a bit long, but hopefully it will provide you with a good understanding of the philosophy behind package management and why it is considered a Good Thing (a phrase commonly capitalized by Linux users to mean that something is squarely in the category of good). If you're in a hurry, you can skip to the next section which will tell you how to actually use  the package system. 

The problems with browsing software vendors' websites and downloading and installing the software they offer are many:

- It is difficult or impossible to find out if the software has been tested to work with your operating system
- It is difficult or impossible to know how this software will interact with the other software installed on your system
- It is difficult or impossible to know if you can place your trust  that  software from an unknown developer software will not cause any harm, willful or negligent, to your system Even if you know about a specific piece of software and its developer, you cannot be entirely sure that you are not downloading an executable that has been swapped out by a malicious third party for some type of malware. 

Furthermore, a problem with downloading and installing multiple different programs, from multiple different developers, is that there is no managerial infrastructure. Before you say “big deal”, consider how you are going to keep all these different pieces of software up to date. If you get tired of a program and want to remove it, how do you know how to achieve that? The program in question might not have come with a removal option, and even if it did, much of the time this will fail to remove the software cleanly and completely. In a very real sense, when you ran that installer program, you gave up some of your control of your computer to a program written entirely by a complete stranger.

Finally, software which is distributed in this way is often, by virtue of necessity, “static”. This means that not only do you need to download the program itself, but also all of the data libraries that are required for it to run. Since a third-party software developer cannot know which data libraries you may already have available on your system, the only way that they can guarantee it will run on your system is by supplying all of the data libraries it needs along with the program itself. This means bigger downloads, and it means that when the time comes to update a given library, it needs to be done separately for all those programs using it, instead of just once. In summary, the distribution of static software results in the unnecessary duplication of a lot of work.  

Package management in Linux Mint, and GNU/Linux operating systems in general, has been established for some time and is the preferred method for managing software as it avoids all of these issues. We've been safely and automatically installing our software since the early 1990s.

Software is first written by a developer, as you might expect, and this end of the production chain is known as “upstream”. As a user of a Linux distribution, you are referred to as being at the furthest point “downstream” (unless you're an admin, in which case your users are the furthest point downstream, but you knew that because you're an admin). Once the developer is happy with the program or the update to the program they have written, they will release the source code for it. They will also communicate in their documentation which data libraries or other programs they took advantage of when they were writing the program. They have been doing this for some time and there are standardized and venerable ways for them to do this. Note that, with a few exceptions (usually either hardware manufacturers who release drivers for Linux, like nVidia or ATI, or certain major companies like Adobe, who we can trust) they release the actual source code for the program, that is, the list of instructions in that program in a human readable form. This has a number of implications, but most importantly for this discussion it means that they are willing to have their software peer reviewed by anyone and everyone with an Internet connection. It's awfully difficult to sneak spyware into your program when you're letting everyone see what you've written!

The software now moves down the stream to package maintainers, who are either volunteers or paid employees working for a Linux distribution. It is their responsibility to compile the source code for the software, test it on the distribution to make sure that it works, resolve any problems that they encounter and finally package the compiled (i.e., machine-readable) software in a convenient format. This package contains the executable program(s), their configuration files, and the instructions the package management software needs to successfully install it. Note that it won't ordinarily contain any static libraries, since it doesn't need to – the libraries are provided by other packages, and are therefore known as shared libraries. Your package management software will know if that a particular package requires another package to be installed first (like a shared library), because, as you will remember, the data libraries and related packages needed for the software to work were declared further upstream and that information is included in the package. The instructions are sufficiently detailed that even specific versions of other packages can be requested to ensure interoperability. The finished package is then uploaded to a special file server, which is called a software repository. 

It is from that single location that you are able to download and install the software you need. You will know that the location is bona fide, because it is signed with a certificate that your package manager will check. You will also know that each individual package that you install is secure, because each package is itself signed by a GPG key, which your package manager will also check. Your package manager will even run an MD5 sum on each package to make sure that nothing went wrong when it was downloading, just like we did before with the LiveDVD iso. Notice how it's doing all of this for you. You're just sitting back, sipping a martini, and chatting in #linuxmint on xchat. The package manager has downloaded the packages you have selected, it will follow, to the letter (computers are fastidious in following instructions), the instructions in the package to perfectly install your software, and all of its dependencies, in the right order. There is no space for human error – if the package worked on the maintainer's computer, then it ought to on yours because the package manager will follow exactly the same procedure. 

When it comes time to check for software updates, your package manager will automatically compare the software version that you have against what is available in the repository, and do all the necessary work to keep your system running smoothly and securely. So, if version 2.4 of BestSoft is uploaded to the repository, and you have version 2.3, the package manager will compare those version numbers, and offer to install the latest version, taking care, of course, of all the dependencies for the newer version of the software. 

Sounding good yet? It gets better.

Humans err where computers don't and from time to time something may go wrong in this process. Perhaps you will, by accident, install hardware drivers for the wrong piece of hardware and this might break something. We've all done that. Or perhaps there's a bug or your favorite feature was removed by the program's developer for some reason. These problems demonstrate, paradoxically, the strength and security of package management. Because your package manager keeps fastidious records of everything it ever does, it is able to reverse installations, cleanly and completely. It will make sure that removing one package doesn't break any others, and you can even tell it specifically to do things like not automatically upgrade certain packages, because you like them the way they are, or to revert to an earlier version. Finally, the whole process is very heavily peer-reviewed. Because you are part of a large community of Linux users, all using the same repositories to obtain their software, if anything goes wrong you can be absolutely sure there will be a big fuss about it, and that the problem will be resolved quickly! In this way, software distribution in GNU/Linux distributions is very much based on trust, from the moment the original developer displays their source code for all to see, to the open discussion on the distribution's website. You can be confident in the software you obtain, not only because of the security protocols already mentioned, but because if anything does go wrong everyone will be talking about it!

Let's look again at our list of problems and see what we have solved:

- It is difficult or impossible to find out if the software has been tested to work with your operating system
  - You know that the software available to you through the repository has been thoroughly tested by the package maintainer and the testing team to work with your operating system. They won't want to get it wrong, mostly on principle, but also because if they do they'll soon be getting lots of emails.
- It is difficult or impossible to know how this software will interact with the other software installed on your system
  - Similarly, package maintainers try their utmost to ensure that packages won't conflict with other packages offered by their distribution. Of course, they might not have every last package installed on their testing machines (in fact, usually package maintainers build their packages on clean installations to ensure that they are standard), but if a member of the user community finds out that there is a problem, they will no doubt let the distribution team know, and the problem will be fixed, or at least worked on. Unless you are a beta tester, then you are unlikely to ever see such a conflict, because that's what beta testing is for.
- It is difficult or impossible to know if you can place your trust in the developer that their software will not cause any harm, willful or negligent, to your system
  - Package maintainers are hardly likely to package software they know will harm people's computers (including their own)! Only software which is known and trusted will ever make it to the repository.
- Even if you know about a specific piece of software and its developer, you cannot be entirely sure that you are not downloading an executable that has been swapped out by a malicious third party for some type of malware. 
  - In addition to the usual security measures put in place by the institutions who own the servers (usually prestigious academic or research institutions, or large companies), the repository and packages themselves are secured by certificates and GPG keys. If something's gone wrong, your package manager will tell you about it. The present author, in ten years of using Linux, has never once known anything to go wrong in this respect.
- It is difficult to remove (all traces of) installed programs 
  - Because the package management software keeps a complete record of all of its actions, it is quite capable of reversing any steps that it took in the past, while ensuring that removing one package will not cause any other package to fail.
- Static packages are big and clunky
  - Because you're using package management, you will only ever download static libraries when there is no shared alternative. If you need new shared data libraries to install a given program, your package manager will know this and install them for you automatically. You will only ever have to download a shared library once because, well, it's shared by all the programs that need it. If you end up removing the last package that needs a shared library, then the package management software will remove that too. But, if you decide that you do want to keep the shared object anyway, perhaps because you just know you'll need it later, then you can tell the package management software to do that, too.
- I'm still not convinced
  - Good! Post a message on the forums about it if you have a genuine concern about package management, or to ask about other people's experiences. It bears repeating that the package method of distribution in GNU/Linux relies on trust, so if there's a problem, we want to hear about it!

A final word. You may have been subjected to rumors to the effect that Linux isn't finished yet, or that if you use Linux then you are a beta-tester, or that Linux software is unstable. These are all half truths. “Linux” will never be “finished”, any more than any other major operating system can be considered “finished”. From the Linux kernel to the artwork on your screen, all the elements of your operating system will always be under some kind of development. This is because programmers are working hard to keep us up to date with the latest developments in programming and hardware technology. This does not mean that the software available for you to use is of bad quality. The base system at the core of  Linux Mint has been under heavy development for about two decades now, and is very mature, stable, and proven. While there are definitely unstable versions of most of the software on your operating system, you won't be using them because you're not a beta tester. You know you're not a beta tester, because you're reading this. The software available to you on the repositories you use will always be stable and well tested, unless you change those repositories to the ones used by the testers (in which case congratulations, you've just become a tester). It's a bit of a no-brainer, really.  

So, to summarize with an example, when you install Opera, Real Player or Google Earth in Linux Mint, these applications do not come from their original developers (Opera, Real and Google). Of course the upstream application comes from these developers, but only after they’ve been properly packaged and tested do they become available for you. So, in other words, you should never need to go and browse the Internet to look for software, as everything you need is available and already tested for you and for your system by the Linux Mint and Ubuntu teams. All you need to do is choose what you want to do. 

Linux Mint will update itself automatically through a tool called the Update Manager, which will update not only the base operating system, but all the software installed on your machine as well. 

It's that simple. Whew!

Some of the most popular applications that are not installed by default in Linux Mint are Opera, Skype, Acrobat Reader, Google Earth and Real Player. 

#### The Software Manager

The easiest way to install software in Linux Mint is to use the Software Manager. It is built on top of the package technology we discussed earlier, but makes things easier to understand, as it allows you to install programs rather than packages (though, remember, it is still using the package system in the background, so it still has the same benefits).

Open the menu and select “Software Manager”. 

The Software Manager lets you browse the software made available for Linux Mint. You can browse by category, search by keyword or sort the software by rating and popularity.
The Menu

If you know what you're looking for, you don't need to launch anything. Just start typing the application's name in the menu and have it installed from there. 

For instance, to install the “gftp” package: 

- Press CTRL+Super_L to open the menu
- Type “gftp”
- Press the “Up” arrow to highlight the “Install gftp” button
- Press Enter

Did we mention how great package management is yet?

#### Synaptic & APT

If you want to install more than one application or if you’re looking for something which is not in the Software Portal or in the Software Manager, Linux Mint provides two other ways to install software. One is a graphical tool called “Synaptic” and the other is a command line tool called “APT”. 

Let’s see how we can install Opera (an alternative to the Firefox Web Browser) with these tools instead:

Open the menu and select “Package Manager”. 

Click on the “Search” button and type “opera”. Then go through the list of packages and find the one corresponding to the Opera Web Browser. Tick the box and select “Mark for Installation” then click on the “Apply” button. 

Now let’s see how we could have installed Opera using the APT command line tool. 

Open the menu and select “Terminal”. Then type the following command:

    apt install opera

Note: Make sure synaptic is closed before using APT. Synaptic is using APT in the background so both can’t run at the same time. The same goes for the Software Manager.

As you can see APT is extremely easy to use but it’s not graphical. It’s OK. If you’re starting with Linux you probably prefer to deal with a graphical interface (that's why they're there) but as time goes on you’ll prefer things to be fast and efficient and as you can see the fastest way to install Opera is to type “apt install opera”. It can’t be simpler than that. 

There is one important difference between the Software Manager and Synaptic/APT though. With Synaptic and APT you basically deal with packages. In our example the Opera application was very simple and was only made of one package which name was also “opera”, but this will not always be the case, and sometimes you might not know what the name of the package is. Sometimes you might not even have access to the packages for a particular application. 

The Software Manager is different because it lets you install “applications” by getting the right “packages” for you, not only from the repositories (packages databases) that Synaptic and APT have access to, but also from other places on the Internet. 

So you might use the Software Manager for two different reasons: 

- Because you’re not used to APT/Synaptic
- Because it can actually install applications you don’t have access to using other tools. 

### Remove applications

#### From the Menu

Removing an application is quite easy in Linux Mint. Simply highlight the application in the menu, right click on it and select “Uninstall”. 

The menu finds the packages and dependencies related to the application you selected. 

Click “Remove” and the application will be uninstalled. 

#### Using APT

Another way to remove applications is by using APT. Again, we’re talking command-line utility here, but see how surprisingly easy this is: 

Open the menu and select “Terminal”. Then type the following command:

    apt remove opera
    
Note: Make sure synaptic is closed before using APT. Synaptic is using APT in the background so both can’t run at the same time. 

And that’s it. With one single command you’ve removed Opera from your computer. 
Synaptic

You can also use Synaptic to remove packages... Linux is all about choice so let’s see how to do this. 

Open the menu and select “Package Manager”. 

Click on the “Search” button and select “opera”. Then go through the list of packages and find the one corresponding to the Opera Web Browser. Tick the box and select “Mark for Removal” then click on the “Apply” button.



### Update your system and your applications
### 更新你的系统和应用软件

If a new version of any package installed on your computer is made available you can upgrade to it. It may be a security update for some component of the operating system, it may be an optimization in one specific library or it may even be a newer version of Firefox. Basically, your system is made of packages and any part of it can be updated by updating some of those packages. This means replacing the current package with a newer version. 

如果安装在您电脑上的包有新版本了，您可以升级最新版。她可能是操作系统一个组件的更新，可能是某个库的优化，也可能是火狐浏览器的一个新版本。基本上，你的系统是由包组成的，任何一部分都可以通过升级包来更新。这就意味着用一个新版本的包替换当前的版本。

There are many ways to do this but only one of them is recommended. 

更新的方法很多，但在此只推荐一种。 

You could use APT to upgrade all your packages with one simple command (“apt upgrade”) but we strongly recommend you don’t do so. The reason is that it doesn't make any distinctions in selecting which updates to apply and assumes that you want all of them. 

你可以用一个简单的APT命令（apt upgrade)来更新系统的所有包，但我们建议你不要这样做。原因是这个工具在选择更新时不做任何区分，默认您都要更新。

Some parts of the system are safe to update and some others aren’t. For instance, by updating your kernel (the part which is responsible among other things for hardware recognition) you might break your sound support, your wireless card support or even some applications (such as VMWare and Virtualbox) which are closely linked to the kernel. 

系统的部分包可以安全更新，但是有一些就不行了。例如，更新您的内核（她负责很多事情，比如说硬件的识别）您可能会损坏声卡的支持，网卡的支持甚至一些和系统内核相关的应用程序（比如VMWare 和 Virtualbox）。

#### Using the Update Manager

#### 使用更新管理器
Linux Mint comes with a tool called the Update Manager. It gives more information about updates and lets you define how safe an update must be before you want to apply it. It looks like a shield and sits on the bottom-right corner of your screen. 

Linux Mint 有一个叫“更新管理器”的工具。她提供了许多关于更新的信息,在更新之前让您决定怎么安全地更新。她看起来像一个盾牌，坐在您屏幕的右下角。

If you place your mouse pointer on top of it, it will tell you either that your system is up to date or, if it isn't, how many updates are available. 

如果您将鼠标移动到上边,她会告诉您系统是否有更新,如果有的话,指出有什么可用的更新。

If you click on the lock icon, the Update Manager opens and shows you the updates that are available. The interface is very easy to use. For each package update you can read the description, the changelog (this is where developers explain their changes when they modify the package), and eventually if Linux Mint assigned warnings or extra information about the updates. You can also see which version is currently installed on your computer and which version is available for you to update to. Finally, you can see the stability level assigned to the package update. Each package update brings improvements or fixes security issues but that doesn’t mean they’re risk-free and can’t introduce new bugs. The stability level is assigned to each package by Linux Mint and gives you an indication of how safe it is for you to apply an update. 

如果你点击锁按钮,更新管理器就打开了,并显示出可用的更新。图形界面很容易操作。您可以查看每个包的更新描述，改版记录（这是开发者们对所修改包的变化进行说明），最后您还可查看 Linux Mint 发出的警告或者关于更新的额外信息。你也可以查看当前电脑里包的版本,以及能够更新到的新版本。每个包的更新都会对包有所改进,或者解决了一些安全隐患,但并不意味着没有危险或者不会引进一些新的 bug。Linux Mint 会标记每个包的稳定级别，更新时给你提示是否安全。

Of course you can click on the columns to sort by stability level, status, package name or by version. You can select all updates or unselect all of them by using the “Clear” and “Select All” buttons. 

当然您可以单击某列进行排序,可以按照稳定性,状态,包的名字,或者版本来排序。你可以通过“选择所有”按钮选中所有的更新,或者“清除”按钮都不选择。 

Level 1 and Level 2 updates are risk-free and you should always apply them. Level 3 updates “should be safe” but, although we recommend you take them, make sure you look over them on the list of updates. If you experience a problem with a particular Level 3 update, tell the Linux Mint development team so they can take measures to make that update a Level 4 or a Level 5  so as to warn or even discourage others against applying it.  

1,2 级别的更新通常是没有危险的,你可以选择更新。3 级别的更新 “应该是安全的”，但是我们建议你在更新表里仔细查看。如果你曾经在 3 级别上的更新出现过问题,请告诉 Linux Mint 研究小组,以便他们采取措,把这个包放在 4,5 级别里,好警告其他用户不要进行这些更新。

If you click on the “Preferences” button you should see the screen above. By default the Update Manager tells you about Level 1, 2 and 3 updates. You can decide to make Level 4 and 5 “visible”. This will make more updates appear in the list. If you want to  you can even make Level 4 and 5 updates “safe” (although this is not recommended). This will cause them to be selected by default within the Update Manager. 

如果你单击“首选项”按钮,你将会看到上边图片所示的窗口。更新管理器会默认显示 1,2,3 级别的更新,你可以让 4,5 级别也显示出来。这将会在表里显示更多的可更新选项。如果你愿意,你甚至可以选择设置 4,5 级别为安全(尽管不推荐)。这样更新管理器就会默认选中他们这些更新。

The Update Manager only counts “safe” updates. So when it tells you your system is up to date, it means there are no updates available assigned with a level that you defined as being “safe”. 

更新管理器只计算“安全”的更新。因此，当她提示你的系统已经是最新,意味着在你所定义的安全级别中已经没有其他更新。

The Update Manager only shows “visible” updates in the list. 

更新管理器只在表里显示“可见的”更新。

For example, if you made all levels “visible” and only Level 1 and 2 “safe”, you would see a lot of updates in the list, but the Update Manager would probably tell you that your system was up to date. 

例如,你使各个级别都可见了,但是只有 1,2 级别是“安全的”。你会在表中看见很多的更新，但是更新管理器会告诉你的系统是最新的了。

The “Auto-Refresh” tab allows you to define how often the Update Manager checks for updates. 

通过“自动刷新”标签你可以设置更新管理器检查更新的周期。

The “Update Method” tab lets you define how the Update Manager checks for new updates. 

通过“更新方法”标签页你可以设置让更新管理器如何检查最新的更新。 

The “Startup delay” is the amount of time the Update Manager waits before checking for an Internet connection. This delay is used to give the Network Manager an opportunity to establish a connection when the computer starts.

“开启延时”是指更新管理器开启之前检查网络链接的时间。计算机启动时，这个延迟时间给网络管理器一个机会建立网络链接。

You can also define which domain name is used by the Update Manager to check the connection to the Internet. The Update Manager will try to ping this domain before looking for updates.

你也可以通过更新管理器定义的域名来检查网络链接情况。更新管理器会在查找更新前尝试ping这个域名。

The “Include dist-upgrade packages” option allows you to define whether the Update Manager should install new dependencies or not. For instance if package A version 1 was installed on your computer and package A version 2 became available, but version 2 had a new dependency on package B which isn’t installed on your computer… what would happen?

“包含间接升级包” 选项让您选择是否让更新管理器建立新的包依赖关系。例如,包 A 的 1 版本已经安装在系统里，现在包 A 的 2 版本可用，但是 2 版本对 B 包有依赖，而 B 包又不存在电脑上。那该怎么办呢?

If you left this checkbox unchecked, version 2 would not appear as an update in the list of updates. 

如果您不选中复选框,版本 2 就不会出现在更新管理器的列表中了。

If you checked this checkbox, it would, and if selected it would install packageB as a dependency. 

如果你选中这个复选框，她就会安装 B 包来作为依赖。

Be careful with this option as dependency can install new packages on your behalf but they can also sometimes remove packages you already have installed.  

在选择安装新包时要注意依赖关系,有时候会把你已经安装的包给删除了。

In the “Ignored packages” tab you can define packages for which you do not want to receive updates. “?” and “*” wildcard characters are supported.

在“忽略包”标签页中,可以设置您不想接受更新的包,可以使用“?”和“*”等通配符。

The “Proxy” tab lets you define proxy settings.

”代理“ 标签页是让您设置代理服务器的。

The last tab lets you change the icons used by the Update Manager in the system tray. 

最后一个标签是让你设置更新管理器在系统托盘里的图标的。

If you get errors with the Update Manager (“Can’t refresh list of packages” for instance), you can check the logs. Right click on the lock icon in the system tray and select “Information”. The following screen appears: 

如果你在使用更新管理器时有错误发生（比如，不能刷新包列表），你可以检查日志文件。鼠标右击系统托盘，然后选择“信息”。显示如下： 


In this screen you can see the process ID of the Update Manager, whether it's running with user or root permissions, and the content of its log file.

在上图中你可以看到更新管理器的进程ID号，是否以root权限运行，以及日志文件的内容。

You can also review the updates that were applied on your system (provided they were applied via the Update Manager) by clicking on “View->History of Updates”.

你还可以查看你系统已经应用的更新情况(通过更新管理器提供的),通过单击“查看->更新历史”来查看。


