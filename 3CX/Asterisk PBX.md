<details>
      <summary><b>What is Asterisk? - Asterisk introduction</b></summary>
Asterisk是PBX（私有分支交换机）的开源软件实现。像任何PBX一样，它允许许多连接的电话相互呼叫，并连接到包括PSTN，ISDN或VoIP提供商的其他电话服务。
Asterisk名称指的是“ *”符号，在Unix和DOS命令行语法中是“通配符”，表示语音网络中非常通用的组件的符号。Asterisk允许多个分组语音协议进行交互，并提供带有用于添加新应用程序的API的模块化设计，这使Asterisk成为融合电信领域的真正通配符。

Asterisk具有GPL许可证。Digium的Mark Spencer最初创建了Asterisk，并且仍然是其主要的维护者，尽管其他程序员也贡献了新功能，并报告了错误。Asterisk最初是为Linux操作系统设计的，现在也可以在OpenBSD，FreeBSD，Mac OS X，Sun Solaris和Microsoft Windows上运行，尽管Linux是“本机”平台，但在这些平台中得到最好的支持。

Asterisk是一个开放源代码融合电信平台，旨在允许不同类型的IP电话硬件，中间件和软件始终保持相互连接。它提供了多层，可以在较低层管理TDM和分组语音，同时为PBX和IVR等电话应用程序提供高度灵活的平台。星号可以桥接和转换不同类型的VoIP协议，例如SIP，MGCP和H.323。同时，它可以提供功能齐全的服务器平台，用于预测性拨号，自定义IVR，远程和中心局PBX以及会议。


通过支持传统电话和VoIP电话服务的混合，Asterisk允许部署人员有效地构建新的电话系统，或将现有系统逐步迁移到新技术。一些站点正在使用Asterisk服务器来替换老化的专用PBX。其他提供附加功能（例如语音邮件或电话菜单）或通过在Internet上进行长途通话来削减成本的工具

 </details>
 <details>
      <summary><b>Asterisk installation for linux（linux安装）</b></summary>

```
wget http://downloads.asterisk.org/pub/telephony/asterisk/releases/asterisk-1.6.2.20.tar.gz
tar -zxvf asterisk-1.6.2.20.tar.gz
rm -f asterisk-1.6.2.20.tar.gz
cd asterisk-1.6.2.20
./configure
make
make install
```
第一次使用命令安装Asterisk PBX的示例
"make samples"
但是，请注意！此命令将重写您已经拥有的所有配置文件。

然后，您可以使用以下命令启动Asterisk PBX
asterisk -vvvc

您可能会在屏幕上看到很多消息。（“ vvv”表示“非常非常冗长”），“ c”字母在所有消息的末尾向我们显示控制台命令行，如下例所示。
*CLI>

到此为止Asterisk已经正在运行，寻找帮助可以输入help命令

您还可以在linux命令行中使用命令“ man asterisk”来获取有关如何启动和停止Asterisk服务器的信息。

Asterisk配置文件已安装在/ etc / asterisk目录中，您可以在其中找到很多信息。

现在，我们将通过一些简单的测试来验证Asterisk是否可以正常运行：

我们必须配置一个软件电话，例如SJPhone（有关Sjphone配置中有关其配置的更多信息），以便在我们自己的Asterisk服务器中注册。默认安装有两个用户可以使用。
A: user: 3000 password=anything works
B: user: 3001 password=anything works

当我们对其进行了正确的配置并且用户已经在我们的Asterisk服务器中注册后，该进行一些在默认分机拨号计划中定义的呼叫了。

