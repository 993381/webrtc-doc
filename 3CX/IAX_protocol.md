<details>
      <summary><b>IAX架构</b></summary>
      IAX协议（Inter-Asterisk eXchange协议）旨在提供Asterisk服务器之间voip数据的控制和传输。如今，它还用于支持协议的客户端和服务器之间的连接。

IAX的当前版本为IAX2，因为IAX的第一个版本已过时。IAX是为VoIP连接（音频流）设计和考虑的协议，尽管它可以支持另一种类型的数据（例如视频流）

，但IAX的主要目标是：

- 最大限度地减少控制和媒体传输的带宽使用，并特别强调个人语音通话
- 避免NAT问题（网络地址转换）
-支持传输拨号计划信息的能力

为了减少带宽，IAX或IAX2使用二进制协议而不是像SIP这样的文本协议，这就是为什么IAX消息的大小小于SIP消息的原因。

为了避免NAT问题，IAX或IAX2通常在端口4569（IAX1使用端口5036）上使用UDP传输协议，并且信令信息和数据都使用相同的协议（与SIP不同）一起使用，因此，IAX的NAT较少问题，并且可以更好地通过路由器和防火墙。
</details>


<details>
      <summary><b>IAX通信示例-消息</b></summary>
      为了理解IAX协议，我们将解释一个使用IAX主要消息进行通信的真实示例：

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200820170936196.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzI4ODgwMDg3,size_16,color_FFFFFF,t_70#pic_center)

IAX或IAX2中的呼叫具有三个常见步骤或情况：

A）呼叫建立
终端启动连接并发送“新”消息。被叫终端用“接受”消息答复，而呼叫者也用“ Ack”消息答复。接下来，被叫终端发出“振铃”信号，而呼叫者发送“ ack”以确认消息的接收。最终，被叫方接受带有“应答”消息的呼叫，而呼叫者确认该消息。呼叫设置已建立。

B）媒体或音频流
M和F帧与音频数据一起沿任一方向发送。每个流主要由IAX迷你帧（M帧）组成，
包含一个以带宽效率为目标的简单4字节标头。通过包含
同步信息的周期性全帧（F帧）对流进行补充。重要的是要注意，这些音频消息使用的是与信令消息（呼叫建立和拆除）相同的UDP协议，以避免NAT问题。

C）呼叫
拆除连接断开只是发送一个“挂断”消息并确认该消息。
</details>

<details>
      <summary><b>IAX型框架</b></summary>
      IAX2中发送的帧或消息是二进制的，因此每个位或每个位集都有其含义。基本上有两种类型的帧：

A）F帧或全帧

全帧是唯一可靠传输的帧类型。这意味着接收方主机必须在接收到后立即将某种类型的消息返回给发送方主机。

IAX2中的F帧或全帧二进制格式

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200820171230884.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzI4ODgwMDg3,size_16,color_FFFFFF,t_70#pic_center)

