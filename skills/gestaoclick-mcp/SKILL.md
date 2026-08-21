---
name: gestaoclick-mcp
description: Skill da REST API do GestãoClick na MCP.AI: 127 endpoints em /api/gestaoclick. ERP GestãoClick (sistema de gestão para PMEs) via API oficial: clientes, fornecedores, produtos e serviços, orçamentos, vendas, ordens de serviço, compras, notas fiscais (produto, consumidor, serviço) e financeiro (pagamentos, recebimentos, contas bancárias, planos de contas, centros de custos). Gere o par de chaves no painel em Meus aplicativos, API. Autentique com workspace API key (sk_live) gerada em app.mcp.ai/settings/api-keys. Use quando o usuário pedir algo coberto pelos endpoints.
---

# GestãoClick — REST API skill

Você tem acesso à **GestãoClick** REST API na MCP.AI.

> ERP GestãoClick (sistema de gestão para PMEs) via API oficial: clientes, fornecedores, produtos e serviços, orçamentos, vendas, ordens de serviço, compras, notas fiscais (produto, consumidor, serviço) e financeiro (pagamentos, recebimentos, contas bancárias, planos de contas, centros de custos). Gere o par de chaves no painel em Meus aplicativos, API.

## Base URL

```
https://api.mcp.ai/api/gestaoclick
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
curl -X POST https://api.mcp.ai/api/gestaoclick/atributos/cadastros/create \
  -H "Authorization: Bearer sk_live_..." \
  -H "Content-Type: application/json" \
  -d '{}'
```

## Reportar problemas

Se um endpoint retornar erro, vazio ou dado inesperado, reporte (não desista calado): **POST /api/gestaoclick/report** com `{ "message": "...", "context"?: "...", "conversation"?: [...] }`. Isso notifica o time da MCP.AI.

## Endpoints (127)

#### `gestaoclick_atributos_cadastros_create`

Campos extras de cadastros: Cadastrar (POST /api/atributos_cadastros). _(POST /api/gestaoclick/atributos/cadastros/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso, + `usuario_id`/`loja_id` se multi-conta/loja). Ex. criar cliente: {"tipo_pessoa":"PF","nome":"...","cpf":"..."}. Campos na doc da GestãoClick. |

#### `gestaoclick_atributos_cadastros_delete`

Campos extras de cadastros: Deletar (DELETE /api/atributos_cadastros/{id}). _(POST /api/gestaoclick/atributos/cadastros/delete)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso, + `usuario_id`/`loja_id` se multi-conta/loja). Ex. criar cliente: {"tipo_pessoa":"PF","nome":"...","cpf":"..."}. Campos na doc da GestãoClick. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `gestaoclick_atributos_cadastros_get`

Campos extras de cadastros: Visualizar (GET /api/atributos_cadastros/{id}). _(POST /api/gestaoclick/atributos/cadastros/get)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `query` | string | Não | Query params como JSON string: filtros do recurso + paginação (`pagina`, `ordenacao`, `direcao`) + atribuição (`usuario_id`, `loja_id`). Ex.: {"nome":"acme","pagina":1}. Campos na doc da GestãoClick. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `gestaoclick_atributos_cadastros_list`

Campos extras de cadastros: Listar (GET /api/atributos_cadastros). _(POST /api/gestaoclick/atributos/cadastros/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `query` | string | Não | Query params como JSON string: filtros do recurso + paginação (`pagina`, `ordenacao`, `direcao`) + atribuição (`usuario_id`, `loja_id`). Ex.: {"nome":"acme","pagina":1}. Campos na doc da GestãoClick. |

#### `gestaoclick_atributos_cadastros_update`

Campos extras de cadastros: Editar (PUT /api/atributos_cadastros/{id}). _(POST /api/gestaoclick/atributos/cadastros/update)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso, + `usuario_id`/`loja_id` se multi-conta/loja). Ex. criar cliente: {"tipo_pessoa":"PF","nome":"...","cpf":"..."}. Campos na doc da GestãoClick. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `gestaoclick_atributos_financeiros_create`

Campos extras financeiros: Cadastrar (POST /api/atributos_financeiros). _(POST /api/gestaoclick/atributos/financeiros/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso, + `usuario_id`/`loja_id` se multi-conta/loja). Ex. criar cliente: {"tipo_pessoa":"PF","nome":"...","cpf":"..."}. Campos na doc da GestãoClick. |

#### `gestaoclick_atributos_financeiros_delete`

Campos extras financeiros: Deletar (DELETE /api/atributos_financeiros/{id}). _(POST /api/gestaoclick/atributos/financeiros/delete)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso, + `usuario_id`/`loja_id` se multi-conta/loja). Ex. criar cliente: {"tipo_pessoa":"PF","nome":"...","cpf":"..."}. Campos na doc da GestãoClick. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `gestaoclick_atributos_financeiros_get`

Campos extras financeiros: Visualizar (GET /api/atributos_financeiros/{id}). _(POST /api/gestaoclick/atributos/financeiros/get)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `query` | string | Não | Query params como JSON string: filtros do recurso + paginação (`pagina`, `ordenacao`, `direcao`) + atribuição (`usuario_id`, `loja_id`). Ex.: {"nome":"acme","pagina":1}. Campos na doc da GestãoClick. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `gestaoclick_atributos_financeiros_list`

Campos extras financeiros: Listar (GET /api/atributos_financeiros). _(POST /api/gestaoclick/atributos/financeiros/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `query` | string | Não | Query params como JSON string: filtros do recurso + paginação (`pagina`, `ordenacao`, `direcao`) + atribuição (`usuario_id`, `loja_id`). Ex.: {"nome":"acme","pagina":1}. Campos na doc da GestãoClick. |

#### `gestaoclick_atributos_financeiros_update`

Campos extras financeiros: Editar (PUT /api/atributos_financeiros/{id}). _(POST /api/gestaoclick/atributos/financeiros/update)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso, + `usuario_id`/`loja_id` se multi-conta/loja). Ex. criar cliente: {"tipo_pessoa":"PF","nome":"...","cpf":"..."}. Campos na doc da GestãoClick. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `gestaoclick_atributos_orcamentos_create`

Campos extras de orçamentos: Cadastrar (POST /api/atributos_orcamentos). _(POST /api/gestaoclick/atributos/orcamentos/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso, + `usuario_id`/`loja_id` se multi-conta/loja). Ex. criar cliente: {"tipo_pessoa":"PF","nome":"...","cpf":"..."}. Campos na doc da GestãoClick. |

#### `gestaoclick_atributos_orcamentos_delete`

Campos extras de orçamentos: Deletar (DELETE /api/atributos_orcamentos/{id}). _(POST /api/gestaoclick/atributos/orcamentos/delete)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso, + `usuario_id`/`loja_id` se multi-conta/loja). Ex. criar cliente: {"tipo_pessoa":"PF","nome":"...","cpf":"..."}. Campos na doc da GestãoClick. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `gestaoclick_atributos_orcamentos_get`

