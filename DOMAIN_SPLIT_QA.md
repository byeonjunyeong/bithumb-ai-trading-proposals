# 독립 도메인 분리 QA

> **현재 배포 결정:** 독립 도메인 구매 전에는 사용자명이 없는 영어 Netlify 주소 2개를 임시 공식 주소로 사용한다. 기존 GitHub Pages는 소스 배포·복구 기준선으로 유지한다. 외부 명칭은 `빗썸용`과 `빗썸×미나라용`, 목표 슬러그는 각각 `bithumb-ai-skillup`과 `bithumb-x-minara` 계열로 확정한다.

## 빗썸용 도메인

사용자가 지정한 한글 도메인 `빗썸-skillup.com`은 DNS·서버 설정에서 `xn---skillup-5b17af13a.com`으로 변환된다. 현재 이 호스트는 DNS 조회 결과가 없고 HTTP 연결도 성립하지 않는다. .com RDAP 대체 조회의 최종 응답은 404였으므로, 도메인 등록 여부와 네임서버 설정을 등록기관에서 확인한 뒤 DNS를 연결해야 한다.

## 분리 원칙

빗썸 제안 버전과 일반 버전은 하위 경로가 아니라 각각 별도 공개 저장소·별도 Pages 배포·별도 루트 도메인으로 구성한다. 기존 `byeonjunyeong.github.io/bithumb/`와 `/minara/`는 새 독립 주소 검증이 끝난 뒤 외부 선택 화면에서 제거한다.

## 독립 기본 주소 검증

빗썸용은 `byeonjunyeong/bithumb-skillup-site` 저장소와 `https://byeonjunyeong.github.io/bithumb-skillup-site/` 주소로 분리했다. 공개 문서 제목은 빗썸 제안용이며 미나라 문구가 없고, 중립 Hero와 LAB 자산이 루트 `./manus-storage/`에서 정상 제공된다.

일반 버전은 `byeonjunyeong/general-skillup-site` 저장소와 `https://byeonjunyeong.github.io/general-skillup-site/` 주소로 분리했다. 공개 문서 제목은 일반 버전으로 정리했으며, 기관·Hero·LAB 01에는 교육 파트너 미나라AI가 자연스럽게 포함된다. 초기 화면에서 종이 배경이 먼저 표시된 뒤 2752×1536px Hero가 정상 로드되는 것을 재확인했다.

## 사용자명 없는 임시 공식 주소 대안

Netlify Drop 공식 안내에 따르면 빌드 결과 폴더 또는 ZIP을 업로드하면 누구나 접근 가능한 공개 링크를 무료로 생성할 수 있고, 대시보드에서 프로젝트명을 변경해 `프로젝트명.netlify.app` 주소를 정할 수 있다. 따라서 유료 독립 도메인 구매·DNS 연결 전에 `byeonjunyeong`이 보이지 않는 빗썸 제안 버전과 일반 버전의 독립 전달 주소를 먼저 만들 수 있다. 실제 공개 업로드는 사용자 확인 후 진행한다.

출처: https://app.netlify.com/drop

배포 화면의 실제 파일 입력은 `#drop-hero-file`이며 `.zip`, `.html`, `.htm`을 허용한다. 일반 라벨 요소는 업로드 대상이 아니므로, 이후 배포 자동화에서는 이 숨김 파일 입력을 직접 사용한다.

숨김 입력을 브라우저 화면에 임시 노출했고 `aria-label="정적 사이트 ZIP 업로드"`를 부여했다. 다음 단계에서 해당 입력으로 빗썸 제안 버전 ZIP을 업로드한다.

`bithumb-skillup-netlify.zip`의 파일 입력 업로드가 성공했으며 Netlify가 `Spinning up your site` 단계에서 첫 공개 주소를 생성 중이다.

빗썸 제안 버전 임시 주소는 `https://venerable-liger-248387.netlify.app`로 생성됐다. 사용자명은 포함되지 않지만, 현재 미소유 Drop 상태라 공통 비밀번호 `My-Drop-Site`로 보호되고 약 1시간 후 만료된다. 영구 공개와 주소명 변경을 위해 만료 전에 무료 계정으로 사이트 소유권을 확보해야 한다.

일반 버전용 새 Drop 화면은 첫 DOM 확인 시 `#drop-hero-file`이 아직 생성되지 않아 업로드 입력 노출을 보류했다. 페이지 렌더 완료를 확인한 뒤 같은 방식으로 재시도한다.

