# AllrangeKit Photo Skill — Codex + ChatGPT Plus

이 파일은 **Codex에서 사진 생성용 프롬프트를 만드는 스킬**이야. 친구는 스킬이 출력한 영어 프롬프트를 ChatGPT Images에 붙여 넣어 최종 이미지를 생성하면 돼.

## 1. 제작자가 할 일
1. ZIP 압축 해제.
2. GitHub에서 `allrange-photo-skill` 저장소 만들기. 브랜드 내부 지침을 추가한다면 **비공개** 저장소로 유지하기.
3. 현재 폴더 안의 `skills/` 폴더와 `README.md`, `친구에게-보내기.md`, `제작자-체크리스트.md`를 GitHub 저장소 루트에 올리기. ZIP을 통째로 업로드하지 않기.
4. Mac/Windows ChatGPT 데스크톱 앱의 Codex 또는 Codex CLI에서 스킬을 한 번 설치해 테스트.
5. 세 가지 실제 브리프(홈페이지/블로그/SNS)로 사진 생성 → 회사 담당자에게 스타일 승인받기.

## 2. 친구가 할 일 — 가장 쉬운 방법
1. ChatGPT Plus 계정으로 **데스크톱 ChatGPT 앱의 Codex**를 연다.
2. Codex 대화에 아래 명령을 보내고 저장소 URL을 본인에게 받은 링크로 바꾼다.

```text
$skill-installer 아래 GitHub 저장소에서 allrange-photo 스킬을 내 Codex에 설치해줘. https://github.com/OWNER/REPO/tree/main/skills/allrange-photo
```

3. 설치되면 Codex를 새 대화로 열고 다음을 붙여 넣는다.

```text
$allrange-photo
[사진 용도]: 홈페이지 메인 배너
[인물]: 30대 동아시아계 여성 1명
[행동]: 소파에 앉아 휴대폰을 보는 모습
[장소]: 자동
[의상]: 자동
[시간·조명]: 자동
[카메라 구도]: 자동
[글씨 넣을 공간]: 오른쪽
```

4. Codex가 출력한 **영문 프롬프트만 복사**하고, 일반 ChatGPT 채팅의 **Images** 기능에서 새 사진을 생성한다.
5. 사진이 마음에 안 들면 원래 Codex 대화에서 "구도만 바꿔줘" 또는 "좀 더 자연스러운 일상 사진으로 바꿔줘"라고 요청한다.

### 설치가 안 되는 경우 (제작자용 우회)
Node.js 22.20 이상을 설치한 터미널에서 실행:

```bash
npx skills add OWNER/REPO --skill allrange-photo -a codex -g
```

또는 `skills/allrange-photo/` 폴더 전체를 현재 프로젝트의 `.agents/skills/allrange-photo/`에 복사해서 Codex에서 해당 프로젝트를 연다. 설치 후 안 보이면 Codex를 재시작한다.

> 참고: ChatGPT Plus에 Codex가 포함되어 있어도 Codex가 이미지를 직접 만드는 도구가 항상 제공된다는 의미는 아님. 이 기본 스킬은 **프롬프트 생성 → ChatGPT 이미지 생성**의 두 단계다. ChatGPT Plus는 API 크레딧이 아니므로 `OPENAI_API_KEY`를 요청하지 않는다.

## 3. 중요한 구분
- SKILL.md: AI가 따를 사진 연출 규칙.
- Codex: 초보자의 한글 설명을 사진 생성 프롬프트로 정리.
- ChatGPT Images: 실제 사진 생성.
- GitHub: 스킬 파일 배포·수정 버전 관리.
- Vercel / FLUX API / 서버: 이 방식에서는 필요 없음.

## 4. 브랜딩과 의료 검수
스킬의 사진 스타일은 제안이며 **회사에서 확정한 브랜드 가이드가 아님**. 사용 전 법무·마케팅 담당자에게 적합성을 확인하고, 실제 검사 키트·로고·수치·검사 결과를 AI가 임의로 만들어낸 장면은 쓰지 않기.
