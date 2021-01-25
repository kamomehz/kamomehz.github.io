---
title: titechPortalAutoLogin
categories: blog
tags: [日记]
---

## Js code

Part 1

```
// ==UserScript==
// @name         portal1
// @namespace    http://tampermonkey.net/
// @version      0.1
// @description  try to take over the world!
// @author       You
// @match        *://portal.nap.gsic.titech.ac.jp/GetAccess/Login?Template=userpass_key*
// @grant        none
// @run-at       document-start
// ==/UserScript==

function scriptSource(table) {
    table.usr_name.value = "";
    table.usr_password.value = "";
    table.submit();
}


scriptSource(document.login)
```


Part 2 

* Fill password matrix in ids. [A1,A2,A3...]


```
// ==UserScript==
// @name         portal2
// @namespace    http://tampermonkey.net/
// @version      0.1
// @description  try to take over the world!
// @author       You
// @match        *://portal.nap.gsic.titech.ac.jp/GetAccess/Login?Template=idg_key&*
// @grant        none
// @run-at       document-start
// ==/UserScript==


function scriptSource2(document) {
    var ids="";
    var ans="";
    for (var i=0;i<3;i++)
    {
        var k0=document.getElementById("authentication").rows[3+i].cells[0].innerHTML;
        var k1=k0[1].charCodeAt()-65;[]
        var k2=k0[3]-1;
        var nums=k1*7+k2;
        ans+=ids[nums];
    }

    document.login.message3.value = ans[0];
    document.login.message4.value = ans[1];
    document.login.message5.value = ans[2];
    document.login.submit()
}
scriptSource2(document)
```

## Put it into tampermonkey (chrome or firefox)