Campos extras de orçamentos: Visualizar (GET /api/atributos_orcamentos/{id}). _(POST /api/gestaoclick/atributos/orcamentos/get)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `query` | string | Não | Query params como JSON string: filtros do recurso + paginação (`pagina`, `ordenacao`, `direcao`) + atribuição (`usuario_id`, `loja_id`). Ex.: {"nome":"acme","pagina":1}. Campos na doc da GestãoClick. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `gestaoclick_atributos_orcamentos_list`

Campos extras de orçamentos: Listar (GET /api/atributos_orcamentos). _(POST /api/gestaoclick/atributos/orcamentos/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `query` | string | Não | Query params como JSON string: filtros do recurso + paginação (`pagina`, `ordenacao`, `direcao`) + atribuição (`usuario_id`, `loja_id`). Ex.: {"nome":"acme","pagina":1}. Campos na doc da GestãoClick. |

#### `gestaoclick_atributos_orcamentos_update`

Campos extras de orçamentos: Editar (PUT /api/atributos_orcamentos/{id}). _(POST /api/gestaoclick/atributos/orcamentos/update)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso, + `usuario_id`/`loja_id` se multi-conta/loja). Ex. criar cliente: {"tipo_pessoa":"PF","nome":"...","cpf":"..."}. Campos na doc da GestãoClick. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `gestaoclick_atributos_ordens_servicos_create`

Campos extras ordens serviço: Cadastrar (POST /api/atributos_ordens_servicos). _(POST /api/gestaoclick/atributos/ordens/servicos/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso, + `usuario_id`/`loja_id` se multi-conta/loja). Ex. criar cliente: {"tipo_pessoa":"PF","nome":"...","cpf":"..."}. Campos na doc da GestãoClick. |

#### `gestaoclick_atributos_ordens_servicos_delete`

Campos extras ordens serviço: Deletar (DELETE /api/atributos_ordens_servicos/{id}). _(POST /api/gestaoclick/atributos/ordens/servicos/delete)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso, + `usuario_id`/`loja_id` se multi-conta/loja). Ex. criar cliente: {"tipo_pessoa":"PF","nome":"...","cpf":"..."}. Campos na doc da GestãoClick. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `gestaoclick_atributos_ordens_servicos_get`

Campos extras ordens serviço: Visualizar (GET /api/atributos_ordens_servicos/{id}). _(POST /api/gestaoclick/atributos/ordens/servicos/get)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `query` | string | Não | Query params como JSON string: filtros do recurso + paginação (`pagina`, `ordenacao`, `direcao`) + atribuição (`usuario_id`, `loja_id`). Ex.: {"nome":"acme","pagina":1}. Campos na doc da GestãoClick. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `gestaoclick_atributos_ordens_servicos_list`

Campos extras ordens serviço: Listar (GET /api/atributos_ordens_servicos). _(POST /api/gestaoclick/atributos/ordens/servicos/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `query` | string | Não | Query params como JSON string: filtros do recurso + paginação (`pagina`, `ordenacao`, `direcao`) + atribuição (`usuario_id`, `loja_id`). Ex.: {"nome":"acme","pagina":1}. Campos na doc da GestãoClick. |

#### `gestaoclick_atributos_ordens_servicos_update`

Campos extras ordens serviço: Editar (PUT /api/atributos_ordens_servicos/{id}). _(POST /api/gestaoclick/atributos/ordens/servicos/update)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso, + `usuario_id`/`loja_id` se multi-conta/loja). Ex. criar cliente: {"tipo_pessoa":"PF","nome":"...","cpf":"..."}. Campos na doc da GestãoClick. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `gestaoclick_atributos_produtos_create`

Campos extras de produtos: Cadastrar (POST /api/atributos_produtos). _(POST /api/gestaoclick/atributos/produtos/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso, + `usuario_id`/`loja_id` se multi-conta/loja). Ex. criar cliente: {"tipo_pessoa":"PF","nome":"...","cpf":"..."}. Campos na doc da GestãoClick. |

#### `gestaoclick_atributos_produtos_delete`

Campos extras de produtos: Deletar (DELETE /api/atributos_produtos/{id}). _(POST /api/gestaoclick/atributos/produtos/delete)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso, + `usuario_id`/`loja_id` se multi-conta/loja). Ex. criar cliente: {"tipo_pessoa":"PF","nome":"...","cpf":"..."}. Campos na doc da GestãoClick. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `gestaoclick_atributos_produtos_get`

Campos extras de produtos: Visualizar (GET /api/atributos_produtos/{id}). _(POST /api/gestaoclick/atributos/produtos/get)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `query` | string | Não | Query params como JSON string: filtros do recurso + paginação (`pagina`, `ordenacao`, `direcao`) + atribuição (`usuario_id`, `loja_id`). Ex.: {"nome":"acme","pagina":1}. Campos na doc da GestãoClick. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `gestaoclick_atributos_produtos_list`

Campos extras de produtos: Listar (GET /api/atributos_produtos). _(POST /api/gestaoclick/atributos/produtos/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `query` | string | Não | Query params como JSON string: filtros do recurso + paginação (`pagina`, `ordenacao`, `direcao`) + atribuição (`usuario_id`, `loja_id`). Ex.: {"nome":"acme","pagina":1}. Campos na doc da GestãoClick. |

#### `gestaoclick_atributos_produtos_update`

Campos extras de produtos: Editar (PUT /api/atributos_produtos/{id}). _(POST /api/gestaoclick/atributos/produtos/update)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso, + `usuario_id`/`loja_id` se multi-conta/loja). Ex. criar cliente: {"tipo_pessoa":"PF","nome":"...","cpf":"..."}. Campos na doc da GestãoClick. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `gestaoclick_atributos_vendas_create`

Campos extras vendas: Cadastrar (POST /api/atributos_vendas). _(POST /api/gestaoclick/atributos/vendas/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso, + `usuario_id`/`loja_id` se multi-conta/loja). Ex. criar cliente: {"tipo_pessoa":"PF","nome":"...","cpf":"..."}. Campos na doc da GestãoClick. |

#### `gestaoclick_atributos_vendas_delete`

Campos extras vendas: Deletar (DELETE /api/atributos_vendas/{id}). _(POST /api/gestaoclick/atributos/vendas/delete)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso, + `usuario_id`/`loja_id` se multi-conta/loja). Ex. criar cliente: {"tipo_pessoa":"PF","nome":"...","cpf":"..."}. Campos na doc da GestãoClick. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `gestaoclick_atributos_vendas_get`

Campos extras vendas: Visualizar (GET /api/atributos_vendas/{id}). _(POST /api/gestaoclick/atributos/vendas/get)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `query` | string | Não | Query params como JSON string: filtros do recurso + paginação (`pagina`, `ordenacao`, `direcao`) + atribuição (`usuario_id`, `loja_id`). Ex.: {"nome":"acme","pagina":1}. Campos na doc da GestãoClick. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `gestaoclick_atributos_vendas_list`

