---
name: tribunal_trf3_obter_certidao-mcp
description: Skill da REST API do Tribunal TRF3: Obter Certidão de Distribuição na MCP.AI: 1 endpoint em /api/tribunal_trf3_obter_certidao. Tribunal TRF3: Obter Certidão de Distribuição, consulta em fonte oficial. Hospedado pela plataforma, sem credenciais da plataforma, pague por consulta com crédito pré-pago. Autentique com workspace API key (sk_live) gerada em app.mcp.ai/settings/api-keys. Use quando o usuário pedir algo coberto pelos endpoints.
---

# Tribunal TRF3: Obter Certidão de Distribuição — REST API skill

Você tem acesso à **Tribunal TRF3: Obter Certidão de Distribuição** REST API na MCP.AI.

> Tribunal TRF3: Obter Certidão de Distribuição, consulta em fonte oficial. Hospedado pela plataforma, sem credenciais da plataforma, pague por consulta com crédito pré-pago.

## Base URL

```
https://api.mcp.ai/api/tribunal_trf3_obter_certidao
```

Todo endpoint é um **POST** na Base URL + o path abaixo. Os parâmetros vão no corpo JSON.

## Autenticação

Inclua em toda request:

```
Authorization: Bearer sk_live_...
Content-Type: application/json
```

> Gere sua chave em **https://app.mcp.ai/settings/api-keys** (workspace API key `sk_live_…`, não expira, revogável). Uma única chave serve pra todos os seus MCPs.

## Formato de resposta

```json
{ "ok": true, "tool": "<tool_id>", "result": <payload> }
```

## Exemplo cURL

```bash
curl -X POST https://api.mcp.ai/api/tribunal_trf3_obter_certidao/consultar \
  -H "Authorization: Bearer sk_live_..." \
  -H "Content-Type: application/json" \
  -d '{"numero_certidao":"..."}'
```

## Reportar problemas

Se um endpoint retornar erro, vazio ou dado inesperado, reporte (não desista calado): **POST /api/tribunal_trf3_obter_certidao/report** com `{ "message": "...", "context"?: "...", "conversation"?: [...] }`. Isso notifica o time da MCP.AI.

## Endpoints (1)

#### `tribunal_trf3_obter_certidao_consultar`

Tribunal TRF3: Obter Certidão de Distribuição, consulta em fonte oficial. _(POST /api/tribunal_trf3_obter_certidao/consultar)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `cpf` | string | Não | Parâmetro de consulta "cpf". |
| `cnpj` | string | Não | Parâmetro de consulta "cnpj". |
| `numero_certidao` | string | Sim | Parâmetro de consulta "numero_certidao". |

---

Este MCP também funciona via **conexão MCP** (Claude / Cursor) em `https://api.mcp.ai/p_tribunal_trf3_obter_certidao` — veja o [README](../../README.md). A skill acima é pra consumir a **REST API** direto (agente próprio / código).
