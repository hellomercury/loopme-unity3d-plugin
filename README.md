# LoopMe-Unity3D-Plugin #

## Overview ##

LoopMe is the largest mobile video DSP and Ad Network, reaching over 1 billion consumers world-wide. LoopMe’s full-screen video and rich media ad formats deliver more engaging mobile advertising experiences to consumers on smartphones and tablets.

The `loopme-unity3d-plugin` is an extension for `Unity3d`, allowing app developers to monetize apps via the LoopMe ad network.

<p align="center">
<img align="center" src="images/ad_overview.jpg" alt="LoopMe Interstitial Ad">
</p>

If you have questions please contact us at support@loopmemedia.com. 

## Features ##

* Full-screen image interstitials
* Full-screen rich media interstitials
* Preloaded video ads
* In-app ad reward notifications, including video view completed

## Requirements ##

An appKey is required to use the `loopme-unity3d-plugin`. The appKey uniquely identifies your app to the LoopMe ad network. (Example appKey: 7643ba4d53.) To get an appKey visit the **[LoopMe Dashboard](http://app.loopme.com)**. 

`loopme-unity3d-plugin` connects to native LoopMe `iOS` & `Android` libraries which control the interstitial ads. Tested on `Unity3D 2018.3.0f2`, supports a minimum of `Android 5.0 (API Level 21)` and `iOS 10.0` and above.

Included `loopme ios SDK 7.0.3` and `loopme android SDK 6.1.9`

## Usage ##

Integrating the `loopme-unity3d-plugin` is very simple and should take less than 10 minutes. 

* Download || clone `loopme-unity3d-plugin`
* Open your project in the `Unity3D` editor and import the `loopme-unity3d-plugin.unitypackage`
* Use `loopme-unity3d-plugin`'s main **LoopMeInterstitial** class static methods to create and display interstitial ads:
   * `CreateInterstitial`: this method creates interstitial with specified appKey.
   * `LoadAds`: retrieves ads for previously specified appKey
   * `ShowAds`: makes ads visible on the screen
   * `Destroy`: use this if interstitial is no longer needed
* Add `LoopMeEventsManager.cs` script as a component to your game object in order to receive interstitial ad events:
   * `interstitialDidLoadEvent`: triggered when interstitial has been loaded the ad content
   * `interstitialDidFailToLoadAdEvent`: triggered when interstitial failed to load the ad content
   * `interstitialDidAppearEvent`: triggered when interstitial ad appeared on the screen
   * `interstitialDidDisappearEvent`: triggered when interstitial ad disappeared from the screen
   * `interstitialVideoDidReachEndEvent`: triggered when interstitial video ad has been completely watched
   * `interstitialDidReceiveTapEvent`: triggered when interstitial ad was clicked
* `interstitialDidExpireEvent`: triggered when interstitial ad is expired, it is recommended to re-load

### Android set-up ###

1. Import `loopme-unity3d-plugin` to your Unity project. 
Make sure `Plugins/Android/*` checked while importing Unity package.
2. Don't forget to change а package name in plugin's AndroidManifest.xml.
```XML
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android" 
   package="YOUR_PACKAGE_NAME"
   xmlns:tools="http://schemas.android.com/tools" 
   android:installLocation="preferExternal">
```

### iOS set-up ###

1. Import `loopme-unity3d-plugin` to your Unity project. Make sure `Plugins/iOS/*` checked while importing Unity package.
2. Select `LoopMeUnitedSDK.framework` in Unity to open Import Settings
3. Add checkmark on following frameworks:
 * `AdSupport`
 * `CoreTelephony`
 * `StoreKit`
 * `AVKit`
 * `GLKit`
 * `WebKit`
 
4. Add following libraries to `Linked Frameworks and Libraries` in `XCode` project
* `libxml2.tbd`

5. Add following flags to other linker flags in `XCode` project's `build settings`
 * `-ObjC`


## Sample project ##

Check out our `loopme-unity3d-demo` as an example of `loopme-unity3d-plugin` integration:
* open `loopme-unity3d-demo` project in `Unity3d` editor
* assign scripts below to `Main Camera` game object:
  * `LoopMeEventsManager.cs`
  * `LoopMeEventsListener.cs`
  * `Demo.cs`
* Build & run

Note: for `iOS` you still need to perform some changes to just generated `XCode` project, see **iOS set-up** section.

## License ##
LICENSED UNDER THE TERMS OF THE BSD LICENSE, AS SPECIFIED BELOW.

DISCLAIMER: IMPORTANT: THIS LOOPME SOFTWARE IS SUPPLIED TO YOU BY LOOPME LTD. ("LOOPME") IN CONSIDERATION OF YOUR AGREEMENT TO THE TERMS FOUND ON OUR **[WEBSITE](http://www.loopmemedia.com/privacy/)**, 
AND YOUR USE, INSTALLATION, MODIFICATION OR REDISTRIBUTION OF THIS LOOPME SOFTWARE CONSTITUTES ACCEPTANCE OF THESE TERMS. 
IF YOU DO NOT AGREE WITH THESE TERMS, PLEASE DO NOT USE, INSTALL, MODIFY OR REDISTRIBUTE THIS LOOPME SOFTWARE.

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS" AND ANY EXPRESS OR IMPLIED WARRANTIES, 
INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE DISCLAIMED. 
IN NO EVENT SHALL THE COPYRIGHT OWNER OR CONTRIBUTORS BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, 
OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) 
HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) 
ARISING IN ANY WAY OUT OF THE USE OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.

COPYRIGHT © 2012, LOOPME LTD, ALL RIGHTS RESERVED