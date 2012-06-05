## Installation of Linux Mint

You can download the Linux Mint operating system for free. It comes as an ISO file which you need to burn to a blank DVD. The liveDVD is then bootable and provides a fully-functional operating system which you can try without affecting your PC. In layman's terms, when you put Linux Mint on a DVD and place it into your computer, you can try it out while leaving your current system intact. 

Note: It is also possible to write the ISO image to a USB stick or other memory device and boot from that, or to boot from the ISO image on the hard drive, but these options are somewhat more advanced and the method presented here is recommended. For help with alternative methods of installing and running Linux Mint, please visit the forums.
If you like what you see when running the liveDVD you can decide to install the system to your hard drive. All the necessary tools (partitioning and installation tools) are present on the DVD. 

### Download the ISO

Note: If you don't have a broadband connection, or if your Internet access is too slow you can order the DVD from this web site: [http://www.osdisc.com](http://www.osdisc.com)

Otherwise, you can visit the Linux Mint download page here: [http://www.linuxmint.com/download.php](http://www.linuxmint.com/download.php)

Then choose the edition you're interested in.

From this page, you should be able to find: 

- an MD5 signature
- a torrent link
- a list of download mirrors

The file you need to download is an ISO file. There are two ways to download this file, by torrent (a Peer to Peer protocol) or via a download mirror (HTTP or FTP protocol). Once your download is finished, you can ensure your ISO file isn’t corrupted by checking its signature with the MD5. 

#### Via Torrent

Torrent is a Peer to Peer (P2P) protocol. Basically, instead of downloading from a central location, a torrent lets you download the ISO file in parts from different people across the Internet. 

The more people who download the ISO file, the faster the download speed gets. This is the preferred and recommended way to download Linux Mint. 

##### Install a Torrent client

You need a piece of software called a “torrent client” in order to download files via torrent.

If you run Linux, you can install “Transmission”. If you run Linux Mint, Transmission is already installed. 

If you run Windows, you can use Vuze ( [http://azureus.sourceforge.net/](http://azureus.sourceforge.net/) ).

##### Download the Torrent file

The next step is to follow the torrent link from the Linux Mint website and to download the .torrent file. This file is very small. After it downloads, you should open it with your torrent client. 

The torrent client will probably ask you where you want to save the ISO. Select a destination and then wait for the download to complete. 

For more information about the torrent protocol, visit: [http://en.wikipedia.org/wiki/BitTorrent](http://en.wikipedia.org/wiki/BitTorrent)

#### Via a download mirror

If you can’t, or do not choose to use the torrent protocol, then look at the list of download mirrors and pick one of them. They’ll provide a link to the ISO file itself which you can just click to start the download. 

Note: Remember that bandwidth is limited though and the more people download from a mirror, the slower the download speed gets for everybody who is downloading from that mirror. Furthermore, if for some reason the download should be interrupted, it may be corrupted and the download may have to be restarted. For these reasons it might be worthwhile using a download manager, like for Linux, or for Windows, if taking this route.

### Read the Release Notes

Your download is probably going to last at least an hour, so now would be the perfect time for you to get familiar with the new features coming with the release you’re currently downloading. 

The release notes are featured on the Linux Mint web page and answer the following questions:

- What are the new features delivered in this release?
- What are the known problems of this release?
- How do I upgrade from the previous release?

They also contain screenshots of the latest release. Of course, you could find out about most features highlighted in the release notes by simply using the operating system, but you might miss a few things, so it is most reliable to read the release notes. 

The release notes for Linux Mint 13 Maya are available here: [http://www.linuxmint.com/rel_maya.php](http://www.linuxmint.com/rel_maya.php)

### Check the MD5

You’ve read the release notes, you just can’t wait to play with the new features or try Linux Mint, and your download just finished successfully. You’re ready to burn a DVD and to boot on it… but hey! Wait for a second! 

If that DVD is faulty you will experience weird bugs and will have a lot of trouble finding help. The two most common reasons for a DVD to be faulty are:

- An issue with the download causing problems in your ISO file
- An error during the burn process that alters the contents of your burned liveDVD 

The MD5 signature, which is present on the download page, provides a quick way for you to make sure that your ISO file is exactly like it should be. So, let’s check the ISO file you just downloaded before we burn it and save ourselves from a lot of potential problems. 

If you run any version of Linux you probably already have the md5sum program installed. Open a terminal and “cd” to the directory where your ISO file is (for instance, if “linuxmint.iso” is on the Desktop), open a terminal and type: 

    cd ~/Desktop
    md5sum linuxmint.iso
    
This command should output a series of numbers and letters which comprise the MD5 sum, or signature, of your ISO file. By design, any small change to the ISO file will cause this signature to be significantly different, allowing us to verify that the file is exactly as it should be.

Compare that signature with the one on the download page of the Linux Mint website. If the two signatures are the same, then you know your ISO file is exactly the same as the original and you can now get ready to burn it on DVD 

If you happen to run Windows, chances are you don’t have md5sum installed. You can get it from here: [http://www.etree.org/md5com.html](http://www.etree.org/md5com.html)

Place the ISO file and the md5sum.exe in the same place (let’s say in C:\) and run “cmd.exe”. In the command line environment, type the following commands: 

    C:
    cd \
    md5sum linuxmint.iso
    
Then compare the signature to the one present on the website. 

### Burn the ISO to DVD

Now that you have checked the ISO file with MD5, you are ready to burn it to a DVD. 

Note: Linux Mint also provides images which fit on 700MB CDs. If you can't burn DVDs please use the CD images instead. 

Get a blank DVD-R (a DVD-RW should work as well, but this type of media is known to have compatibility issues) and your favorite marker and label the DVD. Although labeling your DVDs sounds trivial, you should be sure to do so, as you can easily end up with 20 unlabeled and unidentifiable discs on your desk. :)

Insert the blank DVD-R in the drive and get ready to burn the ISO. 

If you’re running Linux with MATE right-click on the ISO file and select “Write to Disc”. 

If you’re running Linux with KDE, launch K3B and in the “Tools” menu choose “Write ISO Image”. 

If you're running Linux and would like to use the terminal, from the directory you have downloaded the image to:

    cdrecord -v -dao dev=1,0,0 linuxmint.iso
    
Replacing the numbers after dev= with the appropriate device number for your disc drive. You can run

    cdrecord -scanbus
    
to find this out. You may need to be root to run these commands.

If you’re running Windows you can use a program like InfraRecorder:
[http://infrarecorder.sourceforge.net/?page_id=5](http://infrarecorder.sourceforge.net/?page_id=5)

Note: Make sure to burn the ISO image to disk, and not to write the ISO file to the disk. A very common mistake, especially for people using Nero, is to actually burn the ISO file on the disk as a data file. The ISO file is an image of a disk so it needs to be burnt not as a file which will appear on the disk, but as an ISO image which will be decompressed and whose content will be burnt onto the disc. After burning the DVD you shouldn't see the ISO file within the disc, but rather folders like “casper” or “isolinux”. Most burning software has a special option for this. 

### Boot the LiveDVD

Place the DVD in the drive and restart the computer. You should now see the following screen:


Note: If you don’t see this screen and your PC boots as usual it’s probably because your BIOS is not set to boot on DVD. Restart the computer and press F1, F2, Delete, or Escape (or whatever key lets you enter the BIOS configuration) and change your BIOS settings to tell your computer to boot from its DVD drive. 

### Install Linux Mint on your Hard Drive

### 安装Linux Mint到你的硬盘上

From the first screen choose the default “Start Linux Mint” option and press Enter. 

在看到的第一个画面中，选择默认的“Start Linux Mint”选项，然后按下Enter键。

After a little while the live system should be ready and you should see the desktop:

稍等一会，当live系统准备完成后，你就可以看到桌面了：

At this stage Linux Mint is not installed on your computer, it’s simply running from the DVD. The system you have in front of you is, however, almost exactly the same as the one you will have on your computer after the installation is finished. 

此时Linu Mint还没有安装到你的电脑中，它只是简单的在DVD中运行。但是现在，你面前的这个系统和安装后的系统几乎是一模一样的。

Have fun with it and see if you like it. Bear in mind that when running from the DVD, Linux Mint runs significantly slower than it does when it is installed on a hard drive, since it has to read data from the DVD drive, which is a slower medium than the hard drive.

好好的体验这个系统。记住，运行在DVD上的Linux Mint系统要比安装在硬盘上的系统慢得多，这是因为它要从存取速度比硬盘慢的DVD上读取数据。

When you are ready, double-click on the “Install Linux Mint” icon located on the desktop. The Installer appears: 

当你准备好安装的时，双击桌面上的“Install Linux Mint”图标。接着安装向导就会出现：

If you haven’t read the release notes yet, and you have an Internet connection, then this an ideal opportunity to review them; simply click on the underlined link. It is highly recommended that users read the release notes prior to installation in order to advise themselves of new features, as well as any issues that might affect their particular hardware configuration.

如果你还没有阅读发行日志，并且你连接着网络，那这是一次回顾它的好机会；单击有下划线的链接即可。我们强烈推荐用户先阅读发行日志再安装系统，这是为了让用户了解新的特性，以及任何可能对他们的部分硬件配置产生影响的问题。


Select your language and press the “Forward” button.

下一步是选择你想使用的语言并按下”Forward”按钮。

In the next screen, make sure you're connected to a power source (if you're using a laptop), the Internet and that you have the recommended amount of disk space. Then press the “Forward” button. 

在接下来的画面中，请确保你已经接上电源（如果你正在使用笔记本电脑），连接着网络还有足够的硬盘空间。接着按下“Forward”按钮。

In the next screen you can assign your entire hard drive to Linux Mint or install it alongside other operating systems. Alternatively, you can also define and assign the partitions manually. 

下一个画面中，你可以分配你整个硬盘去安装LinuxMint或者和其他的操作系统并存。另外，你还可以手动创建和划分空间。

- If you choose to use the entire disk, its content will be erased and Linux Mint will be installed as the only operating system on your computer.
- If you choose to install it alongside other operating systems, the installer will use the free space available on other partitions to create a new one for Linux Mint. You will be asked how much space you want to allocate to it. The installer will then shrink a partition and take care of everything for you. Post-installation your computer will have a boot screen from which you'll be able to boot all your operating systems. 
- If you choose to specify partitions manually, a partition editor will appear, giving you full control over the partitioning of your hard drive. This is recommended only to advanced users who understand how partitioning works under Linux. Note that Linux Mint requires a partition of at least 6GB and that the recommended size for a swap partition is 1.5 times the amount of RAM available on the computer.

- 如果你选择使用整个硬盘，那它将会擦除硬盘上的所有数据并将Linux Mint作为你电脑上唯一的操作系统。
- 如果你选择和其他的操作系统装在一起，那么安装向导将会用其他分区的闲置可用的空间，来为Linux Mint创建一个新的分区。安装向导会询问你要分配多大的空间。它将会收缩一个分区并为你处理好一切事情。安装完成后，下次启动电脑时会出现一个引导界面，让你能选择你要启动的操作系统。
- 如果你选择手动指定分区，那么将会出现一个分区工具，使你能完全控制你硬盘的分区情况。这是推荐给那些懂得在Linux下进行分区工作的高级用户使用的。注意，Linux Mint需要至少6GB大小的空间，并且推荐分一块是内存1.5倍大小的交换空间(swap partition)。

Choose the appropriate option and click on the “Forward” button.

选择合适的选项并按下“Forward”按钮。

The next screen asks you to confirm. When ready press the “Install Now” button to start the installation. 

下一个画面会让你确认操作。当你准备好就可以点击“Install Now”按钮开始安装。

At this stage, the installation is going on in the background and the installer asks you setup questions:

眼下，安装程序将会在后台运行，安装向导会询问你一些安装配置问题：

Choose your location on the map by clicking on the city which is the nearest to you. The purpose of this step is to identify your time zone. Make sure the “Current time” appears correctly and click the “Forward” button.

在地图上通过点击来选择一个离你最近的城市。这个操作是为了确定你所处的时区，确保”Current time”正确出现后点击“Forward”按钮。

Note: Sometimes the installer doesn't properly handle Summer/Winter time adjustments, so even by selecting the proper city you might see a difference of an hour or so with the correct time. Simply ignore this at this stage and remember to make sure that the time is correct after you reboot in your newly installed Linux Mint desktop.

注意:有时候安装向导不能精确地调整夏令时或者冬令时，所以即使你选择了正确的城市，也可能有一小时左右的时间差。此时还是忽略它吧，不过当你安装完Linux Mint重启进如桌面后，要确认时间是正确的。

Select your keyboard layout. If you are not sure about exactly which layout matches the keyboard you have, click on the text field at the bottom of the screen and start typing with your keyboard. Make sure the keys you press match the characters that appear in the text field in order to ensure you have selected the right keyboard layout. Some layouts only differ with respect to accents, numbers and punctuation signs, so make sure to test these as well. 

选择你的键盘布局，如果你不清楚你的键盘适合哪种键盘布局，那就点击屏幕底部的文本区，再用你的键盘打一些字。如果说你敲击的键和文本区出现的字符对应，就说明你选择了正确的键盘布局。一些布局只在引号，数字和标点符号之间有所不同，所以也一定要测试这些键。

When you’re ready click the “Forward” button. 

完成后点击“Forward”按钮。

Enter your real name and a username and password. Every time you’ll use Linux Mint you’ll use your account with this username and password. Once Linux Mint is installed you’ll be able to define other accounts if other people are to use this computer. 
Also give your computer a name. This name will be used by your computer on the network or in various places of the system. If you’ve never really thought about naming your computers, then now is the time. People commonly pick flower (dahlia, rose, tulip) or planet (mars, jupiter, pluto) names for the computers on their network. It’s entirely up to you what you want to use, but make sure to pick a name you like and that you will easily remember. 

输入你的真实性名以及用户名和密码。以后你每次使用Linux Mint的时候，都会使用这个用户账号和密码的。一旦Linux Mint装好，如果还有其他人要使用你的电脑的话， 你就能创建其它的账号。
当然也要给你的电脑起个名字。这个名字将会用于网络或者别的地方的系统。如果你从来没想过给你的电脑命名，那现在是个好机会。大多数人通常会选择花（大丽花，玫瑰，郁金香）或者星球（火星，木星，冥王星）的名字来作为电脑在网络中的名字。这完全由你决定，但是要确保选择一个你喜欢的而且也容易记的名字。

Note: Capital letters, spaces and special characters are not permitted in the username or in the name of the computer.

注意：大写字母，空格 以及特殊字符不能作为用户名或者电脑的名字。

If you're the only one using the computer and you want to bypass the login screen, check the option “Log in automatically”.  

如果只有你使用这台电脑并且你想跳过登录界面，那就在“Log in automatically”选项前打勾。 

When you’re ready click on the “Forward” button. 

完成后点击“Forward”按钮。

The installer might detect other operating systems on your computer and ask you if you want to migrate some personal information. Typically this allows you to migrate bookmarks, contacts, favorites and other sorts of personal information from other operating systems installed on your hard disk drive into the newly installed Linux Mint.

安装向导会检测出你电脑上其它的操作系统，并且会询问你是否要移动一些个人信息。通常它允许你移动书签，通讯录，收藏夹以及其它操作系统上的一些个人信息。

When you’re ready click on the “Forward” button. 

完成后点击“Forward”按钮。


The installation should take between 10 and 15 minutes. 

安装程序会持续10到15分钟。 

Note: The installer will download packages from the Internet to support the language you’ve selected. Your computer needs to be connected to the Internet for this to work. Otherwise just “skip” that step and you’ll be able to add support for your language after the installation is finished and you’ve rebooted into your new system. 

注意：安装向导会从网络上下载你之前选择的语言包。你的电脑需要连接着网络才能进行此项工作。不然的话就点击”Skip”按钮跳过这一步，你可以在安装完系统重启后，再添加语言支持包。

Once the installation is done click the “Restart Now” button and the liveDVD environment will shut down. 

一旦你的安装程序执行完，就可以点击“Restart Now”按钮，LiveDVD环境也会关闭。

When prompted, remove the DVD from the drive and press Enter. 

当提示从驱动器移出DVD就按下Enter键。

Your PC is now ready to boot Linux Mint from the hard drive. 

现在你的电脑可以从硬盘上启动Linux Mint了。

### The Boot sequence

### 引导顺序

Upon reboot, if you have more than one operating system installed, you should see a “boot menu”.

再次重启，如果你安装了多个操作系统，你应该能看见一个“boot menu”(引导菜单) 。

Once Linux Mint is finished loading you should see a new screen inviting you to enter your username and password. This screen is the “MDM Login Manager” and is commonly called “MDM”. Enter the password you chose during the installation.
 
一旦Linux Mint完成加载，你就会看到一个新的登录界面，需要你输入用户名和密码。这个画面简称为“MDM Login Manager”，通常被叫做“MDM”。输入你在安装时设置的密码。

Note: By default, your “root” password is the same as the password you chose during the installation. If you do not know what this means, then don't worry about it.

注意：默认情况下，你的“root”密码和你在安装Linux Mint时设置的密码是一样的。如果你不明白这是什么意思，那你就不用管它了。
