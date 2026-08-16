# X-RAY — Auditoria de Estoque

Monitoramento, auditoria e rastreabilidade do estoque da filial 114.

Aplicação de arquivo único (HTML + CSS + JavaScript, sem build) sobre Supabase/PostgreSQL.

## O que faz

- Importa Estoque Atual, Entradas e Saídas do ERP direto do Excel, com prévia e validações
- Reconstrói o saldo pelas movimentações e concilia contra o saldo do ERP
- Kardex por produto e por lote
- Inventário com contagem às cegas, motivo obrigatório e aprovação em etapa separada
- Giro, cobertura e idade do saldo (por FIFO, funciona mesmo sem lote rastreável)
- X-Ray do produto: busca global e página que consolida tudo sobre um item
- Log de auditoria imutável

## Como rodar

Abrir `index.html` — nada para instalar. Servido por HTTPS (GitHub Pages, Netlify), a sessão passa a durar semanas.

## Acesso

Restrito por lista de autorização no banco. Quem não estiver nela não enxerga nenhuma linha, mesmo tendo o endereço.

## Configuração

A URL e a chave publicável do Supabase ficam no topo do `index.html`, em `CFG`. A chave é publicável por design: toda a proteção está nas políticas de segurança em nível de linha (RLS) do banco.