Campos extras vendas: Listar (GET /api/atributos_vendas). _(POST /api/gestaoclick/atributos/vendas/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `query` | string | Não | Query params como JSON string: filtros do recurso + paginação (`pagina`, `ordenacao`, `direcao`) + atribuição (`usuario_id`, `loja_id`). Ex.: {"nome":"acme","pagina":1}. Campos na doc da GestãoClick. |

#### `gestaoclick_atributos_vendas_update`

Campos extras vendas: Editar (PUT /api/atributos_vendas/{id}). _(POST /api/gestaoclick/atributos/vendas/update)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso, + `usuario_id`/`loja_id` se multi-conta/loja). Ex. criar cliente: {"tipo_pessoa":"PF","nome":"...","cpf":"..."}. Campos na doc da GestãoClick. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `gestaoclick_centros_custos_list`

Centros de custos: Listar (GET /api/centros_custos). _(POST /api/gestaoclick/centros/custos/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `query` | string | Não | Query params como JSON string: filtros do recurso + paginação (`pagina`, `ordenacao`, `direcao`) + atribuição (`usuario_id`, `loja_id`). Ex.: {"nome":"acme","pagina":1}. Campos na doc da GestãoClick. |

#### `gestaoclick_cidades_list`

Cidades: Listar (GET /api/cidades). _(POST /api/gestaoclick/cidades/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `query` | string | Não | Query params como JSON string: filtros do recurso + paginação (`pagina`, `ordenacao`, `direcao`) + atribuição (`usuario_id`, `loja_id`). Ex.: {"nome":"acme","pagina":1}. Campos na doc da GestãoClick. |

#### `gestaoclick_clientes_create`

Clientes: Cadastrar (POST /api/clientes). _(POST /api/gestaoclick/clientes/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso, + `usuario_id`/`loja_id` se multi-conta/loja). Ex. criar cliente: {"tipo_pessoa":"PF","nome":"...","cpf":"..."}. Campos na doc da GestãoClick. |

#### `gestaoclick_clientes_delete`

Clientes: Deletar (DELETE /api/clientes/{id}). _(POST /api/gestaoclick/clientes/delete)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso, + `usuario_id`/`loja_id` se multi-conta/loja). Ex. criar cliente: {"tipo_pessoa":"PF","nome":"...","cpf":"..."}. Campos na doc da GestãoClick. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `gestaoclick_clientes_get`

Clientes: Visualizar (GET /api/clientes/{id}). _(POST /api/gestaoclick/clientes/get)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `query` | string | Não | Query params como JSON string: filtros do recurso + paginação (`pagina`, `ordenacao`, `direcao`) + atribuição (`usuario_id`, `loja_id`). Ex.: {"nome":"acme","pagina":1}. Campos na doc da GestãoClick. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `gestaoclick_clientes_list`

Clientes: Listar (GET /api/clientes). _(POST /api/gestaoclick/clientes/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `query` | string | Não | Query params como JSON string: filtros do recurso + paginação (`pagina`, `ordenacao`, `direcao`) + atribuição (`usuario_id`, `loja_id`). Ex.: {"nome":"acme","pagina":1}. Campos na doc da GestãoClick. |

#### `gestaoclick_clientes_update`

Clientes: Editar (PUT /api/clientes/{id}). _(POST /api/gestaoclick/clientes/update)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso, + `usuario_id`/`loja_id` se multi-conta/loja). Ex. criar cliente: {"tipo_pessoa":"PF","nome":"...","cpf":"..."}. Campos na doc da GestãoClick. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `gestaoclick_compras_create`

Compras: Cadastrar (POST /api/compras). _(POST /api/gestaoclick/compras/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso, + `usuario_id`/`loja_id` se multi-conta/loja). Ex. criar cliente: {"tipo_pessoa":"PF","nome":"...","cpf":"..."}. Campos na doc da GestãoClick. |

#### `gestaoclick_compras_delete`

Compras: Deletar (DELETE /api/compras/{id}). _(POST /api/gestaoclick/compras/delete)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso, + `usuario_id`/`loja_id` se multi-conta/loja). Ex. criar cliente: {"tipo_pessoa":"PF","nome":"...","cpf":"..."}. Campos na doc da GestãoClick. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `gestaoclick_compras_gerar_parcelas_create`

Compras: Gerar parcelas (POST /api/compras/gerar_parcelas). _(POST /api/gestaoclick/compras/gerar/parcelas/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso, + `usuario_id`/`loja_id` se multi-conta/loja). Ex. criar cliente: {"tipo_pessoa":"PF","nome":"...","cpf":"..."}. Campos na doc da GestãoClick. |

#### `gestaoclick_compras_get`

Compras: Visualizar (GET /api/compras/{id}). _(POST /api/gestaoclick/compras/get)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `query` | string | Não | Query params como JSON string: filtros do recurso + paginação (`pagina`, `ordenacao`, `direcao`) + atribuição (`usuario_id`, `loja_id`). Ex.: {"nome":"acme","pagina":1}. Campos na doc da GestãoClick. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `gestaoclick_compras_list`

Compras: Listar (GET /api/compras). _(POST /api/gestaoclick/compras/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `query` | string | Não | Query params como JSON string: filtros do recurso + paginação (`pagina`, `ordenacao`, `direcao`) + atribuição (`usuario_id`, `loja_id`). Ex.: {"nome":"acme","pagina":1}. Campos na doc da GestãoClick. |

#### `gestaoclick_compras_update`

Compras: Editar (PUT /api/compras/{id}). _(POST /api/gestaoclick/compras/update)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso, + `usuario_id`/`loja_id` se multi-conta/loja). Ex. criar cliente: {"tipo_pessoa":"PF","nome":"...","cpf":"..."}. Campos na doc da GestãoClick. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `gestaoclick_contas_bancarias_list`

