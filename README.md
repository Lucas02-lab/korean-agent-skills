# 한국어 AI 에이전트 스킬 모음

X에서 발견한 AI 에이전트 스킬을 검토하고, 출처와 라이선스를 보존하며 한국어로 정리하는 개인용 비공개 저장소입니다.

## 사용 가능한 스킬

| 스킬 | 하는 일 | 상태 |
| --- | --- | --- |
| [discernment-nudge-ko](skills/discernment-nudge-ko/SKILL.md) | 중요한 답변에서 다시 살펴볼 사실과 가정을 질문으로 제안 | 한국어 수정본; 직접 적용 2사례 확인, 독립 세션 미검증 |
| [humanize-korean-lite](skills/humanize-korean-lite/SKILL.md) | 의미와 격식을 유지하며 한국어 문장을 다듬기 | 간결한 수정본; 직접 적용 2사례 확인, 독립 세션 미검증 |
| [career-resume-ko](skills/career-resume-ko/SKILL.md) | 확인된 경력과 프로젝트로 한국어 경력기술서 작성 | 한국어 수정본; 직접 적용 1사례 확인, 독립 세션 미검증 |

## 설치: Codex

터미널에서 이 저장소를 내려받은 뒤 스킬 폴더를 복사합니다. 아래 명령은 같은 이름의 기존 폴더를 덮어쓰지 않습니다.

```sh
git clone https://github.com/Lucas02-lab/korean-agent-skills.git
mkdir -p "${CODEX_HOME:-$HOME/.codex}/skills"
test ! -e "${CODEX_HOME:-$HOME/.codex}/skills/discernment-nudge-ko" && cp -R korean-agent-skills/skills/discernment-nudge-ko "${CODEX_HOME:-$HOME/.codex}/skills/"
test ! -e "${CODEX_HOME:-$HOME/.codex}/skills/humanize-korean-lite" && cp -R korean-agent-skills/skills/humanize-korean-lite "${CODEX_HOME:-$HOME/.codex}/skills/"
test ! -e "${CODEX_HOME:-$HOME/.codex}/skills/career-resume-ko" && cp -R korean-agent-skills/skills/career-resume-ko "${CODEX_HOME:-$HOME/.codex}/skills/"
```

비공개 저장소이므로 GitHub 접근 권한이 필요합니다. 새 Codex 세션을 시작해 원하는 스킬을 사용해 달라고 요청합니다. 첫 두 스킬의 복사 절차는 격리된 시험 폴더에서 확인했으며 실제 사용자 환경에는 설치하지 않았습니다. 다른 에이전트는 해당 제품의 스킬 경로와 지원 형식을 확인하세요.

## 새 후보를 가져오는 순서

1. X 게시물과 실제 GitHub 원본을 확인하고, 작성자·원본 경로·커밋을 기록합니다.
2. 원본 파일과 별도 파일의 라이선스를 확인합니다. 재배포 조건이 불명확하면 링크만 기록합니다.
3. 지침·스크립트·외부 전송과 설치 명령을 검토합니다. 출처 불명의 코드는 실행하지 않습니다.
4. 한국어 사용 예와 사용 범위를 다듬고, 원본 표시·라이선스·변경 내용을 남깁니다.
5. 설치 형식과 적용 사례를 검증하고, 실제 실행 여부와 한계를 기록합니다.

[원본 검토 기록](candidates/humanize-korean.md) | [첫 번째 스킬의 출처와 변경 기록](skills/discernment-nudge-ko/ORIGIN.md)

## 검증 결과

[가상 요청을 이용한 직접 적용 사례](tests/manual-cases-2026-10-27.md)를 확인하세요. 이 테스트는 같은 Codex 대화에서 스킬을 읽고 적용한 사례이며, 새 세션의 자동 스킬 선택이나 독립 에이전트 평가를 의미하지 않습니다.
