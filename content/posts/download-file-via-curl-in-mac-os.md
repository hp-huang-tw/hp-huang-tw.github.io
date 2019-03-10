---
title: "Download File via Curl in Mac OS"
author: "hp.huang"
date: 2019-01-28T15:40:04+08:00
draft: false
categories: [shell]
tags: [shell, curl]
---

在GNU環境裡常用的下載檔案軟體為 `Wget`,
例如:
{{< highlight bash >}}
wget http://testssl.sh/testssl.sh
{{< /highlight >}}

我的開發環境是 mac os,
mac 的預設裡面並沒有安裝 `Wget`, 需要透過 homebrew 另外下載安裝

但小妹又很懶得在電腦裡面多裝一套件，於是尋找是否有了不需要透過 `Wget` 的做法 
原來透過 `curl` 我們就可以達到下載檔案的目標了!

使用 `curl` 下載檔案的方法非常的簡單
{{< highlight bash >}}
curl http(s)://example.com/filename.suffix -o "output.suffix"`
{{< /highlight >}}

所以 把剛剛的指令改成以下就可以囉!
{{< highlight bash >}}
curl http://testssl.sh/testssl.sh -o "testssl.sh"
{{< /highlight >}}

### Reference
* GNU Wget - https://www.gnu.org/software/wget/
* curl manpage - https://curl.haxx.se/docs/manpage.html