Contas bancárias: Listar (GET /api/contas_bancarias). _(POST /api/gestaoclick/contas/bancarias/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `query` | string | Não | Query params como JSON string: filtros do recurso + paginação (`pagina`, `ordenacao`, `direcao`) + atribuição (`usuario_id`, `loja_id`). Ex.: {"nome":"acme","pagina":1}. Campos na doc da GestãoClick. |

#### `gestaoclick_estados_list`

Estados: Listar (GET /api/estados). _(POST /api/gestaoclick/estados/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `query` | string | Não | Query params como JSON string: filtros do recurso + paginação (`pagina`, `ordenacao`, `direcao`) + atribuição (`usuario_id`, `loja_id`). Ex.: {"nome":"acme","pagina":1}. Campos na doc da GestãoClick. |

#### `gestaoclick_formas_pagamentos_list`

Formas pagamentos: Listar (GET /api/formas_pagamentos). _(POST /api/gestaoclick/formas/pagamentos/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `query` | string | Não | Query params como JSON string: filtros do recurso + paginação (`pagina`, `ordenacao`, `direcao`) + atribuição (`usuario_id`, `loja_id`). Ex.: {"nome":"acme","pagina":1}. Campos na doc da GestãoClick. |

#### `gestaoclick_fornecedores_create`

Fornecedores: Cadastrar (POST /api/fornecedores). _(POST /api/gestaoclick/fornecedores/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso, + `usuario_id`/`loja_id` se multi-conta/loja). Ex. criar cliente: {"tipo_pessoa":"PF","nome":"...","cpf":"..."}. Campos na doc da GestãoClick. |

#### `gestaoclick_fornecedores_delete`

Fornecedores: Deletar (DELETE /api/fornecedores/{id}). _(POST /api/gestaoclick/fornecedores/delete)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso, + `usuario_id`/`loja_id` se multi-conta/loja). Ex. criar cliente: {"tipo_pessoa":"PF","nome":"...","cpf":"..."}. Campos na doc da GestãoClick. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `gestaoclick_fornecedores_get`

Fornecedores: Visualizar (GET /api/fornecedores/{id}). _(POST /api/gestaoclick/fornecedores/get)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `query` | string | Não | Query params como JSON string: filtros do recurso + paginação (`pagina`, `ordenacao`, `direcao`) + atribuição (`usuario_id`, `loja_id`). Ex.: {"nome":"acme","pagina":1}. Campos na doc da GestãoClick. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `gestaoclick_fornecedores_list`

Fornecedores: Listar (GET /api/fornecedores). _(POST /api/gestaoclick/fornecedores/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `query` | string | Não | Query params como JSON string: filtros do recurso + paginação (`pagina`, `ordenacao`, `direcao`) + atribuição (`usuario_id`, `loja_id`). Ex.: {"nome":"acme","pagina":1}. Campos na doc da GestãoClick. |

#### `gestaoclick_fornecedores_update`

Fornecedores: Editar (PUT /api/fornecedores/{id}). _(POST /api/gestaoclick/fornecedores/update)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso, + `usuario_id`/`loja_id` se multi-conta/loja). Ex. criar cliente: {"tipo_pessoa":"PF","nome":"...","cpf":"..."}. Campos na doc da GestãoClick. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `gestaoclick_funcionarios_list`

Funcionários: Listar (GET /api/funcionarios). _(POST /api/gestaoclick/funcionarios/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `query` | string | Não | Query params como JSON string: filtros do recurso + paginação (`pagina`, `ordenacao`, `direcao`) + atribuição (`usuario_id`, `loja_id`). Ex.: {"nome":"acme","pagina":1}. Campos na doc da GestãoClick. |

#### `gestaoclick_grupos_produtos_list`

Grupos de produtos: Listar (GET /api/grupos_produtos). _(POST /api/gestaoclick/grupos/produtos/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `query` | string | Não | Query params como JSON string: filtros do recurso + paginação (`pagina`, `ordenacao`, `direcao`) + atribuição (`usuario_id`, `loja_id`). Ex.: {"nome":"acme","pagina":1}. Campos na doc da GestãoClick. |

#### `gestaoclick_list_accounts`

Lista as conexões (contas) GestãoClick vinculadas a este install — id, label. _(POST /api/gestaoclick/list/accounts)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |

#### `gestaoclick_lojas_list`

Lojas: Listar (GET /api/lojas). _(POST /api/gestaoclick/lojas/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `query` | string | Não | Query params como JSON string: filtros do recurso + paginação (`pagina`, `ordenacao`, `direcao`) + atribuição (`usuario_id`, `loja_id`). Ex.: {"nome":"acme","pagina":1}. Campos na doc da GestãoClick. |

#### `gestaoclick_notas_fiscais_consumidores_cancelar_create`

Notas Fiscais de Consumidores: Cancelar (POST /api/notas_fiscais_consumidores/cancelar/{id}). _(POST /api/gestaoclick/notas/fiscais/consumidores/cancelar/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso, + `usuario_id`/`loja_id` se multi-conta/loja). Ex. criar cliente: {"tipo_pessoa":"PF","nome":"...","cpf":"..."}. Campos na doc da GestãoClick. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `gestaoclick_notas_fiscais_consumidores_create`

Notas Fiscais de Consumidores: Cadastrar (POST /api/notas_fiscais_consumidores). _(POST /api/gestaoclick/notas/fiscais/consumidores/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso, + `usuario_id`/`loja_id` se multi-conta/loja). Ex. criar cliente: {"tipo_pessoa":"PF","nome":"...","cpf":"..."}. Campos na doc da GestãoClick. |

#### `gestaoclick_notas_fiscais_consumidores_delete`

Notas Fiscais de Consumidores: Deletar (DELETE /api/notas_fiscais_consumidores/{id}). _(POST /api/gestaoclick/notas/fiscais/consumidores/delete)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso, + `usuario_id`/`loja_id` se multi-conta/loja). Ex. criar cliente: {"tipo_pessoa":"PF","nome":"...","cpf":"..."}. Campos na doc da GestãoClick. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `gestaoclick_notas_fiscais_consumidores_emitir_create`

Notas Fiscais de Consumidores: Emitir (POST /api/notas_fiscais_consumidores/emitir/{id}). _(POST /api/gestaoclick/notas/fiscais/consumidores/emitir/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso, + `usuario_id`/`loja_id` se multi-conta/loja). Ex. criar cliente: {"tipo_pessoa":"PF","nome":"...","cpf":"..."}. Campos na doc da GestãoClick. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `gestaoclick_notas_fiscais_consumidores_get`

Notas Fiscais de Consumidores: Visualizar (GET /api/notas_fiscais_consumidores/{id}). _(POST /api/gestaoclick/notas/fiscais/consumidores/get)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `query` | string | Não | Query params como JSON string: filtros do recurso + paginação (`pagina`, `ordenacao`, `direcao`) + atribuição (`usuario_id`, `loja_id`). Ex.: {"nome":"acme","pagina":1}. Campos na doc da GestãoClick. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `gestaoclick_notas_fiscais_consumidores_list`

Notas Fiscais de Consumidores: Listar (GET /api/notas_fiscais_consumidores). _(POST /api/gestaoclick/notas/fiscais/consumidores/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `query` | string | Não | Query params como JSON string: filtros do recurso + paginação (`pagina`, `ordenacao`, `direcao`) + atribuição (`usuario_id`, `loja_id`). Ex.: {"nome":"acme","pagina":1}. Campos na doc da GestãoClick. |

#### `gestaoclick_notas_fiscais_consumidores_update`

Notas Fiscais de Consumidores: Editar (PUT /api/notas_fiscais_consumidores/{id}). _(POST /api/gestaoclick/notas/fiscais/consumidores/update)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso, + `usuario_id`/`loja_id` se multi-conta/loja). Ex. criar cliente: {"tipo_pessoa":"PF","nome":"...","cpf":"..."}. Campos na doc da GestãoClick. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `gestaoclick_notas_fiscais_produtos_cancelar_create`

Notas Fiscais de Produtos: Cancelar (POST /api/notas_fiscais_produtos/cancelar/{id}). _(POST /api/gestaoclick/notas/fiscais/produtos/cancelar/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso, + `usuario_id`/`loja_id` se multi-conta/loja). Ex. criar cliente: {"tipo_pessoa":"PF","nome":"...","cpf":"..."}. Campos na doc da GestãoClick. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `gestaoclick_notas_fiscais_produtos_create`

Notas Fiscais de Produtos: Cadastrar (POST /api/notas_fiscais_produtos). _(POST /api/gestaoclick/notas/fiscais/produtos/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso, + `usuario_id`/`loja_id` se multi-conta/loja). Ex. criar cliente: {"tipo_pessoa":"PF","nome":"...","cpf":"..."}. Campos na doc da GestãoClick. |

#### `gestaoclick_notas_fiscais_produtos_delete`

Notas Fiscais de Produtos: Deletar (DELETE /api/notas_fiscais_produtos/{id}). _(POST /api/gestaoclick/notas/fiscais/produtos/delete)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso, + `usuario_id`/`loja_id` se multi-conta/loja). Ex. criar cliente: {"tipo_pessoa":"PF","nome":"...","cpf":"..."}. Campos na doc da GestãoClick. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `gestaoclick_notas_fiscais_produtos_emitir_create`

Notas Fiscais de Produtos: Emitir (POST /api/notas_fiscais_produtos/emitir/{id}). _(POST /api/gestaoclick/notas/fiscais/produtos/emitir/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso, + `usuario_id`/`loja_id` se multi-conta/loja). Ex. criar cliente: {"tipo_pessoa":"PF","nome":"...","cpf":"..."}. Campos na doc da GestãoClick. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `gestaoclick_notas_fiscais_produtos_get`

Notas Fiscais de Produtos: Visualizar (GET /api/notas_fiscais_produtos/{id}). _(POST /api/gestaoclick/notas/fiscais/produtos/get)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `query` | string | Não | Query params como JSON string: filtros do recurso + paginação (`pagina`, `ordenacao`, `direcao`) + atribuição (`usuario_id`, `loja_id`). Ex.: {"nome":"acme","pagina":1}. Campos na doc da GestãoClick. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `gestaoclick_notas_fiscais_produtos_list`

Notas Fiscais de Produtos: Listar (GET /api/notas_fiscais_produtos). _(POST /api/gestaoclick/notas/fiscais/produtos/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `query` | string | Não | Query params como JSON string: filtros do recurso + paginação (`pagina`, `ordenacao`, `direcao`) + atribuição (`usuario_id`, `loja_id`). Ex.: {"nome":"acme","pagina":1}. Campos na doc da GestãoClick. |

#### `gestaoclick_notas_fiscais_produtos_update`

Notas Fiscais de Produtos: Editar (PUT /api/notas_fiscais_produtos/{id}). _(POST /api/gestaoclick/notas/fiscais/produtos/update)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso, + `usuario_id`/`loja_id` se multi-conta/loja). Ex. criar cliente: {"tipo_pessoa":"PF","nome":"...","cpf":"..."}. Campos na doc da GestãoClick. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `gestaoclick_notas_fiscais_servicos_cancelar_create`

Notas Fiscais de Serviços: Cancelar (POST /api/notas_fiscais_servicos/cancelar/{id}). _(POST /api/gestaoclick/notas/fiscais/servicos/cancelar/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso, + `usuario_id`/`loja_id` se multi-conta/loja). Ex. criar cliente: {"tipo_pessoa":"PF","nome":"...","cpf":"..."}. Campos na doc da GestãoClick. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `gestaoclick_notas_fiscais_servicos_create`

Notas Fiscais de Serviços: Cadastrar (POST /api/notas_fiscais_servicos). _(POST /api/gestaoclick/notas/fiscais/servicos/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso, + `usuario_id`/`loja_id` se multi-conta/loja). Ex. criar cliente: {"tipo_pessoa":"PF","nome":"...","cpf":"..."}. Campos na doc da GestãoClick. |

#### `gestaoclick_notas_fiscais_servicos_delete`

Notas Fiscais de Serviços: Deletar (DELETE /api/notas_fiscais_servicos/{id}). _(POST /api/gestaoclick/notas/fiscais/servicos/delete)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso, + `usuario_id`/`loja_id` se multi-conta/loja). Ex. criar cliente: {"tipo_pessoa":"PF","nome":"...","cpf":"..."}. Campos na doc da GestãoClick. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `gestaoclick_notas_fiscais_servicos_emitir_create`

Notas Fiscais de Serviços: Emitir (POST /api/notas_fiscais_servicos/emitir/{id}). _(POST /api/gestaoclick/notas/fiscais/servicos/emitir/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso, + `usuario_id`/`loja_id` se multi-conta/loja). Ex. criar cliente: {"tipo_pessoa":"PF","nome":"...","cpf":"..."}. Campos na doc da GestãoClick. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `gestaoclick_notas_fiscais_servicos_get`

Notas Fiscais de Serviços: Visualizar (GET /api/notas_fiscais_servicos/{id}). _(POST /api/gestaoclick/notas/fiscais/servicos/get)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `query` | string | Não | Query params como JSON string: filtros do recurso + paginação (`pagina`, `ordenacao`, `direcao`) + atribuição (`usuario_id`, `loja_id`). Ex.: {"nome":"acme","pagina":1}. Campos na doc da GestãoClick. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `gestaoclick_notas_fiscais_servicos_list`

Notas Fiscais de Serviços: Listar (GET /api/notas_fiscais_servicos). _(POST /api/gestaoclick/notas/fiscais/servicos/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `query` | string | Não | Query params como JSON string: filtros do recurso + paginação (`pagina`, `ordenacao`, `direcao`) + atribuição (`usuario_id`, `loja_id`). Ex.: {"nome":"acme","pagina":1}. Campos na doc da GestãoClick. |

#### `gestaoclick_notas_fiscais_servicos_update`

Notas Fiscais de Serviços: Editar (PUT /api/notas_fiscais_servicos/{id}). _(POST /api/gestaoclick/notas/fiscais/servicos/update)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso, + `usuario_id`/`loja_id` se multi-conta/loja). Ex. criar cliente: {"tipo_pessoa":"PF","nome":"...","cpf":"..."}. Campos na doc da GestãoClick. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `gestaoclick_orcamentos_create`

Orçamentos: Cadastrar (POST /api/orcamentos). _(POST /api/gestaoclick/orcamentos/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso, + `usuario_id`/`loja_id` se multi-conta/loja). Ex. criar cliente: {"tipo_pessoa":"PF","nome":"...","cpf":"..."}. Campos na doc da GestãoClick. |

#### `gestaoclick_orcamentos_delete`

Orçamentos: Deletar (DELETE /api/orcamentos/{id}). _(POST /api/gestaoclick/orcamentos/delete)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso, + `usuario_id`/`loja_id` se multi-conta/loja). Ex. criar cliente: {"tipo_pessoa":"PF","nome":"...","cpf":"..."}. Campos na doc da GestãoClick. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `gestaoclick_orcamentos_gerar_parcelas_create`

Orçamentos: Gerar parcelas (POST /api/orcamentos/gerar_parcelas). _(POST /api/gestaoclick/orcamentos/gerar/parcelas/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso, + `usuario_id`/`loja_id` se multi-conta/loja). Ex. criar cliente: {"tipo_pessoa":"PF","nome":"...","cpf":"..."}. Campos na doc da GestãoClick. |

#### `gestaoclick_orcamentos_get`

Orçamentos: Visualizar (GET /api/orcamentos/{id}). _(POST /api/gestaoclick/orcamentos/get)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `query` | string | Não | Query params como JSON string: filtros do recurso + paginação (`pagina`, `ordenacao`, `direcao`) + atribuição (`usuario_id`, `loja_id`). Ex.: {"nome":"acme","pagina":1}. Campos na doc da GestãoClick. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `gestaoclick_orcamentos_list`

Orçamentos: Listar (GET /api/orcamentos). _(POST /api/gestaoclick/orcamentos/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `query` | string | Não | Query params como JSON string: filtros do recurso + paginação (`pagina`, `ordenacao`, `direcao`) + atribuição (`usuario_id`, `loja_id`). Ex.: {"nome":"acme","pagina":1}. Campos na doc da GestãoClick. |

#### `gestaoclick_orcamentos_update`

Orçamentos: Editar (PUT /api/orcamentos/{id}). _(POST /api/gestaoclick/orcamentos/update)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso, + `usuario_id`/`loja_id` se multi-conta/loja). Ex. criar cliente: {"tipo_pessoa":"PF","nome":"...","cpf":"..."}. Campos na doc da GestãoClick. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `gestaoclick_ordens_servicos_create`

Ordens de serviços: Cadastrar (POST /api/ordens_servicos). _(POST /api/gestaoclick/ordens/servicos/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso, + `usuario_id`/`loja_id` se multi-conta/loja). Ex. criar cliente: {"tipo_pessoa":"PF","nome":"...","cpf":"..."}. Campos na doc da GestãoClick. |

#### `gestaoclick_ordens_servicos_delete`

Ordens de serviços: Deletar (DELETE /api/ordens_servicos/{id}). _(POST /api/gestaoclick/ordens/servicos/delete)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso, + `usuario_id`/`loja_id` se multi-conta/loja). Ex. criar cliente: {"tipo_pessoa":"PF","nome":"...","cpf":"..."}. Campos na doc da GestãoClick. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `gestaoclick_ordens_servicos_gerar_parcelas_create`

