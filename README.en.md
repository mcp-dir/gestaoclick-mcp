# GestãoClick

### GestãoClick for Claude, ChatGPT and AI agents

GestãoClick ERP (business management for SMBs) via the official API: customers, suppliers, products and services, quotes, sales, service orders, purchases, invoices (product, consumer, service) and finance (payments, receivables, bank accounts, chart of accounts, cost centers). Generate the key pair in the dashboard under My apps, API.

- 📊 **127 tools**
- ✏️ **Read and write**
- 💬 **Works with any MCP client**: Claude Desktop, Cursor, VS Code, Cline, Continue
- 🔑 **Magic-link login (no password)**

[Portuguese version](README.md) · [Full docs (PT-BR)](docs/)

---

## One-click install

### Claude (Web and Desktop)

[➕ Open in Claude and connect](https://claude.ai/new?modal=add-custom-connector#settings/customize-connectors)

Manual: [claude.ai/customize/connectors](https://claude.ai/customize/connectors?surface=cowork) → **+** → **Add custom connector** → name `GestãoClick`, URL `https://api.mcp.ai/p_gestaoclick`.

### Cursor

[➕ Install in Cursor](cursor://anysphere.cursor-deeplink/mcp/install?name=gestaoclick&config=eyJ1cmwiOiJodHRwczovL2FwaS5tY3AuYWkvcF9nZXN0YW9jbGljayJ9)

### VS Code (Copilot Chat)

[➕ Install in VS Code](vscode:mcp/install?name=gestaoclick&config=%7B%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A%2F%2Fapi.mcp.ai%2Fp_gestaoclick%22%7D)

### Any other MCP-over-HTTP client

```
https://api.mcp.ai/p_gestaoclick
```

---

## 127 tools

| Tool | Description |
|---|---|
| `gestaoclick_list_accounts` | Lista as conexões (contas) GestãoClick vinculadas a este install — id, label. |
| `gestaoclick_atributos_cadastros_create` | Campos extras de cadastros: Cadastrar (POST /api/atributos_cadastros). |
| `gestaoclick_atributos_cadastros_delete` | Campos extras de cadastros: Deletar (DELETE /api/atributos_cadastros/{id}). |
| `gestaoclick_atributos_cadastros_get` | Campos extras de cadastros: Visualizar (GET /api/atributos_cadastros/{id}). |
| `gestaoclick_atributos_cadastros_list` | Campos extras de cadastros: Listar (GET /api/atributos_cadastros). |
| `gestaoclick_atributos_cadastros_update` | Campos extras de cadastros: Editar (PUT /api/atributos_cadastros/{id}). |
| `gestaoclick_atributos_financeiros_create` | Campos extras financeiros: Cadastrar (POST /api/atributos_financeiros). |
| `gestaoclick_atributos_financeiros_delete` | Campos extras financeiros: Deletar (DELETE /api/atributos_financeiros/{id}). |
| `gestaoclick_atributos_financeiros_get` | Campos extras financeiros: Visualizar (GET /api/atributos_financeiros/{id}). |
| `gestaoclick_atributos_financeiros_list` | Campos extras financeiros: Listar (GET /api/atributos_financeiros). |
| `gestaoclick_atributos_financeiros_update` | Campos extras financeiros: Editar (PUT /api/atributos_financeiros/{id}). |
| `gestaoclick_atributos_orcamentos_create` | Campos extras de orçamentos: Cadastrar (POST /api/atributos_orcamentos). |
| `gestaoclick_atributos_orcamentos_delete` | Campos extras de orçamentos: Deletar (DELETE /api/atributos_orcamentos/{id}). |
| `gestaoclick_atributos_orcamentos_get` | Campos extras de orçamentos: Visualizar (GET /api/atributos_orcamentos/{id}). |
| `gestaoclick_atributos_orcamentos_list` | Campos extras de orçamentos: Listar (GET /api/atributos_orcamentos). |
| `gestaoclick_atributos_orcamentos_update` | Campos extras de orçamentos: Editar (PUT /api/atributos_orcamentos/{id}). |
| `gestaoclick_atributos_ordens_servicos_create` | Campos extras ordens serviço: Cadastrar (POST /api/atributos_ordens_servicos). |
| `gestaoclick_atributos_ordens_servicos_delete` | Campos extras ordens serviço: Deletar (DELETE /api/atributos_ordens_servicos/{id}). |
| `gestaoclick_atributos_ordens_servicos_get` | Campos extras ordens serviço: Visualizar (GET /api/atributos_ordens_servicos/{id}). |
| `gestaoclick_atributos_ordens_servicos_list` | Campos extras ordens serviço: Listar (GET /api/atributos_ordens_servicos). |
| `gestaoclick_atributos_ordens_servicos_update` | Campos extras ordens serviço: Editar (PUT /api/atributos_ordens_servicos/{id}). |
| `gestaoclick_atributos_produtos_create` | Campos extras de produtos: Cadastrar (POST /api/atributos_produtos). |
| `gestaoclick_atributos_produtos_delete` | Campos extras de produtos: Deletar (DELETE /api/atributos_produtos/{id}). |
| `gestaoclick_atributos_produtos_get` | Campos extras de produtos: Visualizar (GET /api/atributos_produtos/{id}). |
| `gestaoclick_atributos_produtos_list` | Campos extras de produtos: Listar (GET /api/atributos_produtos). |
| `gestaoclick_atributos_produtos_update` | Campos extras de produtos: Editar (PUT /api/atributos_produtos/{id}). |
| `gestaoclick_atributos_vendas_create` | Campos extras vendas: Cadastrar (POST /api/atributos_vendas). |
| `gestaoclick_atributos_vendas_delete` | Campos extras vendas: Deletar (DELETE /api/atributos_vendas/{id}). |
| `gestaoclick_atributos_vendas_get` | Campos extras vendas: Visualizar (GET /api/atributos_vendas/{id}). |
| `gestaoclick_atributos_vendas_list` | Campos extras vendas: Listar (GET /api/atributos_vendas). |
| `gestaoclick_atributos_vendas_update` | Campos extras vendas: Editar (PUT /api/atributos_vendas/{id}). |
| `gestaoclick_centros_custos_list` | Centros de custos: Listar (GET /api/centros_custos). |
| `gestaoclick_cidades_list` | Cidades: Listar (GET /api/cidades). |
| `gestaoclick_clientes_create` | Clientes: Cadastrar (POST /api/clientes). |
| `gestaoclick_clientes_delete` | Clientes: Deletar (DELETE /api/clientes/{id}). |
| `gestaoclick_clientes_get` | Clientes: Visualizar (GET /api/clientes/{id}). |
| `gestaoclick_clientes_list` | Clientes: Listar (GET /api/clientes). |
| `gestaoclick_clientes_update` | Clientes: Editar (PUT /api/clientes/{id}). |
| `gestaoclick_compras_create` | Compras: Cadastrar (POST /api/compras). |
| `gestaoclick_compras_delete` | Compras: Deletar (DELETE /api/compras/{id}). |
| `gestaoclick_compras_gerar_parcelas_create` | Compras: Gerar parcelas (POST /api/compras/gerar_parcelas). |
| `gestaoclick_compras_get` | Compras: Visualizar (GET /api/compras/{id}). |
| `gestaoclick_compras_list` | Compras: Listar (GET /api/compras). |
| `gestaoclick_compras_update` | Compras: Editar (PUT /api/compras/{id}). |
| `gestaoclick_contas_bancarias_list` | Contas bancárias: Listar (GET /api/contas_bancarias). |
| `gestaoclick_estados_list` | Estados: Listar (GET /api/estados). |
| `gestaoclick_formas_pagamentos_list` | Formas pagamentos: Listar (GET /api/formas_pagamentos). |
| `gestaoclick_fornecedores_create` | Fornecedores: Cadastrar (POST /api/fornecedores). |
| `gestaoclick_fornecedores_delete` | Fornecedores: Deletar (DELETE /api/fornecedores/{id}). |
| `gestaoclick_fornecedores_get` | Fornecedores: Visualizar (GET /api/fornecedores/{id}). |
| `gestaoclick_fornecedores_list` | Fornecedores: Listar (GET /api/fornecedores). |
| `gestaoclick_fornecedores_update` | Fornecedores: Editar (PUT /api/fornecedores/{id}). |
| `gestaoclick_funcionarios_list` | Funcionários: Listar (GET /api/funcionarios). |
| `gestaoclick_grupos_produtos_list` | Grupos de produtos: Listar (GET /api/grupos_produtos). |
| `gestaoclick_lojas_list` | Lojas: Listar (GET /api/lojas). |
| `gestaoclick_notas_fiscais_consumidores_cancelar_create` | Notas Fiscais de Consumidores: Cancelar (POST /api/notas_fiscais_consumidores/cancelar/{id}). |
| `gestaoclick_notas_fiscais_consumidores_create` | Notas Fiscais de Consumidores: Cadastrar (POST /api/notas_fiscais_consumidores). |
| `gestaoclick_notas_fiscais_consumidores_delete` | Notas Fiscais de Consumidores: Deletar (DELETE /api/notas_fiscais_consumidores/{id}). |
| `gestaoclick_notas_fiscais_consumidores_emitir_create` | Notas Fiscais de Consumidores: Emitir (POST /api/notas_fiscais_consumidores/emitir/{id}). |
| `gestaoclick_notas_fiscais_consumidores_get` | Notas Fiscais de Consumidores: Visualizar (GET /api/notas_fiscais_consumidores/{id}). |
| `gestaoclick_notas_fiscais_consumidores_list` | Notas Fiscais de Consumidores: Listar (GET /api/notas_fiscais_consumidores). |
| `gestaoclick_notas_fiscais_consumidores_update` | Notas Fiscais de Consumidores: Editar (PUT /api/notas_fiscais_consumidores/{id}). |
| `gestaoclick_notas_fiscais_produtos_cancelar_create` | Notas Fiscais de Produtos: Cancelar (POST /api/notas_fiscais_produtos/cancelar/{id}). |
| `gestaoclick_notas_fiscais_produtos_create` | Notas Fiscais de Produtos: Cadastrar (POST /api/notas_fiscais_produtos). |
| `gestaoclick_notas_fiscais_produtos_delete` | Notas Fiscais de Produtos: Deletar (DELETE /api/notas_fiscais_produtos/{id}). |
| `gestaoclick_notas_fiscais_produtos_emitir_create` | Notas Fiscais de Produtos: Emitir (POST /api/notas_fiscais_produtos/emitir/{id}). |
| `gestaoclick_notas_fiscais_produtos_get` | Notas Fiscais de Produtos: Visualizar (GET /api/notas_fiscais_produtos/{id}). |
| `gestaoclick_notas_fiscais_produtos_list` | Notas Fiscais de Produtos: Listar (GET /api/notas_fiscais_produtos). |
| `gestaoclick_notas_fiscais_produtos_update` | Notas Fiscais de Produtos: Editar (PUT /api/notas_fiscais_produtos/{id}). |
| `gestaoclick_notas_fiscais_servicos_cancelar_create` | Notas Fiscais de Serviços: Cancelar (POST /api/notas_fiscais_servicos/cancelar/{id}). |
| `gestaoclick_notas_fiscais_servicos_create` | Notas Fiscais de Serviços: Cadastrar (POST /api/notas_fiscais_servicos). |
| `gestaoclick_notas_fiscais_servicos_delete` | Notas Fiscais de Serviços: Deletar (DELETE /api/notas_fiscais_servicos/{id}). |
| `gestaoclick_notas_fiscais_servicos_emitir_create` | Notas Fiscais de Serviços: Emitir (POST /api/notas_fiscais_servicos/emitir/{id}). |
| `gestaoclick_notas_fiscais_servicos_get` | Notas Fiscais de Serviços: Visualizar (GET /api/notas_fiscais_servicos/{id}). |
| `gestaoclick_notas_fiscais_servicos_list` | Notas Fiscais de Serviços: Listar (GET /api/notas_fiscais_servicos). |
| `gestaoclick_notas_fiscais_servicos_update` | Notas Fiscais de Serviços: Editar (PUT /api/notas_fiscais_servicos/{id}). |
| `gestaoclick_orcamentos_create` | Orçamentos: Cadastrar (POST /api/orcamentos). |
| `gestaoclick_orcamentos_delete` | Orçamentos: Deletar (DELETE /api/orcamentos/{id}). |
| `gestaoclick_orcamentos_gerar_parcelas_create` | Orçamentos: Gerar parcelas (POST /api/orcamentos/gerar_parcelas). |
| `gestaoclick_orcamentos_get` | Orçamentos: Visualizar (GET /api/orcamentos/{id}). |
| `gestaoclick_orcamentos_list` | Orçamentos: Listar (GET /api/orcamentos). |
| `gestaoclick_orcamentos_update` | Orçamentos: Editar (PUT /api/orcamentos/{id}). |
| `gestaoclick_ordens_servicos_create` | Ordens de serviços: Cadastrar (POST /api/ordens_servicos). |
| `gestaoclick_ordens_servicos_delete` | Ordens de serviços: Deletar (DELETE /api/ordens_servicos/{id}). |
| `gestaoclick_ordens_servicos_gerar_parcelas_create` | Ordens de serviços: Gerar parcelas (POST /api/ordens_servicos/gerar_parcelas). |
| `gestaoclick_ordens_servicos_get` | Ordens de serviços: Visualizar (GET /api/ordens_servicos/{id}). |
| `gestaoclick_ordens_servicos_list` | Ordens de serviços: Listar (GET /api/ordens_servicos). |
| `gestaoclick_ordens_servicos_update` | Ordens de serviços: Editar (PUT /api/ordens_servicos/{id}). |
| `gestaoclick_pagamentos_create` | Pagamentos: Cadastrar (POST /api/pagamentos). |
| `gestaoclick_pagamentos_delete` | Pagamentos: Deletar (DELETE /api/pagamentos/{id}). |
| `gestaoclick_pagamentos_get` | Pagamentos: Visualizar (GET /api/pagamentos/{id}). |
| `gestaoclick_pagamentos_list` | Pagamentos: Listar (GET /api/pagamentos). |
| `gestaoclick_pagamentos_update` | Pagamentos: Editar (PUT /api/pagamentos/{id}). |
| `gestaoclick_planos_contas_list` | Planos de contas: Listar (GET /api/planos_contas). |
| `gestaoclick_produtos_create` | Produtos: Cadastrar (POST /api/produtos). |
| `gestaoclick_produtos_delete` | Produtos: Deletar (DELETE /api/produtos/{id}). |
| `gestaoclick_produtos_get` | Produtos: Visualizar (GET /api/produtos/{id}). |
| `gestaoclick_produtos_list` | Produtos: Listar (GET /api/produtos). |
| `gestaoclick_produtos_update` | Produtos: Editar (PUT /api/produtos/{id}). |
| `gestaoclick_recebimentos_create` | Recebimentos: Cadastrar (POST /api/recebimentos). |
| `gestaoclick_recebimentos_delete` | Recebimentos: Deletar (DELETE /api/recebimentos/{id}). |
| `gestaoclick_recebimentos_get` | Recebimentos: Visualizar (GET /api/recebimentos/{id}). |
| `gestaoclick_recebimentos_list` | Recebimentos: Listar (GET /api/recebimentos). |
| `gestaoclick_recebimentos_update` | Recebimentos: Editar (PUT /api/recebimentos/{id}). |
| `gestaoclick_servicos_create` | Serviços: Cadastrar (POST /api/servicos). |
| `gestaoclick_servicos_delete` | Serviços: Deletar (DELETE /api/servicos/{id}). |
| `gestaoclick_servicos_get` | Serviços: Visualizar (GET /api/servicos/{id}). |
| `gestaoclick_servicos_list` | Serviços: Listar (GET /api/servicos). |
| `gestaoclick_servicos_update` | Serviços: Editar (PUT /api/servicos/{id}). |
| `gestaoclick_situacoes_compras_list` | Situações de compras: Listar (GET /api/situacoes_compras). |
| `gestaoclick_situacoes_orcamentos_list` | Situações de orçamentos: Listar (GET /api/situacoes_orcamentos). |
| `gestaoclick_situacoes_ordens_servicos_list` | Situações de OS: Listar (GET /api/situacoes_ordens_servicos). |
| `gestaoclick_situacoes_vendas_list` | Situações de vendas: Listar (GET /api/situacoes_vendas). |
| `gestaoclick_tipos_contatos_list` | Tipos de contatos: Listar (GET /api/tipos_contatos). |
| `gestaoclick_tipos_enderecos_list` | Tipos de endereços: Listar (GET /api/tipos_enderecos). |
| `gestaoclick_transportadoras_create` | Transportadoras: Cadastrar (POST /api/transportadoras). |
| `gestaoclick_transportadoras_delete` | Transportadoras: Deletar (DELETE /api/transportadoras/{id}). |
| `gestaoclick_transportadoras_get` | Transportadoras: Visualizar (GET /api/transportadoras/{id}). |
| `gestaoclick_transportadoras_list` | Transportadoras: Listar (GET /api/transportadoras). |
| `gestaoclick_transportadoras_update` | Transportadoras: Editar (PUT /api/transportadoras/{id}). |
| `gestaoclick_usuarios_list` | Usuários: Listar (GET /api/usuarios). |
| `gestaoclick_vendas_create` | Vendas: Cadastrar (POST /api/vendas). |
| `gestaoclick_vendas_delete` | Vendas: Deletar (DELETE /api/vendas/{id}). |
| `gestaoclick_vendas_gerar_parcelas_create` | Vendas: Gerar parcelas (POST /api/vendas/gerar_parcelas). |
| `gestaoclick_vendas_get` | Vendas: Visualizar (GET /api/vendas/{id}). |
| `gestaoclick_vendas_list` | Vendas: Listar (GET /api/vendas). |
| `gestaoclick_vendas_update` | Vendas: Editar (PUT /api/vendas/{id}). |

---

## Pricing

See [docs/precos.md](docs/precos.md) (PT-BR).

---

## License

MIT — see [LICENSE](LICENSE). The MCP server at `api.mcp.ai/p_gestaoclick` is proprietary (hosted); this repo (manifests, docs, skills) is MIT.
