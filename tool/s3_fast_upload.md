1) 글로벌 python3 로 pip install awscli 설치 2) aws 자격증명 설정 2-1) aws iam 접속 2-2) 왼쪽에 사용자 네비게이션을 선택
2-3) 자신의 계정 클릭 접속
2-4) 보안 자격증명으로 간후 새로운 액세스 키 만들기
2-5) 팝업에서 비밀키.csv파일을 저장 (처음이자 마지막으로 보여줌.)
2-6) 팝업에서 secret키를 복사 하여 메모장에 일단 복사
2-7) 터미널로 돌아와 aws configure
2-8) 엑세스키 ID 는 액세스키 
2-9) 시크릿키는 메모장에 복사되어 있는 시크릿키
2-10) 리전은 ap-northeast-2
2-11) output 은 text
3) 자격증명 완료후 전역파일을 모음
3-1) python manage.py compilescss
3-2) python manage.py collectstatic
4) 이후 해당 파일들을 s3에 업로드
4-1) .static 폴더로 이동
4-2) aws s3 sync . s3://[s3_url]/ --acl public-read 명령어 실행
5) 끝