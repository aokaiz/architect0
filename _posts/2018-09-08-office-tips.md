---
layout: default
title:  "Office Tips"
date:   2018-09-08 21:30:00 +0800
categories: memo
---

## Powerpoint
### flash控件无法播放
**需要flash文件和ppt放在同一文件夹？**
- [TroubleShooting](http://www.boardworks.co.uk/troubleshooting-_334/#error3)
`此演示文稿中的一些空间无法激活。这些控件可能未在此计算机中注册。`
- 安装flash player(未解决)
- PowerPoint中注册（[参考](https://wenku.baidu.com/view/65203b4e33687e21af45a97c.html)）

`regsvr32.exe C:\Windows\System32\Macromed\Flash\Flash64_30_0_0_154.ocx`

**新版本中block了flash object解决方法**
- [Flash, Silverlight, and Shockwave controls blocked in Microsoft Office](https://support.office.com/en-us/article/flash-silverlight-and-shockwave-controls-blocked-in-microsoft-office-55738f12-a01d-420e-a533-7cef1ff6aeb1?ui=en-US&rs=en-US&ad=US)

### swf转mp4
- [free converter](https://free-swf-to-video-converter-software.en.softonic.com/?ex=BB-527.3)

## Excel
### 工作量统计
``=SUMPRODUCT(--(ISNUMBER(SEARCH(H2,$F$2:$F$50))),--($E$2:$E$50),--($G$2:$G$50))``

### get a list of unique and distinct values in Excel
- [ref.](https://www.ablebits.com/office-addins-blog/2016/04/21/get-list-unique-values-excel/)
```
=IFERROR(INDEX($A$2:$A$10, MATCH(0,INDEX(COUNTIF($B$1:B1, $A$2:$A$10)+(COUNTIF($A$2:$A$10, $A$2:$A$10)<>1),0,0), 0)), "")
```