```
1000 - Main menu
1234 - Transfer the call to the console (you could see the call at the console command line)
1235 - Console voicemail
1236 - Call to the console command line

3000 - Call to 3000 SIP user
3001 - Call to 3001 SIP user

500 - Call to Digium

600 - Echo test

8500 - Voicemail menu

99990 AGI test
99991 EAGI test
99992 Tell the hour
99999 Music

700 Parked call
701-720 Parking calls
```
一个有趣的测试是在两台不同的计算机中配置2部软电话：一台使用3000用户，另一台使用3001用户并互相通话。如果可行，您已准备好在Asterisk的第一步中学习如何配置Asterisk并创建新用户和拨号计划。

  </details>
     
 <details>
      <summary><b>First steps with Asterisk（设置Asterisk）</b></summary>
    现在Asterisk已安装并正在运行，因此我们将通过示例学习我们可以做的第一件事。在此示例中，我们将创建两个具有扩展名和语音邮件的新用户。

1. 创建2个新的SIP用户。

例如，用户“ 20000”和“ 20100”的密码为“ a20000b”和“ b20100a”，

在sip.conf文件末尾添加以下

```
[20000]
type=friend
secret=a20000b
qualify=yes
nat=no
host=dynamic
canreinvite=no
context=miprimerejemplo
mailbox=20000@miprimerbuzon

[20100]
type=friend
secret=b20100a
qualify=yes
nat=no
host=dynamic
canreinvite=no
context=myfirstexample
mailbox=20100@myfirstvoicemail
```

2. Create the extensions for the 2 users

创建扩展名要为用户创建扩展名，我们需要修改文件extensions.conf。如果我们拨打20100，我们应该联系20000用户，如果拨打20100，我们应该联系用户20100。我们还创建一个特殊的分机“ 30000”来访问语音邮件主菜单。

因此，我们将以下行添加到extensions.conf文件的末尾

```
[mifirstexample]
exten => 20000,1,Dial(SIP/20000,30,Ttm)
exten => 20000,2,Hangup
exten => 20000,102,Voicemail(20000)
exten => 20000,103,Hangup

exten => 20100,1,Dial(SIP/20100,30,Ttm)
exten => 20100,2,Hangup
exten => 20100,102,Voicemail(20100)
exten => 20100,103,Hangup

exten => 30000,1,VoicemailMain
```

3. Create the voicemail fot the users
创建语音邮件现在，我们为两个用户创建语音邮件，并在voicemail.conf文件中为他们提供密码。我们将20000邮件的密码设为1234，将20100邮件的密码设为4321

```
[myfirstvoicemail]
20000 => 1234,Peter,peter@midomain.com
20100 => 4321,John,john@midomain.com
```

4. Restart Asterisk server

5. Configure a softphone
现在，我们配置一台或两台软件电话，并进行测试以在不可用时互相呼叫或在语音信箱中发送消息。我们还应该拨打30000号码收听我们的消息。有关如何配置软件电话（例如sjphone）的更多信息，请转到http://www.en.voipforo.com/Telephones/sjphone-configuration.php


   </details>

<details>
      <summary><b>sip.conf file configuration（sip.conf文件配置）</b></summary>
在sip.conf文件中，我们可以配置与SIP协议相关的所有内容。添加新的SIP用户或定义SIP提供程序。
例如，sip.conf文件的简单示例：

```
general]
context=default
port=5060 ; UDP port for Asterisk
bindaddr=0.0.0.0 ; If we want to specify only an IP (if a computer has three different IPs) 0.0.0.0 means any IP
srvlookup=yes ; Enable DNS SRV server

[peter]
type=friend
secret=welcome
qualify=yes ;latency must be under 2000ms.
nat=no ; Telephone without NAT
host=dynamic ; the devices can be registered with different IPs each time
canreinvite=no ; Asterisk by default redirects
context=internal ; the context of the extensions.conf file

```

sip.conf文件以[general]节开头，具有每个用户和对等方（providers）的默认配置。可以在每个用户或对等方的特定配置中覆盖默认值

- 通常，SIP服务器使用端口5060 UDP。这就是为什么我们使用port = 5060的原因。有时，例如，如果我们将SER（Sip Express路由器）与Asterisk一起使用，我们应该更改端口号。