브라우저가 일시적으로 `about:blank`으로 초기화돼 새 Drop 화면을 다시 열었다. 재접속 후 업로드 라벨·FAQ·정적 파일 허용 안내가 정상 렌더링됐으며 일반 버전 ZIP 업로드를 재개할 수 있다.

재접속한 화면에서 `#drop-hero-file`을 정상 노출했고 일반 버전 정적 ZIP 업로드 대상 인덱스를 확보했다.

`general-skillup-netlify.zip` 업로드가 성공했고 Netlify가 두 번째 프로젝트를 생성했다. 현재 `Loading your project…` 단계이며 최종 임시 주소 생성 완료를 추가 확인한다.

일반 버전 임시 주소는 `https://taupe-cannoli-c52b72.netlify.app`로 생성됐다. 이 주소도 사용자명은 포함하지 않지만 미소유 Drop 상태라 공통 비밀번호 `My-Drop-Site`로 보호되고 약 1시간 후 만료된다. 두 사이트 모두 무료 계정으로 소유권을 확보한 뒤 비밀번호·만료 제한을 제거하고 사이트명을 각각 빗썸 제안 버전과 일반 버전으로 변경해야 한다.

## GitHub Pages 기준선 재검증

최종 호스팅 플랫폼을 GitHub Pages로 유지하기로 확정한 뒤 두 독립 저장소와 공개 주소를 재검증했다. `bithumb-skillup-site`와 `general-skillup-site`는 모두 공개 저장소이며 Pages 상태는 `built`, HTTPS 강제는 활성화, 커스텀 도메인은 아직 미설정이다. 두 기본 공개 주소는 모두 HTTP 200을 반환한다.

| 버전 | 배포 커밋 | 테스트 | TypeScript | 프로덕션 빌드 |
|---|---|---:|---:|---:|
| 빗썸 제안 버전 | `237568d89c9ed5fbe0dd8abf60b0dcf8aa7b1882` | 19개 통과 | 통과 | 통과 |
| 일반 버전 | `aafc44ab4f7234ca3e25fdcd2c3d9baade397ea7` | 19개 통과 | 통과 | 통과 |

상세 로그는 `/home/ubuntu/bithumb-token-trading-challenge-delivery/github-pages-baseline.txt`에 저장했다.

## 이전 Netlify 시험 철회 완료

Netlify Claim 브라우저 세션을 종료했고 두 임시 사이트의 소유권을 확보하지 않았다. 업로드에 사용한 `bithumb-skillup-netlify.zip`과 `general-skillup-netlify.zip`도 최종 전달 폴더에서 삭제했다. 공식 배포 기준선은 위 GitHub Pages 두 저장소이며, 이후 작업은 GitHub Pages 커스텀 도메인 연결만 수행한다.

이 기록은 랜덤 임시 주소 시험을 철회한 내역이다. 새 배포는 같은 랜덤 주소를 재사용하지 않고 무료 계정에 소유권을 확보한 뒤, 사용자명이 없는 영문 사이트명을 적용하는 별도 절차로 진행한다. 독립 도메인은 페이지 완성 이후 연결한다.

## 도메인 등록 상태 확인 메모

`bithumb-skillup.com`, `xn---skillup-5b17af13a.com`, `general-skillup.com` 모두 현재 A 레코드가 확인되지 않았다. `bithumb-skillup.com`의 Verisign RDAP는 404를 반환했으며, 나머지 두 RDAP 요청은 네트워크 타임아웃으로 확정 판정하지 못했다. 가비아 등록 검색 화면은 이 브라우저 세션에서 빈 페이지로 렌더링돼 결제·등록 가능 여부 확인 경로로 사용하지 않는다.

Namecheap의 `bithumb-skillup.com` 검색 페이지는 로그인·상단 메뉴까지만 로드되고 등록 가능 여부 본문은 동적 렌더링되지 않았다. 자동 판정으로 결론을 내리지 않고, 도메인 구매·로그인 화면에서는 사용자가 직접 확인하는 안전 절차로 전환한다.

## 영문 Netlify 배포 패키지

독립 도메인 구매 전 임시 공식 주소를 만들기 위해 두 프로젝트를 `VITE_BASE_PATH=/`로 재빌드했다. `bithumb-ai-skillup-netlify.zip`과 `bithumb-x-minara-netlify.zip`은 각각 153KB이며 압축 무결성 검사를 통과했다. 빗썸용 문서 제목은 `빗썸 제안용`, 빗썸×미나라용 문서 제목은 일반 공개 제목을 유지한다.

