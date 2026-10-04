# Yeon-sik | 근거 기반 GitHub 프로필

GitHub 프로필 README를 관리하는 문서 저장소다. 문제·데이터·시스템 경계·구현·검증·문서화의 작업 방식과 주요 프로젝트 링크를 설명한다.

| 항목 | 내용 |
| --- | --- |
| 문서 갱신 | 2026-10-05 (Asia/Seoul) |
| 기준 소스 | [main@701b02c](https://github.com/Yeon-sik/Yeon-sik/tree/701b02c4837cfd662677a0234046a84b51f22003) |
| 저장소 | [Yeon-sik/Yeon-sik](https://github.com/Yeon-sik/Yeon-sik) |
| 범위 | 병합된 main의 source와 명시한 검증 근거. 개발 branch·미커밋 작업은 제외. |

## 1. 30초 요약

GitHub 프로필 README를 관리하는 문서 저장소다. 문제·데이터·시스템 경계·구현·검증·문서화의 작업 방식과 주요 프로젝트 링크를 설명한다.

- 2026-09-23 근거 기반 profile README 커밋이 최근 2주 선택 조건을 충족한다.

## 2. 문제와 해결

**문제**: 프로필 소개가 source·test·운영 증거보다 앞서면 상태를 오해하게 만든다. 각 앱 상세 설명을 복제하면 갱신 비용도 커진다.

**해결**: 프로필에는 짧은 소개·검증 한계를 두고 상세 사실은 해당 레포 문서로 연결한다. 이 Intro/Detail은 프로필 저장소의 운영 책임만 설명한다.

## 3. 핵심 기능과 결과

| 영역 | 현재 source에서 확인한 범위 |
| --- | --- |
| README | Personal OS·FitnessApp·OCR-App·PriceTrace 링크와 구현/실환경 한계. |
| 작업 방식 | 문제 -> 요구 -> 데이터/도메인 -> 경계 -> 구현 -> 검증 -> 문서화. |
| AI 활용 | 생성 코드·추론은 출발점이며 source와 관찰된 동작으로 주장 범위를 결정. |
| 문서 미러 | Git Intro/Detail 원본과 canonical main의 guarded Notion publication. |

## 4. 검증 현황

| 항목 | 상태 | 근거와 한계 |
| --- | --- | --- |
| 프로필 원본 | 확인 | 기준 README.md의 프로젝트 링크와 검증 한계 설명 확인. |
| 앱 테스트 | 해당 없음 | 기준 source는 README뿐이다. 링크된 제품의 실행 검증은 해당 레포에서 수행한다. |

위 결과는 연결한 기준 source revision의 증거다. 이번 변경은 문서·게시 설정만 갱신하며 제품 runtime을 새로 검증한 작업으로 설명하지 않는다. 문서 validator, tracked path·link 검사와 Notion render-only dry run을 수행한다. 병합 뒤 반영은 별도 게시 workflow와 source fingerprint로 확인한다.

## 5. 현재 한계와 다음 단계

- 프로필은 짧은 상태 소개이며 최신 운영 release 보증이 아니다.
- PriceTrace 등 제품 방향의 상세 설명은 해당 레포 Intro/Detail을 원본으로 읽는다.
- 다음 우선 작업은 주요 프로젝트 원본 문서 revision과 프로필 소개를 함께 검토하는 것이다.

## 6. 관련 문서

- [프로젝트 상세](./Project_Detail.md)
- [README](../README.md)

Git Markdown이 원본이며 Notion은 생성 미러다. main에 병합한 뒤 workflow_dispatch에서 operation=publish와 정확한 PUBLISH 확인으로 발행한다. 개인 원본과 인증 정보는 게시하지 않는다.