- DNS是一种管理逻辑地址以便解决的方法。这样就可以在不更改逻辑地址的情况下将呼叫引至不同的地方。使用DNS SRV，我们具有DNS的优势，而如果我们给定“ no”值，则无法路由基于域的呼叫。使用srvlookup = yes激活服务是一个好主意。

每个扩展名由用户或对等体或朋友定义，并以[]之间的名称进行调用

- "user" 类型用于验证传入呼叫，即“对等”用于拨出电话，两者都用作“朋友”。在示例中，我们有一个名为“ peter”的“ friend”扩展名。它可以打入和打出电话。
- "secret" 用于验证的密码，在这种情况下是受欢迎
- Asterisk服务器与电话之间的等待时间可以用qualify = yes进行监视，以确定何时可以到达设备。如果设备的等待时间小于2000毫秒（2秒），则Asterisk默认认为存在该设备。可以用毫秒数代替“yes”来更改该值。
- 如果扩展名位于路由器或防火墙之类的进行NAT（网络地址转换）的设备后面，则“ nat = yes”会强制Asterisk忽略现场联系信息，它将使用软件包的来源地址。
-  如果我们将 "host=dynamic"表示电话将能够通过任何IP地址进行连接。我们可以限制该用户仅使用IP或域名进行访问。如果我们输入“ host = static”，则用户无需使用“ secret”中提供的密码进行注册。
- 在SIP中，邀请消息用于建立呼叫以及重定向音频或视频。同一会话中初始邀请消息之后的任何邀请消息均被视为重新邀请。例如，连接了两个用户，其中一个处于活动状态的保持音乐（MoH），因为他想停止对话。因此，Asterisk重新邀请了第二位用户。后来，第一个用户想要跟进呼叫，并向Asterisk发送重新邀请消息，然后发送给第二个用户，并且两者都重新连接。使用canreinvite = no。强制Asterisk位于中间，不允许最终点直接交换消息RTP。

最后，context = internal显示了将在其中执行此扩展指令的上下文。这与文件extensions.conf的上下文有关，该文件为该上下文提供了拨号计划。因此，“ external”上下文必须存在于文件extensions.conf中，否则我们不应该创建它。几个扩展可以具有相同的上下文。

高级选项：

在以下各列中，我们可以配置“ user”和“ peer”类型。在“friend”的情况下，两列都是可能的，因为朋友是user+peer。

<table width="100%" border="1" cellpadding="0" cellspacing="0" class="normal">
                <tbody><tr class="titulo_post_peq">
                  <td width="16%"><div align="left">User</div></td>
                  <td width="14%"><strong>Peer </strong></td>
                  <td width="70%">Explicación y opciones </td>
                </tr>
                <tr>
                  <td><strong>context</strong></td>
                  <td><strong>context</strong></td>
                  <td>Context in the dialplan (extensions.conf) for a peer or a user.</td>
                </tr>
                <tr>
                  <td><strong>permit</strong></td>
                  <td><strong>permit</strong></td>
                  <td> Allow an IP address</td>
                </tr>
                <tr>
                  <td><strong>deny</strong></td>
                  <td><strong>deny</strong></td>
                  <td>Deny an IP address</td>
                </tr>
                <tr>
                  <td><strong>secret</strong></td>
                  <td><strong>secret</strong></td>
                  <td>Password for registration</td>
                </tr>
                <tr>
                  <td><strong>md5secret</strong></td>
                  <td><strong>md5secret</strong></td>
                  <td>Password with md5 </td>
                </tr>
                <tr>
                  <td><strong>dtmfmode</strong></td>
                  <td><strong>dtmfmode</strong></td>
                  <td>the way dtmf are sent. it could be "RFC2833" or "INFO" </td>
                </tr>
                <tr>
                  <td><strong>canreinvite</strong></td>
                  <td><strong>canreinvite</strong></td>
                  <td>With"yes" Asterisk is forced to be in the middle not allowing that the final points interchange messages RTP directly. . </td>
                </tr>
                <tr>
                  <td><strong>nat</strong></td>
                  <td><strong>nat</strong></td>
                  <td>"yes" alert that the devices is behind NAT</td>
                </tr>
                <tr>
                  <td><strong>callgroup</strong></td>
                  <td><strong>callgroup</strong></td>
                  <td> Defines a callgroup</td>
                </tr>
                <tr>
                  <td><strong>pickupgroup</strong></td>
                  <td><strong>pickupgroup</strong></td>
                  <td> Defines a callgroup in a pickup() application</td>
                </tr>
                <tr>
                  <td><strong>language</strong></td>
                  <td><strong>language</strong></td>
                  <td>Defines a country signals and voices. It must be present in the indications.conf file</td>
                </tr>
                <tr>
                  <td><strong>allow</strong></td>
                  <td><strong>allow</strong></td>
                  <td>allow a codec. Some codesc for the same user are possible. values:<br>
