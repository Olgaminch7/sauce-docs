---
id: Audio-capture
title: Audio Capture
---
import useBaseUrl from '@docusaurus/useBaseUrl';

# Audio Capture 

Audio Capture is a functionality that gives you the ability to record the audio stream your native Android and iOS/iPadOS mobile app generates during tests. 
With this feature, the audio is recorded on our side and merged with the video recording for your test results, including Live and Automated Tests Real Device tests for native applications. 

## What You'll Need

* A Sauce Labs account ([Log in](https://accounts.saucelabs.com/am/XUI/#login/) or sign up for a [free trial license](https://saucelabs.com/sign-up))
* A native Android, iOS, or iPadOS mobile app that makes HTTP/HTTPS requests. We currently support the following:
  * Android 10 and higher
  * iOS 10+ up to iOS 15.3


## Using Audio Capture on Real Devices

To enable audio capture in your tests: 
 
1. On Sauce Labs, click **Live** > **Mobile App**.
2. [Upload your mobile app to Sauce Labs](/mobile-apps/app-storage) through the UI or CLI.
3. After you’ve uploaded your app, return to the **Live** > **Mobile App** page, hover your mouse over your app, then select **Settings**. <br/><img src={useBaseUrl('img/mobile-apps/networkcapturescr.png')} alt="Mobile app settings navigation" width="800"/>
4. Under Default Settings, toggle Instrumentation and App/OS Audio to enable the feature. <br/><img src={useBaseUrl('img/mobile-apps/audio_capture_screen2.png')} alt="Mobile app settings navigation" width="600"/>
   
**For Automated Testing only:** add the audioCapture capability to your test script. Click the link below corresponding to your framework:
 
* Espresso (coming soon)
* XCUITest (coming soon)
* [Appium](/dev/test-configuration-options/#audiocapture)
  
  
Now you can start your live or automated testing session.Your audio recording will be captured and be part of the video recording in the test results page.

## Accessing the Audio through test results page

The audio recording will be included into the video recording in your test results page! You will be able to replay the audio with the built in media player in the test results page. 

You can also download the video file with the included audio stream programmatically using the following API request: 

```
curl --compressed \ -O https://{SAUCE_USERNAME}:{SAUCE_ACCESS_KEY}@{DATA_CENTER}.saucelabs.com/v1/rdc/jobs/{JOB_ID}/video.mp4
```

### Streaming the Audio (coming soon)

## Using Audio Capture on Android

You will be able to capture audio on Android 10 and above.

:::note
Once audioCapture is enabled the status bar will display the recording icon.
:::

We use native Android audio capture for seamless audio capture for our real devices experience. Your test results and sessions are secured, and can only be viewed by you only.
:::caution
If your applications manifest.xml file defines android:allowAudioPlaybackCapture="false", you need to enable instrumentation to have Audio Capture work for your applications. 
(screenshot of instrumentation flag)
:::


## Using Audio Capture on iOS/iPadOS

You will be able to capture audio from iOS 10+ up to iOS 15.3. 
:::note
The  recording and during a live testing session, you will see the status bar clock will display a static 9:41 time. This is just a visual limitation for audio capture, the system clock is not affected by this visual change. 
:::


## Limitations

:::caution
* Emulators and Simulators are not yet supported. 
* Cross browser testing is not yet available. 
:::

## More information

* [Test Results](/test-results/)