Ordens de serviços: Gerar parcelas (POST /api/ordens_servicos/gerar_parcelas). _(POST /api/gestaoclick/ordens/servicos/gerar/parcelas/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso, + `usuario_id`/`loja_id` se multi-conta/loja). Ex. criar cliente: {"tipo_pessoa":"PF","nome":"...","cpf":"..."}. Campos na doc da GestãoClick. |

#### `gestaoclick_ordens_servicos_get`

Ordens de serviços: Visualizar (GET /api/ordens_servicos/{id}). _(POST /api/gestaoclick/ordens/servicos/get)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `query` | string | Não | Query params como JSON string: filtros do recurso + paginação (`pagina`, `ordenacao`, `direcao`) + atribuição (`usuario_id`, `loja_id`). Ex.: {"nome":"acme","pagina":1}. Campos na doc da GestãoClick. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `gestaoclick_ordens_servicos_list`

Ordens de serviços: Listar (GET /api/ordens_servicos). _(POST /api/gestaoclick/ordens/servicos/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `query` | string | Não | Query params como JSON string: filtros do recurso + paginação (`pagina`, `ordenacao`, `direcao`) + atribuição (`usuario_id`, `loja_id`). Ex.: {"nome":"acme","pagina":1}. Campos na doc da GestãoClick. |

#### `gestaoclick_ordens_servicos_update`

Ordens de serviços: Editar (PUT /api/ordens_servicos/{id}). _(POST /api/gestaoclick/ordens/servicos/update)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso, + `usuario_id`/`loja_id` se multi-conta/loja). Ex. criar cliente: {"tipo_pessoa":"PF","nome":"...","cpf":"..."}. Campos na doc da GestãoClick. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `gestaoclick_pagamentos_create`