Netlify 대시보드 루트는 현재 샌드박스 브라우저에서 빈 화면으로 렌더링돼 사이트 생성·이름 변경 UI를 사용할 수 없다. 배포 산출물에는 문제가 없으므로 다음 단계는 Netlify CLI 인증·배포 방식으로 전환한다.

## 영문 Netlify 사이트 생성 완료

사용자 Netlify 팀 `byeonjunyeong`에 CLI 권한을 승인받아 두 사이트를 무료 계정 소유 프로젝트로 생성했다. 랜덤 Drop이 아니므로 만료·공통 비밀번호 제한이 없다.

| 구분 | 프로덕션 주소 | 프로젝트 ID | 배포 ID |
|---|---|---|---|
| 빗썸용 | `https://bithumb-ai-skillup.netlify.app` | `578004b3-443e-48e7-9a98-a36c5edba87d` | `6a84f54513d611965b8eca76` |
| 빗썸×미나라용 | `https://bithumb-x-minara.netlify.app` | `92707f29-347e-46e7-b762-dc653c4be215` | `6a84f6bd2810faa492ff9dde` |

두 배포 모두 Netlify CLI의 `Deploy is live`와 프로덕션 URL 반환을 확인했다.

초기 사이트 생성 직후 팀 SSO 보호로 HTTP 401이 발생했으나, 두 사이트의 `sso_login`을 `false`로 변경해 외부 공개 접근으로 전환했다. 재검증 결과 두 주소와 각 JS·CSS 자산은 모두 HTTP 200이다. 빗썸용 번들에는 `미나라|minara|dmind`가 0건이고, 빗썸×미나라용 번들에는 관련 표기가 존재해 두 버전 분리도 정상이다.

## 로그인 없는 공개 지원서

두 랜딩 모두 별도 회원가입·로그인·비밀번호 없이 작성하는 실제 참가 지원서를 추가했다. 필드는 이름, 이메일, 휴대전화, 현재 소속·학교, 현재 상태, 트레이딩 경험, 100자 이상 지원 동기, 개인정보 수집·이용 동의로 구성했다. 제출 중에는 버튼을 잠그고, 성공 시 현장 접수번호와 완료 안내를 표시하며, 실패 시 입력값을 유지하고 재시도 안내를 표시한다.

Netlify 공식 문서가 요구하는 자동 폼 감지와 정적 HTML 폼 선언, URL 인코딩 AJAX POST 구조를 적용했다. 두 사이트의 `processing_settings.ignore_html_forms`를 `false`로 전환한 뒤 재배포해 아래 운영 폼이 등록된 것을 API로 확인했다.[1]

| 구분 | Netlify 폼 이름 | 폼 ID | Honeypot |
|---|---|---|---|
| 빗썸용 | `bithumb-ai-skillup-application` | `6a850830a182d20008d07868` | 활성 |
| 빗썸×미나라용 | `bithumb-x-minara-application` | `6a8508498dad2e00089bc23f` | 활성 |

외부 비로그인 조건의 QA 지원서를 두 공개 주소에 실제 POST한 결과 모두 HTTP 200을 반환했고, Netlify 운영 수집함에서 각 버전·이름·이메일·지원 동기가 저장된 것을 확인했다. 검증용 제출 2건은 확인 직후 삭제했다.

| 검증 항목 | 빗썸용 | 빗썸×미나라용 |
|---|---:|---:|
| Vitest | 21개 통과 | 21개 통과 |
| TypeScript | 통과 | 통과 |
| 프로덕션 빌드 | 통과 | 통과 |
| 320px 가로 넘침 | 0px | 0px |
| 320px 지원서 폭 | 300px | 300px |
| 1440px 가로 넘침 | 0px | 0px |
| 1440px 지원서 폭 | 1332px | 1332px |
| 비밀번호 필드 | 0개 | 0개 |
| 콘솔 오류·경고 | 0건 | 0건 |

320px에서는 지원 안내와 필드가 1열로 전환되고, 1440px에서는 안내 424px·폼 663.2px의 비대칭 2열로 표시된다. 측정 원본은 최종 전달 폴더의 `netlify-*-application-*.json`, 콘솔 기록은 `netlify-*-application-console.txt`, 모바일 캡처는 `bithumb-application-320.png`에 저장했다.

## References

[1]: https://docs.netlify.com/manage/forms/setup/ "Netlify Forms setup"
