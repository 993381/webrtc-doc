<details>
      <summary><b>编解码器摘要表</b></summary>
      语音传输是类比，而数据网络是数字。通过编码器/解码器（CODEC）进行将模拟波采样为数字信息的过程。将模拟语音信号采样到数字信号有许多标准。这个过程通常很复杂。大多数转换使用脉冲编码调制（PCM）或变化形式

。此外，CODEC压缩数据序列，有时提供回声消除。波形的压缩可以节省带宽。这在低速连接中特别有趣，因此您可以同时拥有更多VoIP连接。节省带宽的另一种方法是使用静默抑制。目的是在对话中没有声音时不发送包裹。

接下来是使用最知名的编解码器的表：

-比特率-通过通信路径传输比特的速率。通常以千比特每秒（Kbps）表示
-采样率-数字化声音时每秒采样的数量。随着每秒采样数的增加，数字复制的质量也会提高。
-帧大小-发送数据包之间的时间
-MOS-（平均意见得分）。它是从1到5的声音质量的主观衡量指标。

为了更好地理解编解码器过程和表中表示的参数，我们建议阅读G.711编解码器过程部分，在这里可以了解其工作原理。 G.711编解码器
<table border="1" class="normal">
                <tbody><tr class="titulomenulateral">
                  <th>Number</th>
                  <th>Standard by </th>
                  <th width="150">Description</th>
                  <th>Bit rate (kb/s)</th>
                  <th>Sampling rate (kHz)</th>
                  <th>Frame size (ms)</th>
                  <th width="150">Remarks
                  </th><th><div align="center">MOS (Mean Opinion Score) </div></th>
                </tr>
                <tr>
                  <td><strong><a href="#g711">G.711 *</a></strong></td>
                  <td>ITU-T</td>
                  <td>Pulse code modulation (PCM)</td>
                  <td align="right">64</td>
                  <td align="right">8</td>
                  <td align="right">Sampling</td>
                  <td> U-law (US, Japan) and A-law (Europe) companding </td>
                  <td><div align="center">4.1 </div></td>
                </tr>
				<tr>
                  <td><strong><a href="new-codecs-g7111-g7291.php">G.711.1 </a></strong></td>
                  <td>ITU-T</td>
                  <td>Pulse code modulation (PCM)</td>
                  <td align="right">80-96 Kbps </td>
                  <td align="right">8</td>
                  <td align="right">Sampling</td>
                  <td> Improvement og G.711 to provide an audio bandwidth of 50 Hz to 7 kHz <a href="new-codecs-g7111-g7291.php">More info</a> </td>
                  <td><div align="center">4.1 </div></td>
                </tr>
                <tr>
                  <td><strong>G.721</strong></td>
                  <td>ITU-T</td>
                  <td>Adaptive differential pulse code modulation (ADPCM)</td>
                  <td align="right">32</td>
                  <td align="right">8</td>
                  <td align="right">Sampling</td>
                  <td> Now described in G.726; obsolete. </td>
                  <td>
                    <div align="center">&nbsp;</div></td>
                </tr>
                <tr>
                  <td><strong>G.722</strong></td>
                  <td>ITU-T</td>
                  <td>7 kHz audio-coding within 64 kbit/s</td>
                  <td align="right">64</td>
                  <td align="right">16</td>
                  <td align="right">Sampling</td>
                  <td> Subband-codec that divides 16 kHz band into two subbands, each coded using ADPCM </td>
                  <td>
                    <div align="center">&nbsp;</div></td>
                </tr>
                <tr>
                  <td><strong>G.722.1</strong></td>
                  <td>ITU-T</td>
                  <td> Coding at 24 and 32 kbit/s for hands-free operation in systems with low frame loss </td>
                  <td align="right">24/32</td>
                  <td align="right">16</td>
                  <td align="right">20</td>
                  <td>&nbsp;</td>
                  <td>
                    <div align="center">&nbsp;</div></td>
                </tr>
				 <tr>
                  <td><strong>G.722.2 AMR-WB</strong></td>
                  <td>ITU-T</td>
                  <td>Adaptive Multi-Rate Wideband Codec (AMR-WB)</td>
                  <td align="right">23.85/ 23.05/ 19.85/ <br>
                  18.25/ 15.85/ 14.25/<br> 
                  12.65/ 8.85/ 6.6</td>
                  <td align="right">16</td>
                  <td align="right">20</td>
                  <td>  is mainly used for speech compression in the 3rd generation mobile telephony. <a href="new-codecs-g7111-g7291.php">More info</a></td>
                  <td>
                    <div align="center">&nbsp;</div></td>
                </tr>
                <tr>
                  <td><strong>G.723</strong></td>
                  <td>ITU-T</td>
                  <td> Extensions of Recommendation G.721 adaptive differential pulse code modulation to 24 and 40 kbit/s for digital circuit multiplication equipment application </td>
                  <td align="right">24/40</td>
                  <td align="right">8</td>
                  <td align="right">Sampling</td>
                  <td> Superceded by G.726; obsolete. This is a completely different codec than G.723.1 </td>
                  <td>
                    <div align="center">&nbsp;</div></td>
                </tr>
                <tr>
                  <td><strong>G.723.1</strong></td>
                  <td>ITU-T</td>
                  <td>Dual rate speech coder for multimedia communications transmitting at 5.3 and 6.3 kbit/s</td>
                  <td align="right">5.6/6.3</td>
                  <td align="right">8</td>
                  <td align="right">30</td>
                  <td> Part of H.324 video conferencing. It encodes speech or other audio signals in frames using linear predictive analysis-by-synthesis coding. The excitation signal for the high rate coder is Multipulse Maximum Likelihood Quantization (MP-MLQ) and for the low rate coder is Algebraic-Code-Excited Linear-Prediction (ACELP). </td>
                  <td>
                    <div align="center">3.8-3.9</div></td>
                </tr>
                <tr>
                  <td><strong>G.726</strong></td>
                  <td>ITU-T</td>
                  <td>40, 32, 24, 16 kbit/s adaptive differential pulse code modulation (ADPCM)</td>
                  <td align="right">16/24/32/40</td>
                  <td align="right">8</td>
                  <td align="right">Sampling</td>
                  <td> ADPCM; replaces G.721 and G.723. </td>
                  <td>
                    <div align="center">3.85</div></td>
                </tr>
                <tr>
                  <td><strong>G.727</strong></td>
                  <td>ITU-T</td>
                  <td>5-, 4-, 3- and 2-bit/sample embedded adaptive differential pulse code modulation (ADPCM)</td>
                  <td align="right">var.</td>
                  <td align="right">&nbsp;</td>
                  <td align="right">Sampling</td>
                  <td> ADPCM. Related to G.726 </td>
                  <td>
                    <div align="center">&nbsp;</div></td>
                </tr>
                <tr>
                  <td><strong>G.728</strong></td>
                  <td>ITU-T</td>
                  <td>Coding of speech at 16 kbit/s using low-delay code excited linear prediction</td>
                  <td align="right">16</td>
                  <td align="right">8</td>
                  <td align="right">2.5</td>
                  <td>CELP.</td>
                  <td>
                    <div align="center">3.61</div></td>
                </tr>
                <tr>
                  <td><strong><a href="#g729">G.729 **</a></strong></td>
                  <td>ITU-T</td>
                  <td>Coding of speech at 8 kbit/s using conjugate-structure algebraic-code-excited linear-prediction (CS-ACELP)</td>
                  <td align="right">8</td>
                  <td align="right">8</td>
                  <td align="right">10</td>
                  <td>Low delay (15 ms)</td>
                  <td>
                    <div align="center">3.92</div></td>
                </tr>
				   <tr>
                  <td><strong><a href="new-codecs-g7111-g7291.php">G.729.1</a></strong></td>
                  <td>ITU-T</td>
                  <td>Coding of speech at 8 kbit/s using conjugate-structure algebraic-code-excited linear-prediction (CS-ACELP)</td>
                  <td align="right">8/12/14/16/<br>
                    18/20/22/24/<br>
                    26/28/30/32</td>
                  <td align="right">8</td>
                  <td align="right">10</td>
                  <td>Improvement og G.711 to provide an audio bandwidth of 50 Hz to 7 kHz <a href="new-codecs-g7111-g7291.php">More info</a> </td>
                  <td>
                    <div align="center"></div></td>
                </tr>
                <tr>
                  <td><strong>GSM 06.10 </strong></td>
                  <td>ETSI</td>
                  <td>Regular­Pulse Excitation Long­Term Predictor (RPE-LTP)</td>
                  <td align="right">13</td>
                  <td align="right">8</td>
                  <td align="right">22.5
                  </td><td>Used for GSM cellular telephony.</td>
                  <td>
                    <div align="center">&nbsp;</div></td>
                </tr>
                <tr>
                  <td><strong>LPC10</strong></td>
                  <td> USA Government </td>
                  <td>Linear-predictive codec</td>
                  <td align="right">2.4</td>
                  <td align="right">8</td>
                  <td align="right">22.5</td>
                  <td> 10 coefficients. </td>
                  <td>
                    <div align="center">&nbsp;</div></td>
                </tr>
                <tr>
                  <td><strong>Speex</strong></td>
                  <td>&nbsp;</td>
                  <td>&nbsp;</td>
                  <td align="right"> 8, 16, 32</td>
                  <td align="right"> 2.15-24.6 (NB) <br>
      4-44.2 (WB)</td>
                  <td align="right"> 30 ( NB ) <br>
      34 ( WB )</td>
                  <td>&nbsp;</td>
                  <td>
                    <div align="center">&nbsp;</div></td>
                </tr>
                <tr>
                  <td><strong>iLBC</strong></td>
                  <td>&nbsp;</td>
                  <td>&nbsp;</td>
                  <td align="right">8</td>
                  <td align="right">13.3</td>
                  <td align="right">30</td>
                  <td>&nbsp;</td>
                  <td>
                    <div align="center">&nbsp;</div></td>
                </tr>
                <tr>
                  <td><strong>DoD CELP</strong></td>
                  <td> American Department of Defense (DoD) USA Government </td>
                  <td>&nbsp;</td>
                  <td align="right">4.8</td>
                  <td align="right">&nbsp;</td>
                  <td align="right">30</td>
                  <td>&nbsp;</td>
                  <td>
                    <div align="center">&nbsp;</div></td>
                </tr>
  <tr><td><strong>EVRC</strong></td>
      <td> 3GPP2 </td>
      <td> Enhanced Variable Rate CODEC </td>
      <td align="right">9.6/4.8/1.2</td>
      <td align="right">8</td>
      <td align="right">20</td>
      <td>Se usa en redes CDMA </td>
      <td>
        <div align="center">&nbsp;</div></td>
  </tr>
  <tr>
    <td><strong>DVI</strong></td>
    <td> Interactive Multimedia Association (IMA) </td>
    <td>DVI4 uses an adaptive delta pulse code modulation (ADPCM) </td>
    <td align="right">32</td>
    <td align="right">Variable</td>
    <td align="right">Sampling</td>
    <td>&nbsp; </td>
    <td>
      <div align="center">&nbsp;</div></td>
  </tr>
 
  <tr>
    <td><strong>L16</strong></td>
    <td>&nbsp; </td>
    <td> Uncompressed audio data samples </td>
    <td align="right">128</td>
    <td align="right">Variable</td>
    <td align="right">Sampling</td>
    <td>&nbsp; </td>
	</tr>
	 <tr>
                  <td><strong>SILK</strong></td>
                  <td>Skype</td>
                  <td>&nbsp; </td>
                  <td align="right"> From 6 to 40 </td>
                  <td align="right">Variable</td>
                  <td align="right">20</td>
                  <td>Harmony codec is related with SILK </td>
                  <td>
                    <div align="center">&nbsp;</div></td>
                </tr>
    <tr><td>
      <div align="center">&nbsp;</div></td>
              </tr></tbody></table>

 * G711有两个版本，分别称为U-law（美国，日本）和A-law（欧洲）。U-law与北美和日本使用的T1标准有关。A-law与世界其他地方使用的E1标准相关。区别在于对模拟信号进行采样的方法。在这两种方案中，信号不是线性采样而是以对数方式采样。有关差异的更多信息，请访问G.711 A Law与u Law。