各字段的含义如下一个::
- ˚F：用于在指示帧是否是一个完整的帧。此字段中的值1表示该帧是全帧，而值0表示该帧不是全帧。
- 源呼叫号码：用于跟踪源主机上的媒体流的端点的15位无符号整数
- - [R ：设置为值1，如果该帧被重发和用于初始传输的值0
- 目的地呼叫号码：与源电话号码相同，但目的地而不是源。
- 时间戳记 -标记每个数据包的时间
- OSeqno：出站流序列number.OSeqno，始终以0和单调增加开始
- ISeqno：类似于OSeqno，不同之处在于它是用来跟踪入站媒体帧的顺序。
- 帧类型：帧类型
- Ç：如果C被设置为1，子类值被解释为二的幂。如果C设置为0，则子类将解释为简单的7位无符号整数值。
- 子类：消息的子类类型。
- 数据：以二进制格式发送的数据。

B）Tramas M o迷你镜架

F帧或Mini Frame用于以最小的协议开销发送媒体。该帧传输不可靠。如果丢失这些帧之一，则不会重新传输。

M帧或mini帧的二进制格式如下：

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200820171332210.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzI4ODgwMDg3,size_16,color_FFFFFF,t_70#pic_center)

含义类似于F帧，但F位设置为0。迷你帧中的时间戳被截断。客户端通常
维护32位完整时间戳。发送迷你帧时，在“时间戳”字段中仅发送时间戳的低16位。当16位时间戳结束时，将发送全帧以允许另一端同步其完整的32位时间戳计数器。

</details>


<details>
      <summary><b>IAX F框架值</b></summary>
     F帧的Type Frame字段与子类字段一起确定已发送或接收的包的功能，它们是控制信令消息。

“类型框架”字段是一组8位（1字节），下表中显示了可以使用的主要值：

表1. F帧或“全帧”的“类型框架”字段的主要值

<table width="100%" border="1" class="normal">
                <tbody><tr class="titulo_post_peq">
                  <td width="15%"><strong>"type frame" value</strong></td>
                  <td width="14%"><strong>Description</strong></td>
                  <td width="71%"><strong>Details</strong></td>
                </tr>
                <tr>
                  <td>00000001</td>
                  <td>DTMF</td>
                  <td>To send DTMF digits</td>
                </tr>
                <tr>
                  <td><strong>00000002</strong></td>
                  <td><strong>Voice Data</strong></td>
                  <td><strong>Subclass field show the audio codec used. See table 2.</strong></td>
                </tr>
                <tr>
                  <td>00000003</td>
                  <td>Video</td>
                  <td>Subclass field show the video codec used.</td>
                </tr>
                <tr>
                  <td><strong>00000004</strong></td>
                  <td><strong>Control</strong></td>
                  <td><strong>Provide session control. They refer to control of the devices connected to the IAX endpoint. Subclass field show the specific control message. See table 3.</strong></td>
                </tr>
                <tr>
                  <td>00000005</td>
                  <td>No usado</td>
                  <td>&nbsp;</td>
                </tr>
                <tr>
                  <td><strong>00000006</strong></td>
                  <td><strong>IAX Control </strong></td>
                  <td><strong>Provide IAX protocol specific endpoint management. They are used to manage IAX protocol interactions that are generally independent of the type of endpoints. Subclass field show the specific IAX control message. See table 4.</strong></td>
                </tr>
                <tr>
                  <td>00000007</td>
                  <td>Text</td>
                  <td>&nbsp;</td>
                </tr>
                <tr>
                  <td>00000008</td>
                  <td>Image</td>
                  <td>&nbsp;</td>
                </tr>
                <tr>
                  <td>00000009</td>
                  <td>HTML</td>
                  <td>&nbsp;</td>
                </tr>
              </tbody></table>

  表2. Frame Type =“ 0x02”的子类值的含义（语音数据）
  <table width="100%" border="1" class="normal">
                      <tbody><tr class="titulo_post_peq">
                        <td width="13%"><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;"> 子类值（类型框架= 0x02）</font></font></strong></td>
                        <td width="87%"><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">说明（会议中使用的编解码器）</font></font></strong></td>
                      </tr>
                      <tr>
                        <td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">0x0001</font></font></td>
                        <td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">G.723.1</font></font></td>
                      </tr>
                      <tr>
                        <td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">0x0002</font></font></td>
                        <td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">GSM</font></font></td>
                      </tr>
                      <tr>
                        <td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">0x0004</font></font></td>
                        <td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">G.711 u（u-law）</font></font></td>
                      </tr>
                      <tr>
                        <td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">0x0008</font></font></td>
                        <td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">G.711 a（a-law）</font></font></td>
                      </tr>
                      <tr>
                        <td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">0x0080</font></font></td>
                        <td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">LPC10</font></font></td>
                      </tr>
                      <tr>
                        <td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">0x0100</font></font></td>
                        <td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">G.729</font></font></td>
                      </tr>
                      <tr>
                        <td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">0x0200</font></font></td>
                        <td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">斯派克斯</font></font></td>
                      </tr>
                      <tr>
                        <td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">0x0400</font></font></td>
                        <td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">iLBC</font></font></td>
                      </tr>
                    </tbody></table>

表3. Frame Type =“ 0x04”（控件）的子类值的含义
<table width="50%" border="1" class="normal">
                      <tbody><tr class="titulo_post_peq">
                        <td width="13%"><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">子类值（类型框架= 0x04）</font></font></strong></td>
                        <td width="19%"><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">描述 </font></font></strong></td>
                      </tr>
                      <tr>
                        <td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">0x01</font></font></td>
                        <td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">挂断</font></font></td>
                      </tr>
                      <tr>
                        <td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">0x02</font></font></td>
                        <td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">环</font></font></td>
                      </tr>
                      <tr>
                        <td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">0x03</font></font></td>
                        <td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">振铃（回铃）</font></font></td>
                      </tr>
                      <tr>
                        <td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">0x04</font></font></td>
                        <td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">回答</font></font></td>
                      </tr>
                      <tr>
                        <td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">0x05</font></font></td>
                        <td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">繁忙状态</font></font></td>
                      </tr>
                      <tr>
                        <td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">0x08</font></font></td>
                        <td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">拥挤状况</font></font></td>
                      </tr>
                      <tr>
                        <td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">0x0e</font></font></td>
                        <td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">通话进度</font></font></td>
                      </tr>
                    </tbody></table>

表4. Frame Type =“ 0x06”（IAX控件）的子类值的含义
<table width="100%" border="1" class="normal">
                      <tbody><tr class="titulo_post_peq">
                        <td width="100"><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">子类值（类型框架= 0x05）</font></font></strong></td>
                        <td width="80"><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">描述 </font></font></strong></td>
                        <td width="180"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">细节</font></font></td>
                        <td>&nbsp;</td>
                        <td width="100">&nbsp;</td>
                        <td width="80">&nbsp;</td>
                        <td width="180">&nbsp;</td>
                      </tr>
                      <tr>
                        <td width="100"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">0x01</font></font></td>
                        <td width="80"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">新</font></font></td>
                        <td width="180"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">发起新通话</font></font></td>
                        <td>&nbsp;</td>
                        <td width="100"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">0x10</font></font></td>
                        <td width="80"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">REGREJ</font></font></td>
                        <td width="180"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">注册拒绝</font></font></td>
                      </tr>
                      <tr>
                        <td width="100"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">0x02</font></font></td>
                        <td width="80"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">平</font></font></td>
                        <td width="180"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">ping请求</font></font></td>
                        <td>&nbsp;</td>
                        <td width="100"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">0x11</font></font></td>
                        <td width="80"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">REGREL</font></font></td>
                        <td width="180"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">注册释放</font></font></td>
                      </tr>
                      <tr>
                        <td width="100"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">0x03</font></font></td>
                        <td width="80"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">傍</font></font></td>
                        <td width="180"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">平回复</font></font></td>
                        <td>&nbsp;</td>
                        <td width="100"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">0x12</font></font></td>
                        <td width="80"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">威航</font></font></td>
                        <td width="180"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">视频/语音转发请求</font></font></td>
                      </tr>
                      <tr>
                        <td width="100"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">0x04</font></font></td>
                        <td width="80"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">确认</font></font></td>
                        <td width="180"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">致谢</font></font></td>
                        <td>&nbsp;</td>
                        <td width="100"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">0x13</font></font></td>
                        <td width="80"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">DPREQ</font></font></td>
                        <td width="180"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">拨号计划请求</font></font></td>
                      </tr>
                      <tr>
                        <td width="100"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">0x05</font></font></td>
                        <td width="80"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">挂断</font></font></td>
                        <td width="180"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">发起电话拆除</font></font></td>
                        <td>&nbsp;</td>
                        <td width="100"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">0x14</font></font></td>
                        <td width="80"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">DPREP</font></font></td>
                        <td width="180"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">拨号计划响应</font></font></td>
                      </tr>
                      <tr>
                        <td width="100"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">0x06</font></font></td>
                        <td width="80"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">拒绝</font></font></td>
                        <td width="180"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">拒绝</font></font></td>
                        <td>&nbsp;</td>
                        <td width="100"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">0x15</font></font></td>
                        <td width="80"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">拨号</font></font></td>
                        <td width="180"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">拨号</font></font></td>
                      </tr>
                      <tr>
                        <td width="100"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">0x07</font></font></td>
                        <td width="80"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">接受</font></font></td>
                        <td width="180"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">公认</font></font></td>
                        <td>&nbsp;</td>
                        <td width="100"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">0x16</font></font></td>
                        <td width="80"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">TXREQ</font></font></td>
                        <td width="180"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">转移要求</font></font></td>
                      </tr>
                      <tr>
                        <td width="100"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">0x08</font></font></td>
                        <td width="80"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">验证码</font></font></td>
                        <td width="180"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">认证请求</font></font></td>
                        <td>&nbsp;</td>
                        <td width="100"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">0x17</font></font></td>
                        <td width="80"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">碳纳米管</font></font></td>
                        <td width="180"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">转移连接</font></font></td>
                      </tr>
                      <tr>
                        <td width="100"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">0x09</font></font></td>
                        <td width="80"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">AUTHREP</font></font></td>
                        <td width="180"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">认证回复</font></font></td>
                        <td>&nbsp;</td>
                        <td width="100"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">0x18</font></font></td>
                        <td width="80"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">TXACC</font></font></td>
                        <td width="180"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">转移接受</font></font></td>
                      </tr>
                      <tr>
                        <td width="100"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">0x0a</font></font></td>
                        <td width="80"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">无效</font></font></td>
                        <td width="180"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">无效的通话</font></font></td>
                        <td>&nbsp;</td>
                        <td width="100"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">0x19</font></font></td>
                        <td width="80"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">准备就绪</font></font></td>
                        <td width="180"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">准备转移</font></font></td>
                      </tr>
                      <tr>
                        <td width="100"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">0x0b</font></font></td>
                        <td width="80"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">拉格</font></font></td>
                        <td width="180"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">滞后请求</font></font></td>
                        <td>&nbsp;</td>
                        <td width="100"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">0x1a</font></font></td>
                        <td width="80"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">TXREL</font></font></td>
                        <td width="180"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">转移释放</font></font></td>
                      </tr>
                      <tr>
                        <td width="100"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">0x0c</font></font></td>
                        <td width="80"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">LAGRP</font></font></td>
                        <td width="180"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">延迟回复</font></font></td>
                        <td>&nbsp;</td>
                        <td width="100"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">0x1b</font></font></td>
                        <td width="80"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">TXREJ</font></font></td>
                        <td width="180"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">转移拒绝</font></font></td>
                      </tr>
                      <tr>
                        <td width="100"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">0x0d</font></font></td>
                        <td width="80"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">REGREQ</font></font></td>
                        <td width="180"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">注册要求</font></font></td>
                        <td>&nbsp;</td>
                        <td width="100"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">0x1c</font></font></td>
                        <td width="80"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">奎尔奇</font></font></td>
                        <td width="180"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">停止音频/视频传输</font></font></td>
                      </tr>
                      <tr>
                        <td width="100"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">0x0e</font></font></td>
                        <td width="80"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">瑞格斯</font></font></td>
                        <td width="180"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">注册认证</font></font></td>
                        <td>&nbsp;</td>
                        <td width="100"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">0x1d</font></font></td>
                        <td width="80"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">取消询问</font></font></td>
                        <td width="180"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">恢复音频/视频传输</font></font></td>
                      </tr>
                      <tr>
                        <td width="100"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">0x0f</font></font></td>
                        <td width="80"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">雷克</font></font></td>
                        <td width="180"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">注册确认</font></font></td>
                        <td>&nbsp;</td>
                        <td width="100"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">0x20</font></font></td>
                        <td width="80"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">MWI</font></font></td>
                        <td width="180"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">留言等待指示</font></font></td>
                      </tr>
                      <tr>
                        <td width="100">&nbsp;</td>
                        <td width="80">&nbsp;</td>
                        <td width="180">&nbsp;</td>
                        <td>&nbsp;</td>
                        <td width="100"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">0x21</font></font></td>
                        <td width="80"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">不支持</font></font></td>
                        <td width="180"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">不支援的讯息</font></font></td>
                      </tr>
                    </tbody></table>               

</details>

<details>
      <summary><b>IAX与SIP-比较和差异</b></summary>
      IAX由Mark Spencer（也是AsterisK的作者）创建的，旨在改善VoIP中与SIP相关的一些问题，他认为可以解决。

IAX和SIP之间的主要区别如下：

-带宽
IAX使用的带宽小于SIP使用的带宽，因为消息是二进制而不是文本消息（SIP）。IAX还尝试减少消息的标头，从而减少所使用的带宽。

- NAT
信令和数据IAX togheter出行避免NAT的问题，通常出现在SIP。SIP中的信号和数据使用不同的协议传输，这就是NAT问题出现的原因。音频流必须通过路由器和防火墙。SIP通常需要STUN服务器来避免这些问题。

-标准化和使用
SIP是IETF很久以前标准化的协议，已被设备和软件制造商广泛使用。IAX仍在标准化，因此，如今没有太多设备可以使用它

-使用的端口
IAX仅使用一个端口（4569）发送所有呼叫的信令和数据。为此，IAX使用中继系统。IAX通过单个用户数据报协议（UDP）复用信令和多个媒体流。否则，SIP使用一个端口（5060）进行信号传输，并使用2个RTP端口进行每个音频连接（至少3个端口）。例如，如果我们有100个同时呼叫，则应使用200个RTP端口和一个用于信令的端口（5060）。IAX仅为所有端口使用一个端口（4569）

-使用服务器时的音频流如果使用
SIP服务器，则信令消息始终通过服务器，但是音频消息（RTP流）可以不通过服务器而端对端传播。在IAX中，信令和数据必须始终通过IAX服务器。当有多个同时呼叫时，这会增加IAX服务器的带宽需求。-其他功能IAX是为VoIP开发的协议


和视频传输，它具有有趣的功能，例如发送或接收拨号计划的可能性。如果使用Asterisk PBX，这些功能非常有趣。SIP是一种通用的Porpouse协议，不仅可以传输音频或视频，还可以传输任何信息。
</details>
