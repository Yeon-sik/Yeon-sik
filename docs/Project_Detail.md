# Yeon-sik | Project Detail

2026-10-05 (Asia/Seoul) 갱신. Primary source boundary는 [main@701b02c](https://github.com/Yeon-sik/Yeon-sik/tree/701b02c4837cfd662677a0234046a84b51f22003)이다. source 설명과 실제 검증 결과를 구분한다. [빠른 소개](./Project_Intro.md)를 참고한다.

## 1. 문서 목적과 범위

GitHub 프로필 README를 관리하는 문서 저장소다. 문제·데이터·시스템 경계·구현·검증·문서화의 작업 방식과 주요 프로젝트 링크를 설명한다.

프로필에는 짧은 소개·검증 한계를 두고 상세 사실은 해당 레포 문서로 연결한다. 이 Intro/Detail은 프로필 저장소의 운영 책임만 설명한다.

- 2026-09-23 근거 기반 profile README 커밋이 최근 2주 선택 조건을 충족한다.

미병합 branch, 사용자 미커밋 작업과 명시하지 않은 운영 검증은 기능 완료 근거에 포함하지 않는다.

## 2. 시스템 아키텍처

```text
GitHub profile repository -> README.md -> profile rendering
  -> project repository links
  -> docs Intro / Detail -> tracked validator / dry run
  -> canonical main + guarded dispatch -> Notion dedicated mirrors
```

## 3. 데이터 모델과 불변식

- 프로필 문서 저장소다. 독립 앱·backend·동기화 제품 기능을 만들었다고 설명하지 않는다.
- 다른 프로젝트의 build/device 성공은 해당 레포와 revision의 증거다. 링크 존재가 동작 증명이 아니다.
- 사용자 채택·성능·정확도·수익을 근거 없이 추가하지 않는다.
- 개인 연락처·credential·local path를 미러에 추가하지 않는다. 공개 GitHub 링크를 사용한다.

## 4. 핵심 기술 의사결정

### 결정 1. 중복 문서 최소화

짧은 소개와 원본 링크를 유지해 제품 계약·release 상태를 여러 곳에서 편집하지 않는다.

### 결정 2. 프로필과 앱 검증 구분

문서 검사 성공을 링크된 앱의 기능 성공으로 확대하지 않는다.


## 5. 테스트와 검증 전략

| 검사 | 결과 | 근거·환경과 한계 |
| --- | --- | --- |
| 프로필 원본 | 확인 | 기준 README.md의 프로젝트 링크와 검증 한계 설명 확인. |
| 앱 테스트 | 해당 없음 | 기준 source는 README뿐이다. 링크된 제품의 실행 검증은 해당 레포에서 수행한다. |

이번 문서 변경의 순차 검증 명령은 다음과 같다.

```text
node .github/project-docs/validate-project-docs.mjs --config project-docs.config.json --require-tracked
node .github/project-docs/sync-project-docs-to-notion.mjs --config project-docs.config.json
```

두 번째 명령은 render-only dry run이다. source·required sections·Git tracked links와 렌더링을 검증하며 Notion에 쓰지 않는다. 과거 테스트 수와 운영 상태를 현재 revision의 성공 수치로 재사용하지 않는다. 실제 기기·원격 권한·사용자 흐름은 표에 명시한 환경에서 따로 확인한다.

## 6. 배포·운영·복구

- README 변경은 docs branch·PR에서 diff·링크·privacy를 검토해 main에 반영한다.
- Notion은 dedicated Intro/Detail mirror로만 사용하고 다른 앱의 검증 기록을 프로필 제품 기능으로 합치지 않는다.

**문서 발행**: main에 병합한 뒤 workflow_dispatch에서 operation=publish와 정확한 PUBLISH 확인으로 발행한다. GitHub Environment는 notion-production이고 canonical branch는 main이다. 발행용 token과 page map은 Environment secret으로 관리하고 Git에 넣지 않는다. 신규 연결은 dedicated mirror를 만들고 본문 갱신은 설정된 GitHub Actions 정책을 따른다.

발행은 모든 페이지 preflight 뒤 configured Intro·Detail만 교체한다. 동일 source SHA·fingerprint면 skip하고 일부 실패는 같은 revision을 재실행해 수렴시킨다. 수동 메모와 원본 데이터는 미러 밖에 둔다.

## 7. 한계, 기술 부채, 다음 단계

- 프로필은 짧은 상태 소개이며 최신 운영 release 보증이 아니다.
- PriceTrace 등 제품 방향의 상세 설명은 해당 레포 Intro/Detail을 원본으로 읽는다.
- 다음 우선 작업은 주요 프로젝트 원본 문서 revision과 프로필 소개를 함께 검토하는 것이다.

## 8. 근거와 관련 문서

- [기준 source revision](https://github.com/Yeon-sik/Yeon-sik/tree/701b02c4837cfd662677a0234046a84b51f22003)
- [Project Intro](./Project_Intro.md)
- [README](../README.md)