* 有许多有趣的解释g729编解码器的版本，因为该编解码器在当今非常流行。
G729：原始编解码器
G729A或附件：它是G729的简化版本，并且与G729兼容。他不太复杂，但素质较低。
G729B或B附件：具有静音抑制功能且与先前版本不兼容的G729
G729AB：具有静音抑制功能且仅与G729B兼容的g729A。
此外，每个G729版本都具有8Kbps的比特率，但也有6.4 kbps（D附件）和11.4 Kbps（E附件）的版本。

</details>

<details>
      <summary><b>G.711 codec process(G.711编解码器过程)</b></summary>
语音和音频信号是模拟信号，而数据网络是数字信号。由模数转换器（ADC）将模拟信号转换为数字信号。

模数转换器或脉冲编码调制（PCM）的过程分为三个步骤：

-采样
-量化
-编码（编码）

在量化过程中，可以使用语音压缩，因为将在此进行解释。章节：

## 采样

采样是通过以精确间隔的时间间隔读取（采样）其电平来以数字形式对模拟信号进行编码的过程。所获得的值称为样本。

下图显示了此过程：<br/>
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200821104639267.png#pic_center)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200821104615842.png#pic_center)

采样通常以相等的间隔进行；该间隔称为采样间隔。采样间隔的倒数称为采样频率或采样率。采样率单位为Hz
采样定理给出了必须遵循采样频率的条件。“它指出，在特定的截止频率之上没有频率成分的频带受限信号由其在相等间隔点处的离散值唯一确定。以等于或大于截止频率两倍的采样率”

