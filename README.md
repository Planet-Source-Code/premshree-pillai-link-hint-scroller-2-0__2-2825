<div align="center">

## Link Hint Scroller 2\.0


</div>

### Description

When you move your mouse over the above link a hint or something about the link will appear below the link in a scrolling fashion. When you move your mouseout the scrolling will stop.
 
### More Info
 
When you move your mouse over the above link a hint or something about the link will appear below the link in a scrolling fashion. When you move your mouseout the scrolling will stop.

To use this Javascript,view the source of this document. Firstly you must copy the script and place it in the head section. Then you must copy the <DIV> section and place it wherever you want it in the body. All the required section are marked by the comments <!--BEGIN REQUIRED--> and <!--END REQUIRED-->

scroll_length : Scroll length variable (150 here)

time_length : Speed of scroll (50 here, meaning after 50 milliseconds the hint will change position by 1 pixel i.e a speed of 20 pixels/second)

begin_pos : Beginning position of hint (300 here)

New in Version 2.0

In this version, you can change the direction of scrolling.

scroll_dir : Direction of scrolling ("right" here)


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Premshree Pillai](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/premshree-pillai.md)
**Level**          |Intermediate
**User Rating**    |4.7 (14 globes from 3 users)
**Compatibility**  |
**Category**       |[Layers](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/layers__2-78.md)
**World**          |[Java](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/java.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/premshree-pillai-link-hint-scroller-2-0__2-2825/archive/master.zip)





### Source Code

```
<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.0 Transitional//EN">
<html>
<head>
<title>Link Hint Scroller 2.0</title>
<style type="text/css">
.link{font-family:verdana,arial,helvetica; font-size:8pt; color:#DD0000; font-weight:normal}
.link:hover{font-family:verdana,arial,helvetica; font-size:8pt; color:#FF9900; font-weight:normal}
.prem_hint{font-family:verdana,arial,helvetica; font-size:8pt; color:#000000; font-weight:normal}
.header{font-family:arial,verdana,helvetica; font-size:20pt; color:#3366CC; font-weight:bold}
</style>
<!--BEGIN REQUIRED-->
<script language="javascript">
// Location of this script:
// http://www.qiksearch.com/javascripts/link_hint_scroller20.htm
//*********************************************
//* Link Hint Scroller 2.0          *
//* Modified 18/04/02             *
//* This script when you move your mouse over *
//* displays a scrolling hint         *
//* (c) Premshree Pillai,           *
//* http://www.qiksearch.com         *
//* E-mail : premshree@hotmail.com      *
//* Use the script freely as long as this   *
//* message is intact             *
//*********************************************
window.onerror = null;
 var bName = navigator.appName;
 var bVer = parseInt(navigator.appVersion);
 var NS4 = (bName == "Netscape" && bVer >= 4);
 var IE4 = (bName == "Microsoft Internet Explorer" && bVer >= 4);
 var NS3 = (bName == "Netscape" && bVer < 4);
 var IE3 = (bName == "Microsoft Internet Explorer" && bVer < 4);
//-----------------------------------------------------------
 var scroll_length = 150; //The scroll length
 var time_length =50; //Scroll delay in milliseconds
 var begin_pos = 260; //Start position of scroll hint
 var i=begin_pos;
 var j=i;
 var scroll_dir = "right"; // To scroll left use "left"
              // To scroll right use "right"
//-----------------------------------------------------------
if (NS4 || IE4) {
 if (navigator.appName == "Netscape") {
 layerStyleRef="layer.";
 layerRef="document.layers";
 styleSwitch="";
 }else{
 layerStyleRef="layer.style.";
 layerRef="document.all";
 styleSwitch=".style";
 }
}
//SCROLL
function Scroll(layerName)
{
 if (NS4 || IE4)
 {
 if(scroll_dir=="right")
 {
  if(i<(begin_pos+scroll_length))
  {
  eval(layerRef+'["'+layerName+'"]'+
  styleSwitch+'.visibility="visible"');
  eval(layerRef+'["'+layerName+'"]'+ styleSwitch+'.left="'+(i)+'"');
  i++;
  j++;
  }
 }
 if(scroll_dir=="left")
 {
  if(i>(begin_pos-scroll_length))
  {
  eval(layerRef+'["'+layerName+'"]'+
  styleSwitch+'.visibility="visible"');
  eval(layerRef+'["'+layerName+'"]'+ styleSwitch+'.right="'+(-i)+'"');
  i--;
  j--;
  }
 }
 if(i==j)
 {
  setTimeout("Scroll('"+layerName+"')",time_length);
 }
 }
}
//STOP SCROLLING
function StopScroll(layerName)
{
 if(scroll_dir=="right")
 {
 i=begin_pos+scroll_length;
 eval(layerRef+'["'+layerName+'"]'+
 styleSwitch+'.left="'+(i)+'"');
 hideLayer(layerName);
 }
 if(scroll_dir=="left")
 {
 i=begin_pos-scroll_length;
 eval(layerRef+'["'+layerName+'"]'+
 styleSwitch+'.right="'+(-i)+'"');
 hideLayer(layerName);
 }
}
function reset()
{
 i=begin_pos;
 j=i;
}
// HIDE HINT
function hideLayer(layerName)
{
 if (NS4 || IE4)
 {
 eval(layerRef+'["'+layerName+'"]'+
 styleSwitch+'.visibility="hidden"');
 }
}
</script>
<!--END REQUIRED-->
</head>
<body bgcolor="#FFFFFF">
<center>
<span class="header">Link Hint Scroller 2.0</span>
<br>
<!--BEGIN REQUIRED-->
<a href="#" class="link" onmouseover="javascript:reset();Scroll('prem_hint');" onmouseout="javascript:StopScroll('prem_hint');">Move your mouse over</a>
</center>
<div id="prem_hint" style="position:relative; visibility:hidden" class="prem_hint">
<b>This is the hint or description for the above link!</b>
</div>
<!--END REQUIRED-->
<table align="center" width="400"><tr><td>
<font face="verdana,arial,helvetica" size="-1" color="#000000">
When you move your mouse over the above link a hint or something about the link
will appear below the link in a scrolling fashion. When you move your mouseout the scrolling will stop.
<br><br>To use this Javascript,view the source of this document. Firstly you must copy the script
and place it in the head section. Then you must copy the &lt;DIV&gt; section and place it wherever you want it in the body. All the required section are marked by the comments &lt;!--BEGIN REQUIRED--&GT; and &lt;!--END REQUIRED--&gt;
<br><br>
<font face="courier">scroll_length</font> : Scroll length variable (150 here)<br>
<font face="courier">time_length</font> : Speed of scroll (50 here, meaning after 50 milliseconds the hint will change position by 1 pixel i.e a speed of 20 pixels/second)<br>
<font face="courier">begin_pos</font> : Beginning position of hint (300 here)
<br><br>
<b>New in Version 2.0</b><br>
In this version, you can change the direction of scrolling.<br>
<font face="courier">scroll_dir</font> : Direction of scrolling ("right" here)
</font>
</td></tr></table>
<br>
<center><a href="mailto:premshree@hotmail.com" class="link">&#169 Premshree Pillai</a></center>
<br>
<center><a href="http://www.qiksearch.com/javascripts/link_hint_scroller20.htm"><font face="arial,verdana,helvetica" size="-2" color="#CCCCCC">http://www.qiksearch.com/javascripts/link_hint_scroller20.htm</font></a></center>
</body>
</html>
```