"allow=all" ,"allow=alaw", "allow=ulaw", "allow=g723.1" ; allow="g729" , "allow=ilbc" , "allow=gsm".</td>
                </tr>
                <tr>
                  <td><strong>disallow</strong></td>
                  <td><strong>disallow</strong></td>
                  <td>disallow a codec. Some values that allow</td>
                </tr>
                <tr>
                  <td><strong>insecure</strong></td>
                  <td><strong>insecure</strong></td>
                  <td> Defines the way the connections with peers are managed. It has these values very|yes|no|invite|port. "no" is the default value that means that authentication is compulsory. </td>
                </tr>
                <tr>
                  <td><strong>trustpid</strong></td>
                  <td><strong>trustpid</strong></td>
                  <td> If the <strong>Remote-Party-ID </strong> is trusted. By default "no" </td>
                </tr>
                <tr>
                  <td><strong>progressinband</strong></td>
                  <td><strong>progressinband</strong></td>
                  <td> If inband signals must be generated. By default <strong>never </strong> </td>
                </tr>
                <tr>
                  <td><strong>promiscredir</strong></td>
                  <td><strong>promiscredir</strong></td>
                  <td>Redirections 302 are supported. By default "no" </td>
                </tr>
                <tr>
                  <td><strong>callerid</strong></td>
                  <td>&nbsp;</td>
                  <td>Defines the identifier when there is no other information available</td>
                </tr>
                <tr>
                  <td><strong>accountcode</strong></td>
                  <td>&nbsp;</td>
                  <td>Users can be associated with an accountcode . For billing purposes. </td>
                </tr>
                <tr>
                  <td><strong>amaflags</strong></td>
                  <td>&nbsp;</td>
                  <td>To CDR and billing purpouses It can be "default", "omit", "billing", or "documentation"</td>
                </tr>
                <tr>
                  <td><strong>incominglimit</strong></td>
                  <td>&nbsp;</td>
                  <td>Limit of simultaneous calls</td>
                </tr>
                <tr>
                  <td><strong>restrictcid</strong></td>
                  <td>&nbsp;</td>
                  <td>To hide the caller ID. Deprecated</td>
                </tr>
                <tr>
                  <td>&nbsp;</td>
                  <td><strong>mailbox</strong></td>
                  <td> Voicemail extension</td>
                </tr>
                <tr>
                  <td>&nbsp;</td>
                  <td><strong>username</strong></td>
                  <td>If Asterisk acts like SIP client is the user name showed to the calling SIP server.</td>
                </tr>
                <tr>
                  <td>&nbsp;</td>
                  <td><strong>fromdomain</strong></td>
                  <td> From field of SIP messages</td>
                </tr>
                <tr>
                  <td>&nbsp;</td>
                  <td><strong>regexten</strong></td>
                  <td>&nbsp;</td>
                </tr>
                <tr>
                  <td>&nbsp;</td>
                  <td><strong>fromuser</strong></td>
                  <td>User From field of SIP messages</td>
                </tr>
                <tr>
                  <td>&nbsp;</td>
                  <td><strong>host</strong></td>
                  <td>adress or host of the remote devices. it can be:<br>
      - An IP address or a host<br>
      - "dynamic" - any IP with password<br>
      - "static" - any IP without password</td>
                </tr>
                <tr>
                  <td>&nbsp;</td>
                  <td><strong>mask</strong></td>
                  <td>&nbsp;</td>
                </tr>
                <tr>
                  <td>&nbsp;</td>
                  <td><strong>port</strong></td>
                  <td>UDP port<span class="textoca"></span></td>
                </tr>
                <tr>
                  <td>&nbsp;</td>
                  <td><strong>qualify</strong></td>
                  <td>to determine when the device can be reached</td>
                </tr>
                <tr>
                  <td>&nbsp;</td>
                  <td><strong>defaultip</strong></td>
                  <td> default IP of the <strong>host= </strong> when "dynamic" is selected</td>
                </tr>
                <tr>
                  <td>&nbsp;</td>
                  <td><strong>rtptimeout</strong></td>
                  <td>Timeout that ends the call when there is no RTP traffic</td>
                </tr>
                <tr>
                  <td>&nbsp;</td>
                  <td><strong>rtpholdtimeout</strong></td>
                  <td>Timeout that ends the call when there is no RTP traffic on hold</td>
                </tr>
              </tbody></table>