Pagamentos: Cadastrar (POST /api/pagamentos). _(POST /api/gestaoclick/pagamentos/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso, + `usuario_id`/`loja_id` se multi-conta/loja). Ex. criar cliente: {"tipo_pessoa":"PF","nome":"...","cpf":"..."}. Campos na doc da GestãoClick. |

#### `gestaoclick_pagamentos_delete`

Pagamentos: Deletar (DELETE /api/pagamentos/{id}). _(POST /api/gestaoclick/pagamentos/delete)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso, + `usuario_id`/`loja_id` se multi-conta/loja). Ex. criar cliente: {"tipo_pessoa":"PF","nome":"...","cpf":"..."}. Campos na doc da GestãoClick. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `gestaoclick_pagamentos_get`

Pagamentos: Visualizar (GET /api/pagamentos/{id}). _(POST /api/gestaoclick/pagamentos/get)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `query` | string | Não | Query params como JSON string: filtros do recurso + paginação (`pagina`, `ordenacao`, `direcao`) + atribuição (`usuario_id`, `loja_id`). Ex.: {"nome":"acme","pagina":1}. Campos na doc da GestãoClick. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `gestaoclick_pagamentos_list`

Pagamentos: Listar (GET /api/pagamentos). _(POST /api/gestaoclick/pagamentos/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `query` | string | Não | Query params como JSON string: filtros do recurso + paginação (`pagina`, `ordenacao`, `direcao`) + atribuição (`usuario_id`, `loja_id`). Ex.: {"nome":"acme","pagina":1}. Campos na doc da GestãoClick. |

#### `gestaoclick_pagamentos_update`

Pagamentos: Editar (PUT /api/pagamentos/{id}). _(POST /api/gestaoclick/pagamentos/update)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso, + `usuario_id`/`loja_id` se multi-conta/loja). Ex. criar cliente: {"tipo_pessoa":"PF","nome":"...","cpf":"..."}. Campos na doc da GestãoClick. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `gestaoclick_planos_contas_list`

