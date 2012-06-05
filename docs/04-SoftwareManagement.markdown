##Software Management

软件管理

### Package Management in Linux Mint

### Linux Mint 下的软件包的管理

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

#### 软件管理器

The easiest way to install software in Linux Mint is to use the Software Manager. It is built on top of the package technology we discussed earlier, but makes things easier to understand, as it allows you to install programs rather than packages (though, remember, it is still using the package system in the background, so it still has the same benefits).

在Linux Mint中安装软件最简单的方法就是使用软件管理器。她是在建立在包管理基础之上的技术，使很多东西简单化，让您安装软件而不是包（尽管如此，记住了，她后台使用的还是包管理器，所以她也有和包管理器相同的益处）。

Open the menu and select “Software Manager”. 

打开菜单选择“软件管理器”。

The Software Manager lets you browse the software made available for Linux Mint. You can browse by category, search by keyword or sort the software by rating and popularity.

软件管理器可以让您查看到在Linux Mint上可以使用的软件。您可以按类查看，搜索关键字，或者按排名或者受欢迎程度排序。

The Menu

菜单

If you know what you're looking for, you don't need to launch anything. Just start typing the application's name in the menu and have it installed from there. 

如果您知道您自己在找什么软件，您不需要运行任何东西。只需要在菜单里输入应用程序的名字，然后安装即可。

For instance, to install the “gftp” package: 

例如，安装“gftp”这个软件包

- Press CTRL+Super_L to open the menu

- 按下组合键CTRL+SUPER_L来打来菜单

- Type “gftp”

- 输入“gftp”

- Press the “Up” arrow to highlight the “Install gftp” button

- 按“上”箭头来使“install gftp”高亮

- Press Enter

- 按回车键

Did we mention how great package management is yet?

- 怎么样我们谈到的软件管理器还不错吧？

#### Synaptic & APT

#### 新立得和APT

If you want to install more than one application or if you’re looking for something which is not in the Software Portal or in the Software Manager, Linux Mint provides two other ways to install software. One is a graphical tool called “Synaptic” and the other is a command line tool called “APT”. 

如果你想安装更多的应用程序，或者你找的软件不在Software Portal和软件管理器中，Linux Mint提供了另外2种方式来安装软件。一个是图形化的工具叫做“新立得”，一个是命令行工具叫做“APT”。

Let’s see how we can install Opera (an alternative to the Firefox Web Browser) with these tools instead:

我们来看一下如何通过以上两种方式来安装Opera（一种类似于火狐的浏览器）。

Open the menu and select “Package Manager”. 

打开菜单，选择包管理器。

Click on the “Search” button and type “opera”. Then go through the list of packages and find the one corresponding to the Opera Web Browser. Tick the box and select “Mark for Installation” then click on the “Apply” button. 

点击搜索按钮，输入“Opera”。然后在列表里找寻对应Opera浏览器的项目，把勾给挑上，并“标记为安装” ，单击“应用”按钮。

Now let’s see how we could have installed Opera using the APT command line tool. 

接下来让我们看看怎么使用命令行工具来安装Opera。

Open the menu and select “Terminal”. Then type the following command:

打来主菜单，选择“终端”，输入以下的命令。

    apt install opera

	apt install opera
	
Note: Make sure synaptic is closed before using APT. Synaptic is using APT in the background so both can’t run at the same time. The same goes for the Software Manager.

注意：确保你的新立得已经关闭了，因为新立得的后台运行得实际上是APT工具，不可以同时运行。同理软件管理器也是如此。

As you can see APT is extremely easy to use but it’s not graphical. It’s OK. If you’re starting with Linux you probably prefer to deal with a graphical interface (that's why they're there) but as time goes on you’ll prefer things to be fast and efficient and as you can see the fastest way to install Opera is to type “apt install opera”. It can’t be simpler than that. 

