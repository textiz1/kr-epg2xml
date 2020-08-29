# kr-epg2xml
TVHeadend EPG2XML for Synology NAS - wiserain/tvheadend

사용법
Synology - Wiserain/tvheadend
/docker/wiserain-tvheadend/epg2xml에서 모두 파일 넣어돼요.

Ubuntu - tvheadend
/home 목록이 놓어돼요.
tv_grab_file 수정후 자기 목록으로 바꿔요. https://github.com/Rigolo/tv-grab-file
"cat ~/.xmltv/tv_grab_file.xmltv
  exit 0" 에서
"cat ~(자기기기목록)/xmltv.xml
  exit 0"
  
tv_grab_kr_sk 자기 목록으로 바꿔요. https://github.com/wiserain/docker-tvheadend/blob/master/root/usr/bin/tv_grab_kr_sk
"python3 -u /epg2xml/epg2xml.py -i SK -o /epg2xml/xml/xmltv.xml
    cat /epg2xml/xml/xmltv.xml" 에서
"python3 -u (자기기기목록)/epg2xml.py -i SK -o (자기기기목록)/xml/xmltv.xml
    cat (자기기기목록)/xml/xmltv.xml"

파일넣어후, 기기ssh후, epg2xml넣은 목록에서 찾아요. 

Synology - Wiserain/tvheadend
찾는후, 이 명령을 입력해, >sudo chmod -R 777 /(기기목록)/epg2xml, 그후이 패스워드 입력해요. 그후, TVheadend에서 채널/EPG댑에 EPG그래버 모듈안에서 내부:XMLTV (SK) 겨짐후, 잠시만 기다려주세요. 채널이 많다니까, 좀 기다려해야곘다. 

Ubuntu - tvheadend
찾는후, 이 명령을 입력해, >sudo chmod -R 777 /(기기목록)/epg2xml, 그후이 패스워드 입력해요. 그후, TVheadend에서 채널/EPG댑에 EPG그래버 모듈안에서 내부:tv_grab_file 겨짐후, 잠시만 기다려주세요. 채널이 많다니까, 좀 기다려해야곘다. 

