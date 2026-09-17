# Практична робота № 1

**Дисципліна:** Основи побудови інформаційних систем та мереж

**Тема:** Спостереження за процесом звернення до вебресурсу. Побудова власної моделі рівнів взаємодії

|  |  |
|---|---|
| **Прізвище, ім'я** | Магомедов Ельдар |
| **Група** | ІПЗ 3-2.01 |
| **Номер варіанта** | 17 |
| **Домен варіанта** | `sqlite.org` |
| **Середовище виконання** | Windows |
| **Версія curl** | `curl 8.16.0 (Windows) libcurl/8.16.0 Schannel zlib/1.3.1 WinIDN` |
| **Дата виконання** | 17.09.2026 |

Частина A. Збір експериментальних даних
A.1. Запит із діагностичним виводом
Команда:curl.exe -v https://sqlite.org

Вивід:
* Host sqlite.org:443 was resolved.
* IPv6: (none)
* IPv4: 194.195.208.62
*   Trying 194.195.208.62:443...
* schannel: disabled automatic use of client certificate
* ALPN: curl offers http/1.1
* ALPN: server did not agree on a protocol. Uses default.
* Established connection to sqlite.org (194.195.208.62 port 443) from 10.1.8.239 port 52932
* using HTTP/1.x
> GET / HTTP/1.1
> Host: sqlite.org
> User-Agent: curl/8.16.0
> Accept: */*
>
* Request completely sent off
* schannel: remote party requests renegotiation
* schannel: renegotiating SSL/TLS connection
* schannel: SSL/TLS connection renegotiated
* schannel: remote party requests renegotiation
* schannel: renegotiating SSL/TLS connection
* schannel: SSL/TLS connection renegotiated
< HTTP/1.1 200 OK
< Connection: keep-alive
< Date: Thu, 17 Sep 2026 14:06:33 GMT
< Last-Modified: Fri, 11 Sep 2026 11:09:53 GMT
< Cache-Control: max-age=120
< ETag: "m6aa3e181s22b6"
< Content-type: text/html; charset=utf-8
< Content-length: 8886
<
<!DOCTYPE html>
<html><head>
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta http-equiv="content-type" content="text/html; charset=UTF-8">
<link href="sqlite.css" rel="stylesheet">
<title>SQLite Home Page</title>
<!-- path= -->
</head>
<body>
<div class=nosearch>
<a href="index.html">
<img class="logo" src="images/sqlite370_banner.svg" alt="SQLite" border="0">
</a>
<div><!-- IE hack to prevent disappearing logo --></div>
<div class="tagline desktoponly">
Small. Fast. Reliable.<br>Choose any three.
</div>
<div class="menu mainmenu">
<ul>
<li><a href="index.html">Home</a>
<li class='mobileonly'><a href="javascript:void(0)" onclick='toggle_div("submenu")'>Menu</a>
<li class='wideonly'><a href='about.html'>About</a>
<li class='desktoponly'><a href="docs.html">Documentation</a>
<li class='desktoponly'><a href="download.html">Download</a>
<li class='wideonly'><a href='copyright.html'>License</a>
<li class='desktoponly'><a href="support.html">Support</a>
<li class='desktoponly'><a href="prosupport.html">Purchase</a>
<li class='search' id='search_menubutton'>
<a href="javascript:void(0)" onclick='toggle_search()'>Search</a>
</ul>
</div>
<div class="menu submenu" id="submenu">
<ul>
<li><a href='about.html'>About</a>
<li><a href='docs.html'>Documentation</a>
<li><a href='download.html'>Download</a>
<li><a href='support.html'>Support</a>
<li><a href='prosupport.html'>Purchase</a>
</ul>
</div>
<div class="searchmenu" id="searchmenu">
<form method="GET" action="search">
<select name="s" id="searchtype">
<option value="d">Search Documentation</option>
<option value="c">Search Changelog</option>
</select>
<input type="text" name="q" id="searchbox" value="">
<input type="submit" value="Go">
</form>
</div>
</div>
<script>
function toggle_div(nm) {
var w = document.getElementById(nm);
if( w.style.display=="block" ){
w.style.display = "none";
}else{
w.style.display = "block";
}
}
function toggle_search() {
var w = document.getElementById("searchmenu");
if( w.style.display=="block" ){
w.style.display = "none";
} else {
w.style.display = "block";
setTimeout(function(){
document.getElementById("searchbox").focus()
}, 30);
}
}
function div_off(nm){document.getElementById(nm).style.display="none";}
window.onbeforeunload = function(e){div_off("submenu");}
/* Disable the Search feature if we are not operating from CGI, since */
/* Search is accomplished using CGI and will not work without it. */
if( !location.origin || !location.origin.match || !location.origin.match(/http/) ){
document.getElementById("search_menubutton").style.display = "none";
}
/* Used by the Hide/Show button beside syntax diagrams, to toggle the */
function hideorshow(btn,obj){
var x = document.getElementById(obj);
var b = document.getElementById(btn);
if( x.style.display!='none' ){
x.style.display = 'none';
b.innerHTML='show';
}else{
x.style.display = '';
b.innerHTML='hide';
}
return false;
}
var antiRobot = 0;
function antiRobotGo(){
if( antiRobot!=3 ) return;
antiRobot = 7;
var j = document.getElementById("mtimelink");
if(j && j.hasAttribute("data-href")) j.href=j.getAttribute("data-href");
}
function antiRobotDefense(){
document.body.onmousedown=function(){
antiRobot |= 2;
antiRobotGo();
document.body.onmousedown=null;
}
document.body.onmousemove=function(){
antiRobot |= 2;
antiRobotGo();
document.body.onmousemove=null;
}
setTimeout(function(){
antiRobot |= 1;
antiRobotGo();
}, 100)
antiRobotGo();
}
antiRobotDefense();
</script>


