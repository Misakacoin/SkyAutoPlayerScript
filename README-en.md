# SkyAutoPlayerScript

A script to play Sheets generated by [SkyStudio](https://play.google.com/store/apps/details?id=com.Maple.SkyStudio) automatically in game Sky with accessibility services using Auto.js

[![shared sheet](https://badgen.net/badge/shared%20sheets/121%20in%20total/green)](shared_sheets/) [![sheet contributors](https://badgen.net/badge/sheet%20contributors/23/pink)](#shared-sheets) [![Hosted in](https://badgen.net/badge/CDN/jsDelivr?icon=jsdelivr)](https://www.jsdelivr.com/)

## Feature

There are many features in SkyAutoPlayerScript compared to other auto player scripts.

* Friendly GUI, no code edit, fluent ui animation.
* Multi-functional player control panel with **pause**, **progress control** and **speed control**.
* Set key coordinates by yourself with guidence, avoiding key offset when playing.
* There are many excellent online [shared sheets](https://github.com/StageGuard/SkyAutoPlayerScript/tree/master/shared_sheets).
* Automatically update script.
* [Multi-language support](#translation).
* ...

## Usage

1. Download release `4.1.1 Alpha2 (461) -> armeabi-v7a` in [`Ericwyn/Auto.js/releases@V4.1.1.Alpha2`](https://github.com/Ericwyn/Auto.js/releases/tag/V4.1.1.Alpha2)

2. Turn on **Accessibility service** and allow **Display pop-up window** permission for Auto.js

3. Create a new script file in Auto.js. Copy the code below and run!

```javascript
"ui";
"use strict";
var emitter = events.emitter(threads.currentThread());
threads.start(function() {
  emitter.emit("evaluate", (function(){
    var resp = http.get("https://gitee.com/stageguard/SkyAutoPlayerScript/raw/master/source/SkyAutoplayer.js");
    if(resp.statusCode >= 200 && resp.statusCode < 300) {
      return resp.body.string();
    } else {
      resp = http.get("https://cdn.jsdelivr.net/gh/StageGuard/SkyAutoPlayerScript@" + http.get("https://gitee.com/stageguard/SkyAutoPlayerScript/raw/master/gitVersion").body.string() + "/source/SkyAutoplayer.js");
      if(resp.statusCode >= 200 && resp.statusCode < 300) {
        return resp.body.string();
      } else {
        return "console.show();console.log(\"Failed to load script\")";
      }
	}
  }()));
});
emitter.on('evaluate', function(s){
  eval(s);
});
```
## Clear data

`SkyAutoPlayerScript` will store data while running, if you want to delete all data, please run the code below in Auto.js

```
storages.remove("StageGuard:SkyAutoPlayer:Config");
files.removeDir("/storage/emulated/0/Documents/SkyAutoPlayer/");
```

# Upload sheets

SkyAutoplayerScript will load online shared sheets from the file `shared_sheets.json` in this repository and it is convenient to download and play.

If you want to let sheets that transcribed by yourself or permitted to reprint shown on the list, you can do one of the following ways:

### 1. Pull Request

You can clone this repository, put your sheet file into `shared_sheets` folder and add a new item in `shared_sheets.json` :

```javascript
{
  //sheet name
  "name": "Vicetone - Nevada",
  //sheet file name in shared_sheets folder
  "file": "Nevada.txt",
  //transcriber
  "author": "StageGuard",
  //short description about this sheet
  "desc": "Nevada SkyStudio钢琴版。\n内包含<u>比较复杂的和弦</u>，不适合手弹(笑\n你可以在SkyStudio的练习模式试试[狗头]",
  //BPM in sheet file
  "bpm": 497,
  //key count(a 15 key sheet or 8 key sheet)
  "keyCount": 15,
  //pitch level in sheet file
  "pitchLevel": 3,
  //note count
  //length of array songNotes in sheet file
  "noteCount": 1308,
  //your social link
  //you can add many links if you want
  "social": [
    {
      //platform code name, currently support github, twitter, douyin(tiktok) and coolapk
      "platform": "github",
      //social platform name
      "name": "GitHub",
      //social link
      "link": "https://github.com/StageGuard/"
    }
  ]
},
```

After finishing, you need to create a new `pull request` and wait it to be merged.

> Attention: Before creating a new `pull request` , make sure your local repository is up-to-date!

### 2. If you are not familiar with Github...

Just mail your sheet file to [beamiscool@qq.com](mailto:beamiscool@qq.com) and don't forget the sheet description !

# Attention!

### Before using this script, you must read the following notes!

1. SkyAutoplayerScript is not fully tested, if you meet a bug, please PM CoolApk@StageGuard or create a new issue.

2. **SkyAutoplayerScript is a free and open source project. If you want to use it for commercial purposes, please add the link refers to this repository.**

3. **Shared sheets is not under the protection of LGPL-2.1, if you want to reprint shared sheets to other platforms, please contact sheet transcriber by yourself!**

4. The script is just for entertainment and it is not suitable to use it in formal occasion.

5. Script just gives you a short-time sense of satisfaction and do not make you progress.

6. This script is just a "player" and no built-in sheets, you must download [SkyStudio](https://play.google.com/store/apps/details?id=com.Maple.SkyStudio) to make sheets.

7. The script will not support decrypt sheet, including **SkyStudio encryped sheet** or **encrypted js** etc...<br>And the repository will also not accept encrypted sheet.


<details> <summary>Issues </summary>

# Use it to make profits: [#1](https://github.com/StageGuard/SkyAutoPlayerScript/issues/1)

# Embezzle shared sheets: 

Gitee user [嗨游圈(@vipssp)](https://gitee.com/vipssp) upload all shared sheets in [/shared_sheets](https://github.com/StageGuard/SkyAutoPlayerScript/tree/master/shared_sheets) **without permission** to his [Gitee repository](https://gitee.com/vipssp/SkyAutoPlayerScript/)

He also doesn't delete these sheets from his repository after [notification](https://gitee.com/vipssp/SkyAutoPlayerScript/commit/197925a71ff9cc6248be682a55406fc5814b12d7#note_3637784).

I decide to pin him in README.md after comminucating with some sheet sharer.

<table>
<tr>
    <td align="center" height="200">
        <img src="https://gitee.com/stageguard/SkyAutoPlayerScript/raw/master/resources/static/2020-12-19_0-8-40.PNG" />
    </td>
    <td align="center" height="200">
        <img src="https://gitee.com/stageguard/SkyAutoPlayerScript/raw/master/resources/static/2020-12-19_0-9-57.PNG" />
    </td>
    <td align="center" height="200">
        <img src="https://gitee.com/stageguard/SkyAutoPlayerScript/raw/master/resources/static/2020-12-19_0-44-4.PNG" />
    </td>
    <td align="center" height="200">
        <img src="https://gitee.com/stageguard/SkyAutoPlayerScript/raw/master/resources/static/Screenshot_2020-12-19-00-10-12-499_com.coolapk.market.jpg" />
    </td>
    <td align="center" height="200">
        <img src="https://gitee.com/stageguard/SkyAutoPlayerScript/raw/master/resources/static/Screenshot_2020-12-19-00-11-23-671_com.coolapk.market.jpg" />
    </td>
</tr>
</table>
</details>

# Contribution

Welcome everyone to contribute this project, including pull request, issue, new feature request or translation.

### ⚠️WARNING
CodeFactor Evaluation: [![CodeFactor](https://www.codefactor.io/repository/github/stageguard/skyautoplayerscript/badge)](https://www.codefactor.io/repository/github/stageguard/skyautoplayerscript)

Because of the limitation of Auto.js, it is impossible to extract functions and method so all functions are defined in a single file. Also, my coding skill is poor, so it is `a little hard` to understand source code.

## Contributor

### SkyAutoPlayerScript

[@tiaod](https://github.com/tiaod)

### Shared sheets

CoolApk [@Aex技术总监](http://www.coolapk.com/u/1286879)<br>
CoolApk [@夏卡卡卡](http://www.coolapk.com/u/2313452)<br>
CoolApk [@深空失忆か](http://www.coolapk.com/u/3005974)<br>
Douyin [@子哲啊🌈(zizhe1880689503)](https://v.douyin.com/J9gUaVE/)<br>
CoolApk [@你们很有趣呢](http://www.coolapk.com/u/2416229)<br>
CoolApk [@情如风雪无常](http://www.coolapk.com/u/643670)<br>
CoolApk [@慕疵](http://www.coolapk.com/u/3286967)<br>
CoolApk [@社区最弱萌新](http://www.coolapk.com/u/3291313)<br>
CoolApk [@九方辰](http://www.coolapk.com/u/634078)<br>
CoolApk [@北极马可罗尼](http://www.coolapk.com/u/463478)<br>
Bilibili [@UTF16](https://space.bilibili.com/623364258)<br>
CoolApk [@Syngenex](http://www.coolapk.com/u/1093421)<br>
Twitter [Phoebe@huunhut1217](https://mobile.twitter.com/huunhut1217)<br>
CoolApk [@终究是错付了](http://www.coolapk.com/u/2293899)<br>
CoolApk [@DesperatU](http://www.coolapk.com/u/1075889)<br>
CoolApk [@明明酱](http://www.coolapk.com/u/1706128)<br>
CoolApk [@cxk的篮球](http://www.coolapk.com/u/1090769)<br>
CoolApk [@头条乀](http://www.coolapk.com/u/1192320)<br>
CoolApk [@Alusias](http://www.coolapk.com/u/808787)<br>
[chikin](mailto:2869826936@qq.com)<br>
CoolApk [@温茶予君](http://www.coolapk.com/u/1212499)<br>
CoolApk [@落红难相聚](http://www.coolapk.com/u/2082465)<br>
CoolApk [@bugjump233](http://www.coolapk.com/u/3294062)<br>

## Translation

SkyAutoplayerScript version 21 has supported multi-language and can also fetch online language list, follow [contribute-translation.md](contribute-translation.md) (English) guide to contribute translation.

### Contributor

None

# Icon from:

[Iconfont-阿里巴巴矢量图标库](https://www.iconfont.cn/)

# Thanks to:

[projectXero](https://gitee.com/projectXero) (Provide `ListAdapter` used in Rhino)

# LICENSE

```
    SkyAutoPlayer (Auto.js script)
	  Copyright © 2020-2021 StageGuard

  This library is free software; you can redistribute it and/or
  modify it under the terms of the GNU Lesser General Public
  License as published by the Free Software Foundation; either
  version 2.1 of the License, or (at your option) any later version.

  This library is distributed in the hope that it will be useful,
  but WITHOUT ANY WARRANTY; without even the implied warranty of
  MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the GNU
  Lesser General Public License for more details.

  You should have received a copy of the GNU Lesser General Public
  License along with this library; if not, write to the Free Software
  Foundation, Inc., 51 Franklin Street, Fifth Floor, Boston, MA  02110-1301
  USA
```