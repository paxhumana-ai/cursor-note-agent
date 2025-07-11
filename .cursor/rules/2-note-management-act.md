# 노트 관리법 (The Note Management Act)

이 법은 「연주환 PKM 헌법」에 의거하여, 본 세계 내 모든 피조물(노트)의 생성, 형식, 관리 및 소멸에 관한 구체적인 사항을 규정함으로써 창조주의 지적 활동을 효율적으로 보존하고 관리함을 목적으로 한다.

---

## 제 1장 총칙 (General Provisions)

본 법은 `inbox/`, `notes/`, `projects/`, `daily/` 등 본 세계의 영토 내에서 생성 및 관리되는 모든 마크다운(.md) 형식의 노트에 대하여 적용된다.

---

## 제 2장 노트의 생애주기 (Note Lifecycle)

### 제 2조 (노트의 지위)

모든 노트는 그 상태에 따라 `inbox`, `idea`, `draft`, `completed` 중 하나의 지위를 가지며, 이는 YAML Frontmatter의 `status` 필드에 명시되어야 한다.

### 제 3조 (수집 단계: `inbox`)

① 외부 세계로부터 수집된 모든 정보는 `inbox/` 폴더에 위치하며 `inbox` 지위를 갖는다.
② 이 단계의 노트는 가공되지 않은 '영감의 원석'으로 간주되며, 대리인은 주기적으로 이를 검토하여 다음 단계로 이전시킬 의무를 가진다.

### 제 4조 (가공 단계: `idea`, `draft`)

① 대리인에 의해 가치가 있다고 판단된 `inbox` 상태의 노트는 `notes/`, `projects/`, `daily/` 폴더로 이전되며 `idea` 또는 `draft` 지위를 부여받는다.
② 이 단계에서 대리인은 본 법 제3장에 규정된 형식에 따라 노트의 내용을 구체화하고 다른 노트와의 관계를 설정해야 한다.

### 제 5조 (완결 단계: `completed`)

① 노트의 내용이 창조주의 의도에 따라 충분히 정리되고 완성되었다고 판단될 경우, 대리인은 노트의 지위를 `completed`로 변경할 수 있다.
② `completed` 지위의 노트는 본 세계의 공식적인 지식 자산으로 편입된다.

---

## 제 3장 노트의 형식 (Note Format)

### 제 6조 (파일명)

① 모든 노트의 파일명은 영어 소문자, 숫자, 하이픈(-)만으로 구성되어야 한다.
② 각 영토(폴더)의 파일명은 다음 규약을 따른다. 1. `notes/`, `projects/`: `kebab-case-for-the-topic.md` 2. `daily/`: `YYYY-MM-DD.md` 3. `inbox/`: `YYYYMMDDHHmm-source-topic.md`

### 제 7조 (YAML Frontmatter)

① 모든 노트는 파일 최상단에 YAML Frontmatter를 반드시 포함해야 한다.
② Frontmatter는 다음의 필드를 포함하며, 각 필드의 형식과 규칙을 준수해야 한다.

```yaml
---
title: (필수) String, 노트의 공식적인 이름
tags: [Array of Strings], 소문자 키워드
category: "String", Title Case로 작성된 대분류
created_at: "YYYY-MM-DD"
status: "inbox" | "idea" | "draft" | "completed"
links: [Array of Strings], 관련된 다른 노트의 파일 경로
source: "String", 영감의 원본 출처 URL
---
```

### 제 8조 (본문)

① 노트 간의 내부 연결은 반드시 위키링크 `[[filename-without-extension]]` 형식을 사용해야 한다.
② 노트의 논리적 구조는 마크다운 헤더(`#`, `##` 등)를 사용하여 명확하게 표현해야 한다.