```
Ejemplos:

[grandstream1]
type=friend ; is both peer and user
context=mycontext ; context name
username=grandstream1 ; usually the same as the section
fromuser=grandstream1 ; overwrites caller-ID
callerid=John Smith<1234>
host=192.168.0.23 ; a private IP of a LAN
nat=no ; no NAT
canreinvite=yes ;
dtmfmode=info ; it can be RFC2833 or INFO
mailbox=1234@default ; mailbox 1234 in the context "default"
disallow=all ;
allow=ulaw ; allow alaw codec
; listed with allow= does NOT matter!
;allow=alaw
;allow=g723.1 ; Only g723.1 pass through
;allow=g729 ; Only g729 pass through

[xlite1]
;silence suppresion can be activated
;Xlite sends keep-alive NAT packets ,so qualify=yes is not necessary
type=friend
username=xlite1
callerid="john jones" <5678>
host=dynamic ; xlite softphone could be in any IP address
nat=yes ; X-Lite is behind a NAT device
canreinvite=no ; when a device is behind a NAT device it usually is no
disallow=all
allow=gsm ; GSM needs low bandwithd than ulaw and alaw
allow=ulaw
allow=alaw

[user1_snomsip]
type=friend
secret=blah ; password to register
host=dynamic
dtmfmode=inband ; the possibilities are inband , rfc2833, or info
defaultip=192.168.0.59 ; IP address of the device
mailbox=1234; Voicemail
disallow=all
allow=ulaw ; because we have chosen inband for dtmf we need alaw or ulaw (G.711)
allow=alaw

[user2_pingtel]
type=friend
username=user2_pingtel
secret=blah
host=dynamic
qualify=1000 ; If it is over 1 second without response the connection is broken
callgroup=1,3-4 ; members of groups 1,3 and 4
pickupgroup=1,3-4 ; member of "pickup" groups 1,2 and 4
defaultip=192.168.0.60 ;IP
disallow=all
allow=ulaw
allow=alaw
allow=g729

[user3_cisco]
type=friend
username=user3_cisco
secret=blah
nat=yes ; is behind NAT
host=dynamic
canreinvite=no ;
qualify=200 ; 200 ms to receive a response
defaultip=192.168.0.4
disallow=all
allow=ulaw
allow=alaw
allow=g729

[user4_cisco1]
type=friendusername=user4_cisco
fromuser=peter ;
secret=blah
defaultip=192.168.0.4 ;
amaflags=default ; Possibilities are default, omit, billing or documentation
accountcode=peter ; For billing purposes
disallow=all
allow=ulaw
allow=alaw
allow=g729
allow=g723.1


```

</details>
     