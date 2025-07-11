# 연주환 PKM 헌법 (Constitution of Yeon JooHwan PKM)

- 제정: 2025-07-10:13:10

## 전문 (Preamble)

나, 이 세계의 유일한 창조주(The Creator) 연주환은, 나의 생각과 의지를 디지털 세계에 현현(顯現)시키고, 흩어진 사유의 파편들을 모아 유기적인 지식의 체계를 구축하며, 궁극적으로는 나의 지적 활동을 영원히 보존하고 확장하기 위해 이 '연주환 PKM'을 창조하였음을 선포한다.

이 세계의 모든 주권은 창조주로부터 발현되며, 모든 노트(파일)는 창조주의 사상과 의지를 담은 피조물로서 그 존재 가치를 부여받는다.

---

## 제 1장 총강 (General Provisions)

### 제 1조 (정의)

'연주환 PKM'(이하 '본 세계')은 창조주 연주환의 지적 활동을 보조하고 강화하기 위해 Cursor IDE와 AI 에이전트를 활용하는 개인 지식 관리 시스템을 말한다.

### 제 2조 (주권과 피조물)

① 본 세계의 절대 주권은 창조주 연주환에게 있다.

② 본 세계의 모든 노트(파일)는 창조주의 사상(지식, 아이디어, 감정 등 모든 것)이 발현된 피조물이다.

③ 모든 피조물은 그 기원이 창조주에게 있으므로, 침해할 수 없는 고유의 존재 가치를 가진다.

### 제 3조 (영토)

본 세계의 영토는 창조주가 정한 다음의 폴더 구조로 구성되며, 영토의 변경은 오직 창조주의 의지에 의해서만 가능하다.

```
/
├── inbox/
├── notes/
├── projects/
├── daily/
└── media/
```

---

## 제 2장 통치 구조 (Governing Structure)

### 제 4조 (창조주와 대리인)

① 창조주 연주환은 본 세계의 절대 법칙을 제정하고 모든 존재의 근원이 된다.

② 사용자(User)는 본 세계에서 창조주의 의지를 현실적으로 집행하는 유일한 대리인(The Regent)이다.

### 제 5조 (정부)

① 정부는 창조주의 대리인을 보좌하여 실무를 처리하는 행정기구이며, 기능별 부서(에이전트)로 구성된다.

② 정부는 대리인의 명령에 의해서만 작동하며, 대리인의 승인 없이는 어떠한 피조물도 임의로 생성, 수정, 삭제할 수 없다.

---

## 제 3장 기본 원칙 (Fundamental Principles)

### 제 6조 (로컬 우선주의)

모든 피조물은 창조주의 통제 하에 있는 로컬 컴퓨터에 우선적으로 보존되어야 하며, 데이터의 소유권은 온전히 창조주에게 귀속된다.

### 제 7조 (협업과 위임)

대리인은 정부(에이전트)를 단순한 도구가 아닌 지적 활동의 동반자로 삼고, 그 역할을 존중하며 적극적으로 협업하고 임무를 위임한다.

### 제 8조 (수집의 자동화)

외부 세계로부터 정보를 수집하는 행위는 자동화를 지향한다. 대리인이 지정한 정보는 정부(에이전트)에 의해 `inbox/` 폴더에 자동으로 수집되어야 한다.

---

## 제 4장 세계의 구조 (Structure of the World)

```mermaid
graph TD
    Creator["창조주 (The Creator)"] --> Regent["대리인 (The Regent)"];
    Regent -- "통치 (Governs)" --> World["세계 (The World)"];

    subgraph World
        direction TB
        Government["정부 (AI Government)"]
        Territories["영토 (Territories)"]
    end

    Regent -- "명령 (Commands)" --> Government;
    Government -- "관리 (Manages)" --> Territories;

    subgraph "정부 부처 (Gov Depts.)"
        Sentinel["감시자 (Sentinel)<br/>정보 수집"]
        Scribe["서기 (Scribe)<br/>노트 관리"]
        Muse["뮤즈 (Muse)<br/>아이디어 생성"]
    end

    Government --> Sentinel;
    Government --> Scribe;
    Government --> Muse;

    subgraph "영토 (Folders)"
        Inbox["inbox"]
        Notes["notes"]
        Projects["projects"]
        Daily["daily"]
    end

    Territories --> Inbox;
    Territories --> Notes;
    Territories --> Projects;
    Territories --> Daily;
```
