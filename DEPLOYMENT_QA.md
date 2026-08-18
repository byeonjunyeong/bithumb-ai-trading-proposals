# 배포 QA

## 로컬 GitHub Pages 구조 검증

GitHub Pages와 같은 정적 하위 경로 구조를 로컬 4177 포트에서 재현했다. `http://127.0.0.1:4177/bithumb/`를 320×720px로 열었을 때 문서 제목은 `빗썸 AI 활용 토큰 트레이딩 챌린지 | 빗썸 제안용`으로 확인됐고 React 페이지가 정상 부팅됐다.

두 빌드의 `/assets/` 경로는 각 페이지의 `./assets/`로, `/manus-storage/` 경로는 공통 `../manus-storage/`로 변환했다. 빗썸용·미나라용 번들이 참조하는 정적 스토리지 자산 29개를 저장소에 포함했고 누락 파일은 0개다.

빗썸 제안용 320px 페이지에서 `clientWidth`와 `scrollWidth`는 모두 320px이었다. 제외 브랜드 노출은 0건이고, Hero는 로컬 `hero-neutral`, LAB 01은 로컬 `lab01-neutral-v2` 자산으로 로드됐다. 화면에 진입한 이미지의 로딩 오류도 0건이었다.

미나라 제안용 하위 경로는 `http://127.0.0.1:4177/minara/`에서 정상 부팅됐고 문서 제목은 `빗썸 AI 활용 토큰 트레이딩 챌린지 | 미나라AI 제안용`으로 확인됐다.

미나라 제안용 320px 페이지에서도 `clientWidth`와 `scrollWidth`는 모두 320px이었다. 본문에 미나라AI 교육자 표기가 유지됐고, Hero는 로컬 `poster-hero-minara-v3`, LAB 01은 로컬 `lab01-poster` 자산으로 로드됐다. 화면에 진입한 이미지의 로딩 오류는 0건이었다.

하위 경로·자산 로딩 검증 후 브라우저 콘솔은 오류 0건, 경고 0건이었다.

## 공식 주소 확인

GitHub 사용자 사이트 자동 배포가 완료돼 루트·빗썸용·미나라용 경로가 모두 HTTP 200을 반환했다. 빗썸 공개 페이지의 제목과 본문은 빗썸 제안용 무미나라 문구로 표시되고, Hero·LAB 01·혜택 이미지가 `https://byeonjunyeong.github.io/manus-storage/`에서 제공되는 것을 확인했다.

미나라 공개 페이지는 `빗썸 AI 활용 토큰 트레이딩 챌린지 | 미나라AI 제안용` 제목과 미나라AI 주관·교육 진행자 문구를 표시한다. 초기 캡처 직후에는 종이 배경이 먼저 표시됐지만 재확인 시 2752×1536px 미나라 Hero가 정상 로드됐고, LAB 01과 운영기관 자산도 공개 `manus-storage` 경로에서 제공됐다.

최종 공식 주소는 루트 `https://byeonjunyeong.github.io/`, 빗썸 제안용 `https://byeonjunyeong.github.io/bithumb/`, 미나라 제안용 `https://byeonjunyeong.github.io/minara/`이다.