与采样定理一致，电话音频信号（频率在300 Hz至3400 Hz之间）应以等于或大于6800 Hz的频率采样（2 xs 3400）。

实际上，我们通常采用8000赫兹的采样频率或采样率。因此，每秒获取8000个样本，这些样本对应于相等的间隔：

T = 1/8000 = 0.000125秒。= 125微秒

因此，同一信号的两个连续采样间隔为125 µs，这称为采样间隔。

## 量化
量化是将获得的样本的高度转换为有限数量的离散值的过程。有几种量化方法，我们将根据其复杂性进行解释。

均匀量化

有必要使用有限数量的离散值来近似表示样本的幅度。样本可以采用的所有幅度范围均以相等数量的间隔划分。所有幅度落在一个间隔内的样本取相同的值。

量化过程必然会引入误差，因为样本的实际幅度被近似值所替代。该误差称为量化噪声。

可以通过增加量化间隔的数量来减少量化噪声，但是实际的限制迫使间隔数量不能超过某个值。

所有间隔都具有相同宽度的这种类型的量化称为均匀量化。

下图显示了模拟信号量化的效果。量化间隔的数量为八个。

原始信号是连续线。
在远程终端中重建的样本由点表示
。重建的信号是间歇线。

每个样本的量化噪声会在重构信号中产生变形或失真。在此通过间歇和点线显示。<br/>

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200821104749718.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzI4ODgwMDg3,size_16,color_FFFFFF,t_70#pic_center)

