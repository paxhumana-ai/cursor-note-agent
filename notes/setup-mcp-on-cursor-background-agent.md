---
title: "커서 백그라운드 에이전트에 MCP 서버 설치하기"
tags: ["cursor", "background-agent", "mcp", "docker", "environment-json"]
category: "Cursor"
created_at: "2025-07-11"
status: "draft"
links: []
source: "https://docs.cursor.com/background-agent#how-to-use"
---

# 개요

이 문서는 커서(Cursor)의 백그라운드 에이전트 환경에서 MCP(Model Context Protocol) 서버를 설치하고 설정하는 방법에 대해 논의한 내용을 정리한 것입니다. 백그라운드 에이전트는 기본적으로 MCP 서버가 설치되어 있지 않으므로, 추가적인 설정이 필요합니다.

# 설치 방법

백그라운드 에이전트에 MCP 서버를 설치하는 주요 방법은 두 가지가 있습니다.

## 1. `environment.json` 활용

가장 간단한 방법은 프로젝트 루트의 `.cursor/environment.json` 파일에 `install` 명령어를 추가하여 MCP 서버 관련 패키지를 설치하는 것입니다.

```json
{
  "snapshot": "POPULATED_FROM_SETTINGS",
  "install": "npm install && npm install -g @upstash/context7-mcp @playwright/mcp",
  "terminals": [
    {
      "name": "Run Next.js",
      "command": "npm run dev"
    }
  ]
}
```

이 방법은 기존 환경 설정에 간단히 몇 줄을 추가하여 MCP 서버를 구동할 수 있다는 장점이 있습니다.

## 2. Dockerfile 사용

보다 정교하고 독립적인 환경 구성이 필요한 경우, `Dockerfile`을 사용하여 시스템 레벨에서 의존성을 관리할 수 있습니다.

```dockerfile
FROM ubuntu:latest

# Node.js 및 npm 설치
RUN apt-get update && apt-get install -y nodejs npm

# MCP 서버 패키지 전역 설치
RUN npm install -g @upstash/context7-mcp @playwright/mcp

# 기타 필요한 시스템 의존성 설치...
```

이 방법은 환경의 재현성을 보장하고, 복잡한 시스템 레벨의 설정이 필요할 때 유용합니다.

# 주요 고려사항

MCP 서버를 설정할 때 다음 사항들을 고려해야 합니다.

1.  **MCP 서버 설정**: 로컬 환경의 `mcp.json` 파일에 정의된 설정(커맨드, 인수 등)이 백그라운드 에이전트 환경에도 동일하게 적용될 수 있도록 구성해야 합니다.
2.  **환경 변수**: 로컬 `mcp.json`에서 사용하는 `DEFAULT_MINIMUM_TOKENS`와 같은 환경 변수들을 백그라운드 에이전트 환경에서도 설정해주어야 합니다.
3.  **네트워크**: Notion과 같이 URL 기반으로 동작하는 MCP 서버의 경우, 백그라운드 에이전트의 격리된 네트워크 환경에서 해당 URL에 접근할 수 있는지 확인이 필요합니다.

# 권장 접근법

우선 **`environment.json`을 사용하는 간단한 방법으로 시도**해보고, MCP 서버들이 정상적으로 설치되고 동작하는지 확인하는 것을 권장합니다. 만약 더 복잡한 설정이 필요하거나 환경을 완벽하게 통제해야 할 경우, `Dockerfile`을 이용한 접근법을 고려할 수 있습니다.