<div class="rightsidebar desktoponly border2px">
<h3 align="center">Common Links</h3>
<ul class=nounderline>
<li> <a href="features.html">Features</a> </li>
<li> <a href="whentouse.html">When to use SQLite</a> </li>
<li> <a href="quickstart.html">Getting Started</a> </li>
<li> <a href="https://sqlite.org/fiddle">Try it live!</li>
<li> <a href="lang.html">SQL Syntax</a>
<ul>
<li> <a href="pragma.html#toc">Pragmas</a>
<li> <a href="lang_corefunc.html">SQL functions</a>
<li> <a href="lang_datefunc.html">Date &amp; time functions</a>
<li> <a href="lang_aggfunc.html#aggfunclist">Aggregate functions</a>
<li> <a href="windowfunctions.html#biwinfunc">Window functions</a>
<li> <a href="lang_mathfunc.html">Math functions</a>
<li> <a href="json1.html">JSON functions</a>
</ul>
</li>
<li> <a href="c3ref/intro.html">C/C++ Interface Spec</a>
<ul>
<li> <a href="cintro.html">Introduction</a>
<li> <a href="c3ref/funclist.html">List of C-language APIs</a>
</ul>
</li>
<li> <a href="tclsqlite.html">The TCL Interface Spec</a>
<li> <a href="quirks.html">Quirks and Gotchas</a> </li>
<li> <a href="faq.html">Frequently Asked Questions</a> </li>
<li> <a href="https://www.sqlite.org/src/timeline">Commit History</a> </li>
<li> <a href="chronology.html">Prior Releases</a>
<li> <a href="https://www.sqlite.org/src/wiki?name=Bug+Reports">Bugs</a> </li>
<li> <a href="news.html">News</a> </li>
</ul>

</div>

<p>SQLite is a C-language library that implements a
<a href="footprint.html">small</a>,
<a href="fasterthanfs.html">fast</a>,
<a href="selfcontained.html">self-contained</a>,
<a href="hirely.html">high-reliability</a>,
<a href="fullsql.html">full-featured</a>,
SQL database engine.
SQLite is the <a href="mostdeployed.html">most used</a> database engine in the world.
SQLite is built into all mobile phones and most computers and
comes bundled inside countless other applications that people
use every day.
<a href="about.html">More Information...</a>

<p>
SQLite <a href="https://sqlite.org/src">source code</a>
is in the <a href="copyright.html">public-domain</a> and is free to
everyone to use for any purpose.

<h3>Latest Release</h3>
<a href="releaselog/3_53_4.html">Version 3.53.4</a> (2026-07-24).
<a class="button" href="download.html">Download</a>
<a class="button" href="chronology.html">Prior Releases</a>