非均匀量化
在均匀量化中，失真或噪声不取决于样本幅度。因此，当幅度较低时，误差或量化噪声的影响较大。对于其模拟幅度接近量化间隔之一的信号，情况至关重要。

为了解决这个问题，有两种解决方案：

-增加量化间隔-如果间隔更大，则误差或噪声会更少，但是我们需要更多的二进制数来量化样本，因此最终需要更多的带宽来传输它。

-通过不均匀的量化。使用了有限数量的间隔。每个宽度都不相同。因此，它们不是统一的。低电平的间隔宽度短于高电平的间隔宽。这样，就像微弱的信号具有大量的量化级别一样，减少了失真或噪声。另一方面，强信号比对应于统一量化的信号具有更差的失真或噪声行为，但仍然足够好。

因此，我们可以做的是通过编解码器（压缩器/解压缩器）使用非均匀量化，然后使用统一量化，如下图所示：</br>
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200821104842868.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzI4ODgwMDg3,size_16,color_FFFFFF,t_70#pic_center)

### 编码律
不统一的量化过程遵循称为编码律的某些特征。

编码律有两种类型：连续和分段。

在连续编码定律中，量化间隔具有不同的宽度，从对应于低电平信号的较小值增大到对应于高电平信号的较大值。

在分段编码法则中，操作范围分为有限数量的组。同一组的每个间隔具有相同的宽度，与其他组不同。

