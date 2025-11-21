# ONVIF-profile-S
this tool can use on the IP Camera system. it can easily report the RTSP URL and other information.

I ported these source codes on the Raspberry pi, and I also run on the raspberry pi. below picture is a result.

![Screen Shot 2022-03-11 at 11 03 55](https://user-images.githubusercontent.com/8576322/157848976-36d34d2b-9c87-4018-8c1a-53393796e682.png)


And then, We can see the below images. we can easily use the Onvif management tool to search the program. 

![Screen Shot 2022-03-11 at 11 03 14](https://user-images.githubusercontent.com/8576322/157849131-ec6bbbf6-ef48-4adf-b70e-8015cc475188.png)

And also, we can see all information on the Onvif management tool.

![Screen Shot 2022-03-11 at 11 03 27](https://user-images.githubusercontent.com/8576322/157849249-e12cb583-aa86-4b3a-a2d3-b6819423d47a.png)
![Screen Shot 2022-03-11 at 11 03 46](https://user-images.githubusercontent.com/8576322/157849264-aa4add36-b7e2-48c3-85cf-fe038859e386.png)
![Screen Shot 2022-03-11 at 11 03 35](https://user-images.githubusercontent.com/8576322/157849285-30bed67e-9d06-4487-ae02-52aeb72bdb22.png)

for all reference my results. if any problems, feel free to mail me. thanks.

## RTSP source options
The demo stream advertised through ONVIF can be backed by a small GStreamer test pipeline or by hardware cameras attached to a Raspberry Pi. The RTSP helper defaults to the GStreamer test generator when the configuration contains values similar to:

```
"CameraType" : "testsrc",
"RTSPServer" : 3, "RtspServerComment" : "## Select RTSP Server > 1:RPOS RTSP Server 2:V4L2 RTSP Server by mpromonet (auto selected if MulticastEnabled=true) 3:GStreamer",
```

With this setting, the sample stream is created internally for debugging. Switching `CameraType` to a USB or PCI camera will direct the RTSP server to publish that device instead, allowing the `/v1`/`/v2` URIs reported by `GetStreamUri` to point at real video.

## Alarm and event triggers
Input/output alarms are expected to be driven either by the Raspberry Pi GPIO pins or by external producers (for example, a Python helper or REST request). These triggers can be fed into the ONVIF events pipeline (PullPoint) to notify an NVR once the subscription and event queue logic are wired up in the service handlers.
