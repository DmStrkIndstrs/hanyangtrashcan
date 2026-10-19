# 여사님 몰래 마라탕 버리기

한양대 청소 여사님 눈을 피해 마라탕·떡볶이를 일반쓰레기통에 몰래 버리는 브라우저 잠입 게임.

`index.html` 하나로 돌아갑니다. 브라우저로 열거나 GitHub Pages로 배포하세요.

## 조작
- 이동: WASD / 방향키 (모바일: 화면 터치)
- 달리기: Shift (시끄러워서 여사님이 돌아봄)
- 버리기: 쓰레기통 앞에서 Space 또는 버튼 꾹

## 스테이지
1. 학생회관 학생식당
2. 제1공학관 3층 복도
3. 백남학술정보관 열람실 (여사님 두 분)

## 랭킹 켜기 (Firebase 익명 로그인)
설정 전에도 게임은 되고, 랭킹 영역에 "연결 전" 안내만 보여요.

1. https://console.firebase.google.com 에서 프로젝트 만들기 (Analytics는 꺼도 됨)
2. **Build → Authentication → 시작하기 → Sign-in method → 익명(Anonymous)** 사용 설정
3. **Build → Firestore Database → 데이터베이스 만들기** (프로덕션 모드, 위치 `asia-northeast3 (서울)`)
4. Firestore **규칙** 탭에 이 레포의 `firestore.rules` 내용을 붙여넣고 **게시**
5. **프로젝트 설정 → 내 앱 → 웹(</>) 앱 추가** 후 나오는 `firebaseConfig`를 `firebase-config.js`의 `null` 자리에 붙여넣기
6. **Authentication → 설정 → 승인된 도메인**에 `dmstrkindstrs.github.io` (커스텀 도메인을 쓰면 그 도메인도) 추가
7. 커밋하고 푸시하면 끝

랭킹은 1→3 스테이지를 끝낸 총 시간(걸려서 다시 한 시간 포함) 기준이고, 익명 계정마다 최고 기록 하나만 남아요.
점수는 브라우저에서 계산해 올리는 구조라 마음먹고 조작하는 것까지 막지는 못해요. 규칙에서 20초 미만 같은 비정상 기록은 거부합니다.
