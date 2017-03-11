# rtqkr
=======================

rtqkr는 우리나라 대표 포털인 네이버, 다음, 줌의 실시간 검색어와 그 순위를 수집하는 프로젝트입니다. 

각 사이트에서 제공하는 순위인 네이버(20위),다음(10위),줌(20위) 총 50개 키워드를 1분 마다 수집하고 있습니다.

수집 코드는 R의 기본 함수들을 활용했으며, 전체 코드는 toGoogleSheet.R 파일에 작성되어 있습니다.

각 포털의 실시간 검색어를 가져오는 수집 코드는 getData 폴더에 각 파일로 toGoogleSheet.R 에도 초기 불러오는 형태로 작성되어 있습니다.

2017넌 2월 기준 rocker/tidyverse:latest 도커 이미지를 사용했습니다.

1분마다 실행하는 것은 ubuntu의 crontab을 사용했습니다.

crontab 은 bash에서 crontab -e를 실행하고, crontabExam.txt 에 작성 예시가 들어가 있습니다. 예시는 5분 단위로 수집하는 내용입니다.

현재 수집하고 있는 데이터는 [리스트](https://docs.google.com/spreadsheets/d/1aJ2Bv8CCR4OhBoVdsQD16OWON89VwuaLYKDDP-OiTG4/edit)에 이름과 url을 관리하고 있습니다.

[zapier](https://zapier.com/)를 이용해서 new sheet가 생길때마다 list sheet에 내용을 기록하는 자동화 zap을 작성하였으며 5분마다 갱신됩니다.

google sheet는 200만 줄까지 작성할 수 있으며, 파일 업로드가 아니라면 용량을 차지하지 않아서 무한히 저장할 수 있습니다.

1분 단위로 기록하여 50개 * 60분 * 24시간 + 컬럼명 1줄 = 72001줄의 sheet가 필요하며 rtqk_날짜 의 파일 이름으로 매일 생성하고 있습니다.

trtqk_날짜 는 테스트 코드의 수집 데이터로 현재 수집코드의 개선을 위해서 병렬로 수행하고 있습니다.

크롤링 작업을 할 작은 서버에 대해서 기부 받습니다.

1분마다 수집하는 것에 대해서 신뢰도를 유지하기 어려운 부분이 있어서 여러 백업이 필요한 상황입니다.

기부는 [연락](mrchypark@gmail.com)주세요. 감사합니다.

