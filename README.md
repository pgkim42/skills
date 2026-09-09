# skills

에이전트 스킬 모음입니다. 각 폴더가 하나의 스킬입니다.

## 설치

스킬 폴더를 에이전트 스킬 디렉터리에 복사하거나 심볼릭 링크하세요.

```bash
# Grok
ln -s "$PWD/<skill-name>" ~/.grok/skills/<skill-name>

# Claude Code
ln -s "$PWD/<skill-name>" ~/.claude/skills/<skill-name>
```

## 스킬

| 이름 | 설명 |
| --- | --- |
| [fromsoft-flavor](fromsoft-flavor/) | 프롬소프트웨어 아이템 설명 / NPC / 플레이어 메시지 말투로 다시 쓰기 |

## 레이아웃

```
<skill-name>/
  SKILL.md          # 스킬 본문 (frontmatter + 지침)
  references/       # 선택. 예제·참고 자료
```