如您所见，APT是非常好用的，但是不是图形化的。没关系，如果您刚开始使用Linux，您可能更多的使用图形界面（这也是图形界面的益处），但是随着时间的移动，您可能希望更快更加有效的完成一些事情，比如说安装Opera最简单的方法是“apt install opera”。这再简单不过喽。

There is one important difference between the Software Manager and Synaptic/APT though. With Synaptic and APT you basically deal with packages. In our example the Opera application was very simple and was only made of one package which name was also “opera”, but this will not always be the case, and sometimes you might not know what the name of the package is. Sometimes you might not even have access to the packages for a particular application. 

软件管理器,新立得和APT它们之间的一个重要差别在于，新立得和APT主要用来处理包，在我们的例子中，Opera非常简单，她本身只是由一个包组成的，但是情况并不总是这样的,一些情况下，您并不知道包的名字。有时候您甚至可能接触不到某个软件的包。

The Software Manager is different because it lets you install “applications” by getting the right “packages” for you, not only from the repositories (packages databases) that Synaptic and APT have access to, but also from other places on the Internet. 

软件管理器的不同，在您选择安装应用程序时，自动会为您选择好包。包的来源不仅仅是来自新立得和APT所依赖的源，还来自互联网上的其他地方。

So you might use the Software Manager for two different reasons: 

因此您使用软件管理器可能有以下两种原因：

- Because you’re not used to APT/Synaptic

- 您不习惯新立得和APT

- Because it can actually install applications you don’t have access to using other tools. 

- 因为她能准确的安装好应用软件，在您不使用其他工具的情况下。

### Remove applications

### 删除应用程序

#### From the Menu

#### 从菜单中删除

Removing an application is quite easy in Linux Mint. Simply highlight the application in the menu, right click on it and select “Uninstall”. 

在Linux Mint里删除一个软件是很简单的。只需要在菜单里标注应用程序，单击右键选择“卸载”即可。

The menu finds the packages and dependencies related to the application you selected. 

在菜单中会找到您要删除的软件包和她的依赖关系。

Click “Remove” and the application will be uninstalled. 

单击删除，应用程序就会被删除了。

#### Using APT

#### 使用APT删除

Another way to remove applications is by using APT. Again, we’re talking command-line utility here, but see how surprisingly easy this is: 

另外一个删除软件的方法就是使用APT命令，我们又在讨论命令行工具了。让我们来看看她是多么简单而令人惊讶吧。

Open the menu and select “Terminal”. Then type the following command:

打开主菜单，选择终端，输入下面的命令

    apt remove opera

	apt remove opera
	
Note: Make sure synaptic is closed before using APT. Synaptic is using APT in the background so both can’t run at the same time. 

注意：确保你的新立得已经关闭了，因为新立得的后台运行得实际上是APT工具，不可以同时运行。

And that’s it. With one single command you’ve removed Opera from your computer. 

搞定，你只用了一条指令就把Opera从计算机中移除了。

#### Synaptic  

#### 使用新立得删除

You can also use Synaptic to remove packages... Linux is all about choice so let’s see how to do this. 

你也可以使用新立得来删除包，因为Linux下总有很多选择，让我们来看看怎么使用的它吧：

Open the menu and select “Package Manager”. 

打开主菜单选择“包管理器”

Click on the “Search” button and select “opera”. Then go through the list of packages and find the one corresponding to the Opera Web Browser. Tick the box and select “Mark for Removal” then click on the “Apply” button.

点击搜索按钮，选择“Opera”，然后查看包的列表，找对应于Opera浏览器的选项。把勾挑上，右键选择标记为删除，单击应用按钮即可。

### Update your system and your applications

If a new version of any package installed on your computer is made available you can upgrade to it. It may be a security update for some component of the operating system, it may be an optimization in one specific library or it may even be a newer version of Firefox. Basically, your system is made of packages and any part of it can be updated by updating some of those packages. This means replacing the current package with a newer version. 

There are many ways to do this but only one of them is recommended. 

You could use APT to upgrade all your packages with one simple command (“apt upgrade”) but we strongly recommend you don’t do so. The reason is that it doesn't make any distinctions in selecting which updates to apply and assumes that you want all of them. 