通常，使用的编码规则是分段的。

G.711 A律（a律）和µ律（u律）编码方案

当今使用的两种主要编码律是A律（a律）和µ律（u律），也称为g .711编解码器。Law（a-law）主要用于欧洲PCM系统中，µ law（u-law）用于美国PCM系统中。

A定律由13个直线段组成（实际上，它们是16个段，但是三个中心段是对齐的，因此将它们减少到13个）

。A定律的数学公式为：

y = Ax / 1+ LA- --------------------对于0 = <x = <1 / A
y = 1+ L（Ax）/ 1+ LA -------- -----对于1 / A = <x = <1

是L尼泊尔对数。

参数A取值为87.6。x和y代表压缩器的输入和输出信号

µ律的数学公式为：

y = L（1 + µx）/ L（1 + µ）------------- -对于0 = <x = <1

，其中µ = 255

下图以图形形式表示A律（a律）：

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200821104956688.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzI4ODgwMDg3,size_16,color_FFFFFF,t_70#pic_center)

差分量化（Differential PCM）

在听觉声音信号中，LF（低频）通常更为常见。因此，两个连续样本的水平通常相差很小。利用这种情况，已经创建

了差分量化。在差分量化中，不是单独处理每个样本，而是对样本和上一个样本之间的差异进行量化和编码。由于量化两个连续样本之间的差异所需的量化间隔的数量少于量化一个隔离样本所需的量化间隔的数量，因此，差分量化可降低传输频率，因为这与量化间隔成比例。

增量差分量化和ADPCM（自适应增量PCM）

如果我们在差分量化中增加采样频率，则两个连续的样本的电平几乎没有差异。因此，可以使用单个量化间隔来量化差异。

使用这种方法，只需要逐个采样，传输速度（比特率）将等于采样速度。这种类型的量化称为增量量化。

在这种增量量化中，输出变化的水平是唯一的。在其他类型的增量量化中，变化不是固定的，而是取决于输入信号的变化。例如，ADPCM或适应性增量PCM基于动态地适应量化范围，具体取决于输入信号的微小差异或巨大差异。

## 编纂-编解码
编码是一个过程，通过该过程，量化的样本将由带有“ 1”和“ 0”的二进制数表示。

通常在电话中，使用256个量化间隔来表示所有可能的采样值（例如，对于G.711或A律和µ律）。因此，需要8位代表所有间隔（2 8 = 256）。其他使用ADPCM或增量量化的编解码器使用较少的时间间隔，因此需要较少的位来对样本进行编码。

进行量化和编码的设备称为编码器。

