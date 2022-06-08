---
layout: post
title: You're up and running!
---

sed 파일 처리 example Memoranda

down file txt 배포 가공 가공
😉
jenkins “Multi-line String Parameter” 에서 복붙된 DEPLOY_LIST
를 받아서, 아래 Build 영역, Create/Update Text File에 정의된 alc_stock_deploy_list.txt로 받는다.
ex)
File Path : alc_stock_deploy_list.txt
Create at Workspace : true
Text File Content : ${DEPLOY_LIST}

위에서 받아온 alc_stock_deploy_list.txt를 가공해야 한다.
sed 명령어로 말이다.

sed ‘s/ //g;s/"//g;s/₩///g;/$/d’ /app/deploy_prod/alc_stock_deploy_list.txt > /app/deploy_prod/target_alc.txt
echo “” >> /app/deploy_prod/target_alc.txt
rm -rf /app/deploy_prod/alc_stock_deploy_list.txt

