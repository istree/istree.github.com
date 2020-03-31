---
layout: dev
title: Jenkins
---
## Jenkins mac os ip주소 설정

host주소로 Jenkins서버에 액세스 하고싶은 경우

다음 파일을 편집한다.

```bash
sudo vim /usr/local/Cellar/jenkins/2.209/homebrew.mxcl.jenkins.plist 
```
httpListenAddress 매개변수가 기본적으로 127.0.0.1로 되어있다. 0.0.0.0 으로 바꾸고 저장.

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
  <dict>
    <key>Label</key>
    <string>homebrew.mxcl.jenkins</string>
    <key>ProgramArguments</key>
    <array>
      <string>/usr/libexec/java_home</string>
      <string>-v</string>
      <string>1.8</string>
      <string>--exec</string>
      <string>java</string>
      <string>-Dmail.smtp.starttls.enable=true</string>
      <string>-jar</string>
      <string>/usr/local/opt/jenkins/libexec/jenkins.war</string>
      <string>--httpListenAddress=0.0.0.0</string>
      <string>--httpPort=9040</string>
    </array>
    <key>RunAtLoad</key>
    <true/>
  </dict>
</plist>
```