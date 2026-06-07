# AGENTS.md

> Codex 세션 시작 시 자동 로드되는 운영 규칙 파일.
> 작업 폴더(`arcade-senpai/`) 루트에 둔다.

## 작업 맥락

전체 프로젝트 맥락은 아래 파일을 참조한다 (작품 정체·인물·리부트 결정·config·워크플로우):

@PROJECT_CONTEXT.md

---

## Code 전용 운영 규칙

### 절대 규칙
- **mana-novel 스킬 사용 금지.** 이 작품은 《국정원 에이스는 오락실 관리자를
  선배님이라 부른다》이며, 전용 config/design 세트를 사용한다. mana-novel은
  별개 작품(《마나를 모르는 외신이 왔다》) 전용이다.
- **`source-50/` 은 읽기 전용 원작 자산.** 절대 수정·삭제하지 않는다.
  역추출 시 읽기만 하고, 산출물은 `design/` 에 쓴다.
- novel-config.md 의 guard_rails 는 회차 집필·퇴고에서 항상 강제한다.

### 도구 (awesome-novel-studio)
- 설치: `/plugin marketplace add MJbae/awesome-novel-studio` → `/plugin install`
- 슬래시 커맨드: `/design-big`(설계), `/create EP###`(집필), `/polish`(퇴고)
- continuity-bridge 가 직전 회차 상태를 물고 다음 화에 주입한다.
- 16축 polish + custom_axes(MISREAD / POV_BALANCE / LIGHT / HOOK1K) 적용.

### Git / 버전 관리
- 회차 단위로 커밋한다. (예: `EP001 초안`, `EP001 polish 반영`)
- Cowork 세션과 **동일 디렉터리/레포**를 공유한다. 양쪽 작업은 git으로 합친다.
- 회차 파일이 양쪽에 따로 쌓이지 않게 한다 (continuity-bridge 정합성 유지).

### 작업 순서 리마인더
1. `source-50/` txt 역추출 → `design/` (characters / misread-state / worldbuilding / keep-scenes)
2. `/design-big` 노피아 타깃 재설계 → novel-config.md 반영
3. `/create EP001` → `/polish` → 검수 → 커밋, 반복

### Codex cross-review (나중 단계 — 지금 아님)
- EP001~005 를 Codex 단독으로 안정화한 뒤에만 도입.
- OpenAI 공식 Codex 플러그인을 Codex 에 연결.
- Codex 역할: 톤 일관성 / 첫 1,000자 이탈 위험 / 외부 시점 컷 효용 / 라노벨 코팅 적정성
  같은 **메타 피드백만**. 작품 고유 설정·오독 일관성은 맡기지 않는다.
