# skyway-webrtc-gateway

[日本語版はこちら](./README.md)

SkyWay WebRTC Gateway is an experimental approach to expand WebRTC possiblity. We're seeking new partners who challanges innovation.

## Concept

The mission of SkyWay is to make everyone use WebRTC easily. At first SkyWay starts to provide signaling to browser, then extends the device support to iOS and Android. As a next step, in order to the range of device and use case, we developed the SkyWay WebRTC Gateway which is IP reachable.

## Background

WebRTC Engine inside the browsers is only controlled by the browser's API. Control via JavaScript is the condititon.

![Can not control WebRTC engine inside browser](https://raw.githubusercontent.com/skyway/skyway-webrtc-gateway/master/images/as_is.png)

Because of this, you might have the problem like:

- You want devices to use WebRTC but the devices is not capable of running browser
- How can we operate the IoT device outside?
- I want to analyze the video with AI or to send data...
- I want to use WebRTC on server-side but the headless browsers doesn't meet my requirements...
- Can we make use of SIP/RTP property we already have?
- etc...

What if there's a WebRTC Engine which can be controlled by the program? This can leads to develop software or service freely...

<div align="center">
<img src="https://raw.githubusercontent.com/skyway/skyway-webrtc-gateway/master/images/to_be.png" width=50%>
</div>

In order to meet this needs, previously there's limited ways like developing something with [libWebRTC](https://github.com/aisouard/libwebrtc) from scratch, [OpenWebRTC](https://www.openwebrtc.org), or [Janus](https://janus.conf.meetecho.com). However, it's really difficult to understand the library and to develop application. In addition, before your starting production service there are other problems like:

- Usability of existing application is different from the browser's one
- You need to prepare signaling and TURN server
- You can not get enough support from developers

## Functions

To solve these problems, we have developed the SkyWay WebRTC Gateway which equips WebRTC engine which is wrapped with SkyWay. There are functions below:

- You can use SkyWay as you do
    - Signaling server, TURN server
    - Controll the application with REST API which is similar to existing SkyWay's API
- You can inject data to SkyWay WebRTC Gateway from outside
    - Send RTP to SkyWay WebRTC Gateway and the remote party can recevie it as MediaStream
    - Receive RTP which is sent by remote party is originally MediaStream
    - Send UDP and inject it to DataChannel
    - Receive UDP which is originally DataChannel
    - DataChannelで届いたデータをUDPで受け取る
- Because SkyWay WebRTC Gateway runs as stand-alone application, low performance devices can use it

![You can use WebRTC by the program outside](https://raw.githubusercontent.com/skyway/skyway-webrtc-gateway/master/images/module.png)

## How to use

At first you need to use REST API, then you establish WebRTC sesssion. After this, what you need to do is send RTP or UDP to SkyWay WebRTC Gateway via established session from your program. Lots of use case should be covered. For instance, you can inject the video to recording device, or you can send control signal to the device which in behind the firewall.

## Use case

By controlling WebRTC Engine freely, the use case is unlimited. Some use cases are introduced below.

- Control the low performance device which can't use WebRTC by itself

![IoT UseCase](https://raw.githubusercontent.com/skyway/skyway-webrtc-gateway/master/images/iot.png)

- Recording audio

![Recorder UseCase](https://raw.githubusercontent.com/skyway/skyway-webrtc-gateway/master/images/record.png)

- Implement communication components of VR game with WebRTC

![VR Game](https://raw.githubusercontent.com/skyway/skyway-webrtc-gateway/master/images/vr_game.png)

- Want to be virtual WebRTCer by sending the same video to 1,000 people

![Virtual Youtuber](https://github.com/skyway/skyway-webrtc-gateway/blob/master/images/vtuber.png)

- Store the data on the AI platform on the cloud

![AI UseCase1](https://raw.githubusercontent.com/skyway/skyway-webrtc-gateway/master/images/ai_1.png)

- View the analyzed data on the AI platform on the cloud

![AI UseCase2](https://raw.githubusercontent.com/skyway/skyway-webrtc-gateway/master/images/ai_2.png)

- Utilization of existing SIP/RTP eqiupments

![SIP UseCase](https://raw.githubusercontent.com/skyway/skyway-webrtc-gateway/master/images/sip.png)

If you found the exciting use cases, let us know!

## How to Use

[API Reference](http://35.200.46.204)

[samples](https://github.com/skyway/skyway-webrtc-gateway/tree/master/samples)

[sequence](https://github.com/skyway/skyway-webrtc-gateway/tree/master/sequence)

[Docs](https://github.com/skyway/skyway-webrtc-gateway/tree/master/docs)

[FAQ](https://github.com/skyway/skyway-webrtc-gateway/blob/master/FAQ.md)

[Developer community](https://support.skyway.io/hc/en-us/community/topics/360000026987-WebRTC-Gateway)

## Download

### x86_64

- [Linux](https://github.com/skyway/skyway-webrtc-gateway/releases/download/0.2.1/gateway_linux_x64)(Ubuntu18.04, 16.04, etc.)
- [Windows](https://github.com/skyway/skyway-webrtc-gateway/releases/download/0.2.1/gateway_windows.exe)(Windows 10, 8, 7)

MD5

gateway_linux_x64: afd5749f0e048308f80744c09c0c531c

gateway_windows.exe: b8359b76886c8b4d777b113e2129fb06

### ARM

- [ARM](https://github.com/skyway/skyway-webrtc-gateway/releases/download/0.2.1/gateway_linux_arm)

Minimum Requirements:
- Hardware: Raspberry Pi 3B or later
- Software: Raspbian Version 9 or later

MD5

gateway_linux_arm: 8012702da8e0f4466bff1f24a60c1a5c

## Updates and Release Notes

[issues](https://github.com/skyway/skyway-webrtc-gateway/issues)
[release notes](https://github.com/skyway/skyway-webrtc-gateway/blob/master/release-notes.md)

## License

[Terms](https://webrtc.ecl.ntt.com/terms.html)

This software includes the softwares which are disributed under Apache2 license.

[LICENSE](https://github.com/skyway/skyway-webrtc-gateway/blob/master/LICENSE.txt)

[NOTICE](https://github.com/skyway/skyway-webrtc-gateway/blob/master/NOTICE.txt)
