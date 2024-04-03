네이버에 사이트 등록하기!!
1. 내가 만든 사이트를 서버에 등록하기
 1. AWS 가입
    1. 구글 검색창에 'aws'라고 검색 (aws는 서버를 무료로 대여해 줌(부분유로))
    2. AWS 계정 생성 버튼 클릭!!
    3. '루트 사용자 이메일 주소', 'AWS 계정 이름' 입력
        '루트 사용자 이메일 주소' : ID로 쓸 이메일 주소
        'AWS 계정 이름' : 닉네임
    4. 이메일로 발송된 확인 코드 입력
    5. 비밀번호 생성
    6. 이름, 연락처 등 개인 정보 입력
    7. 영어로 주소 입력
    8. 카드 입력 (해외 결제되는 카드를 입력해야 함)

 2. AWS에 사이트 등록
    1. 회원 가입이 완료되면, 루트(관리자) 사용자로 로그인 함
    2. '검색'에 'S3'를 입력하고 '클라우드의 확장 가능한 스토리지' 선택
    3. '버킷 만들기' 선택
    4. 'AWS 리전' (서버 위치)에서 '서울' 선택
    5. '버킷 이름'에 사이트 이름 입력
    6. '모든 퍼블릭 엑세스 차단' 해제
    7. '버킷 만들기' 버튼 클릭
    8. 내가 만든 버킷을 선택하고, '권한' 탭 클릭
    9. '버킷 정책' -> '편집' 버튼을 클릭하고, 다음 코드 입력한 다음, '변경 사항 저장' 버튼 클릭
       {
            "Version": "2012-10-17",
            "Statement": [
                {
                    "Effect": "Allow",
                    "Principal": "*",
                    "Action": "s3:*",
                    "Resource": "arn:aws:s3:::jaekuky-practice.com/*"
                }
            ]
        }
    10. '권한 개요' -> '액세스'가 '퍼블릭'인지 확인
    11. '속성'탭 -> '정적 웹 사이트 호스팅' -> '편집' 버튼 클릭
    12. '정적 웹 사이트 호스팅' -> '활성화' -> '인덱스 문서'에 업로드할 html파일 이름 입력 (기본 값인 'index.html' 권장) -> '변경 사항 저장' 버튼 클릭
    13. '객체'탭 클릭 -> html, css 등 홈페이지 파일 업로드
    14. '요약' -> '대상'에 있는 웹 주소 클릭 
    15. '속성'탭 -> '정적 웹 사이트 호스팅'에 있는 주소가 내 홈페이지 주소임
    
3. 네이버에 내 사이트 등록
    1. '네이버 서치 어드바이저'(https://searchadvisor.naver.com/)에 접속
    2. '웹마스터 도구' 버튼 클릭
    3. '사이트 등록'에 내 홈페이지 주소 입력하고, 맨 우측에 있는 아이콘 클릭 
    4. '사이트 소유확인' -> 'HTML 태그' 복사
    5. 내 홈페이지 'index.html'의 <title>태그 위에 복사한 <meta> 태그 붙여넣기
    6. 내 홈페이지 'index.html'의 head 태그에 다음 <meta> 태그 추가
        <meta
        name="keyword"
        content="HTML, 코딩, 대전코딩, 코딩배우기, 둔산동 코딩"
        />
        <meta property="og:site_name" content="아이티코리아코딩" />
        <meta property="og:title" content="아이티코리아 류재국" />
        <meta property="og:description" content="HTML코딩, 대전코딩, 코딩배우기" />
        <meta property="og:locale" content="ko_KR" />
        <meta name="NaverBot" content="All" />
        <meta name="NaverBot" content="index,follow" />
        <meta name="Yeti" content="All" />
        <meta name="Yeti" content="index,follow" />
    7. 수정된 'index.html' 파일을 AWS에 업로드
    8. AWS에 'robot.txt', 'sitemap.xml' 업로드
