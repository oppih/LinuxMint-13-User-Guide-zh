## Linux Mint的安装

您可以免费下载Linux Mint操作系统。网站所提供下载的是一个ISO文件，所以您需要将其刻录入一张空白DVD中。然后便可用此liveDVD启动系统，同时它也提供了全功能操作系统而对您的电脑却毫无影响。通俗地讲，当您将Linux Mint刻入DVD中并用它启动电脑，进行试用时对您当前的系统没有丝毫的影响。


注意：您亦可将ISO镜像写入到U盘或者其他存储设备中，然后从这些设备启动系统，或者从硬盘上的ISO镜像文件直接启动，但这些是较高级的选择，我们更推荐您使用本文呈现的方法安装系统。欲寻求安装和运行Linux Mint的其他备选方法，请访问论坛。
 
如果您喜欢运行liveDVD时所见的一切，可以考虑将此系统直接安装到您的硬盘上。DVD中包含了所有需要的工具（包括分区及安装工具）。

### 下载ISO文件

注意：如果您没有宽带连接，或者联网速度很慢，可以在这个网站上订购DVD光盘，网址是：[http://www.osdisc.com](http://www.osdisc.com)

此外，您也可以访问Linux Mint的下载页面：
[http://www.linuxmint.com/download.php](http://www.linuxmint.com/download.php)

然后选择您感兴趣的版本进行下载。

在此网页，您应该能看到：

- 一个MD5签名
- 一个种子下载链接
- 一个镜像下载列表

您需要下载的是一个ISO文件。有两种途径来下载此文件，通过BT（点对点协议）或者镜像下载（HTTP或FTP协议）进行文件下载。一旦下载完成，您可以通过检查其MD5签名来确保ISO文件没有被毁坏。

#### 通过BT下载

BT是一种点对点（P2P）协议。从本质来讲，种子文件使得您可以跨越网络从不同人的手中下载ISO文件的部分文件，而并非从一个中心位置直接下载。

下载此ISO文件的人越多，下载的速度就越快。这是下载Linux Mint的首选方式，同时也是我们推崇的方法。
 
#### 安装BT客户端

为了能够通过BT下载文件，您需要安装一款BT客户端软件。

如果您运行的是Linux系统，可以安装“Transmission”这款软件。如果运行的是Linux Mint，就不必费心啦，因为Transmission早就被预置安装了。

如果是Windows，您可以使用Vuze
（[http://azureus.sourceforge.net/](http://azureus.sourceforge.net/)）。

#### 下载种子文件

下一步就是通过Linux Mint网页中的种子链接去下载后缀为.torrent的种子文件。文件很小，下载完成后，您得用BT客户端才能打开它。

BT客户端将可能会询问您欲将ISO文件存往何处。请选择一个目标文件夹，然后耐心地等待下载完成吧。

欲获更多BT协议信息，请访问网站：
[http://en.wikipedia.org/wiki/BitTorrent](http://en.wikipedia.org/wiki/BitTorrent)

#### 通过镜像下载

如果您不能或者不愿选择BT协议下载镜像，就来看看镜像下载列表并在里面随心挑一个吧。它们自身将会提供一个ISO文件的下载链接，您只需轻轻一点即可开始下载了。

注意：别忘了带宽总是会受限制的，而且下载同一镜像的人越多，每个人获取镜像的速度就越慢。此外，如果因为某些原因导致下载中断，镜像可能会因此毁坏而让您不得不重新下载。考虑到诸多因素，如果采取这种途径，不管对Linux还是Windows，使用下载管理器都意义非凡。

### 阅读发行说明

下载将可能持续至少一个小时，所以现在是您熟悉您正在下载的发行版系统新特性的绝佳时机。

发行说明位于Linux Mint官方网页的重要位置，它主要回答了以下几个问题：

- 在此发行版中有哪些新增特性？
- 此发行版存在哪些已知的问题？
- 如何从前一版本进行升级？

其中也包括了最新发行版的屏幕截图。当然，您可以直接使用此系统来发掘发行说明中提及的重点突显的特性，但您也可能会错失一些东西，所以还是乖乖阅读一下发行说明吧。

Linux Mint 13 May的发行说明可在此获得：
[http://www.linuxmint.com/rel_maya.php](http://www.linuxmint.com/rel_maya.php)

### 校验MD5

阅读完发行日志，您已经等不及想体验这些新特性或者使用Linux Mint了吧，刚好此时镜像下载也刚完成。现在就可以准备刻录光盘然后启动系统……但是，稍安勿躁！

如果那张DVD有错误，您将会遇到诡异问题，而且寻求帮助时也会遇到很多麻烦。导致DVD文件有误的最常见两个原因是：

- 下载过程中的问题导致了ISO文件的错误
- 刻录过程中的错误改变了liveDVD的内容

下载页面上的MD5签名为确保您下载的ISO文件完整无误提供了一条快捷的途径。所以，在我们刻录前先对已下载的文件进行MD5校验以避免那些潜伏的问题。
 
如果您运行了其他版本的Linux，可能已经安装了md5sum程序。打开终端并使用“cd”命令切换到ISO文件所在目录（比如，假设“linuxmint.iso”文件在桌面上），开启终端并键入：

    cd ~/Desktop
    md5sum linuxmint.iso
    
这条命令应该会输出一串数字和字母，其中包含了您的ISO文件的MD5校验值。依照设计，任何小的改动都将引起MD5值的明显改变，这样我们就能验证文件没有被篡改过。

将这个MD5值与Linux Mint网站下载页面的值进行比较。如果两者相同，那么您的ISO文件就没问题，现在您就可以准备将它刻录到DVD上啦。

如果碰巧您运行的是Windows，那么可能没有安装md5sum。可以从这里下载：
[http://www.etree.org/md5com.html](http://www.etree.org/md5com.html)

请将ISO文件和md5sum.exe放在同一目录下（假设在C:\），然后运行“cmd.exe”。在命令行环境中，键入如下命令：

    C:
    cd \
    md5sum linuxmint.iso
    
然后将这个值与网页上的MD5值进行比较。

### 将ISO刻录至DVD 

现在您已经用MD5对ISO文件进行了校验，就可以把它刻录到DVD上了。

注意：Linux Mint同样提供了适合700MB CD的镜像文件。如果您无法进行DVD刻录，请使用CD镜像。

取一个空白的DVD-R（DVD-RW也行，但这种类型的介质会牵扯到兼容性问题），还有您最喜欢的标签，把它贴在DVD上做标记。虽然做标记看起来挺微不足道，但您也应该不厌其烦地做好，否则桌上若有20张无标签的光盘，您将该凌乱了。:)

将空白DVD-R插入光驱，然后准备ISO镜像的刻录工作。

如果您运行的是Linux Gnome桌面，请右击ISO文件并选择“写入磁盘”。

如果您运行的是Linux KED桌面，请启动K3B程序，然后在“工具”菜单中选择“写入ISO镜像”。

如果您运行Linux并且喜欢在终端中工作，进入您下载镜像的目录，运行如下命令：

    cdrecord -v -dao dev=1,0,0 linuxmint.iso
    
用您适当的磁盘设备号替换dev=后面的数字。可以运行如下命令（需要root权限）找到设备号。

    cdrecord -scanbus

如果您运行的是Windows，可以用类似InfraRecorder的刻录软件：
[http://infrarecorder.sourceforge.net/?page_id=5](http://infrarecorder.sourceforge.net/?page_id=5)

注意：请确定是将ISO镜像刻录到光盘，而不是将ISO文件写入光盘。对使用Nero的人们来说，一个极其普遍的错误是他们会实际将ISO文件当做数据文件刻录到光盘中。ISO文件是磁盘的一个镜像，因此它不应被刻录成磁盘上的一个文件，而应该是一个被解压ISO镜像，其内容被刻录在光盘上。刻录完DVD后，在光盘中您不会看到ISO文件，而应是类似“casper”或者“isolinux”之类的目录文件。大部分刻录软件对此都有指定的选项。

### 引导LiveDVD

将DVD放入光驱中然后重启电脑。您将会看到以下界面：

![boot-screen](https://github.com/oppih/LinuxMint-13-User-Guide-zh/raw/master/images/boot-screen.png)

注意：如果您没有看到此界面并且您的电脑像以往一样正常启动，那么可能是由于您的BIOS没有设置为从DVD启动。重启电脑，按下F1、F2、Delete或者Escape键（或者其他能让您进入BIOS配置的键）然后修改您的BIOS设置以告知电脑从DVD驱动启动。

### 安装Linux Mint到您的硬盘上

在看到的第一个画面中，选择默认的“Start Linux Mint”选项，然后按下Enter键。

![start-screen](https://github.com/oppih/LinuxMint-13-User-Guide-zh/raw/master/images/start-screen.png)

稍等一会，当live系统准备完成后，您就可以看到桌面了：

![desktop](https://github.com/oppih/LinuxMint-13-User-Guide-zh/raw/master/images/desktop.png)

此时Linu Mint还没有安装到您的电脑中，它只是简单的在DVD中运行。但是现在，您面前的这个系统和安装后的系统几乎是一模一样的。

好好的体验这个系统。记住，运行在DVD上的Linux Mint系统要比安装在硬盘上的系统慢得多，这是因为它要从存取速度比硬盘慢的DVD上读取数据。

当您准备好安装的时候，双击桌面上的“Install Linux Mint”图标。接着安装向导就会出现：

![installer](https://github.com/oppih/LinuxMint-13-User-Guide-zh/raw/master/images/installer.png)

如果您还没有阅读发行日志，并且您连接着网络，那这是一次回顾它的好机会；单击有下划线的链接即可。我们强烈推荐用户先阅读发行日志再安装系统，这是为了让用户了解新的特性，以及任何可能因部分硬件配置产生的问题。

下一步是选择您想使用的语言并按下”Forward”按钮。

![preparing](https://github.com/oppih/LinuxMint-13-User-Guide-zh/raw/master/images/preparing.png)

在接下来的画面中，请确保您已经接上电源（如果您正在使用笔记本电脑），连接着网络还有足够的硬盘空间。接着按下“Forward”按钮。

![installation-type](https://github.com/oppih/LinuxMint-13-User-Guide-zh/raw/master/images/installation-type.png)

下一个画面中，您可以分配您整个硬盘去安装LinuxMint或者和其他的操作系统并存。另外，您还可以手动创建和划分空间。

- 如果您选择使用整个硬盘，那它将会擦除硬盘上的所有数据并将Linux Mint作为您电脑上唯一的操作系统。
- 如果您选择和其他的操作系统装在一起，那么安装向导将会用其他分区的闲置可用的空间，来为Linux Mint创建一个新的分区。安装向导会询问您要分配多大的空间。它将会收缩一个分区并为您处理好一切事情。安装完成后，下次启动电脑时会出现一个引导界面，让您能选择您要启动的操作系统。
- 如果您选择手动指定分区，那么将会出现一个分区工具，使您能完全控制您硬盘的分区情况。这是推荐给那些懂得在Linux下进行分区工作的高级用户使用的。注意，Linux Mint需要至少6GB大小的空间，并且推荐分一块是内存1.5倍大小的交换空间(swap partition)。

选择合适的选项并按下“Forward”按钮。

![partition](https://github.com/oppih/LinuxMint-13-User-Guide-zh/raw/master/images/partition.png)

下一个画面会让您确认操作。当您准备好就可以点击“Install Now”按钮开始安装。

眼下，安装程序将会在后台运行，安装向导会询问您一些安装配置问题：

![timezone](https://github.com/oppih/LinuxMint-13-User-Guide-zh/raw/master/images/timezone.png)

在地图上通过点击来选择一个离您最近的城市。这个操作是为了确定您所处的时区，确保”Current time”正确出现后点击“Forward”按钮。

注意:有时候安装向导不能精确地调整夏令时或者冬令时，所以即使您选择了正确的城市，也可能有一小时左右的时间差。此时还是忽略它吧，不过当您安装完Linux Mint重启进入桌面后，要确认时间是正确的。

![keyboard-layout](https://github.com/oppih/LinuxMint-13-User-Guide-zh/raw/master/images/keyboard-layout.png)

选择您的键盘布局，如果您不清楚您的键盘适合哪种键盘布局，那就点击屏幕底部的文本区，再用您的键盘打一些字。如果说您敲击的键和文本区出现的字符对应，就说明您选择了正确的键盘布局。一些布局只在引号，数字和标点符号之间有所不同，所以也一定要测试这些键。

完成后点击“Forward”按钮。

输入您的真实姓名名以及用户名和密码。以后您每次使用Linux Mint的时候，都会使用这个用户账号和密码的。一旦Linux Mint装好，如果还有其他人要使用您的电脑的话， 您就能创建其它的账号。

当然也要给您的电脑起个名字。这个名字将会用于网络或者别的地方的系统。如果您从来没想过给您的电脑命名，那现在是个好机会。大多数人通常会选择花（大丽花，玫瑰，郁金香）或者星球（火星，木星，冥王星）的名字来作为电脑在网络中的名字。这完全由您决定，但是要确保选择一个您喜欢的而且也容易记的名字。

注意：大写字母，空格以及特殊字符不能作为用户名或者电脑的名字。

如果只有您使用这台电脑并且您想跳过登录界面，那就在“Log in automatically”选项前打勾。 

完成后点击“Forward”按钮。

![yourname](https://github.com/oppih/LinuxMint-13-User-Guide-zh/raw/master/images/yourname.png)

安装向导会检测出您电脑上其它的操作系统，并且会询问您是否要移动一些个人信息。通常它会将您的书签、通讯录、收藏夹以及其它操作系统上的一些个人信息移动到新安装的Linux Mint系统里。

完成后点击“Forward”按钮。

![installing](https://github.com/oppih/LinuxMint-13-User-Guide-zh/raw/master/images/installing.png)

安装程序会持续10到15分钟。

注意：安装向导会从网络上下载您之前选择的语言包。您的电脑需要连接着网络才能进行此项工作。不然的话就点击”Skip”按钮跳过这一步，您可以在安装完系统重启后，再添加语言支持包。

一旦您的安装程序执行完，就可以点击“Restart Now”按钮，LiveDVD环境也会关闭。

看到提示信息后，从驱动器中取出DVD,再按下Enter键。

现在您的电脑可以从硬盘上启动Linux Mint了。

### 引导顺序

再次重启，如果您安装了多个操作系统，您应该能看见一个“boot menu”(引导菜单)。
 
一旦Linux Mint完成加载，您就会看到一个新的登录界面，需要您输入用户名和密码。这个画面简称为“MDM Login Manager”，通常被叫做“MDM”。输入您在安装时设置的密码。

![login-screen](https://github.com/oppih/LinuxMint-13-User-Guide-zh/raw/master/images/login-screen.png)

注意：默认情况下，您的“root”密码和您在安装 Linux Mint 时设置的密码是一样的。如果您不明白这是什么意思，那您就不用管它了。