<div class="mobileonly">
<h3>Common Links</h3>
<ul class=nounderline>
<li> <a href="features.html">Features</a> </li>
<li> <a href="whentouse.html">When to use SQLite</a> </li>
<li> <a href="quickstart.html">Getting Started</a> </li>
<li> <a href="https://sqlite.org/fiddle">Try it live!</li>
<li> <a href="lang.html">SQL Syntax</a>
<ul>
<li> <a href="pragma.html#toc">Pragmas</a>
<li> <a href="lang_corefunc.html">SQL functions</a>
<li> <a href="lang_datefunc.html">Date &amp; time functions</a>
<li> <a href="lang_aggfunc.html#aggfunclist">Aggregate functions</a>
<li> <a href="windowfunctions.html#biwinfunc">Window functions</a>
<li> <a href="lang_mathfunc.html">Math functions</a>
<li> <a href="json1.html">JSON functions</a>
</ul>
</li>
<li> <a href="c3ref/intro.html">C/C++ Interface Spec</a>
<ul>
<li> <a href="cintro.html">Introduction</a>
<li> <a href="c3ref/funclist.html">List of C-language APIs</a>
</ul>
</li>
<li> <a href="tclsqlite.html">The TCL Interface Spec</a>
<li> <a href="quirks.html">Quirks and Gotchas</a> </li>
<li> <a href="faq.html">Frequently Asked Questions</a> </li>
<li> <a href="https://www.sqlite.org/src/timeline">Commit History</a> </li>
<li> <a href="chronology.html">Prior Releases</a>
<li> <a href="https://www.sqlite.org/src/wiki?name=Bug+Reports">Bugs</a> </li>
<li> <a href="news.html">News</a> </li>
</ul>

</div>

<h3>Sponsors</h3>

<p>SQLite is made possible in part by sponsors and
<a href="consortium.html">SQLite Consortium</a> members, including:</p>
<a name="sponsors"></a>
<style>
#sponsors {
  margin:auto;
  width:80%;
}
.onesponsor a img {
  width:200px;
  max-width:200px;
  padding:1ex;
}
</style>
<div id="sponsors"></div>
<script>
  var sponsors = [{
    "name":"Bloomberg",
    "href":"https://www.techatbloomberg.com/",
    "src":"bloomberg.png",
    "wx":0
  },{
    "name":"Bentley",
    "href":"https://www.bentley.com/",
    "src":"bentley.gif",
    "wx":0
  },{
    "name":"NDS",
    "href":"http://www.nds-association.org/",
    "src":"nds.png",
    "wx":0
  },{
    "name":"Expensify",
    "href":"https://www.expensify.com/",
    "src":"expensify.png",
    "wx":225,
    "hx":32
  },{
    "name":"Reportr",
    "href":"https://reportr.com/?utm_source=sqlite",
    "src":"reportr.png",
    "wx":0
  }];

  for(var i=0; i<sponsors.length; i++){sponsors[i].idx = Math.random();}
  sponsors.sort(function(a,b){return a.idx-b.idx});
  var h = "";
  for(var i=0; i<sponsors.length; i++){
    h += "<span class='onesponsor'><a href='";
    h += sponsors[i].href;
    h += "'><img src='images/foreignlogos/";
    h += sponsors[i].src + "'";
    var altText = sponsors[i].name;
    if( altText ){
      h += " alt='" + altText + "'";
    }
    h += ">";
    if( sponsors[i].text ){
      h += "<span class='sponsor-text'>" + sponsors[i].text + "</span>";
    }
    h += "</a></span>\n";
    if( (i%2)==1 && i<sponsors.length-1 ){
      h += "<br>\n";
    }
  }
  document.getElementById("sponsors").innerHTML = h;

</script>
<br clear="both">
<p align="center"><small><i>This page was last updated on 2026-08-14 19:21:30Z </small></i></p>

A.2. Запит без захисту з'єднання
Команда:curl.exe -v http://neverssl.com

