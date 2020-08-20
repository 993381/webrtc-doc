H.323是两者中比较成熟的一种，但是由于缺乏灵活性，可能会出现问题。SIP当前定义不多，但是具有更大的可扩展性，可以简化Internet应用程序的集成。最终哪种协议会胜出？现在说还为时过早，但是我们的公正分析将帮助您确定哪种协议最适合您的应用程序。

<table width="100%" border="1" cellpadding="7" cellspacing="0" class="normal">
            <tbody><tr class="titulo_post_peq">
              <td align="right" height="22">&nbsp;</td>
              <td align="center" height="22"> <b>H.323</b> </td>
              <td align="center" height="22"> <b>SIP</b> </td>
            </tr>
            <tr>
              <td height="80" align="left" valign="top" bgcolor="#F0F1F7" class="texton"><div align="left" class="sinenlacea">Architecture</div></td>
              <td align="left" valign="top" height="80" bgcolor="#F0F1F7"> H.323 covers almost every service, such as capability exchange, conference control, basic signaling,QoS, registration, service discovery, and so on. </td>
              <td align="left" valign="top" height="80" bgcolor="#F0F1F7"> SIP is modular because it covers basic call signaling, user location, and registration.&nbsp; Other features are in other separate orthogonal protocols </td>
            </tr>
            <tr>
              <td height="48" rowspan="2" valign="top" class="textoca">
                <div align="left">Components </div></td>
              <td valign="top" align="center" height="16"> Terminal/Gateway </td>
              <td valign="top" align="center" height="16"> UA</td>
            </tr>
            <tr>
              <td valign="top" align="center" height="16"> Gatekeeper </td>
              <td valign="top" align="center" height="16"> Servers</td>
            </tr>
            <tr>
              <td height="44" rowspan="2" align="right" valign="top" class="textoca">
                <div align="left">Protocols </div></td>
              <td valign="top" align="center" height="14"> RAS/Q.931 </td>
              <td valign="top" align="center" height="14"> SI</td>
            </tr>
            <tr>
              <td valign="top" align="center" height="14"> H.245 </td>
              <td valign="top" align="center" height="14"> SDP</td>
            </tr>
            <tr>
              <td height="16" colspan="3" align="left" bgcolor="#F0F1F7" class="sinenlacea"> <strong>Call control Functionality</strong> </td>
            </tr>
            <tr>
              <td height="16" align="right" class="textoca"><div align="left">Call Transfer</div></td>
              <td align="center" height="16">Yes</td>
              <td align="center" height="16">Yes</td>
            </tr>
            <tr>
              <td height="16" align="right" class="textoca"><div align="left">Call Forwarding</div></td>
              <td align="center" height="16">Yes</td>
              <td align="center" height="16">Yes</td>
            </tr>
            <tr>
              <td height="16" align="right" class="textoca"><div align="left"> Call Holding</div></td>
              <td align="center" height="16">Yes</td>
              <td align="center" height="16">Yes</td>
            </tr>
            <tr>
              <td height="32" align="right" class="textoca"><div align="left">Call Parking/Pickup</div></td>
              <td align="center" height="32">Yes</td>
              <td align="center" height="32">Yes</td>
            </tr>
            <tr>
              <td height="16" align="right" class="textoca"><div align="left">Call Waiting</div></td>
              <td align="center" height="16">Yes</td>
              <td align="center" height="16">Yes</td>
            </tr>
            <tr>
              <td height="32" align="right" class="textoca"><div align="left">Message Waiting Indication</div></td>
              <td align="center" height="32">Yes</td>
              <td align="center" height="32">No</td>
            </tr>
            <tr>
              <td height="32" align="right" class="textoca"><div align="left">Name Identification</div></td>
              <td align="center" height="32">Yes</td>
              <td align="center" height="32">No</td>
            </tr>
            <tr>
              <td height="48" align="right" class="textoca"><div align="left">Call Completion on Busy Subscriber</div></td>
              <td align="center" height="48">Yes</td>
              <td align="center" height="48">Yes</td>
            </tr>
            <tr>
              <td height="16" align="right" class="textoca"><div align="left">Call Offer</div></td>
              <td align="center" height="16">Yes</td>
              <td align="center" height="16">No</td>
            </tr>
            <tr>
              <td height="16" align="right" class="textoca"><div align="left">Call Intrusion</div></td>
              <td align="center" height="16">Yes</td>
              <td align="center" height="16">No</td>
            </tr>
            <tr>
              <td height="32" align="right" valign="top" class="textoca">&nbsp;&nbsp;
                  <div align="left"></div></td>
              <td align="left" valign="top" height="32"> H.323 splits them across H.450, RAS, H.245 and Q.931 </td>
              <td align="left" valign="top" height="32">&nbsp;</td>
            </tr>
            <tr>
              <td width="582" align="right" valign="top" height="16" colspan="3" bgcolor="#F0F1F7">
                <div align="left" class="enlacen"><b>Advanced features</b> </div></td>
            </tr>
            <tr>
              <td height="32" align="right" valign="top" class="textoca"><div align="left">Multicast Yesgnaling</div></td>
              <td valign="top" height="32"> Yes, location requests (LRQ) and auto gatekeeper discovery (GRQ). </td>
              <td valign="top" height="32"> Yes, e.g., through group INVITEs. </td>
            </tr>
            <tr>
              <td height="64" align="right" valign="top" class="textoca"><div align="left">Third-party Call Contro</div></td>
              <td valign="top" height="64"> Yes, through third-party pause and re-routing which is defined within H.323. More sophisticated control is defined by the related H.450.x series of standards. .</td>
              <td valign="top" height="64"> Yes, through SIP as described in separate Internet Drafts. </td>
            </tr>
            <tr>
              <td height="16" align="right" valign="top" class="textoca"><div align="left">Conference</div></td>
              <td align="center" valign="top" height="16">Yes</td>
              <td align="center" valign="top" height="16">Yes</td>
            </tr>
            <tr>
              <td height="3" align="right" valign="top" class="textoca">
                <div align="left">Click for Dial</div></td>
              <td align="center" valign="top" height="3"> Yes</td>
              <td align="center" valign="top" height="3"> Yes</td>
            </tr>
            <tr>
              <td align="right" valign="top" height="3" colspan="3" bgcolor="#F0F1F7">
                <div align="left"><b class="enlacen">Scalability</b></div></td>
            </tr>
            <tr>
              <td height="3" align="right" valign="top" class="textoca">
                <div align="left">Large Number of Domains</div></td>
              <td align="left" valign="top" height="3"> The initial intent of H.323 was for the support of LANs, so it was not inherently designed for wide area addressing. The concept of a zone was added to accommodate wide area addressing.&nbsp; Procedures are defined for �user location� across zones for email names. Annex G defines communication between administrative domains, describing methods to allow for address resolution, access authorization and usage reporting between administrative domains. In multi-domain searches, there is no easy way to perform loop detection. Performing the loop detection can be done (using the PathValue field), but introduces other issues related to scalability. </td>
              <td align="left" valign="top" height="3"> SIP inherently supports wide area addressing. When multiple servers are involved in setting up a call, SIP uses a loop detection algorithm similar to the one used in BGP, which can be done in a stateless manner, thus avoiding scalability issues. The SIP Registrar and redirect servers were designed to support user location.</td>
            </tr>
            <tr>
              <td height="3" align="right" valign="top" class="textoca"><div align="left">Large Number of Calls</div></td>
              <td align="left" valign="top" height="3"> H.323 call control can be implemented in a stateless manner.&nbsp; A gateway can use messages defined in H.225 to assist the gatekeeper in performing load balancing across gateways. </td>
              <td align="left" valign="top" height="3"> Call control can be implemented in a call stateless manner. SIP supports n to n scaling between UAs and servers. SIP takes less CPU cycles to generate signaling messages; therefore a server could theoretically handle more transactions. SIP has specified a method of load balancing based upon the DNS SRV record translation mechanisms.</td>
            </tr>
            <tr>
              <td height="2" align="right" valign="top" class="textoca">
                <div align="left">Connection state </div></td>
              <td align="left" valign="top" height="2"> Stateful or Stateless </td>
              <td align="left" valign="top" height="2">
                <p align="left">Stateful or Stateless. &nbsp; A SIP call is independent of the existence of a transport-layer connection, but instead signals call termination explicitly. </p></td>
            </tr>
            <tr>
              <td height="2" align="right" valign="top" class="textoca">
                <div align="left">Internationalization</div></td>
              <td align="center" valign="top" height="2">
                <p align="left">Yes, H.323 uses Unicode (BMPString within ASN.1) for some textual information (h323-id), but generally has few textual parameters. </p></td>
              <td align="center" valign="top" height="2">
                <p align="left">Yes, SIP uses Unicode (ISO 10646-1), encoded as UTF-8, for all text strings, affording full character set neutrality for names, messages and parameters. SIP provides for the indication of languages and language preferences. </p></td>
            </tr>
            <tr>
              <td height="193" align="left" valign="top" bgcolor="#F0F1F7" class="enlacen"> <b>Security</b> </td>
              <td align="left" valign="top" height="193" bgcolor="#F0F1F7"> Defines security mechanisms and negotiation facilities via H.235 , can also use SSL for transport-layer security. </td>
              <td align="left" height="193" bgcolor="#F0F1F7"> SIP supports caller and callee authentication via HTTP mechanisms. Cryptographically secure authentication and encryption is supported hop-by-hop via SSL/TSL, but SIP could use any transport-layer or HTTP-like security mechanism, such as SSH or S-HTTP. Keys for media encryption are conveyed using SDP. SSL supports symmetric and asymmetric authentication. SIP also defines end-to-end authentication and encryption using either PGP or S/MIME.&nbsp; </td>
            </tr>
            <tr>
              <td height="128" align="left" valign="top" class="enlacen"> <b><strong>Interoperab<strong>ility among Versions </strong> </strong> </b> </td>
              <td align="left" valign="top" height="128"> The fully backward compatibility in H.323 enables all implementations based on different H.323 versions to be seamlessly integrated. </td>
              <td align="left" valign="top" height="128"> In SIP, a newer version may discard some old features that are not expected to be implemented any more. This approach saves code size and reduces protocol complexity, but loses some compatibility between different versions. </td>
            </tr>
            <tr>
              <td height="64" align="left" valign="top" bgcolor="#F0F1F7" class="enlacen"> <b><strong>Implementation Interoperability </strong></b></td>
              <td align="left" valign="top" height="64" bgcolor="#F0F1F7"> H.323 provides an implementers' guide, which clarifies the standard and helps towards interoperability among different implementations. </td>
              <td align="left" valign="top" height="64" bgcolor="#F0F1F7"> SIP thus far has not provided an implementation agreement.</td>
            </tr>
            <tr>
              <td height="128" align="left" valign="top" class="enlacen"> <b>Billing</b> </td>
              <td valign="top" height="128"> Even with H.323's direct call model, the ability to successfully bill for the call is not lost because the endpoint reports to the gatekeeper the beginning and end time of the call via the RAS protocol. </td>
              <td valign="top" height="128"> If the SIP proxy wants to collect billing information, it has no choice but to stay in the call signaling path for the entire duration of the call so that it can detect when the call completes. Even then, the statistics are skewed because the call signaling may have been delayed. </td>
            </tr>
            <tr>
              <td height="224" align="left" valign="top" bgcolor="#F0F1F7" class="enlacen"> <b>Codecs</b> </td>
              <td valign="top" height="224" bgcolor="#FAFAFF"> H.323 supports any codec, standardized or proprietary, not just ITU-T codecs. There have been codepoints for MPEG and GSM, which are not ITU-T codecs, in H.323 for a long time; many vendors support proprietary codecs through ASN.1 NonStandardParameters, which is equivalent to SIP's "privately-named codec by mutual agreement"; and any codec can be signaled via the GenericCapability feature that was added in H.323v3. Payload types can be specified statically or dynamically. </td>
              <td valign="top" height="224" bgcolor="#FAFAFF"> SIP supports any IANA-registered codec (as a legacy feature) or other codec whose name is mutually agreed upon. Payload types can be specified statically or dynamically </td>
            </tr>
            <tr>
              <td height="64" align="left" valign="top" class="enlacen"> <b>Call Forking</b></td>
              <td valign="top" height="64"> H.323 gatekeeper can control the call signaling and may fork the call to any number of devices simultaneously. </td>
              <td valign="top" height="64"> SIP proxies can control the call signaling and may fork the call to any number of devices simultaneously. </td>
            </tr>
            <tr>
              <td width="119" height="48" align="left" valign="top" bgcolor="#F0F1F7" class="enlacen"> <b>Transport <b>Protocol</b></b></td>
              <td valign="top" height="48" bgcolor="#F0F1F7"> Reliable or unreliable , e.g., TCP or UDP. Most H.323 entities use a reliable transport for signaling. </td>
              <td valign="top" height="48" bgcolor="#F0F1F7"> Reliable or unreliable , e.g., TCP or UDP. Most SIP entities use an unreliable transport for signaling. </td>
            </tr>
            <tr>
              <td height="1" align="left" valign="top" class="enlacen"> <b>Message Encoding</b></td>
              <td valign="top" height="1"> H.323 encodes messages in a compact binary format that is suitable for narrowband and broadband connections.
              </td><td valign="top" height="1"> SIP messages are encoded in ASCII text format, suitable for humans to read.&nbsp; </td>
            </tr>
            <tr>
              <td height="32" align="left" valign="top" bgcolor="#F0F1F7" class="enlacen"> <b>Addressing</b> </td>
              <td valign="top" height="32" bgcolor="#F0F1F7"> Flexible addressing mechanisms, including URLs and E.164 numbers.
              </td><td valign="top" height="32" bgcolor="#F0F1F7"> SIP only understands URL-style addresses. </td>
            </tr>
            <tr>
              <td width="119" height="160" align="left" valign="top" class="enlacen"> <b>PSTN Interworking</b></td>
              <td valign="top" height="160"> H.323 borrows from traditional PSTN protocols, e.g., Q.931, and is therefore well suited for PSTN integration. However, H.323 does not employ the PSTN's circuit-switched technology--like SIP, H.323 is completely packet-switched. How Media Gateway Controllers fit into the overall H.323 architecture is well-defined within the standard. </td>
              <td valign="top" height="160"> SIP has no commonality with the PSTN and such signaling must be "shoe-horned" into SIP. SIP has no architecture that describes the decomposition of the gateway into the Media Gateway Controller and the Media Gateways. </td>
            </tr>
            <tr>
              <td width="119" height="128" align="left" valign="top" bgcolor="#F0F1F7" class="enlacen"> <b>Loop Detection</b></td>
              <td valign="top" bgcolor="#F0F1F7"> Yes, routing gatekeepers can detect loops by looking at the CallIdentifier and destinationAddress fields in call-processing messages. If the combination of these matches an existing call, it is a loop. </td>
              <td valign="top" height="128" bgcolor="#F0F1F7"> Yes, the SIP message Via header facilitates this. However, there has been talk about deprecating Via as a means of loop detection due to its complexity. Instead, the Max-Forwards header seems to be the prefered method of limiting hops and therefore loops.
            </td></tr>
            <tr>
              <td height="32" align="left" valign="top" class="enlacen"> <b>Minimum Ports for VoIP Call</b></td>
              <td valign="top" height="32"> 5 (Call signaling, 2 RTP, and 2 RTCP.)</td>
              <td valign="top" height="32"> 5 (Call signaling, 2 RTP, and 2 RTCP.)</td>
            </tr>
            <tr>
              <td width="119" height="112" align="left" valign="top" bgcolor="#F0F1F7" class="enlacen"> <b>Video and Data Conferencing</b></td>
              <td valign="top" height="112" bgcolor="#F0F1F7"> H.323 fully supports video and data conferencing. Procedures are in place to provide control for the conference as well as lip synchronization of audio and video streams. </td>
              <td valign="top" height="112" bgcolor="#F0F1F7"> SIP has limited support for video and no support for data conferencing protocols like T.120. SIP has no protocol to control the conference and there is no mechanism within SIP for lip synchronization. </td>
            </tr>
          </tbody></table>