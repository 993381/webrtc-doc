## Jibr配置修改和Http接口
[论坛相关连接](https://community.jitsi.org/t/jibri-configuration-changes-incoming-interested-in-feedback/71895)

[使用第三方库](https://github.com/lightbend/config/blob/master/HOCON.md)

[第三方库](https://github.com/jitsi/jitsi-metaconfig)

[相关PR1](https://github.com/jitsi/jibri/pull/324)
[相关PR2](https://github.com/jitsi/jibri/pull/315)

[相关issue](https://github.com/jitsi/jibri/issues/325)

[docker多个jibri自动伸缩解决方案]:https://community.jitsi.org/t/multiple-jibri-servers-on-one-machine/27845/27

/usr/share/jitsi-videobridge/jvb.sh --host=$${JVB_HOST:-localhost} --domain=${JVB_HOSTNAME} --port=${JVB_PORT} --secret=${JVB_SECRET} ${JVB_OPTS} < /dev/null >> ${LOGFILE} 2>&1"

-Dnet.java.sip.communicator.SC_HOME_DIR_LOCATION=/etc/jitsi -Dnet.java.sip.communicator.SC_HOME_DIR_NAME=videobridge -Dnet.java.sip.communicator.SC_LOG_DIR_LOCATION=/var/log/jitsi -Djava.util.logging.config.file=/etc/jitsi/videobridge/logging.properties"

nohup ./jvb.sh --host=localhost --domain=meet.rtctest.7moor.com --port=5347 --secret=password1 "--apis=xmpp,rest" > ~/jvb.log 2>&1 & echo $! > /var/run/jitsi-videobridge.pid

nohup ./jicofo.sh --host=localhost --domain=meet.rtctest.7moor.com --secret=password2 --user_domain=auth.meet.rtctest.7moor.com --user_name=focus --user_password=password3 > ~/jicofo.log 2>&1 &

DAEMON_OPTS=" --host=$JICOFO_HOST --domain=$JICOFO_HOSTNAME --port=$JICOFO_PORT --secret=$JICOFO_SECRET --user_name=$JICOFO_AUTH_USER --user_domain=$JICOFO_AUTH_DOMAIN --user_password=$JICOFO_AUTH_PASSWORD $JICOFO_OPTS"

        --exec /bin/bash -- -c "cd $DAEMON_DIR; JAVA_SYS_PROPS=\"$JAVA_SYS_PROPS\" exec $DAEMON $DAEMON_OPTS < /dev/null >> $LOGFILE 2>&1"

nohup ./jvb.sh --host=localhost --domain=jitsi.webrtcsample.ink --port=5347 --secret=top1secret "--apis=xmpp,rest" > ~/jvb.log 2>&1 & echo $! > /var/run/jitsi-videobridge.pid

nohup ./jicofo.sh --host=localhost --domain=jitsi.webrtcsample.ink  --secret=top2secret --user_domain=auth.jitsi.webrtcsample.ink --user_name=focus --user_password=top3secret "" > ~/jicofo.log 2>&1 &


cp: cannot stat 'node_modules/lib-jitsi-meet//lib-jitsi-meet.min.js': No such file or directory
cp: cannot stat 'node_modules/lib-jitsi-meet//lib-jitsi-meet.min.map': No such file or directory
Makefile:57: recipe for target 'deploy-lib-jitsi-meet' failed

top1secret

prosodyctl cert generate jitsi.webrtcsample.ink
prosodyctl cert generate auth.jitsi.webrtcsample.ink

prosodyctl register focus auth.jitsi.webrtcsample.ink top3secret


prosodyctl register jvb auth.meet.rtctest.7moor.com password1

prosodyctl register focus auth.meet.rtctest.7moor.com password3

prosodyctl register focus auth.jitsi.example.com password3

prosodyctl cert generate auth.meet.rtctest.7moor.com

java -Xmx3072m -XX:+UseConcMarkSweepGC -XX:+HeapDumpOnOutOfMemoryError -XX:HeapDumpPath=/tmp -Djdk.tls.ephemeralDHKeySize=2048 -Djava.util.logging.config.file=/usr/share/jitsi-videobridge/lib/logging.properties -cp /usr/share/jitsi-videobridge/jitsi-videobridge.jar:/usr/share/jitsi-videobridge/lib/* org.jitsi.videobridge.Main --host=localhost --domain=meet.rtctest.7moor.com --port=5347 --secret=password1 --apis=xmpp


./jicofo.sh --host=34.92.92.116 --domain=jitsi.webrtcsample.ink --port=5347 --secret=top2secret --user_name=focus --user_domain=auth.jitsi.webrtcsample.ink --user_password=top3secret --apis=xmpp

./jicofo.sh --host=localhost --domain=jitsi.example.com --secret=YOURSECRET2 --user_domain=auth.jitsi.example.com --user_name=focus --user_password=YOURSECRET3 --apis=xmpp

13:46 2:10
13:15 

720p每秒15帧
一分钟16M


// 日志出现的错误  

2020-08-12T06:48:51.164Z [conference.js] <ee._onConferenceFailed>:  CONFERENCE FAILED: conference.iceFailed

2020-08-12T06:46:39.779Z [JitsiMeetJS.js] <Object.getGlobalOnErrorHandler>:  UnhandledError: null Script: null Line: null Column: null StackTrace:  Error: Strophe: request id 196.1 error 0 happened
    at Object.r.Strophe.log (lib-jitsi-meet.min.js:17)
    at Object.error (lib-jitsi-meet.min.js:1)
    at D.Bosh._onRequestStateChange (lib-jitsi-meet.min.js:1)
s @ lib-jitsi-meet.min.js:10
getGlobalOnErrorHandler @ lib-jitsi-meet.min.js:17
window.onerror @ app.bundle.min.js:1
callErrorHandler @ lib-jitsi-meet.min.js:1
r.Strophe.log @ lib-jitsi-meet.min.js:17
error @ lib-jitsi-meet.min.js:1
_onRequestStateChange @ lib-jitsi-meet.min.js:1
XMLHttpRequest.send (async)
d @ lib-jitsi-meet.min.js:1
_processRequest @ lib-jitsi-meet.min.js:1
_throttledRequestHandler @ lib-jitsi-meet.min.js:1
_onIdle @ lib-jitsi-meet.min.js:1
_onIdle @ lib-jitsi-meet.min.js:1
(anonymous) @ lib-jitsi-meet.min.js:1
setTimeout (async)
_send @ lib-jitsi-meet.min.js:1
send @ lib-jitsi-meet.min.js:1
sendIQ @ lib-jitsi-meet.min.js:1
sendIQ @ lib-jitsi-meet.min.js:1
(anonymous) @ lib-jitsi-meet.min.js:1
sendIQ2 @ lib-jitsi-meet.min.js:1
ping @ lib-jitsi-meet.min.js:17
(anonymous) @ lib-jitsi-meet.min.js:17
14:46:39.780 lib-jitsi-meet.min.js:10 2020-08-12T06:46:39.780Z [modules/xmpp/strophe.util.js] <Object.r.Strophe.log>:  Strophe: request id 196.1 error 0 happened
s @ lib-jitsi-meet.min.js:10
r.Strophe.log @ lib-jitsi-meet.min.js:17
error @ lib-jitsi-meet.min.js:1
_onRequestStateChange @ lib-jitsi-meet.min.js:1
XMLHttpRequest.send (async)
d @ lib-jitsi-meet.min.js:1
_processRequest @ lib-jitsi-meet.min.js:1
_throttledRequestHandler @ lib-jitsi-meet.min.js:1
_onIdle @ lib-jitsi-meet.min.js:1
_onIdle @ lib-jitsi-meet.min.js:1
(anonymous) @ lib-jitsi-meet.min.js:1
setTimeout (async)
_send @ lib-jitsi-meet.min.js:1
send @ lib-jitsi-meet.min.js:1
sendIQ @ lib-jitsi-meet.min.js:1
sendIQ @ lib-jitsi-meet.min.js:1
(anonymous) @ lib-jitsi-meet.min.js:1
sendIQ2 @ lib-jitsi-meet.min.js:1
ping @ lib-jitsi-meet.min.js:17
(anonymous) @ lib-jitsi-meet.min.js:17
14:46:39.781 lib-jitsi-meet.min.js:10 2020-08-12T06:46:39.781Z [modules/xmpp/strophe.util.js] <Object.r.Strophe.log>:  Strophe: request errored, status: 0, number of errors: 1
s @ lib-jitsi-meet.min.js:10
r.Strophe.log @ lib-jitsi-meet.min.js:17
warn @ lib-jitsi-meet.min.js:1
_hitError @ lib-jitsi-meet.min.js:1
_onRequestStateChange @ lib-jitsi-meet.min.js:1
XMLHttpRequest.send (async)
d @ lib-jitsi-meet.min.js:1
_processRequest @ lib-jitsi-meet.min.js:1
_throttledRequestHandler @ lib-jitsi-meet.min.js:1
_onIdle @ lib-jitsi-meet.min.js:1
_onIdle @ lib-jitsi-meet.min.js:1
(anonymous) @ lib-jitsi-meet.min.js:1
setTimeout (async)
_send @ lib-jitsi-meet.min.js:1
send @ lib-jitsi-meet.min.js:1
sendIQ @ lib-jitsi-meet.min.js:1
sendIQ @ lib-jitsi-meet.min.js:1
(anonymous) @ lib-jitsi-meet.min.js:1
sendIQ2 @ lib-jitsi-meet.min.js:1
ping @ lib-jitsi-meet.min.js:17
(anonymous) @ lib-jitsi-meet.min.js:17
14:46:39.831 lib-jitsi-meet.min.js:1 POST https://jitsi.rtctest.7moor.com/http-bind?room=dd net::ERR_TIMED_OUT
d @ lib-jitsi-meet.min.js:1
_processRequest @ lib-jitsi-meet.min.js:1
_throttledRequestHandler @ lib-jitsi-meet.min.js:1
_onIdle @ lib-jitsi-meet.min.js:1
_onIdle @ lib-jitsi-meet.min.js:1
(anonymous) @ lib-jitsi-meet.min.js:1
setTimeout (async)
_send @ lib-jitsi-meet.min.js:1
send @ lib-jitsi-meet.min.js:1
sendIQ @ lib-jitsi-meet.min.js:1
sendIQ @ lib-jitsi-meet.min.js:1
(anonymous) @ lib-jitsi-meet.min.js:1
sendIQ2 @ lib-jitsi-meet.min.js:1
ping @ lib-jitsi-meet.min.js:17
(anonymous) @ lib-jitsi-meet.min.js:17
14:46:39.848 lib-jitsi-meet.min.js:10 2020-08-12T06:46:39.848Z [JitsiMeetJS.js] <Object.getGlobalOnErrorHandler>:  UnhandledError: null Script: null Line: null Column: null StackTrace:  Error: Strophe: request id 197.1 error 0 happened
    at Object.r.Strophe.log (lib-jitsi-meet.min.js:17)
    at Object.error (lib-jitsi-meet.min.js:1)
    at D.Bosh._onRequestStateChange (lib-jitsi-meet.min.js:1)
s @ lib-jitsi-meet.min.js:10
getGlobalOnErrorHandler @ lib-jitsi-meet.min.js:17
window.onerror @ app.bundle.min.js:1
callErrorHandler @ lib-jitsi-meet.min.js:1
r.Strophe.log @ lib-jitsi-meet.min.js:17
error @ lib-jitsi-meet.min.js:1
_onRequestStateChange @ lib-jitsi-meet.min.js:1
XMLHttpRequest.send (async)
d @ lib-jitsi-meet.min.js:1
_processRequest @ lib-jitsi-meet.min.js:1
_throttledRequestHandler @ lib-jitsi-meet.min.js:1
_onIdle @ lib-jitsi-meet.min.js:1
_onIdle @ lib-jitsi-meet.min.js:1
(anonymous) @ lib-jitsi-meet.min.js:1
setTimeout (async)
_send @ lib-jitsi-meet.min.js:1
send @ lib-jitsi-meet.min.js:1
sendIQ @ lib-jitsi-meet.min.js:1
sendIQ @ lib-jitsi-meet.min.js:1
(anonymous) @ lib-jitsi-meet.min.js:1
sendIQ2 @ lib-jitsi-meet.min.js:1
ping @ lib-jitsi-meet.min.js:17
(anonymous) @ lib-jitsi-meet.min.js:17
14:46:39.851 lib-jitsi-meet.min.js:10 2020-08-12T06:46:39.851Z [modules/xmpp/strophe.util.js] <Object.r.Strophe.log>:  Strophe: request id 197.1 error 0 happened

Logger.js:154 2020-08-12T06:10:04.179Z [modules/RTC/BridgeChannel.js] <RTCDataChannel.e.onerror>:  Channel error: undefined
 
 XMPP error reply received from speakerstats.jitsi.rtctest.7moor.com: XMPPError: service-unavailable - cancel
 Jicofo 2020-08-12 11:12:33.578 SEVERE: [136] org.jitsi.impl.protocol.xmpp.OpSetSimpleCapsImpl.log() Failed to discover features for callcontrol.jitsi.rtctest.7moor.com: XMPP error reply received from callcontrol.jitsi.rtctest.7moor.com: XMPPError: service-unavailable - wait

 lib-jitsi-meet.min.js?v=4127:10 2020-08-12T03:26:59.623Z [JitsiMeetJS.js] <Object.getGlobalOnErrorHandler>:  UnhandledError: null Script: null Line: null Column: null StackTrace:  Error: Strophe: request id 121.1 error 0 happened
    at Object.r.Strophe.log (lib-jitsi-meet.min.js?v=4127:17)
    at Object.error (lib-jitsi-meet.min.js?v=4127:1)
    at D.Bosh._onRequestStateChange (lib-jitsi-meet.min.js?v=4127:1)

    2020-08-12T03:26:59.630Z [modules/xmpp/strophe.util.js] <Object.r.Strophe.log>:  Strophe: request id 121.1 error 0 happened


    2020-08-12 11:27:35.462 INFO: [15475] [confId=d09bc426513a7671 gid=ff5059 stats_id=Colten-aRl conf_name=plainchamberssackexclusively ufrag=df4hn1efgaae5v epId=3fe32375 local_ufrag=df4hn1efgaae5v] ConnectivityCheckClient.processTimeout#857: timeout for pair: 47.241.133.80:10000/udp/srflx -> 222.212.140.66:49406/udp/prflx (stream-3fe32375.RTP), failing.
2020-08-12 11:27:38.466 INFO: [15475] [confId=d09bc426513a7671 gid=ff5059 stats_id=Colten-aRl conf_name=plainchamberssackexclusively ufrag=df4hn1efgaae5v epId=3fe32375 local_ufrag=df4hn1efgaae5v] ConnectivityCheckClient.processTimeout#857: timeout for pair: 47.241.133.80:10000/udp/srflx -> 222.212.140.66:49406/udp/prflx (stream-3fe32375.RTP), failing.
2020-08-12 11:27:40.494 INFO: [18] VideobridgeExpireThread.expire#144: Running expire()
2020-08-12 11:27:41.470 INFO: [15475] [confId=d09bc426513a7671 gid=ff5059 stats_id=Colten-aRl conf_name=plainchamberssackexclusively ufrag=df4hn1efgaae5v epId=3fe32375 local_ufrag=df4hn1efgaae5v] ConnectivityCheckClient.processTimeout#857: timeout for pair: 47.241.133.80:10000/udp/srflx -> 222.212.140.66:49406/udp/prflx (stream-3fe32375.RTP), failing.
2020-08-12 11:27:42.610 INFO: [20] Videobridge.createConference#320: create_conf, id=53d38401dd2e702 gid=null logging=false
2020-08-12 11:27:42.611 INFO: [20] AbstractHealthCheckService.run#171: Performed a successful health check in PT0.001S. Sticky failure: false
2020-08-12 11:27:44.474 INFO: [15475] [confId=d09bc426513a7671 gid=ff5059 stats_id=Colten-aRl conf_name=plainchamberssackexclusively ufrag=df4hn1efgaae5v epId=3fe32375 local_ufrag=df4hn1efgaae5v] ConnectivityCheckClient.processTimeout#857: timeout for pair: 47.241.133.80:10000/udp/srflx -> 222.212.140.66:49406/udp/prflx (stream-3fe32375.RTP), failing.
2020-08-12 11:27:47.478 INFO: [15475] [confId=d09bc426513a7671 gid=ff5059 stats_id=Colten-aRl conf_name=plainchamberssackexclusively ufrag=df4hn1efgaae5v epId=3fe32375 local_ufrag=df4hn1efgaae5v] ConnectivityCheckClient.processTimeout#857: timeout for pair: 47.241.133.80:10000/udp/srflx -> 222.212.140.66:49406/udp/prflx (stream-3fe32375.RTP), failing.
2020-08-12 11:27:50.482 INFO: [15475] [confId=d09bc426513a7671 gid=ff5059 stats_id=Colten-aRl conf_name=plainchamberssackexclusively ufrag=df4hn1efgaae5v epId=3fe32375 local_ufrag=df4hn1efgaae5v] ConnectivityCheckClient.processTimeout#857: timeout for pair: 47.241.133.80:10000/udp/srflx -> 222.212.140.66:49406/udp/prflx (stream-3fe32375.RTP), failing.
2020-08-12 11:27:52.614 INFO: [20] Videobridge.createConference#320: create_conf, id=9db3918a74e429fc gid=null logging=false
2020-08-12 11:27:52.616 INFO: [20] AbstractHealthCheckService.run#171: Performed a successful health check in PT0.002S. Sticky failure: false
2020-08-12 11:27:53.486 INFO: [15475] [confId=d09bc426513a7671 gid=ff5059 stats_id=Colten-aRl conf_name=plainchamberssackexclusively ufrag=df4hn1efgaae5v epId=3fe32375 local_ufrag=df4hn1efgaae5v] ConnectivityCheckClient.processTimeout#857: timeout for pair: 47.241.133.80:10000/udp/srflx -> 222.212.140.66:49406/udp/prflx (stream-3fe32375.RTP), failing.
2020-08-12 11:27:56.490 INFO: [15475] [confId=d09bc426513a7671 gid=ff5059 stats_id=Colten-aRl conf_name=plainchamberssackexclusively ufrag=df4hn1efgaae5v epId=3fe32375 local_ufrag=df4hn1efgaae5v] ConnectivityCheckClient.processTimeout#857: timeout for pair: 47.241.133.80:10000/udp/srflx -> 222.212.140.66:49406/udp/prflx (stream-3fe32375.RTP), failing.


2020-08-12 11:27:59.494 INFO: [15475] [confId=d09bc426513a7671 gid=ff5059 stats_id=Colten-aRl conf_name=plainchamberssackexclusively ufrag=df4hn1efgaae5v epId=3fe32375 local_ufrag=df4hn1efgaae5v] ConnectivityCheckClient.processTimeout#857: timeout for pair: 47.241.133.80:10000/udp/srflx -> 222.212.140.66:49406/udp/prflx (stream-3fe32375.RTP), failing.
2020-08-12 11:28:02.498 INFO: [15475] [confId=d09bc426513a7671 gid=ff5059 stats_id=Colten-aRl conf_name=plainchamberssackexclusively ufrag=df4hn1efgaae5v epId=3fe32375 local_ufrag=df4hn1efgaae5v] ConnectivityCheckClient.processTimeout#857: timeout for pair: 47.241.133.80:10000/udp/srflx -> 222.212.140.66:49406/udp/prflx (stream-3fe32375.RTP), failing.
2020-08-12 11:28:02.618 INFO: [20] Videobridge.createConference#320: create_conf, id=73d8987da6c932eb gid=null logging=false
2020-08-12 11:28:02.636 INFO: [20] AbstractHealthCheckService.run#171: Performed a successful health check in PT0.018S. Sticky failure: false
2020-08-12 11:28:05.502 INFO: [15475] [confId=d09bc426513a7671 gid=ff5059 stats_id=Colten-aRl conf_name=plainchamberssackexclusively ufrag=df4hn1efgaae5v epId=3fe32375 local_ufrag=df4hn1efgaae5v] ConnectivityCheckClient.processTimeout#857: timeout for pair: 47.241.133.80:10000/udp/srflx -> 222.212.140.66:49406/udp/prflx (stream-3fe32375.RTP), failing.
2020-08-12 11:28:08.506 INFO: [15475] [confId=d09bc426513a7671 gid=ff5059 stats_id=Colten-aRl conf_name=plainchamberssackexclusively ufrag=df4hn1efgaae5v epId=3fe32375 local_ufrag=df4hn1efgaae5v] ConnectivityCheckClient.processTimeout#857: timeout for pair: 47.241.133.80:10000/udp/srflx -> 222.212.140.66:49406/udp/prflx (stream-3fe32375.RTP), failing.
2020-08-12 11:28:11.510 INFO: [15475] [confId=d09bc426513a7671 gid=ff5059 stats_id=Colten-aRl conf_name=plainchamberssackexclusively ufrag=df4hn1efgaae5v epId=3fe32375 local_ufrag=df4hn1efgaae5v] ConnectivityCheckClient.processTimeout#857: timeout for pair: 47.241.133.80:10000/udp/srflx -> 222.212.140.66:49406/udp/prflx (stream-3fe32375.RTP), failing.
2020-08-12 11:28:12.622 INFO: [20] Videobridge.createConference#320: create_conf, id=d476e0cd7bbfeddb gid=null logging=false
2020-08-12 11:28:12.624 INFO: [20] AbstractHealthCheckService.run#171: Performed a successful health check in PT0.002S. Sticky failure: false
2020-08-12 11:28:14.514 INFO: [15475] [confId=d09bc426513a7671 gid=ff5059 stats_id=Colten-aRl conf_name=plainchamberssackexclusively ufrag=df4hn1efgaae5v epId=3fe32375 local_ufrag=df4hn1efgaae5v] ConnectivityCheckClient.processTimeout#857: timeout for pair: 47.241.133.80:10000/udp/srflx -> 222.212.140.66:49406/udp/prflx (stream-3fe32375.RTP), failing.
2020-08-12 11:28:17.072 INFO: [15438] [confId=d09bc426513a7671 epId=0ec935a7 gid=ff5059 stats_id=Colten-aRl conf_name=plainchamberssackexclusively] TlsClientImpl.notifyAlertReceived#211: close_notify received, connection closing
2020-08-12 11:28:17.518 INFO: [15475] [confId=d09bc426513a7671 gid=ff5059 stats_id=Colten-aRl conf_name=plainchamberssackexclusively ufrag=df4hn1efgaae5v epId=3fe32375 local_ufrag=df4hn1efgaae5v] ConnectivityCheckClient.processTimeout#857: timeout for pair: 47.241.133.80:10000/udp/srflx -> 222.212.140.66:49406/udp/prflx (stream-3fe32375.RTP), failing.
2020-08-12 11:28:20.470 INFO: [15475] [confId=d09bc426513a7671 gid=ff5059 stats_id=Colten-aRl conf_name=plainchamberssackexclusively ufrag=47tqi1efgaae6j epId=0ec935a7 local_ufrag=47tqi1efgaae6j] ConnectivityCheckClient.processTimeout#857: timeout for pair: 47.241.133.80:10000/udp/srflx -> 222.212.140.66:61822/udp/prflx (stream-0ec935a7.RTP), failing.
2020-08-12 11:28:20.522 INFO: [15475] [confId=d09bc426513a7671 gid=ff5059 stats_id=Colten-aRl conf_name=plainchamberssackexclusively ufrag=df4hn1efgaae5v epId=3fe32375 local_ufrag=df4hn1efgaae5v] ConnectivityCheckClient.processTimeout#857: timeout for pair: 47.241.133.80:10000/udp/srflx -> 222.212.140.66:49406/udp/prflx (stream-3fe32375.RTP), failing.
2020-08-12 11:28:22.626 INFO: [20] Videobridge.createConference#320: create_conf, id=318442cc2c7babb9 gid=null logging=false
2020-08-12 11:28:22.627 INFO: [20] AbstractHealthCheckService.run#171: Performed a successful health check in PT0.001S. Sticky failure: false
2020-08-12 11:28:23.474 INFO: [15475] [confId=d09bc426513a7671 gid=ff5059 stats_id=Colten-aRl conf_name=plainchamberssackexclusively ufrag=47tqi1efgaae6j epId=0ec935a7 local_ufrag=47tqi1efgaae6j] ConnectivityCheckClient.processTimeout#857: timeout for pair: 47.241.133.80:10000/udp/srflx -> 222.212.140.66:61822/udp/prflx (stream-0ec935a7.RTP), failing.
2020-08-12 11:28:23.526 INFO: [15475] [confId=d09bc426513a7671 gid=ff5059 stats_id=Colten-aRl conf_name=plainchamberssackexclusively ufrag=df4hn1efgaae5v epId=3fe32375 local_ufrag=df4hn1efgaae5v] ConnectivityCheckClient.processTimeout#857: timeout for pair: 47.241.133.80:10000/udp/srflx -> 222.212.140.66:49406/udp/prflx (stream-3fe32375.RTP), failing.
2020-08-12 11:28:26.478 INFO: [15475] [confId=d09bc426513a7671 gid=ff5059 stats_id=Colten-aRl conf_name=plainchamberssackexclusively ufrag=47tqi1efgaae6j epId=0ec935a7 local_ufrag=47tqi1efgaae6j] ConnectivityCheckClient.processTimeout#857: timeout for pair: 47.241.133.80:10000/udp/srflx -> 222.212.140.66:61822/udp/prflx (stream-0ec935a7.RTP), failing.
2020-08-12 11:28:26.530 INFO: [15475] [confId=d09bc426513a7671 gid=ff5059 stats_id=Colten-aRl conf_name=plainchamberssackexclusively ufrag=df4hn1efgaae5v epId=3fe32375 local_ufrag=df4hn1efgaae5v] ConnectivityCheckClient.processTimeout#857: timeout for pair: 47.241.133.80:10000/udp/srflx -> 222.212.140.66:49406/udp/prflx (stream-3fe32375.RTP), failing.
2020-08-12 11:28:29.482 INFO: [15475] [confId=d09bc426513a7671 gid=ff5059 stats_id=Colten-aRl conf_name=plainchamberssackexclusively ufrag=47tqi1efgaae6j epId=0ec935a7 local_ufrag=47tqi1efgaae6j] ConnectivityCheckClient.processTimeout#857: timeout for pair: 47.241.133.80:10000/udp/srflx -> 222.212.140.66:61822/udp/prflx (stream-0ec935a7.RTP), failing.
2020-08-12 11:28:29.534 INFO: [15475] [confId=d09bc426513a7671 gid=ff5059 stats_id=Colten-aRl conf_name=plainchamberssackexclusively ufrag=df4hn1efgaae5v epId=3fe32375 local_ufrag=df4hn1efgaae5v] ConnectivityCheckClient.processTimeout#857: timeout for pair: 47.241.133.80:10000/udp/srflx -> 222.212.140.66:49406/udp/prflx (stream-3fe32375.RTP), failing.
2020-08-12 11:28:31.719 INFO: [15432] [confId=d09bc426513a7671 epId=733c9992 local_ufrag=7avf91efgbckf7 gid=ff5059 conf_name=plainchamberssackexclusively ufrag=7avf91efgbckf7] Agent.gatherCandidates#662: Gathering candidates for component stream-733c9992.RTP.
2020-08-12 11:28:31.720 INFO: [15432] [confId=d09bc426513a7671 epId=733c9992 gid=ff5059 conf_name=plainchamberssackexclusively] Endpoint.lambda$setTransportInfo$8#1110: Ignoring empty DtlsFingerprint extension: <transport xmlns='urn:xmpp:jingle:transports:ice-udp:1'><fingerprint xmlns='urn:xmpp:jingle:apps:dtls:0' required='false'/></transport>
2020-08-12 11:28:31.720 INFO: [15432] [confId=d09bc426513a7671 epId=733c9992 gid=ff5059 conf_name=plainchamberssackexclusively] Endpoint.describe#1293: Transport description:
 <transport xmlns='urn:xmpp:jingle:transports:ice-udp:1' pwd='valgnle6d8rf1t5schtojdbdc' ufrag='7avf91efgbckf7'><rtcp-mux/><fingerprint xmlns='urn:xmpp:jingle:apps:dtls:0' setup='actpass' hash='sha-256'>81:E4:1B:D2:A6:79:D9:F0:78:F4:A7:1E:D5:0B:5E:62:E3:1B:A9:5A:1E:E8:12:17:4B:1C:54:52:62:43:B5:B7</fingerprint><candidate component='1' foundation='1' generation='0' id='4fb7bfc0285065000148f5ece' network='0' priority='2130706431' protocol='udp' type='host' ip='172.19.0.1' port='10000'/><candidate component='1' foundation='2' generation='0' id='52a6f264285065000148d5ece' network='0' priority='2130706431' protocol='udp' type='host' ip='172.17.0.1' port='10000'/><candidate component='1' foundation='3' generation='0' id='25edab7328506500029245fc7' network='0' priority='2113932031' protocol='udp' type='host' ip='192.168.0.250' port='10000'/><candidate component='1' foundation='4' generation='0' id='57d659b1285065000ffffffff986de41d' network='0' priority='1677724415' protocol='udp' type='srflx' ip='47.241.133.80' port='10000' rel-addr='192.168.0.250' rel-port='10000'/></transport>
2020-08-12 11:28:32.486 INFO: [15475] [confId=d09bc426513a7671 gid=ff5059 stats_id=Colten-aRl conf_name=plainchamberssackexclusively ufrag=47tqi1efgaae6j epId=0ec935a7 local_ufrag=47tqi1efgaae6j] ConnectivityCheckClient.processTimeout#857: timeout for pair: 47.241.133.80:10000/udp/srflx -> 222.212.140.66:61822/udp/prflx (stream-0ec935a7.RTP), failing.
2020-08-12 11:28:32.538 INFO: [15475] [confId=d09bc426513a7671 gid=ff5059 stats_id=Colten-aRl conf_name=plainchamberssackexclusively ufrag=df4hn1efgaae5v epId=3fe32375 local_ufrag=df4hn1efgaae5v] ConnectivityCheckClient.processTimeout#857: timeout for pair: 47.241.133.80:10000/udp/srflx -> 222.212.140.66:49406/udp/prflx (stream-3fe32375.RTP), failing.
2020-08-12 11:28:32.630 INFO: [20] Videobridge.createConference#320: create_conf, id=19f55cb4fc836eeb gid=null logging=false
2020-08-12 11:28:32.632 INFO: [20] AbstractHealthCheckService.run#171: Performed a successful health check in PT0.002S. Sticky failure: false
2020-08-12 11:28:35.490 INFO: [15475] [confId=d09bc426513a7671 gid=ff5059 stats_id=Colten-aRl conf_name=plainchamberssackexclusively ufrag=47tqi1efgaae6j epId=0ec935a7 local_ufrag=47tqi1efgaae6j] ConnectivityCheckClient.processTimeout#857: timeout for pair: 47.241.133.80:10000/udp/srflx -> 222.212.140.66:61822/udp/prflx (stream-0ec935a7.RTP), failing.
2020-08-12 11:28:35.542 INFO: [15475] [confId=d09bc426513a7671 gid=ff5059 stats_id=Colten-aRl conf_name=plainchamberssackexclusively ufrag=df4hn1efgaae5v epId=3fe32375 local_ufrag=df4hn1efgaae5v] ConnectivityCheckClient.processTimeout#857: timeout for pair: 47.241.133.80:10000/udp/srflx -> 222.212.140.66:49406/udp/prflx (stream-3fe32375.RTP), failing.
2020-08-12 11:28:38.040 INFO: [15432] [confId=d09bc426513a7671 epId=733c9992 gid=ff5059 stats_id=Colten-aRl conf_name=plainchamberssackexclusively] DtlsTransport.setSetupAttribute#120: The remote side is acting as DTLS server, we'll act as client
2020-08-12 11:28:38.041 INFO: [15432] [confId=d09bc426513a7671 gid=ff5059 stats_id=Colten-aRl componentId=1 conf_name=plainchamberssackexclusively ufrag=7avf91efgbckf7 name=stream-733c9992 epId=733c9992 local_ufrag=7avf91efgbckf7] Component.addRemoteCandidate#330: Add remote candidate for stream-733c9992.RTP: 10.36.100.86:58916/udp/host
2020-08-12 11:28:38.041 INFO: [15432] [confId=d09bc426513a7671 epId=733c9992 local_ufrag=7avf91efgbckf7 gid=ff5059 stats_id=Colten-aRl conf_name=plainchamberssackexclusively] IceTransport.startConnectivityEstablishment#176: Starting the agent with remote candidates.
2020-08-12 11:28:38.041 INFO: [15432] [confId=d09bc426513a7671 gid=ff5059 stats_id=Colten-aRl conf_name=plainchamberssackexclusively ufrag=7avf91efgbckf7 epId=733c9992 local_ufrag=7avf91efgbckf7] Agent.startConnectivityEstablishment#753: Start ICE connectivity establishment.
2020-08-12 11:28:38.041 INFO: [15432] [confId=d09bc426513a7671 gid=ff5059 stats_id=Colten-aRl conf_name=plainchamberssackexclusively ufrag=7avf91efgbckf7 epId=733c9992 local_ufrag=7avf91efgbckf7] Agent.initCheckLists#996: Init checklist for stream stream-733c9992
2020-08-12 11:28:38.041 INFO: [15432] [confId=d09bc426513a7671 gid=ff5059 stats_id=Colten-aRl conf_name=plainchamberssackexclusively ufrag=7avf91efgbckf7 epId=733c9992 local_ufrag=7avf91efgbckf7] Agent.setState#963: ICE state changed from Waiting to Running.
2020-08-12 11:28:38.041 INFO: [15432] [confId=d09bc426513a7671 epId=733c9992 local_ufrag=7avf91efgbckf7 gid=ff5059 stats_id=Colten-aRl conf_name=plainchamberssackexclusively] IceTransport.iceStateChanged#321: ICE state changed old=Waiting new=Running
2020-08-12 11:28:38.041 INFO: [15432] [confId=d09bc426513a7671 gid=ff5059 stats_id=Colten-aRl conf_name=plainchamberssackexclusively ufrag=7avf91efgbckf7 epId=733c9992 local_ufrag=7avf91efgbckf7] Agent.startConnectivityEstablishment#775: Trigger checks for pairs that were received before running state
2020-08-12 11:28:38.041 INFO: [15432] [confId=d09bc426513a7671 gid=ff5059 stats_id=Colten-aRl conf_name=plainchamberssackexclusively ufrag=7avf91efgbckf7 epId=733c9992 local_ufrag=7avf91efgbckf7] Agent.triggerCheck#1773: Add peer CandidatePair with new reflexive address to checkList: CandidatePair (State=Frozen Priority=7962116751007684095):
	LocalCandidate=candidate:3 1 udp 2113932031 192.168.0.250 10000 typ host
	RemoteCandidate=candidate:10000 1 udp 1853824767 222.212.140.66 58916 typ prflx
2020-08-12 11:28:38.041 INFO: [15432] [confId=d09bc426513a7671 gid=ff5059 stats_id=Colten-aRl conf_name=plainchamberssackexclusively ufrag=7avf91efgbckf7 epId=733c9992 local_ufrag=7avf91efgbckf7] ConnectivityCheckClient.startChecks#142: Start connectivity checks.
2020-08-12 11:28:38.041 INFO: [15432] [confId=d09bc426513a7671 epId=733c9992 gid=ff5059 stats_id=Colten-aRl conf_name=plainchamberssackexclusively] Endpoint.describe#1293: Transport description:
 <transport xmlns='urn:xmpp:jingle:transports:ice-udp:1' pwd='valgnle6d8rf1t5schtojdbdc' ufrag='7avf91efgbckf7'><rtcp-mux/><fingerprint xmlns='urn:xmpp:jingle:apps:dtls:0' setup='active' hash='sha-256'>81:E4:1B:D2:A6:79:D9:F0:78:F4:A7:1E:D5:0B:5E:62:E3:1B:A9:5A:1E:E8:12:17:4B:1C:54:52:62:43:B5:B7</fingerprint><candidate component='1' foundation='1' generation='0' id='5e06a18b285065000148f5ece' network='0' priority='2130706431' protocol='udp' type='host' ip='172.19.0.1' port='10000'/><candidate component='1' foundation='2' generation='0' id='45c9b624285065000148d5ece' network='0' priority='2130706431' protocol='udp' type='host' ip='172.17.0.1' port='10000'/><candidate component='1' foundation='3' generation='0' id='1e80687428506500029245fc7' network='0' priority='2113932031' protocol='udp' type='host' ip='192.168.0.250' port='10000'/><candidate component='1' foundation='4' generation='0' id='7d5d8ef2285065000ffffffff986de41d' network='0' priority='1677724415' protocol='udp' type='srflx' ip='47.241.133.80' port='10000' rel-addr='192.168.0.250' rel-port='10000'/></transport>
2020-08-12 11:28:38.050 INFO: [15432] [confId=d09bc426513a7671 gid=ff5059 stats_id=Colten-aRl componentId=1 conf_name=plainchamberssackexclusively ufrag=7avf91efgbckf7 name=stream-733c9992 epId=733c9992 local_ufrag=7avf91efgbckf7] Component.addUpdateRemoteCandidates#347: Update remote candidate for stream-733c9992.RTP: 10.36.100.86:58916/udp
2020-08-12 11:28:38.050 INFO: [15432] [confId=d09bc426513a7671 gid=ff5059 stats_id=Colten-aRl componentId=1 conf_name=plainchamberssackexclusively ufrag=7avf91efgbckf7 name=stream-733c9992 epId=733c9992 local_ufrag=7avf91efgbckf7] Component.addUpdateRemoteCandidates#369: Not adding duplicate remote candidate: 10.36.100.86:58916/udp
2020-08-12 11:28:38.050 INFO: [15432] [confId=d09bc426513a7671 gid=ff5059 stats_id=Colten-aRl componentId=1 conf_name=plainchamberssackexclusively ufrag=7avf91efgbckf7 name=stream-733c9992 epId=733c9992 local_ufrag=7avf91efgbckf7] Component.addUpdateRemoteCandidates#347: Update remote candidate for stream-733c9992.RTP: 10.36.100.86:58916/udp
2020-08-12 11:28:38.050 INFO: [15432] [confId=d09bc426513a7671 gid=ff5059 stats_id=Colten-aRl componentId=1 conf_name=plainchamberssackexclusively ufrag=7avf91efgbckf7 name=stream-733c9992 epId=733c9992 local_ufrag=7avf91efgbckf7] Component.addUpdateRemoteCandidates#369: Not adding duplicate remote candidate: 10.36.100.86:58916/udp
2020-08-12 11:28:38.051 INFO: [15432] [confId=d09bc426513a7671 epId=733c9992 gid=ff5059 stats_id=Colten-aRl conf_name=plainchamberssackexclusively] Endpoint.describe#1293: Transport description:
 <transport xmlns='urn:xmpp:jingle:transports:ice-udp:1' pwd='valgnle6d8rf1t5schtojdbdc' ufrag='7avf91efgbckf7'><rtcp-mux/><fingerprint xmlns='urn:xmpp:jingle:apps:dtls:0' setup='active' hash='sha-256'>81:E4:1B:D2:A6:79:D9:F0:78:F4:A7:1E:D5:0B:5E:62:E3:1B:A9:5A:1E:E8:12:17:4B:1C:54:52:62:43:B5:B7</fingerprint><candidate component='1' foundation='1' generation='0' id='16bc622b285065000148f5ece' network='0' priority='2130706431' protocol='udp' type='host' ip='172.19.0.1' port='10000'/><candidate component='1' foundation='2' generation='0' id='1ecc8e4e285065000148d5ece' network='0' priority='2130706431' protocol='udp' type='host' ip='172.17.0.1' port='10000'/><candidate component='1' foundation='3' generation='0' id='392862b28506500029245fc7' network='0' priority='2113932031' protocol='udp' type='host' ip='192.168.0.250' port='10000'/><candidate component='1' foundation='4' generation='0' id='12a9a2b5285065000ffffffff986de41d' network='0' priority='1677724415' protocol='udp' type='srflx' ip='47.241.133.80' port='10000' rel-addr='192.168.0.250' rel-port='10000'/></transport>
2020-08-12 11:28:38.086 INFO: [15452] [confId=d09bc426513a7671 gid=ff5059 stats_id=Colten-aRl conf_name=plainchamberssackexclusively ufrag=7avf91efgbckf7 epId=733c9992 local_ufrag=7avf91efgbckf7] ConnectivityCheckClient$PaceMaker.run#919: Pair failed: 172.19.0.1:10000/udp/host -> 10.36.100.86:58916/udp/host (stream-733c9992.RTP)
2020-08-12 11:28:38.110 INFO: [15452] [confId=d09bc426513a7671 gid=ff5059 stats_id=Colten-aRl conf_name=plainchamberssackexclusively ufrag=7avf91efgbckf7 epId=733c9992 local_ufrag=7avf91efgbckf7] ConnectivityCheckClient$PaceMaker.run#919: Pair failed: 172.17.0.1:10000/udp/host -> 10.36.100.86:58916/udp/host (stream-733c9992.RTP)
2020-08-12 11:28:38.134 INFO: [15452] [confId=d09bc426513a7671 gid=ff5059 stats_id=Colten-aRl conf_name=plainchamberssackexclusively ufrag=7avf91efgbckf7 epId=733c9992 local_ufrag=7avf91efgbckf7] ConnectivityCheckClient$PaceMaker.run#919: Pair failed: 192.168.0.250:10000/udp/host -> 10.36.100.86:58916/udp/host (stream-733c9992.RTP)
2020-08-12 11:28:38.149 INFO: [15469] [confId=d09bc426513a7671 gid=ff5059 stats_id=Colten-aRl conf_name=plainchamberssackexclusively ufrag=7avf91efgbckf7 epId=733c9992 local_ufrag=7avf91efgbckf7] ConnectivityCheckClient.processSuccessResponse#627: Pair succeeded: 192.168.0.250:10000/udp/host -> 222.212.140.66:58916/udp/prflx (stream-733c9992.RTP).
2020-08-12 11:28:38.149 INFO: [15469] [confId=d09bc426513a7671 gid=ff5059 stats_id=Colten-aRl componentId=1 conf_name=plainchamberssackexclusively ufrag=7avf91efgbckf7 name=stream-733c9992 epId=733c9992 local_ufrag=7avf91efgbckf7] ComponentSocket.addAuthorizedAddress#99: Adding allowed address: 222.212.140.66:58916/udp
2020-08-12 11:28:38.149 INFO: [15469] [confId=d09bc426513a7671 gid=ff5059 stats_id=Colten-aRl conf_name=plainchamberssackexclusively ufrag=7avf91efgbckf7 epId=733c9992 local_ufrag=7avf91efgbckf7] ConnectivityCheckClient.processSuccessResponse#636: Pair validated: 47.241.133.80:10000/udp/srflx -> 222.212.140.66:58916/udp/prflx (stream-733c9992.RTP).
2020-08-12 11:28:38.149 INFO: [15469] [confId=d09bc426513a7671 gid=ff5059 stats_id=Colten-aRl conf_name=plainchamberssackexclusively ufrag=7avf91efgbckf7 epId=733c9992 local_ufrag=7avf91efgbckf7] DefaultNominator.strategyNominateFirstValid#142: Nominate (first valid): 47.241.133.80:10000/udp/srflx -> 222.212.140.66:58916/udp/prflx (stream-733c9992.RTP).
2020-08-12 11:28:38.149 INFO: [15469] [confId=d09bc426513a7671 gid=ff5059 stats_id=Colten-aRl conf_name=plainchamberssackexclusively ufrag=7avf91efgbckf7 epId=733c9992 local_ufrag=7avf91efgbckf7] Agent.nominate#1846: verify if nominated pair answer again
2020-08-12 11:28:38.149 INFO: [15469] [confId=d09bc426513a7671 gid=ff5059 stats_id=Colten-aRl conf_name=plainchamberssackexclusively ufrag=7avf91efgbckf7 epId=733c9992 local_ufrag=7avf91efgbckf7] ConnectivityCheckClient.processSuccessResponse#705: IsControlling: true USE-CANDIDATE:false.
2020-08-12 11:28:38.238 INFO: [15469] [confId=d09bc426513a7671 gid=ff5059 stats_id=Colten-aRl conf_name=plainchamberssackexclusively ufrag=7avf91efgbckf7 epId=733c9992 local_ufrag=7avf91efgbckf7] ConnectivityCheckClient.processSuccessResponse#627: Pair succeeded: 47.241.133.80:10000/udp/srflx -> 222.212.140.66:58916/udp/prflx (stream-733c9992.RTP).
2020-08-12 11:28:38.238 INFO: [15469] [confId=d09bc426513a7671 gid=ff5059 stats_id=Colten-aRl conf_name=plainchamberssackexclusively ufrag=7avf91efgbckf7 epId=733c9992 local_ufrag=7avf91efgbckf7] ConnectivityCheckClient.processSuccessResponse#636: Pair validated: 47.241.133.80:10000/udp/srflx -> 222.212.140.66:58916/udp/prflx (stream-733c9992.RTP).
2020-08-12 11:28:38.238 INFO: [15469] [confId=d09bc426513a7671 gid=ff5059 stats_id=Colten-aRl conf_name=plainchamberssackexclusively ufrag=7avf91efgbckf7 epId=733c9992 local_ufrag=7avf91efgbckf7] ConnectivityCheckClient.processSuccessResponse#705: IsControlling: true USE-CANDIDATE:true.
2020-08-12 11:28:38.238 INFO: [15469] [confId=d09bc426513a7671 gid=ff5059 stats_id=Colten-aRl conf_name=plainchamberssackexclusively ufrag=7avf91efgbckf7 epId=733c9992 local_ufrag=7avf91efgbckf7] ConnectivityCheckClient.processSuccessResponse#720: Nomination confirmed for pair: 47.241.133.80:10000/udp/srflx -> 222.212.140.66:58916/udp/prflx (stream-733c9992.RTP).
2020-08-12 11:28:38.238 INFO: [15469] [confId=d09bc426513a7671 gid=ff5059 stats_id=Colten-aRl conf_name=plainchamberssackexclusively ufrag=7avf91efgbckf7 name=stream-733c9992 epId=733c9992 local_ufrag=7avf91efgbckf7] CheckList.handleNominationConfirmed#406: Selected pair for stream stream-733c9992.RTP: 47.241.133.80:10000/udp/srflx -> 222.212.140.66:58916/udp/prflx (stream-733c9992.RTP)
2020-08-12 11:28:38.238 INFO: [15469] [confId=d09bc426513a7671 gid=ff5059 stats_id=Colten-aRl conf_name=plainchamberssackexclusively ufrag=7avf91efgbckf7 epId=733c9992 local_ufrag=7avf91efgbckf7] Agent.checkListStatesUpdated#1937: CheckList of stream stream-733c9992 is COMPLETED
2020-08-12 11:28:38.238 INFO: [15469] [confId=d09bc426513a7671 gid=ff5059 stats_id=Colten-aRl conf_name=plainchamberssackexclusively ufrag=7avf91efgbckf7 epId=733c9992 local_ufrag=7avf91efgbckf7] Agent.setState#963: ICE state changed from Running to Completed.
2020-08-12 11:28:38.238 INFO: [15469] [confId=d09bc426513a7671 epId=733c9992 local_ufrag=7avf91efgbckf7 gid=ff5059 stats_id=Colten-aRl conf_name=plainchamberssackexclusively] IceTransport.iceStateChanged#321: ICE state changed old=Running new=Completed
2020-08-12 11:28:38.238 INFO: [15469] [confId=d09bc426513a7671 epId=733c9992 gid=ff5059 stats_id=Colten-aRl conf_name=plainchamberssackexclusively] Endpoint$3.connected#399: ICE connected
2020-08-12 11:28:38.239 INFO: [15456] [confId=d09bc426513a7671 epId=733c9992 gid=ff5059 stats_id=Colten-aRl conf_name=plainchamberssackexclusively] DtlsTransport.startDtlsHandshake#98: Starting DTLS handshake
2020-08-12 11:28:38.239 INFO: [15469] [confId=d09bc426513a7671 gid=ff5059 stats_id=Colten-aRl conf_name=plainchamberssackexclusively ufrag=7avf91efgbckf7 epId=733c9992 local_ufrag=7avf91efgbckf7] Agent.logCandTypes#2045: Harvester used for selected pair for stream-733c9992.RTP: srflx
2020-08-12 11:28:38.319 INFO: [15456] [confId=d09bc426513a7671 epId=733c9992 gid=ff5059 stats_id=Colten-aRl conf_name=plainchamberssackexclusively] TlsClientImpl.notifyServerVersion#165: Negotiated DTLS version DTLS 1.2
2020-08-12 11:28:38.404 INFO: [15456] [confId=d09bc426513a7671 epId=733c9992 gid=ff5059 stats_id=Colten-aRl conf_name=plainchamberssackexclusively] Endpoint$6.handshakeComplete#443: DTLS handshake complete
2020-08-12 11:28:38.405 INFO: [15479] [confId=d09bc426513a7671 epId=733c9992 gid=ff5059 stats_id=Colten-aRl conf_name=plainchamberssackexclusively] Endpoint.lambda$acceptSctpConnection$6#942: Attempting to establish SCTP socket connection
Got sctp association state update: 1
sctp is now up.  was ready? false
2020-08-12 11:28:38.494 INFO: [15475] [confId=d09bc426513a7671 gid=ff5059 stats_id=Colten-aRl conf_name=plainchamberssackexclusively ufrag=47tqi1efgaae6j epId=0ec935a7 local_ufrag=47tqi1efgaae6j] ConnectivityCheckClient.processTimeout#857: timeout for pair: 47.241.133.80:10000/udp/srflx -> 222.212.140.66:61822/udp/prflx (stream-0ec935a7.RTP), failing.
2020-08-12 11:28:38.506 INFO: [15479] [confId=d09bc426513a7671 epId=733c9992 gid=ff5059 stats_id=Colten-aRl conf_name=plainchamberssackexclusively] Endpoint$7.onReady#882: SCTP connection is ready, creating the Data channel stack
2020-08-12 11:28:38.506 INFO: [15479] [confId=d09bc426513a7671 epId=733c9992 gid=ff5059 stats_id=Colten-aRl conf_name=plainchamberssackexclusively] Endpoint$7.onReady#909: Will wait for the remote side to open the data channel.
2020-08-12 11:28:38.506 INFO: [15456] [confId=d09bc426513a7671 epId=733c9992 gid=ff5059 stats_id=Colten-aRl conf_name=plainchamberssackexclusively] DataChannelStack.onIncomingDataChannelPacket#62: Received data channel open message
2020-08-12 11:28:38.506 INFO: [15456] [confId=d09bc426513a7671 epId=733c9992 gid=ff5059 stats_id=Colten-aRl conf_name=plainchamberssackexclusively] Endpoint$7.lambda$onReady$1#890: Remote side opened a data channel.
2020-08-12 11:28:38.546 INFO: [15475] [confId=d09bc426513a7671 gid=ff5059 stats_id=Colten-aRl conf_name=plainchamberssackexclusively ufrag=df4hn1efgaae5v epId=3fe32375 local_ufrag=df4hn1efgaae5v] ConnectivityCheckClient.processTimeout#857: timeout for pair: 47.241.133.80:10000/udp/srflx -> 222.212.140.66:49406/udp/prflx (stream-3fe32375.RTP), failing.
2020-08-12 11:28:40.498 INFO: [18] VideobridgeExpireThread.expire#144: Running expire()
2020-08-12 11:28:40.498 INFO: [18] [confId=d09bc426513a7671 epId=3fe32375 gid=ff5059 stats_id=Colten-aRl conf_name=plainchamberssackexclusively] Endpoint.shouldExpire#741: Allowing to expire because of no activity in over PT1M
2020-08-12 11:28:40.498 INFO: [18] VideobridgeExpireThread.expire#161: Expiring endpoint 3fe32375
2020-08-12 11:28:40.498 INFO: [15480] [confId=d09bc426513a7671 epId=3fe32375 gid=ff5059 stats_id=Colten-aRl conf_name=plainchamberssackexclusively] AbstractEndpoint.expire#303: Expiring.
2020-08-12 11:28:40.499 INFO: [15480] [confId=d09bc426513a7671 epId=3fe32375 gid=ff5059 stats_id=Colten-aRl conf_name=plainchamberssackexclusively] Transceiver.teardown#315: Tearing down
2020-08-12 11:28:40.499 INFO: [15480] [confId=d09bc426513a7671 epId=3fe32375 gid=ff5059 stats_id=Colten-aRl conf_name=plainchamberssackexclusively] RtpReceiverImpl.tearDown#287: Tearing down
2020-08-12 11:28:40.499 INFO: [15480] [confId=d09bc426513a7671 epId=3fe32375 gid=ff5059 stats_id=Colten-aRl conf_name=plainchamberssackexclusively] RtpSenderImpl.tearDown#263: Tearing down
2020-08-12 11:28:40.499 INFO: [15480] [confId=d09bc426513a7671 epId=3fe32375 gid=ff5059 stats_id=Colten-aRl conf_name=plainchamberssackexclusively] DtlsTransport.stop#180: Stopping
2020-08-12 11:28:40.499 INFO: [15480] [confId=d09bc426513a7671 epId=3fe32375 local_ufrag=df4hn1efgaae5v gid=ff5059 stats_id=Colten-aRl conf_name=plainchamberssackexclusively] IceTransport.stop#235: Stopping
2020-08-12 11:28:40.500 INFO: [15450] [confId=d09bc426513a7671 gid=ff5059 stats_id=Colten-aRl componentId=1 conf_name=plainchamberssackexclusively ufrag=df4hn1efgaae5v name=stream-3fe32375 epId=3fe32375 local_ufrag=df4hn1efgaae5v] MergingDatagramSocket$SocketContainer.runInReaderThread#770: Failed to receive: java.net.SocketException: Socket closed
2020-08-12 11:28:40.500 INFO: [15480] [confId=d09bc426513a7671 gid=ff5059 stats_id=Colten-aRl componentId=1 conf_name=plainchamberssackexclusively ufrag=df4hn1efgaae5v name=stream-3fe32375 epId=3fe32375 local_ufrag=df4hn1efgaae5v] MergingDatagramSocket.close#142: Closing.
2020-08-12 11:28:40.500 WARNING: [15450] [confId=d09bc426513a7671 gid=ff5059 stats_id=Colten-aRl componentId=1 conf_name=plainchamberssackexclusively ufrag=df4hn1efgaae5v name=stream-3fe32375 epId=3fe32375 local_ufrag=df4hn1efgaae5v] MergingDatagramSocket.doRemove#349: Removing the active socket. Won't be able to send until a new one is elected.
2020-08-12 11:28:40.500 INFO: [15400] [confId=d09bc426513a7671 epId=3fe32375 local_ufrag=df4hn1efgaae5v gid=ff5059 stats_id=Colten-aRl conf_name=plainchamberssackexclusively] IceTransport.startReadingData#201: Socket closed, stopping reader
2020-08-12 11:28:40.501 INFO: [15400] [confId=d09bc426513a7671 epId=3fe32375 local_ufrag=df4hn1efgaae5v gid=ff5059 stats_id=Colten-aRl conf_name=plainchamberssackexclusively] IceTransport.startReadingData#213: No longer running, stopped reading packets
2020-08-12 11:28:40.501 INFO: [15480] [confId=d09bc426513a7671 epId=3fe32375 gid=ff5059 stats_id=Colten-aRl conf_name=plainchamberssackexclusively] Endpoint.expire#809: Expired.
2020-08-12 11:28:41.066 WARNING: [15400] [confId=d09bc426513a7671 epId=733c9992 gid=ff5059 stats_id=Colten-aRl conf_name=plainchamberssackexclusively] AbstractEndpointMessageTransport.onClientEndpointMessage#220: Unable to find endpoint 3fe32375 to send EndpointMessage
2020-08-12 11:28:41.242 INFO: [15370] [confId=d09bc426513a7671 gid=ff5059 stats_id=Colten-aRl conf_name=plainchamberssackexclusively ufrag=7avf91efgbckf7 epId=733c9992 local_ufrag=7avf91efgbckf7] Agent.setState#963: ICE state changed from Completed to Terminated.
2020-08-12 11:28:41.242 INFO: [15370] [confId=d09bc426513a7671 epId=733c9992 local_ufrag=7avf91efgbckf7 gid=ff5059 stats_id=Colten-aRl conf_name=plainchamberssackexclusively] IceTransport.iceStateChanged#321: ICE state changed old=Completed new=Terminated
2020-08-12 11:28:41.498 INFO: [15475] [confId=d09bc426513a7671 gid=ff5059 stats_id=Colten-aRl conf_name=plainchamberssackexclusively ufrag=47tqi1efgaae6j epId=0ec935a7 local_ufrag=47tqi1efgaae6j] ConnectivityCheckClient.processTimeout#857: timeout for pair: 47.241.133.80:10000/udp/srflx -> 222.212.140.66:61822/udp/prflx (stream-0ec935a7.RTP), failing.
2020-08-12 11:28:42.634 INFO: [20] Videobridge.createConference#320: create_conf, id=dd4c1a4953d11632 gid=null logging=false
2020-08-12 11:28:42.650 INFO: [20] AbstractHealthCheckService.run#171: Performed a successful health check in PT0.016S. Sticky failure: false

java -Xmx3072m -XX:+HeapDumpOnOutOfMemoryError 
-XX:HeapDumpPath=/tmp 
-Djdk.tls.ephemeralDHKeySize=2048 
-Djava.util.logging.config.file=/usr/share/jicofo/lib/logging.properties 
-Dnet.java.sip.communicator.SC_HOME_DIR_LOCATION=/etc/jitsi -Dnet.java.sip.communicator.SC_HOME_DIR_NAME=jicofo
 -Dnet.java.sip.communicator.SC_LOG_DIR_LOCATION=/var/log/jitsi 
 -Djava.util.logging.config.file=/etc/jitsi/jicofo/logging.properties -cp /usr/share/jicofo/jicofo.jar:/usr/share/jicofo/lib/agafua-syslog-0.4.jar:
 /usr/share/jicofo/lib/annotations-15.0.jar:/usr/share/jicofo/lib/
 aopalliance-repackaged-2.6.1.jar:/usr/share/jicofo/lib/bccontrib-1.0.jar:/usr/share/jicofo/lib/bcpkix-jdk15on-1.54.jar:/usr/share/jicofo/lib/bcprov-jdk15on-1.54.jar:/usr/share/jicofo/lib/cglib-nodep-2.2.jar:/usr/share/jicofo/lib/checker-qual-2.11.1.jar:/usr/share/jicofo/lib/commons-codec-1.6.jar:/usr/share/jicofo/lib/commons-lang3-3.1.jar:/usr/share/jicofo/lib/commons-logging-1.2.jar:/usr/share/jicofo/lib/concurrentlinkedhashmap-lru-1.0_jdk5.jar:/usr/share/jicofo/lib/config-1.3.4.jar:/usr/share/jicofo/lib/core-2.0.1.jar:/usr/share/jicofo/lib/dnsjava-2.1.7.jar:/usr/share/jicofo/lib/dom4j-1.6.1.jar:/usr/share/jicofo/lib/error_prone_annotations-2.3.4.jar:/usr/share/jicofo/lib/failureaccess-1.0.1.jar:/usr/share/jicofo/lib/fmj-1.0-20190327.151046-25.jar:/usr/share/jicofo/lib/guava-29.0-jre.jar:/usr/share/jicofo/lib/hk2-api-2.6.1.jar:/usr/share/jicofo/lib/hk2-locator-2.6.1.jar:/usr/share/jicofo/lib/hk2-utils-2.6.1.jar:/usr/share/jicofo/lib/httpclient-4.4.1.jar:/usr/share/jicofo/lib/httpcore-4.4.1.jar:/usr/share/jicofo/lib/ice4j-3.0-18-g686164f.jar:/usr/share/jicofo/lib/j2objc-annotations-1.3.jar:/usr/share/jicofo/lib/jackson-annotations-2.10.1.jar:/usr/share/jicofo/lib/jackson-core-2.10.0.jar:/usr/share/jicofo/lib/jackson-databind-2.10.1.jar:/usr/share/jicofo/lib/jackson-module-jaxb-annotations-2.10.1.jar:/usr/share/jicofo/lib/jain-sip-ri-ossonly-1.2.98c7f8c-jitsi-oss1.jar:/usr/share/jicofo/lib/jakarta.activation-api-1.2.1.jar:/usr/share/jicofo/lib/jakarta.annotation-api-1.3.5.jar:/usr/share/jicofo/lib/jakarta.inject-2.6.1.jar:/usr/share/jicofo/lib/jakarta.validation-api-2.0.2.jar:/usr/share/jicofo/lib/jakarta.ws.rs-api-2.1.6.jar:/usr/share/jicofo/lib/jakarta.xml.bind-api-2.3.2.jar:/usr/share/jicofo/lib/java-dogstatsd-client-2.5.jar:/usr/share/jicofo/lib/java-sdp-nist-bridge-1.1.jar:/usr/share/jicofo/lib/javassist-3.22.0-CR2.jar:/usr/share/jicofo/lib/javax.servlet-api-3.1.0.jar:/usr/share/jicofo/lib/jbosh-0.9.2.jar:/usr/share/jicofo/lib/jcip-annotations-1.0.jar:/usr/share/jicofo/lib/jcl-core-2.8.jar:/usr/share/jicofo/lib/jersey-client-2.30.1.jar:/usr/share/jicofo/lib/jersey-common-2.30.1.jar:/usr/share/jicofo/lib/jersey-container-jetty-http-2.30.1.jar:/usr/share/jicofo/lib/jersey-container-servlet-2.30.1.jar:/usr/share/jicofo/lib/jersey-container-servlet-core-2.30.1.jar:/usr/share/jicofo/lib/jersey-entity-filtering-2.30.1.jar:/usr/share/jicofo/lib/jersey-hk2-2.30.1.jar:/usr/share/jicofo/lib/jersey-media-jaxb-2.30.1.jar:/usr/share/jicofo/lib/jersey-media-json-jackson-2.30.1.jar:/usr/share/jicofo/lib/jersey-server-2.30.1.jar:/usr/share/jicofo/lib/jetty-client-9.4.15.v20190215.jar:/usr/share/jicofo/lib/jetty-continuation-9.4.17.v20190418.jar:/usr/share/jicofo/lib/jetty-http-9.4.15.v20190215.jar:/usr/share/jicofo/lib/jetty-io-9.4.15.v20190215.jar:/usr/share/jicofo/lib/jetty-proxy-9.4.15.v20190215.jar:/usr/share/jicofo/lib/jetty-security-9.4.15.v20190215.jar:/usr/share/jicofo/lib/jetty-server-9.4.15.v20190215.jar:/usr/share/jicofo/lib/jetty-servlet-9.4.15.v20190215.jar:/usr/share/jicofo/lib/jetty-util-9.4.15.v20190215.jar:/usr/share/jicofo/lib/jetty-webapp-7.0.1.v20091125.jar:/usr/share/jicofo/lib/jetty-xml-7.0.1.v20091125.jar:/usr/share/jicofo/lib/jicoco-1.1-42-geac01c8.jar:/usr/share/jicofo/lib/jicoco-config-1.1-42-geac01c8.jar:/usr/share/jicofo/lib/jitsi-android-osgi-1.0-20180322.162617-2.jar:/usr/share/jicofo/lib/jitsi-configuration-2.13.cb5485e.jar:/usr/share/jicofo/lib/jitsi-credentialsstorage-2.13.cb5485e.jar:/usr/share/jicofo/lib/jitsi-dnsservice-2.13.cb5485e.jar:/usr/share/jicofo/lib/jitsi-metaconfig-c3d8c51747.jar:/usr/share/jicofo/lib/jitsi-netaddr-2.13.cb5485e.jar:/usr/share/jicofo/lib/jitsi-protocol-2.13.cb5485e.jar:/usr/share/jicofo/lib/jitsi-protocol-jabber-2.13.cb5485e.jar:/usr/share/jicofo/lib/jitsi-protocol-media-2.13.cb5485e.jar:/usr/share/jicofo/lib/jitsi-util-2.13.cb5485e.jar:/usr/share/jicofo/lib/jitsi-utils-1.0-58-gaa5a28f.jar:/usr/share/jicofo/lib/jitsi-xmpp-extensions-1.0-13-ga40f9c3.jar:/usr/share/jicofo/lib/jna-5.5.0.jar:/usr/share/jicofo/lib/jnsapi-0.0.3-jitsi-smack4.2-3.jar:/usr/share/jicofo/lib/json-simple-1.1.1.jar:/usr/share/jicofo/lib/jsr305-3.0.2.jar:/usr/share/jicofo/lib/jxmpp-core-0.6.2.jar:/usr/share/jicofo/lib/jxmpp-jid-0.6.2.jar:/usr/share/jicofo/lib/jxmpp-util-cache-0.6.2.jar:/usr/share/jicofo/lib/kotlin-osgi-bundle-1.3.72.jar:/usr/share/jicofo/lib/kotlin-reflect-1.3.72.jar:/usr/share/jicofo/lib/kotlin-stdlib-1.3.72.jar:/usr/share/jicofo/lib/kotlin-stdlib-common-1.3.71.jar:/usr/share/jicofo/lib/kotlin-stdlib-jdk7-1.3.72.jar:/usr/share/jicofo/lib/kotlin-stdlib-jdk8-1.3.72.jar:/usr/share/jicofo/lib/libidn-1.15.jar:/usr/share/jicofo/lib/libjitsi-1.0-0-gb3296cf.jar:/usr/share/jicofo/lib/listenablefuture-9999.0-empty-to-avoid-conflict-with-guava.jar:/usr/share/jicofo/lib/object-cloner-0.1.jar:/usr/share/jicofo/lib/objenesis-2.6.jar:/usr/share/jicofo/lib/orange-extensions-1.3.0.jar:/usr/share/jicofo/lib/org.apache.felix.framework-4.4.0.jar:/usr/share/jicofo/lib/org.apache.felix.main-4.4.0.jar:/usr/share/jicofo/lib/org.osgi.core-4.3.1.jar:/usr/share/jicofo/lib/osgi-resource-locator-1.0.3.jar:/usr/share/jicofo/lib/reflections-0.9.11.jar:/usr/share/jicofo/lib/sdes4j-1.1.3.jar:/usr/share/jicofo/lib/sdp-api-1.0.jar:/usr/share/jicofo/lib/sentry-1.7.30.jar:/usr/share/jicofo/lib/slf4j-api-1.7.26.jar:/usr/share/jicofo/lib/slf4j-jdk14-1.7.26.jar:/usr/share/jicofo/lib/smack-bosh-4.2.4-47d17fc.jar:/usr/share/jicofo/lib/smack-core-4.2.4-47d17fc.jar:/usr/share/jicofo/lib/smack-debug-4.2.4-47d17fc.jar:/usr/share/jicofo/lib/smack-experimental-4.2.4-47d17fc.jar:/usr/share/jicofo/lib/smack-extensions-4.2.4-47d17fc.jar:/usr/share/jicofo/lib/smack-im-4.2.4-47d17fc.jar:/usr/share/jicofo/lib/smack-java7-4.2.4-47d17fc.jar:/usr/share/jicofo/lib/smack-legacy-4.2.4-47d17fc.jar:/usr/share/jicofo/lib/smack-resolver-javax-4.2.4-47d17fc.jar:/usr/share/jicofo/lib/smack-sasl-javax-4.2.4-47d17fc.jar:/usr/share/jicofo/lib/smack-tcp-4.2.4-47d17fc.jar:/usr/share/jicofo/lib/tinder-1.3.0.jar:/usr/share/jicofo/lib/weupnp-0.1.4.jar:/usr/share/jicofo/lib/xml-apis-1.0.b2.jar:/usr/share/jicofo/lib/xmlpull-1.1.3.4a.jar:/usr/share/jicofo/lib/xpp3-1.1.4c.jar:/usr/share/jicofo/lib/zrtp4j-light-4.1.0-jitsi-1-20190327.161225-1.jar 
 
 org.jitsi.jicofo.Main --host=localhost --domain=jitsi.webrtcsample.ink --port=5347 --secret=top2secret --user_name=focus --user_domain=auth.jitsi.webrtcsample.ink --user_password=top3secret --apis=xmpp