Вивід:
* Host neverssl.com:80 was resolved.
* IPv6: (none)
* IPv4: 34.223.124.45
*   Trying 34.223.124.45:80...
* Established connection to neverssl.com (34.223.124.45 port 80) from 10.1.8.239 port 61780
* using HTTP/1.x
> GET / HTTP/1.1
> Host: neverssl.com
> User-Agent: curl/8.16.0
> Accept: */*
>
* Request completely sent off
< HTTP/1.1 200 OK
< Date: Thu, 17 Sep 2026 14:10:47 GMT
< Server: Apache/2.4.68 ()
< Upgrade: h2,h2c
< Connection: Upgrade
< Last-Modified: Wed, 29 Jun 2022 00:23:33 GMT
< ETag: "f79-5e28b29d38e93"
< Accept-Ranges: bytes
< Content-Length: 3961
< Vary: Accept-Encoding
< Content-Type: text/html; charset=UTF-8
<
<html>
        <head>
                <title>NeverSSL - Connecting ... </title>
                <style>
                body {
                        font-family: Montserrat, helvetica, arial, sans-serif;
                        font-size: 16x;
                        color: #444444;
                        margin: 0;
                }
                h2 {
                        font-weight: 700;
                        font-size: 1.6em;
                        margin-top: 30px;
                }
                p {
                        line-height: 1.6em;
                }
                .container {
                        max-width: 650px;
                        margin: 20px auto 20px auto;
                        padding-left: 15px;
                        padding-right: 15px
                }
                .header {
                        background-color: #42C0FD;
                        color: #FFFFFF;
                        padding: 10px 0 10px 0;
                        font-size: 2.2em;
                }
                .notice {
                        background-color: red;
                        color: white;
                        padding: 10px 0 10px 0;
                        font-size: 1.25em;
                        animation: flash 4s infinite;
                }
                @keyframes flash {
                0% {
                        background-color: red;
                }
                50% {
                        background-color: #AA0000;
                }
                0% {
                        background-color: red;
                }
                }
                <!-- CSS from Mark Webster https://gist.github.com/markcwebster/9bdf30655cdd5279bad13993ac87c85d -->
                </style>

                <script>
                        var adjectives = [ 'cool' , 'calm' , 'relaxed', 'soothing', 'serene', 'slow',
                                                        'beautiful', 'wonderful', 'wonderous', 'fun', 'good',
                                                        'glowing', 'inner', 'grand', 'majestic', 'astounding',
                                                        'fine', 'splendid', 'transcendent', 'sublime', 'whole',
                                                        'unique', 'old', 'young', 'fresh', 'clear', 'shiny',
                                                        'shining', 'lush', 'quiet', 'bright', 'silver' ];

                        var nouns =       [ 'day', 'dawn', 'peace', 'smile', 'love', 'zen', 'laugh',
                                                        'yawn', 'poem', 'song', 'joke', 'verse', 'kiss', 'sunrise',
                                                        'sunset', 'eclipse', 'moon', 'rainbow', 'rain', 'plan',
                                                        'play', 'chart', 'birds', 'stars', 'pathway', 'secret',
                                                        'treasure', 'melody', 'magic', 'spell', 'light', 'morning'];

                        var prefix =
                                        // Choose 3 zen adjectives
                                        adjectives.sort(function(){return 0.5-Math.random()}).slice(-3).join('')
                                        +
                                        // Coupled with a zen noun
                                        nouns.sort(function(){return 0.5-Math.random()}).slice(-1).join('');
                        window.location.href = 'http://' + prefix + '.neverssl.com/online';
                </script>
        </head>
        <body>
        <noscript>
                <div class="notice">
                        <div class="container">
                                ⚠️ JavaScript appears to be disabled. NeverSSL's cache-busting works better if you enable JavaScript for <code>neverssl.com</code>.
                        </div>
                </div>
        </noscript>
        <div class="header">
                <div class="container">
                <h1>NeverSSL</h1>
                </div>
        </div>
        <div class="content">
        <div class="container">

        <h1 id="status"></h1>
        <script>document.querySelector("#status").textContent = "Connecting ...";</script>
        <noscript>

                <h2>What?</h2>
                <p>This website is for when you try to open Facebook, Google, Amazon, etc
                on a wifi network, and nothing happens. Type "http://neverssl.com"
                into your browser's url bar, and you'll be able to log on.</p>

                <h2>How?</h2>
                <p>neverssl.com will never use SSL (also known as TLS). No
                encryption, no strong authentication, no <a
                href="https://en.wikipedia.org/wiki/HTTP_Strict_Transport_Security">HSTS</a>,
                no HTTP/2.0, just plain old unencrypted HTTP and forever stuck in the dark
                ages of internet security.</p>

                <h2>Why?</h2>
                <p>Normally, that's a bad idea. You should always use SSL and secure
                encryption when possible. In fact, it's such a bad idea that most websites
                are now using https by default.</p>

                <p>And that's great, but it also means that if you're relying on
                poorly-behaved wifi networks, it can be hard to get online.  Secure
                browsers and websites using https make it impossible for those wifi
                networks to send you to a login or payment page. Basically, those networks
                can't tap into your connection just like attackers can't. Modern browsers
                are so good that they can remember when a website supports encryption and
                even if you type in the website name, they'll use https.</p>

                <p>And if the network never redirects you to this page, well as you can
                see, you're not missing much.</p>

        <a href="https://twitter.com/neverssl">Follow @neverssl</a>

        </noscript>

        </div>
        </div>

        </body>
</html>

A.3. Запит до служби доменних імен
Windows: Resolve-DnsName sqlite.org
Команда (перше виконання):Resolve-DnsName sqlite.org
Вивід:Name                                           Type   TTL   Section    IPAddress
----                                           ----   ---   -------    ---------
sqlite.org                                     AAAA   109   Answer     2600:3c02::f03c:95ff:fe07:695
sqlite.org                                     A      173   Answer     194.195.208.62
Команда (повторне виконання через 5–7 хвилин):Resolve-DnsName sqlite.org
Вивід:
Name                                           Type   TTL   Section    IPAddress
----                                           ----   ---   -------    ---------
sqlite.org                                     AAAA   263   Answer     2600:3c02::f03c:95ff:fe07:695
sqlite.org                                     A      14    Answer     194.195.208.62

**Зафіксовані значення:**

| Параметр | Перше виконання | Повторне виконання |
|---|---|---|
| Час виконання (год:хв) | 16:31 | 16:35 |
| IP-адреса | 194.195.208.62 | 194.195.208.62 |
| Значення TTL | 173 | 14 |

A.4. Контрольний ресурс
Команда:curl.exe -v https://google.com
Вивід:
* Host google.com:443 was resolved.
* IPv6: (none)
* IPv4: 172.217.23.238
*   Trying 172.217.23.238:443...
* schannel: disabled automatic use of client certificate
* ALPN: curl offers http/1.1
* ALPN: server accepted http/1.1
* Established connection to google.com (172.217.23.238 port 443) from 10.1.8.239 port 59374
* using HTTP/1.x
> GET / HTTP/1.1
> Host: google.com
> User-Agent: curl/8.16.0
> Accept: */*
>
* Request completely sent off
* schannel: remote party requests renegotiation
* schannel: renegotiating SSL/TLS connection
* schannel: SSL/TLS connection renegotiated
< HTTP/1.1 301 Moved Permanently
< Location: https://www.google.com/
< Content-Type: text/html; charset=UTF-8
< Content-Security-Policy-Report-Only: object-src 'none';base-uri 'self';script-src 'nonce-xbGb_jza1zLDZ9N8Yr64fQ' 'strict-dynamic' 'report-sample' 'unsafe-eval' 'unsafe-inline' https: http:;report-uri https://csp.withgoogle.com/csp/gws/other-hp
< Date: Thu, 17 Sep 2026 14:39:23 GMT
< Expires: Sat, 17 Oct 2026 14:39:23 GMT
< Cache-Control: public, max-age=2592000
< Server: gws
< Content-Length: 220
< X-XSS-Protection: 0
< X-Frame-Options: SAMEORIGIN
< Alt-Svc: h3=":443"; ma=2592000,h3-29=":443"; ma=2592000
<
<HTML><HEAD><meta http-equiv="content-type" content="text/html;charset=utf-8">
<TITLE>301 Moved</TITLE></HEAD><BODY>
<H1>301 Moved</H1>
The document has moved
<A HREF="https://www.google.com/">here</A>.
</BODY></HTML>