Planos de contas: Listar (GET /api/planos_contas). _(POST /api/gestaoclick/planos/contas/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `query` | string | Não | Query params como JSON string: filtros do recurso + paginação (`pagina`, `ordenacao`, `direcao`) + atribuição (`usuario_id`, `loja_id`). Ex.: {"nome":"acme","pagina":1}. Campos na doc da GestãoClick. |

#### `gestaoclick_produtos_create`

Produtos: Cadastrar (POST /api/produtos). _(POST /api/gestaoclick/produtos/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso, + `usuario_id`/`loja_id` se multi-conta/loja). Ex. criar cliente: {"tipo_pessoa":"PF","nome":"...","cpf":"..."}. Campos na doc da GestãoClick. |

#### `gestaoclick_produtos_delete`

Produtos: Deletar (DELETE /api/produtos/{id}). _(POST /api/gestaoclick/produtos/delete)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso, + `usuario_id`/`loja_id` se multi-conta/loja). Ex. criar cliente: {"tipo_pessoa":"PF","nome":"...","cpf":"..."}. Campos na doc da GestãoClick. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `gestaoclick_produtos_get`

Produtos: Visualizar (GET /api/produtos/{id}). _(POST /api/gestaoclick/produtos/get)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `query` | string | Não | Query params como JSON string: filtros do recurso + paginação (`pagina`, `ordenacao`, `direcao`) + atribuição (`usuario_id`, `loja_id`). Ex.: {"nome":"acme","pagina":1}. Campos na doc da GestãoClick. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `gestaoclick_produtos_list`

Produtos: Listar (GET /api/produtos). _(POST /api/gestaoclick/produtos/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `query` | string | Não | Query params como JSON string: filtros do recurso + paginação (`pagina`, `ordenacao`, `direcao`) + atribuição (`usuario_id`, `loja_id`). Ex.: {"nome":"acme","pagina":1}. Campos na doc da GestãoClick. |

#### `gestaoclick_produtos_update`

Produtos: Editar (PUT /api/produtos/{id}). _(POST /api/gestaoclick/produtos/update)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso, + `usuario_id`/`loja_id` se multi-conta/loja). Ex. criar cliente: {"tipo_pessoa":"PF","nome":"...","cpf":"..."}. Campos na doc da GestãoClick. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `gestaoclick_recebimentos_create`

Recebimentos: Cadastrar (POST /api/recebimentos). _(POST /api/gestaoclick/recebimentos/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso, + `usuario_id`/`loja_id` se multi-conta/loja). Ex. criar cliente: {"tipo_pessoa":"PF","nome":"...","cpf":"..."}. Campos na doc da GestãoClick. |

#### `gestaoclick_recebimentos_delete`

Recebimentos: Deletar (DELETE /api/recebimentos/{id}). _(POST /api/gestaoclick/recebimentos/delete)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso, + `usuario_id`/`loja_id` se multi-conta/loja). Ex. criar cliente: {"tipo_pessoa":"PF","nome":"...","cpf":"..."}. Campos na doc da GestãoClick. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `gestaoclick_recebimentos_get`

Recebimentos: Visualizar (GET /api/recebimentos/{id}). _(POST /api/gestaoclick/recebimentos/get)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `query` | string | Não | Query params como JSON string: filtros do recurso + paginação (`pagina`, `ordenacao`, `direcao`) + atribuição (`usuario_id`, `loja_id`). Ex.: {"nome":"acme","pagina":1}. Campos na doc da GestãoClick. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `gestaoclick_recebimentos_list`

Recebimentos: Listar (GET /api/recebimentos). _(POST /api/gestaoclick/recebimentos/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `query` | string | Não | Query params como JSON string: filtros do recurso + paginação (`pagina`, `ordenacao`, `direcao`) + atribuição (`usuario_id`, `loja_id`). Ex.: {"nome":"acme","pagina":1}. Campos na doc da GestãoClick. |

#### `gestaoclick_recebimentos_update`

Recebimentos: Editar (PUT /api/recebimentos/{id}). _(POST /api/gestaoclick/recebimentos/update)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso, + `usuario_id`/`loja_id` se multi-conta/loja). Ex. criar cliente: {"tipo_pessoa":"PF","nome":"...","cpf":"..."}. Campos na doc da GestãoClick. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `gestaoclick_servicos_create`

Serviços: Cadastrar (POST /api/servicos). _(POST /api/gestaoclick/servicos/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso, + `usuario_id`/`loja_id` se multi-conta/loja). Ex. criar cliente: {"tipo_pessoa":"PF","nome":"...","cpf":"..."}. Campos na doc da GestãoClick. |

#### `gestaoclick_servicos_delete`

Serviços: Deletar (DELETE /api/servicos/{id}). _(POST /api/gestaoclick/servicos/delete)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso, + `usuario_id`/`loja_id` se multi-conta/loja). Ex. criar cliente: {"tipo_pessoa":"PF","nome":"...","cpf":"..."}. Campos na doc da GestãoClick. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `gestaoclick_servicos_get`

Serviços: Visualizar (GET /api/servicos/{id}). _(POST /api/gestaoclick/servicos/get)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `query` | string | Não | Query params como JSON string: filtros do recurso + paginação (`pagina`, `ordenacao`, `direcao`) + atribuição (`usuario_id`, `loja_id`). Ex.: {"nome":"acme","pagina":1}. Campos na doc da GestãoClick. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `gestaoclick_servicos_list`

Serviços: Listar (GET /api/servicos). _(POST /api/gestaoclick/servicos/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `query` | string | Não | Query params como JSON string: filtros do recurso + paginação (`pagina`, `ordenacao`, `direcao`) + atribuição (`usuario_id`, `loja_id`). Ex.: {"nome":"acme","pagina":1}. Campos na doc da GestãoClick. |

#### `gestaoclick_servicos_update`

Serviços: Editar (PUT /api/servicos/{id}). _(POST /api/gestaoclick/servicos/update)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso, + `usuario_id`/`loja_id` se multi-conta/loja). Ex. criar cliente: {"tipo_pessoa":"PF","nome":"...","cpf":"..."}. Campos na doc da GestãoClick. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `gestaoclick_situacoes_compras_list`

