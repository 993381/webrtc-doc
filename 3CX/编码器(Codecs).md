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