A.5. Ресурси з некоректною конфігурацією сертифіката
Випадок 1
curl.exe -v https://expired.badssl.com
* Host expired.badssl.com:443 was resolved.
* IPv6: (none)
* IPv4: 104.154.89.105
*   Trying 104.154.89.105:443...
* schannel: disabled automatic use of client certificate
* ALPN: curl offers http/1.1
* schannel: next InitializeSecurityContext failed: SEC_E_CERT_EXPIRED (0x80090328) - The received certificate has expired.
* closing connection #0
curl: (35) schannel: next InitializeSecurityContext failed: SEC_E_CERT_EXPIRED (0x80090328) - The received certificate has expired.
Випадок 2
curl.exe -v https://wrong.host.badssl.com
* Host wrong.host.badssl.com:443 was resolved.
* IPv6: (none)
* IPv4: 104.154.89.105
*   Trying 104.154.89.105:443...
* schannel: disabled automatic use of client certificate
* ALPN: curl offers http/1.1
* schannel: SNI or certificate check failed: SEC_E_WRONG_PRINCIPAL (0x80090322) - The target principal name is incorrect.
* closing connection #0
curl: (60) schannel: SNI or certificate check failed: SEC_E_WRONG_PRINCIPAL (0x80090322) - The target principal name is incorrect.
More details here: https://curl.se/docs/sslcerts.html