解码是从数字信号重构样本的过程。此过程在称为解码器的设备中进行。

同一设备中的编码器和解码器的组称为编解码器。

重要提示：如果要计算编解码器的比特率，我们只需要将样本中表示的采样率乘以秒或Herzios乘以量化每个样本所需的比特，就可以得到编解码器的比特率。

无论如何，由于复杂的编解码器具有压缩功能，因此无法始终以此方式推导出比特率

## G 711.1
G.711.1语音编解码器是ITU-T在2008年标准化的。如果您需要有关此编解码器的信息，则可以访问G.711.1


</details>

<details>
      <summary><b>G711.1-G729.1-G722.1-G722.1</b></summary>
在过去的几年中，它出现了新的编解码器版本

G711 ，G729或G722经典编解码器G 711.1

新的G.711.1编解码器已于ITU-T于2008年3月批准。

新的G.711.1编解码器是建立在顶部的嵌入式宽带编解码器。窄带G.711编解码器。其目的是
轻松与旧版G.711基础架构进行互操作。它提供了两个扩展层。第一个扩展
提高了低频（包括50-300 Hz频段）中的G.711的质量，该频段通常不
随G.711一起发送。第二扩展使用不同的扩展
层对高达7 kHz的高频进行编码。

根据使用一或两个扩展层，G.711.1的双码率需要80或96 Kbps。
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200821105406164.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzI4ODgwMDg3,size_16,color_FFFFFF,t_70#pic_center)
G.711.1编解码器仅具有5 ms的低延迟。

该编解码器旨在在宽带网络上实现高质量的语音服务，尤其是IP电话和多点语音会议。

## G.729.1

G.729.1编解码器也是基于G.729窄带版本构建的嵌入式宽带编解码器。G.729.1
也是“可伸缩的”，因为彼此之间添加了许多扩展层。第一扩展
层以12 Kbps提供增强的窄带质量。从那里开始，每层2 Kbps的额外层将增加
宽带能力，并提高质量，最高速率可达32 Kbps。以此速度，据说G.729.1
提供了可接受的音乐质量。与G.711.1的情况一样，G.729.1的嵌入式和可伸缩特性
在质量和所需的比特率之间付出了代价，并且G.729.1的性能不如其他宽带
编解码器，例如G.722.2（ AMR-WB）

该编解码器的主要用途是：VoIP（IP电话），包括IP电话，其他VoIP手机，软件电话，IP PBX；媒体服务器/网关；呼叫中心设备；录音设备；测验设备; 适用于企业公司网络或大众市场的音频/视频会议（例如通过xDSL或无线接入的PSTN仿真）；语音邮件服务器。

也称为G729J或G729EV。

## G.722.1或SIREN 7

G.722.1或SIREN 7描述了一种数字宽带编码器算法，该算法提供50 Hz至7 kHz的音频带宽，以24 kbps或32 kbps的比特率运行。G.722.1对于低帧丢失的高清VoIP系统中的免提操作很有用。

它也存在G.722.1 Annex C或SIREN 14，它以24、32，y 48 kbit / s的bir速率提供高达14 Khz的音频损坏。

## G.722.2 o AMR-WB（“自适应多速率宽带”）

自适应多速率宽带编解码器（AMR-WB）是第三代合作伙伴计划（3GPP）引入的语音编码器标准，该AMR-WB编解码器已由ITU-T标准机构批准，并称为G。 722.2。该语音编码器主要用于第三代移动电话中的语音压缩。

该编解码器具有9个基本比特率，分别为23.85、23.05、19.85、18.25、15.85、14.25、12.65、8.85和6.6 kbit / s。该编解码器基于所有比特率的代数编码线性预测（ACELP）原理工作。为了降低平均比特率，此编解码器使用语音活动检测（VAD）和舒适噪声生成（CNG）算法来支持不连续传输（DTX）。

编码器的帧大小为20毫秒，编码器的算法延迟为25毫秒。



</details>