Some parts of the system are safe to update and some others aren’t. For instance, by updating your kernel (the part which is responsible among other things for hardware recognition) you might break your sound support, your wireless card support or even some applications (such as VMWare and Virtualbox) which are closely linked to the kernel. 

#### Using the Update Manager

Linux Mint comes with a tool called the Update Manager. It gives more information about updates and lets you define how safe an update must be before you want to apply it. It looks like a shield and sits on the bottom-right corner of your screen. 

If you place your mouse pointer on top of it, it will tell you either that your system is up to date or, if it isn't, how many updates are available. 

If you click on the lock icon, the Update Manager opens and shows you the updates that are available. The interface is very easy to use. For each package update you can read the description, the changelog (this is where developers explain their changes when they modify the package), and eventually if Linux Mint assigned warnings or extra information about the updates. You can also see which version is currently installed on your computer and which version is available for you to update to. Finally, you can see the stability level assigned to the package update. Each package update brings improvements or fixes security issues but that doesn’t mean they’re risk-free and can’t introduce new bugs. The stability level is assigned to each package by Linux Mint and gives you an indication of how safe it is for you to apply an update. 

Of course you can click on the columns to sort by stability level, status, package name or by version. You can select all updates or unselect all of them by using the “Clear” and “Select All” buttons. 

Level 1 and Level 2 updates are risk-free and you should always apply them. Level 3 updates “should be safe” but, although we recommend you take them, make sure you look over them on the list of updates. If you experience a problem with a particular Level 3 update, tell the Linux Mint development team so they can take measures to make that update a Level 4 or a Level 5  so as to warn or even discourage others against applying it.  


If you click on the “Preferences” button you should see the screen above. By default the Update Manager tells you about Level 1, 2 and 3 updates. You can decide to make Level 4 and 5 “visible”. This will make more updates appear in the list. If you want to  you can even make Level 4 and 5 updates “safe” (although this is not recommended). This will cause them to be selected by default within the Update Manager. 

The Update Manager only counts “safe” updates. So when it tells you your system is up to date, it means there are no updates available assigned with a level that you defined as being “safe”. 

The Update Manager only shows “visible” updates in the list. 

For example, if you made all levels “visible” and only Level 1 and 2 “safe”, you would see a lot of updates in the list, but the Update Manager would probably tell you that your system was up to date. 

The “Auto-Refresh” tab allows you to define how often the Update Manager checks for updates. 

The “Update Method” tab lets you define how the Update Manager checks for new updates. 

The “Startup delay” is the amount of time the Update Manager waits before checking for an Internet connection. This delay is used to give the Network Manager an opportunity to establish a connection when the computer starts.

You can also define which domain name is used by the Update Manager to check the connection to the Internet. The Update Manager will try to ping this domain before looking for updates.

The “Include dist-upgrade packages” option allows you to define whether the Update Manager should install new dependencies or not. For instance if package A version 1 was installed on your computer and package A version 2 became available, but version 2 had a new dependency on package B which isn’t installed on your computer… what would happen?

If you left this checkbox unchecked, version 2 would not appear as an update in the list of updates. 

If you checked this checkbox, it would, and if selected it would install packageB as a dependency. 

Be careful with this option as dependency can install new packages on your behalf but they can also sometimes remove packages you already have installed.  

In the “Ignored packages” tab you can define packages for which you do not want to receive updates. “?” and “*” wildcard characters are supported.

The “Proxy” tab lets you define proxy settings.

The last tab lets you change the icons used by the Update Manager in the system tray. 

If you get errors with the Update Manager (“Can’t refresh list of packages” for instance), you can check the logs. Right click on the lock icon in the system tray and select “Information”. The following screen appears: 


In this screen you can see the process ID of the Update Manager, whether it's running with user or root permissions, and the content of its log file.

You can also review the updates that were applied on your system (provided they were applied via the Update Manager) by clicking on “View->History of Updates”.