curl failed to verify the legitimacy of the server and therefore could not
establish a secure connection to it. To learn more about this situation and
how to fix it, please visit the webpage mentioned above.
Випадок  3
curl.exe -v https://self-signed.badssl.com
 Host self-signed.badssl.com:443 was resolved.
* IPv6: (none)
* IPv4: 104.154.89.105
*   Trying 104.154.89.105:443...
* schannel: disabled automatic use of client certificate
* ALPN: curl offers http/1.1
* schannel: SEC_E_UNTRUSTED_ROOT (0x80090325) - The certificate chain was issued by an authority that is not trusted.
* closing connection #0
curl: (60) schannel: SEC_E_UNTRUSTED_ROOT (0x80090325) - The certificate chain was issued by an authority that is not trusted.
More details here: https://curl.se/docs/sslcerts.html

curl failed to verify the legitimacy of the server and therefore could not
establish a secure connection to it. To learn more about this situation and
how to fix it, please visit the webpage mentioned above.

## Частина B. Власна модель рівнів

**Кількість виділених груп:** 6

| № | Назва групи (власне формулювання) | Рядки виводу, віднесені до групи | Обґрунтування |
|---|---|---|---|
| 1 | Обмін вебданими | `> GET / HTTP/1.1`, `> Host: sqlite.org`, `< HTTP/1.1 200 OK`, `< Content-type: text/html; charset=utf-8` | Ці рядки показують безпосередній обмін HTTP-повідомленнями між клієнтом і вебсервером: відправлення запиту та отримання відповіді. |
| 2 | Захист з'єднання | `schannel: remote party requests renegotiation`, `schannel: renegotiating SSL/TLS connection`, `schannel: SSL/TLS connection renegotiated` | Рядки відображають роботу механізму SSL/TLS, який забезпечує захищений обмін даними. |
| 3 | Узгодження протоколу | `ALPN: curl offers http/1.1`, `ALPN: server did not agree on a protocol. Uses default.`, `using HTTP/1.x` | Клієнт і сервер визначають, який варіант протоколу буде використаний для подальшого обміну. |
| 4 | Визначення мережевої адреси | `Host sqlite.org:443 was resolved.`, `IPv6: (none)`, `IPv4: 194.195.208.62` | Доменне ім'я перетворюється на IP-адресу, необхідну для встановлення мережевого з'єднання. |
| 5 | Встановлення з'єднання з вузлом | `Trying 194.195.208.62:443...`, `Established connection to sqlite.org (194.195.208.62 port 443) from 10.1.8.239 port 52932` | Клієнт використовує отриману IP-адресу та порт 443 для встановлення з'єднання із сервером. |
| 6 | Передавання даних через встановлене з'єднання | `Request completely sent off`, `Connection #0 to host sqlite.org:443 left intact` | Ці повідомлення характеризують стан створеного з'єднання під час передавання даних та після завершення запиту. |

. Контрольні питання
Відповіді подають у складі звіту