Situações de compras: Listar (GET /api/situacoes_compras). _(POST /api/gestaoclick/situacoes/compras/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `query` | string | Não | Query params como JSON string: filtros do recurso + paginação (`pagina`, `ordenacao`, `direcao`) + atribuição (`usuario_id`, `loja_id`). Ex.: {"nome":"acme","pagina":1}. Campos na doc da GestãoClick. |

#### `gestaoclick_situacoes_orcamentos_list`

Situações de orçamentos: Listar (GET /api/situacoes_orcamentos). _(POST /api/gestaoclick/situacoes/orcamentos/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `query` | string | Não | Query params como JSON string: filtros do recurso + paginação (`pagina`, `ordenacao`, `direcao`) + atribuição (`usuario_id`, `loja_id`). Ex.: {"nome":"acme","pagina":1}. Campos na doc da GestãoClick. |

#### `gestaoclick_situacoes_ordens_servicos_list`

Situações de OS: Listar (GET /api/situacoes_ordens_servicos). _(POST /api/gestaoclick/situacoes/ordens/servicos/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `query` | string | Não | Query params como JSON string: filtros do recurso + paginação (`pagina`, `ordenacao`, `direcao`) + atribuição (`usuario_id`, `loja_id`). Ex.: {"nome":"acme","pagina":1}. Campos na doc da GestãoClick. |

#### `gestaoclick_situacoes_vendas_list`

Situações de vendas: Listar (GET /api/situacoes_vendas). _(POST /api/gestaoclick/situacoes/vendas/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `query` | string | Não | Query params como JSON string: filtros do recurso + paginação (`pagina`, `ordenacao`, `direcao`) + atribuição (`usuario_id`, `loja_id`). Ex.: {"nome":"acme","pagina":1}. Campos na doc da GestãoClick. |

#### `gestaoclick_tipos_contatos_list`

Tipos de contatos: Listar (GET /api/tipos_contatos). _(POST /api/gestaoclick/tipos/contatos/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `query` | string | Não | Query params como JSON string: filtros do recurso + paginação (`pagina`, `ordenacao`, `direcao`) + atribuição (`usuario_id`, `loja_id`). Ex.: {"nome":"acme","pagina":1}. Campos na doc da GestãoClick. |

#### `gestaoclick_tipos_enderecos_list`

Tipos de endereços: Listar (GET /api/tipos_enderecos). _(POST /api/gestaoclick/tipos/enderecos/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `query` | string | Não | Query params como JSON string: filtros do recurso + paginação (`pagina`, `ordenacao`, `direcao`) + atribuição (`usuario_id`, `loja_id`). Ex.: {"nome":"acme","pagina":1}. Campos na doc da GestãoClick. |

#### `gestaoclick_transportadoras_create`

Transportadoras: Cadastrar (POST /api/transportadoras). _(POST /api/gestaoclick/transportadoras/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso, + `usuario_id`/`loja_id` se multi-conta/loja). Ex. criar cliente: {"tipo_pessoa":"PF","nome":"...","cpf":"..."}. Campos na doc da GestãoClick. |

#### `gestaoclick_transportadoras_delete`

Transportadoras: Deletar (DELETE /api/transportadoras/{id}). _(POST /api/gestaoclick/transportadoras/delete)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso, + `usuario_id`/`loja_id` se multi-conta/loja). Ex. criar cliente: {"tipo_pessoa":"PF","nome":"...","cpf":"..."}. Campos na doc da GestãoClick. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `gestaoclick_transportadoras_get`

Transportadoras: Visualizar (GET /api/transportadoras/{id}). _(POST /api/gestaoclick/transportadoras/get)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `query` | string | Não | Query params como JSON string: filtros do recurso + paginação (`pagina`, `ordenacao`, `direcao`) + atribuição (`usuario_id`, `loja_id`). Ex.: {"nome":"acme","pagina":1}. Campos na doc da GestãoClick. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `gestaoclick_transportadoras_list`

Transportadoras: Listar (GET /api/transportadoras). _(POST /api/gestaoclick/transportadoras/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `query` | string | Não | Query params como JSON string: filtros do recurso + paginação (`pagina`, `ordenacao`, `direcao`) + atribuição (`usuario_id`, `loja_id`). Ex.: {"nome":"acme","pagina":1}. Campos na doc da GestãoClick. |

#### `gestaoclick_transportadoras_update`

Transportadoras: Editar (PUT /api/transportadoras/{id}). _(POST /api/gestaoclick/transportadoras/update)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso, + `usuario_id`/`loja_id` se multi-conta/loja). Ex. criar cliente: {"tipo_pessoa":"PF","nome":"...","cpf":"..."}. Campos na doc da GestãoClick. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `gestaoclick_usuarios_list`

Usuários: Listar (GET /api/usuarios). _(POST /api/gestaoclick/usuarios/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `query` | string | Não | Query params como JSON string: filtros do recurso + paginação (`pagina`, `ordenacao`, `direcao`) + atribuição (`usuario_id`, `loja_id`). Ex.: {"nome":"acme","pagina":1}. Campos na doc da GestãoClick. |

#### `gestaoclick_vendas_create`

Vendas: Cadastrar (POST /api/vendas). _(POST /api/gestaoclick/vendas/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso, + `usuario_id`/`loja_id` se multi-conta/loja). Ex. criar cliente: {"tipo_pessoa":"PF","nome":"...","cpf":"..."}. Campos na doc da GestãoClick. |

#### `gestaoclick_vendas_delete`

Vendas: Deletar (DELETE /api/vendas/{id}). _(POST /api/gestaoclick/vendas/delete)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso, + `usuario_id`/`loja_id` se multi-conta/loja). Ex. criar cliente: {"tipo_pessoa":"PF","nome":"...","cpf":"..."}. Campos na doc da GestãoClick. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `gestaoclick_vendas_gerar_parcelas_create`

Vendas: Gerar parcelas (POST /api/vendas/gerar_parcelas). _(POST /api/gestaoclick/vendas/gerar/parcelas/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso, + `usuario_id`/`loja_id` se multi-conta/loja). Ex. criar cliente: {"tipo_pessoa":"PF","nome":"...","cpf":"..."}. Campos na doc da GestãoClick. |

#### `gestaoclick_vendas_get`

Vendas: Visualizar (GET /api/vendas/{id}). _(POST /api/gestaoclick/vendas/get)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `query` | string | Não | Query params como JSON string: filtros do recurso + paginação (`pagina`, `ordenacao`, `direcao`) + atribuição (`usuario_id`, `loja_id`). Ex.: {"nome":"acme","pagina":1}. Campos na doc da GestãoClick. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `gestaoclick_vendas_list`

Vendas: Listar (GET /api/vendas). _(POST /api/gestaoclick/vendas/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `query` | string | Não | Query params como JSON string: filtros do recurso + paginação (`pagina`, `ordenacao`, `direcao`) + atribuição (`usuario_id`, `loja_id`). Ex.: {"nome":"acme","pagina":1}. Campos na doc da GestãoClick. |

#### `gestaoclick_vendas_update`

Vendas: Editar (PUT /api/vendas/{id}). _(POST /api/gestaoclick/vendas/update)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas GestãoClick conectadas: id ou label da conexão. Veja gestaoclick_list_accounts. |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso, + `usuario_id`/`loja_id` se multi-conta/loja). Ex. criar cliente: {"tipo_pessoa":"PF","nome":"...","cpf":"..."}. Campos na doc da GestãoClick. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

---

Este MCP também funciona via **conexão MCP** (Claude / Cursor) em `https://api.mcp.ai/p_gestaoclick` — veja o [README](../../README.md). A skill acima é pra consumir a **REST API** direto (agente próprio / código).
