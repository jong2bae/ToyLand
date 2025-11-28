---
description: 현재 프로젝트의 네이밍 규칙을 새로 분석하고 전역 설정에 추가합니다 (느림, 새로 분석)
tags: [project, setup, naming, new]
---

# 프로젝트 네이밍 규칙 새로 분석

현재 프로젝트의 네이밍 규칙을 처음부터 분석해서 `~/.claude/project_naming_conventions/`에 저장합니다.

## 실행할 작업:

1. **프로젝트 식별**: 현재 디렉토리가 pf3-api인지 pf3-adm인지 자동 감지
2. **네이밍 규칙 분석**: 컨트롤러, 서비스, 매퍼의 네이밍 패턴 분석
3. **문서 생성**: 다음 4개 파일을 `~/.claude/project_naming_conventions/{프로젝트명}/`에 생성
   - README_NAMING_CONVENTIONS.md
   - NAMING_CONVENTIONS_ANALYSIS.md
   - NAMING_CONVENTIONS_QUICK_REFERENCE.md
   - CODE_EXAMPLES_BY_LAYER.md
4. **INDEX.md 업데이트**: 프로젝트 카탈로그에 현재 프로젝트 추가
5. **CLAUDE.md 업데이트**: 전역 설정에 QUICK_REFERENCE.md 경로 추가

## 시작합니다

각 컨트롤러와 서비스 그리고 매퍼까지 한 묶음이라고 가정했을 때, 이 프로젝트의 네이밍 규칙을 분석해서 `~/.claude/project_naming_conventions/` 디렉토리에 문서화해줘.

**자동으로 할 작업:**

1. 현재 프로젝트 이름을 자동 감지 (pf3-api 또는 pf3-adm)
2. 프로젝트의 Controller, Service, Mapper 파일들을 분석
3. 네이밍 패턴, 메서드 명명 규칙, 패키지 구조 추출
4. 다음 4개 파일을 `~/.claude/project_naming_conventions/{프로젝트명}/` 에 생성:
   - `README_NAMING_CONVENTIONS.md` (12KB) - 전체 가이드 및 네비게이션
   - `NAMING_CONVENTIONS_ANALYSIS.md` (36KB) - 상세 분석 문서
   - `NAMING_CONVENTIONS_QUICK_REFERENCE.md` (6.5KB) - 빠른 참조 가이드
   - `CODE_EXAMPLES_BY_LAYER.md` (21KB) - 실제 코드 예제

5. `~/.claude/project_naming_conventions/INDEX.md` 파일 생성 또는 업데이트:
   - 현재 프로젝트 정보 추가
   - 핵심 네이밍 패턴 요약
   - 사용 예시 포함

6. `~/.claude/CLAUDE.md` 파일 업데이트:
   - 아래 내용이 없으면 파일 맨 아래에 추가:
   ```markdown
   # Project Naming Conventions - Smart Auto-Detection
   @project_naming_conventions/INDEX.md
   @project_naming_conventions/pf3-api/NAMING_CONVENTIONS_QUICK_REFERENCE.md
   @project_naming_conventions/pf3-adm/NAMING_CONVENTIONS_QUICK_REFERENCE.md
   ```

**분석 기준:**
- 파일명 패턴: {Feature}{Type}.java (예: AssetController.java)
- 클래스명 패턴: {Feature}{Type}
- 패키지 구조: com.jiran.{module}.{layer}
- 메서드명 패턴: api{Entity}{Operation}{HTTP} 또는 json{Entity}{Action}
- 매퍼 메서드: get{Description}(), set{Description}()
- XML 파일: sqlmap-{feature}.xml

**완료 후:**
설정이 완료되면 다음과 같이 사용할 수 있습니다:
```
"게시판 기능 네이밍 추천해줘"
"파일 업로드 API 만들 건데 컨트롤러, 서비스, 매퍼 이름 뭐로 하지?"
```

프로젝트가 자동 감지되어 해당 프로젝트의 네이밍 규칙에 맞게 추천됩니다.