1. Скільки рядків діагностичного виводу передує отриманню даних сторінки (завдання A.1)?
Перед отриманням даних сторінки curl виводить діагностичні рядки, які описують визначення IP-адреси, встановлення з'єднання, узгодження захищеного HTTPS-з'єднання, відправлення HTTP-запиту та отримання заголовків відповіді сервера.
2. Які рядки наявні у виводі завдання A.1 і відсутні у виводі завдання A.2? Чим це зумовлено?
У виводі A.1 є рядки, пов'язані з SSL/TLS, наприклад schannel та ALPN. У A.2 таких рядків немає. Це зумовлено тим, що в A.1 використовується HTTPS із захищеним TLS-з'єднанням, а в A.2 — звичайний HTTP без TLS.
3. Звідки у виводі з'явилося значення 443 , якщо його не було вказано в адресі?
443 — це стандартний порт протоколу HTTPS. Оскільки в адресі було вказано https://sqlite.org, програма curl автоматично використала порт 443.
4. Як змінилося значення TTL за час між двома запитами (A.3)? Що означає це число?
У моїх запитах значення TTL для IPv4 змінилося з 173 до 14, тобто зменшилося на 159 секунд. TTL (Time To Live) показує, скільки часу DNS-запис може залишатися в кеші до його оновлення.
5. Чим відрізняються між собою три причини помилок із завдання A.5? Сформулювати кожну однією фразою.

| Випадок | Причина недовіри |
|---|---|
| `expired` | Термін дії сертифіката закінчився. |
| `wrong.host` | Сертифікат виданий для іншого імені хоста. |
| `self-signed` | Сертифікат є самопідписаним і не має довіреного центру сертифікації. |

6. Три рядки з власних виводів, про які не йшлося на лекції 1:

| № | Рядок виводу | Джерело (номер завдання) |
|---|---|---|
| 1 | `* schannel: disabled automatic use of client certificate` | A.1 |
| 2 | `* ALPN: server did not agree on a protocol. Uses default.` | A.1 |
| 3 | `* schannel: remote party requests renegotiation` | A.1 |

Висновки
150–300 слів. Спиратися на власні спостереження, а не на матеріал лекції.
D.1. Що виявилося неочевидним або несподіваним
Назвати конкретно, з посиланням на рядок виводу.
Для мене було несподіваним, що під час одного HTTPS з'єднання сервер може запросити повторне узгодження TLS. `* schannel: remote party requests renegotiation` у виводі A.1. До виконання роботи я очікував, що захищене з'єднання узгоджується лише один раз на початку.
D.2. Чому саме така кількість груп у частині B
На якій підставі ухвалено рішення. Що змусило б його змінити.
Я виділив 6 груп, тому що рядки виводу вдалося розділити на шість різних за призначенням етапів. Рядки, які описували схожі дії, я об'єднував в одну групу. Я б змінив кількість груп, якби у виводі з'явилися додаткові дії, які не можна було б логічно віднести до жодної з цих шести груп.
D.3. Питання, яке залишилося без відповіді
Чому сервер `sqlite.org` декілька разів запитував повторне узгодження SSL/TLS під час одного з'єднання?

## Використання штучного інтелекту

**Факт використання:** використано

**Установлений рівень для цієї роботи:** Р3 — ШІ як співвиконавець

**Фактичний рівень використання:** Р3

### Використані системи

| Система | Версія або модель | Період використання |
|---|---|---|
| ChatGPT | GPT-5.6 Sol | 17.09.2026 |

### Промпти

| № | Розділ роботи | Текст промпта |
|---|---|---|
| 1 | Контрольні питання | `Які рядки наявні у виводі завдання A.1 і відсутні у виводі завдання A.2? Чим це зумовлено?` |
| 2 | Висновки, D.2 | `D.2. Чому саме така кількість груп у частині B. На якій підставі ухвалено рішення. Що змусило б його змінити.  |
| 3 | Висновки, D.3 | `D.3. Питання, яке залишилося без відповіді` |

### Дії з отриманим результатом

| № промпта | Що перевірено | Що змінено | Що відхилено і чому |
|---|---|---|---|
| 1 | Відповіді зіставлено з власними виводами A.1 та A.2. | Формулювання адаптовано до отриманих результатів. | Не використано твердження, які не підтверджувалися власними виводами. |
| 2 | Перевірено відповідність кількості груп таблиці частини B. | Кількість груп виправлено з 5 на 6 після перевірки власної таблиці. | Відхилено початковий варіант із 5 групами, оскільки фактично в таблиці B було 6 груп. |
| 3 | Перевірено наявність відповідного рядка у власному виводі A.1. | Питання сформульовано на основі рядка `remote party requests renegotiation`. | Інші варіанти не використано. |

### Підтвердження

Підтверджую, що всі наведені в цьому звіті виводи команд отримано мною особисто внаслідок фактичного виконання відповідних дій, а відомості цього розділу є повними та достовірними.
