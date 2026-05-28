<img width="1003" height="192" alt="ChatGPT Image May 28, 2026, 01_28_04 AM (2)" src="https://github.com/user-attachments/assets/dd01c9b3-1c04-496f-a968-a485bae7f3ee" />


# FiscoPilot -  Copiloto Fiscal  para PME

SaaS B2B brasileiro que ajuda pequenas e médias empresas a importar, interpretar e agir sobre seus dados fiscais — antes que inconsistências virem multas.

# FiscoPilot — Resumo do Aplicativo

## O que é o FiscoPilot

O **FiscoPilot** é um SaaS B2B brasileiro que atua como um **copiloto fiscal para pequenas e médias empresas (PMEs)**. Ele importa, interpreta e age sobre dados fiscais — antes que inconsistências virem multas.

O aplicativo foi projetado especificamente para **donos de PME**, que recebem entre 60 e 200 notas fiscais eletrônicas (NF-e) de compra por mês e não têm como saber se há erros fiscais escondidos nos arquivos XML ilegíveis que recebem dos fornecedores.

**Tagline:** *Suas notas fiscais explicadas.*

---

## O Problema

PMEs brasileiras perdem entre **R$ 7.700 e R$ 29.600 por ano** com:
- Multas por inconsistência fiscal (R$ 2.000 a R$ 8.000/ano)
- Imposto pago a maior por crédito não tomado (R$ 1.500 a R$ 6.000/ano)
- Horas do dono desperdiçadas caçando documentos (R$ 3.000 a R$ 12.000/ano)
- Honorários contábeis extras por retrabalho (R$ 1.200 a R$ 3.600/ano)

O dono da PME toma decisões operacionais — comprar, vender, contratar — às cegas do ponto de vista fiscal. Quando o erro aparece, já é multa. Quando o crédito não é tomado, já prescreveu.

---

## A Solução

O FiscoPilot resolve isso sendo a **primeira ferramenta que lê documentos fiscais automaticamente, detecta o que está errado ou arriscado e explica em português claro o que o dono precisa fazer — antes que o problema chegue ao fisco.**

O fluxo é simples:
1. A auxiliar administrativa (Fernanda) faz upload dos arquivos XML das notas fiscais de compra
2. O sistema processa em segundos e cruza os dados com **8 regras fiscais determinísticas** do Simples Nacional
3. O dono (Roberto) recebe no celular um dashboard com: total de notas, quantas estão OK, quantas têm pontos de atenção e quantas são de risco alto
4. Para cada inconsistência, o sistema mostra **impacto em reais** e um **checklist de ações** ("Ligue para o fornecedor, peça carta de correção, avise o contador")
5. No fim do mês, um **relatório em PDF** é gerado automaticamente para envio ao contador

---

## As 8 Regras Fiscais do Motor Determinístico

| Regra | O que detecta | Score |
|---|---|---|
| **R1 — CFOP divergente** | Código de operação fiscal de saída em nota de entrada | 85 |
| **R2 — Alíquota ICMS** | Alíquota de ICMS diferente da tabela interestadual oficial | 70 |
| **R3 — NCM suspeito** | Classificação fiscal do produto fora do perfil de material de construção | 50 |
| **R4 — CNPJ irregular** | Fornecedor com CNPJ suspenso, baixado ou inapto | 80-100 |
| **R5 — Valor divergente** | Valor total da nota não bate com a soma dos itens | 60-90 |
| **R6 — CST incompatível** | CST de PIS/COFINS incompatível com Simples Nacional | 50 |
| **R7 — Chave inválida** | Dígito verificador da NF-e não confere (possível nota falsa) | 100 |
| **R8 — ICMS ST indevido** | Substituição Tributária destacada para produto que não está na lista de ST do estado | 75 |

Cada inconsistência recebe um score de 0 a 100 e é classificada como **OK** (0-30), **ATENÇÃO** (31-69) ou **RISCO ALTO** (70-100).

---

## Público-Alvo (ICP)

**Dono(a) de PME**, com 5 a 20 funcionários, faturamento mensal entre R$ 80 mil e R$ 300 mil, optante do Simples Nacional, que compra de 20 a 50 fornecedores diferentes por mês e recebe entre 60 e 200 NF-e de entrada mensalmente.

### Por que este ICP?

- **Dor fiscal concreta:** CFOP e ICMS-ST geram multas frequentes no setor
- **Volume ideal:** 60-200 notas/mês — suficiente para gerar valor, baixo o suficiente para o MVP
- **Dono acessível:** Participa ativamente de grupos de WhatsApp do setor
- **ROI claro:** "Evite multa de R$ 2.000 por CFOP errado" é imediato e quantificável
- **MVP simples:** Apenas NF-e (XML padronizado nacionalmente), apenas Simples Nacional

---

## Personas

### Roberto Almeida — O Dono (Comprador)
- 51 anos, ensino médio, dono-fundador da loja há 14 anos
- Usa WhatsApp intensamente, app de banco, mas não sabe o que é XML
- Celular Android (Samsung, 2 anos de idade)
- **Medo principal:** Tomar uma multa fiscal que quebre o negócio
- **Gatilho de compra:** Alguém mostrar na frente dele que "essa nota aqui está errada e você nem sabia" usando o próprio CNPJ dele

### Fernanda Souza — Auxiliar Administrativo (Usuária Operacional)
- 28 anos, ensino médio, trabalha na loja há 3 anos
- Sabe usar Excel básico, baixar XML de e-mail, converter foto em PDF
- **Frustração principal:** "Fornecedor manda XML por e-mail com nome todo errado. Tenho que abrir um por um."
- **Gatilho de adoção:** Se ela vê que o produto elimina "abrir 110 XMLs na mão", ela pede pro Roberto comprar

### Dona Célia — A Contadora (Influenciadora)
- 47 anos, técnica em contabilidade, CRC ativo
- Atende ~40 empresas (90% Simples Nacional), 12h/dia de trabalho
- **Frustração principal:** "Cliente manda 50 fotos de nota fiscal pelo WhatsApp. Tenho que digitar tudo na mão."
- **Gatekeeper:** Se ela vetar o produto, a venda não fecha

---

## Funcionalidades do MVP (90 dias)

### Módulo 1 — Ingestão de Documentos
- Upload de arquivos XML via interface web (arrastar e soltar ou ZIP)
- Ingestão via e-mail dedicado (notas@fiscopillot.com.br)
- Validação automática de tipo e formato de arquivo
- Indicador de progresso real durante processamento

### Módulo 2 — Processamento
- Parser de NF-e (modelo 55, layout 4.00) com extração de todos os campos fiscais
- Motor de 8 regras determinísticas (R1 a R8)
- Classificação de risco com score de 0 a 100
- Deduplicação por chave de acesso

### Módulo 3 — Dashboard
- Visão resumida: total de notas, cards OK/Atenção/Risco Alto
- Lista detalhada de inconsistências ordenada por gravidade
- Detalhe da inconsistência com explicação em português claro
- Checklist de ações ("O que fazer?")
- Gerenciamento de status (Pendente / Em andamento / Resolvida / Ignorada)
- Filtro por período e busca por fornecedor

### Módulo 4 — Comunicação
- Resumo semanal via WhatsApp (toda segunda-feira às 8h)
- Alerta imediato via WhatsApp para inconsistências de risco alto
- Notificação "tudo certo" mesmo sem inconsistências (silêncio positivo)
- Exportação de relatório do contador em PDF
- Autenticação 100% por link mágico via WhatsApp (sem senha)

### Módulo 5 — Administração
- Multi-tenant (cada loja vê apenas seus próprios dados)
- Papéis e permissões (Admin e Operador)
- Log de auditoria imutável (append-only)
- Log de processamento com rastreabilidade completa

---

## Tecnologia

| Camada | Tecnologia |
|---|---|
| **Front-end** | Next.js 14 (App Router) + React 18 + Tailwind CSS 3 + shadcn/ui |
| **Back-end** | Fastify 5 + TypeScript 5 |
| **Banco de dados** | PostgreSQL 16 (Docker) |
| **ORM** | Drizzle ORM |
| **Parser de XML** | fast-xml-parser |
| **PDF** | pdfkit |
| **Autenticação** | Magic link via WhatsApp + JWT (HS256, 7 dias) |
| **Notificações** | WhatsApp Business Cloud API (Meta) |
| **IA (opcional)** | OpenRouter → GPT-4o-mini (apenas paráfrase de explicações) |
| **Infraestrutura** | Docker Compose em VPS (Hetzner CX22, 4GB RAM) |
| **CI/CD** | GitHub Actions → GitHub Container Registry |
| **Monitoramento** | Sentry + Uptime Robot + pino |
| **Backup** | pg_dump diário → AWS S3 (AES-256) |

---

## Modelo de Negócio

- **Preço:** R$ 97/mês (plano único no MVP)
- **Trial:** 15 dias grátis com onboarding guiado pelo founder
- **Cobrança:** Pix manual nos primeiros 6 meses (até ~20 clientes)
- **Meta MVP (90 dias):** 10 clientes pagantes = R$ 970 MRR
- **Meta 12 meses:** 80 clientes = R$ 15.760 MRR (com plano a R$ 197/mês na Fase D)
- **Sem contrato.** Sem fidelidade. Sem multa de cancelamento.

---

## O que o Produto NÃO Faz (Limites de Compliance)

- ❌ NÃO calcula imposto devido nem gera guias (DAS, ICMS, etc.)
- ❌ NÃO envia obrigações acessórias (SPED, DIRF, DEFIS)
- ❌ NÃO substitui o contador — complementa o trabalho dele
- ❌ NÃO edita campos de NF-e (impedido por lei — risco de falsificação)
- ❌ NÃO faz diagnóstico com IA — usa apenas regras determinísticas. IA só parafraseia explicações já existentes
- ❌ NÃO emite nota fiscal de serviço, NFC-e ou CT-e (apenas processa NF-e de entrada)

---

## Roadmap

### MVP (Mês 1-3)
Core do produto: upload de XML, 8 regras fiscais, dashboard mobile-first, notificações WhatsApp, relatório PDF para o contador

### Fase A — Retenção e Redução de Atrito (Mês 4-5)
Mensagem pronta para fornecedor, painel de economia/riscos evitados, relatório mensal do dono, notificações mais inteligentes, onboarding raio-x fiscal, ingestão por WhatsApp

### Fase B — Monitoramento Contínuo (Mês 5-7)
Download automático de XML via certificado digital A1, Kanban de pendências fiscais, alertas cadastrais (certificado vencendo, CNPJ inapto, IE irregular)

### Fase C — Inteligência e Ecossistema (Mês 7-9)
Portal do contador (login próprio, comentários, validações), score de fornecedores, assistente de IA contextual

### Fase D — Plataforma e Escala (Mês 9-12)
Simulador da Reforma Tributária (CBS/IBS), integração com ERPs (Bling, Tiny, Omie, Conta Azul), biblioteca de regras fiscais por UF e setor

---

**Total de funcionalidades:** 35 no MVP + 30 pós-MVP = **65 funcionalidades**
**Prazo de construção:** 90 dias (MVP) + ~9 meses (Fases A-D)
**Equipe:** 1 founder full-stack + 1 engenheiro back-end + 1 designer UX part-time

---

*"O FiscoPilot lê suas notas fiscais de compra, encontra o que está errado e te explica em português claro o que fazer — antes que o erro vire multa."*

---

## Etapa 1 — Definição do Problema Central

### Objetivo da etapa

Definir com precisão cirúrgica qual problema o Copiloto Fiscal para PME resolve, para quem resolve e por que esse problema merece um produto dedicado — sem confundir com ERP, software contábil ou consultoria.

### Premissas adotadas

| # | Premissa | Justificativa |
|---|---|---|
| P1 | O dono da PME não entende de fiscal, nem quer entender | O papel dele é tocar o negócio; fiscal é obrigação acessória indesejada |
| P2 | O contador terceirizado é peça fixa do ecossistema e não será substituído | O produto não compete com o contador; complementa-o |
| P3 | A maioria das PMEs opera no Simples Nacional ou Lucro Presumido | São os regimes com menor sofisticação fiscal interna |
| P4 | Documentos fiscais eletrônicos (NF-e, NFC-e, CT-e, NFS-e) são onipresentes e subutilizados | A infraestrutura pública de dados fiscais já existe; o problema é interpretação |
| P5 | A Reforma Tributária (CBS/IBS) introduzirá complexidade adicional perceptível entre 2026-2033 | A janela de oportunidade do produto é agora |
| P6 | O MVP será vendável em até 90 dias de construção | Implica escopo restrito, stack leve e time pequeno (2-3 pessoas) |

### Definição do problema em 1 frase

> PMEs brasileiras perdem dinheiro, tempo e tranquilidade porque não existe uma ferramenta simples que traduza documentos fiscais em riscos compreensíveis antes que virem multas.

### Definição expandida

O dono da PME brasileira recebe e emite dezenas de documentos fiscais eletrônicos por mês. Esses documentos contêm dados que determinam quanto imposto ele pagará, se terá crédito, se está exposto a malha fina. Mas esses dados são inacessíveis: vêm em XML ilegível, linguagem técnica incompreensível (CFOP, NCM, CST) e ficam dispersos entre portais da Sefaz, e-mails de fornecedores, WhatsApp do contador e sistemas que não conversam entre si. O resultado é que o dono toma decisões operacionais — comprar, vender, contratar — às cegas do ponto de vista fiscal. Quando o erro aparece, já é multa. Quando o crédito não é tomado, já prescreveu. Quando a notificação chega, o medo paralisa. O Copiloto Fiscal resolve isso sendo a primeira ferramenta que lê documentos fiscais automaticamente, detecta o que está errado ou arriscado e explica em português claro o que o dono precisa fazer — antes que o problema chegue ao fisco.

### Por que é urgente

- A Receita Federal e as Sefaz estaduais já cruzam NF-e eletronicamente em tempo real
- A Reforma Tributária (CBS/IBS) criará um novo regime de apuração que penaliza dados desorganizados
- PMEs não têm estrutura interna para compliance fiscal proativo
- O mercado ainda oferece ou ERP pesado ou planilha; não há meio-termo inteligente

### Por que é frequente

Toda operação de compra ou venda gera risco fiscal. Uma PME com 50 transações/mês está exposta a risco 50 vezes/mês. A frequência é semanal, às vezes diária.

### Por que gera disposição de pagamento

PMEs brasileiras já pagam de R$ 69 a R$ 199/mês por SaaS de gestão. O Copiloto Fiscal se posiciona como "seguro" contra multas e "tradutor" do fiscal. Valor percebido: evita uma multa de R$ 500 a R$ 5.000. O preço mensal é irrisório comparado ao custo de um erro.

### Impacto operacional

| Dimensão | Impacto concreto |
|---|---|
| Tempo do dono | 3 a 6 horas/mês perdidas em caça a documentos fiscais e idas e vindas com contador |
| Tempo do contador | Retrabalho de correção consome 15-25% do esforço mensal |
| Atraso em decisão | Dono adia investimento/contratação por insegurança fiscal |
| Erro em cascata | Um erro de classificação (ex.: CFOP) contamina DAS, DEFIS e declarações acessórias |

### Impacto financeiro

| Fonte de perda | Estimativa conservadora por PME/ano |
|---|---|
| Multas por inconsistência | R$ 2.000 a R$ 8.000 |
| Imposto pago a maior (crédito não tomado) | R$ 1.500 a R$ 6.000 |
| Horas do dono desperdiçadas (custo de oportunidade) | R$ 3.000 a R$ 12.000 |
| Honorários contábeis extras por retrabalho | R$ 1.200 a R$ 3.600 |
| **Total estimado** | **R$ 7.700 a R$ 29.600/ano** |

### Impacto emocional para o dono da PME

| Emoção | Gatilho | Consequência |
|---|---|---|
| Ansiedade crônica | Não saber se está tudo certo até o contador avisar (ou o fisco notificar) | Evita crescer, evita contratar, evita investir |
| Impotência | Receber uma notificação fiscal e não ter ideia do que fazer | Dependência total do contador, sensação de refém |
| Raiva | Descobrir que pagou errado por 18 meses e ninguém avisou | Ruptura com contador, desconfiança generalizada |
| Vergonha | Não saber explicar para o contador o básico da própria operação | Insegurança na relação, evitação de contato |
| Medo | Saber que uma fiscalização pode quebrar a empresa | Paralisia decisória |

### Por que as soluções atuais não resolvem bem

| Solução atual | Por que falha para esse problema |
|---|---|
| ERP (ContaAzul, Omie, Bling) | Focado em emissão e contas a pagar/receber. Não analisa consistência fiscal cruzada, não explica risco em linguagem simples. |
| Escritório contábil | Vê dados retrospectivamente (mês fechado). Não monitora em tempo real. Linguajar técnico. Comunicação por e-mail/WhatsApp sem rastreabilidade. |
| Software fiscal tradicional (Mastermaq, Alterdata) | Interface hostil, voltado para contador, não para dono de PME. Exige conhecimento técnico-fiscal. |
| Planilha Excel / WhatsApp | Erro humano garantido. Sem rastreabilidade. Sem proteção. Sem inteligência. |
| Sefaz / Portal da NF-e | Consulta individual de notas. Consultar 200 notas por mês manualmente é inviável. |
**Lacuna de mercado**: não existe um produto que **traduza a complexidade fiscal** para o dono da PME em linguagem simples, com alertas proativos, antes que o problema vire multa.

### Decisões recomendadas

| Decisão | Conteúdo | Status |
|---|---|---|
| D1 | O problema central não é "automatizar fiscal", é "reduzir assimetria de informação fiscal entre dono da PME e risco real" | Decisão de MVP |
| D2 | O produto atua como uma camada de tradução entre dados fiscais brutos e compreensão do dono | Decisão de MVP |
| D3 | O contador é aliado do ecossistema, não competidor | Decisão de MVP |
| D4 | O produto nunca substitui obrigação legal do contador (assinar declarações, apurar oficialmente) | Decisão de compliance |
| D5 | Foco em risco detectável deterministicamente via regras fiscais; IA como apoio explicativo, não como motor primário | Decisão técnica |

### Riscos e pontos de atenção

| Risco | Severidade | Mitigação |
|---|---|---|
| PME não perceber o risco até tomar multa — baixo senso de urgência | Alta | Onboarding deve mostrar "riscos ocultos" reais do próprio CNPJ em segundos (efeito "raio-x imediato") |
| Contador sentir-se ameaçado pelo produto e boicotar adoção | Alta | Posicionar produto como ferramenta do contador também; gerar leads para contadores parceiros |
| Complexidade fiscal brasileira inviabilizar regras determinísticas completas | Média | Começar com ~15 regras de alto impacto e alta confiabilidade; expandir progressivamente |
| Dono da PME esperar que o produto "substitua o contador" | Média | Comunicação clara desde o onboarding: "você ainda precisa do contador; a gente te ajuda a fazer perguntas melhores" |
| Custo de aquisição de clientes (CAC) alto vs. LTV baixo | Média | MVP com venda consultiva em grupos de WhatsApp de empresários; baixo CAC inicial |

## Etapa 2 — Escolha do ICP Principal

### Objetivo da etapa

Selecionar, entre 5 perfis de cliente distintos, o **único ICP** para o qual o MVP do FiscoPilot será projetado e comercializado nos primeiros 6 meses. A escolha deve maximizar probabilidade de venda e minimizar complexidade do MVP.

### Premissas adotadas

| # | Premissa | Justificativa |
|---|---|---|
| P1 | O MVP suportará apenas NF-e (modelo 55) como documento de entrada | NF-e tem XML padronizado nacionalmente via Sefaz; NFS-e, CT-e e NFC-e têm padrões fragmentados por município/estado |
| P2 | O MVP operará no regime Simples Nacional primeiro | 84% das PMEs brasileiras estão no Simples; menor complexidade regulatória para regras determinísticas |
| P3 | O produto será vendido diretamente pelo founder nos primeiros 6 meses (inside sales) | Sem time de vendas; validação com canais de baixo custo |
| P4 | O ICP deve ter ao menos 30 transações de entrada/mês para gerar valor percebido | Abaixo disso, o volume de documentos não justifica assinatura mensal |
| P5 | O ICP deve permitir demonstração de valor em menos de 5 minutos | Efeito "raio-x imediato" ao importar XMLs reais |

### Os 5 ICPs candidatos

| # | ICP | Regime predominante | Volume mensal de docs fiscais (entrada) | Porte típico (funcionários) | Faturamento médio |
|---|---|---|---|---|---|
| A | **Loja de material de construção** | Simples Nacional | 60–200 NF-e | 5–20 | R$ 80k–R$ 300k/mês |
| B | **Clínica médica/odontológica** | Simples Nacional | 10–40 NFS-e + NF-e | 3–15 | R$ 40k–R$ 200k/mês |
| C | **Pequena indústria de confecção** | Simples Nacional | 30–80 NF-e (insumos) + emissão própria | 8–30 | R$ 100k–R$ 400k/mês |
| D | **Distribuidor regional de bebidas** | Simples Nacional / Lucro Presumido | 100–500 NF-e | 10–40 | R$ 200k–R$ 800k/mês |
| E | **Restaurante / food service** | Simples Nacional | 20–60 NF-e (insumos) + NFC-e emissão | 5–25 | R$ 50k–R$ 200k/mês |

### Matriz comparativa (0 = pior, 5 = melhor)

| Critério (peso) | A — Material de construção | B — Clínica | C — Confecção | D — Distribuidor de bebidas | E — Restaurante |
|---|---|---|---|---|---|
| **Urgência da dor** (25%) | **5** — CFOP e ST geram multas frequentes, dono sofre com erros de classificação | **3** — ISS e retenções geram problema, mas menor intensidade | **4** — Diferencial de alíquota e CFOP interestadual são pontos cegos | **4** — ICMS ST e substituição tributária são fonte crônica de erro | **2** — Erro fiscal raramente é percebido antes da notificação |
| **Frequência da dor** (20%) | **5** — Toda NF-e de entrada é vetor de erro; 60–200/mês | **2** — Poucas NFS-e/mês; baixo volume de transações | **4** — Toda compra interestadual gera risco; 30–80/mês | **5** — Altíssimo volume; risco em centenas de transações/mês | **3** — 20–60 NF-e de insumos; saída é NFC-e (fora do escopo MVP) |
| **Capacidade de pagamento** (15%) | **4** — Ticket de R$ 99–R$ 197 é <1% do faturamento | **3** — Pagam software de agenda (R$ 200–800); fiscal é secundário | **4** — Alta capacidade; já pagam ERP simples e contador | **5** — Maior faturamento; ticket de R$ 299 é confortável | **3** — Margem apertada; sensibilidade a custo fixo adicional |
| **Facilidade de aquisição** (15%) | **4** — Grupos de WhatsApp de lojistas, associações comerciais, sindicatos patronais; canais segmentados | **3** — Grupos de dentistas/médicos; decisão passa por secretária/gerente; ciclo mais longo | **3** — APLs locais concentram geograficamente; aquisição presencial viável | **2** — Nicho disperso; venda consultiva mais longa; donos menos acessíveis digitalmente | **4** — Grupos de restaurateurs no WhatsApp, influenciadores do setor, boca a boca forte |
| **Clareza de ROI** (15%) | **5** — "Evite multa de R$ 2.000 por CFOP errado" é imediato e quantificável | **2** — ROI difuso: "pague o ISS certo" não gera alívio emocional imediato | **4** — ICMS interestadual é erro caro; ROI claro mas depende do contador explicar | **4** — Erro de ST em alto volume gera prejuízo grande; ROI visível | **2** — Difícil quantificar prevenção; "paguei menos imposto" é abstrato para restaurateur |
| **Simplicidade do MVP** (10%) | **4** — Apenas NF-e; CFOP, NCM, CST e alíquotas são regras determinísticas bem documentadas | **2** — NFS-e municipal é fragmentada; cada prefeitura tem XML diferente; MVP exigiria muitos conectores | **3** — NF-e de insumos + interesse em crédito de ICMS/IPI; IPI adiciona complexidade | **2** — Volume alto exige infraestrutura robusta; ST tem regras complexas demais para MVP | **1** — NFC-e emissão é fora do escopo; insumos envolvem ST e perecíveis; complexidade alta |

### Ranking ponderado final

| ICP | Urgência (25%) | Frequência (20%) | Pagamento (15%) | Aquisição (15%) | ROI (15%) | Simplicidade (10%) | **Pontuação ponderada** |
|---|---|---|---|---|---|---|---|
| **A — Material de construção** | 5 × 0,25 = 1,25 | 5 × 0,20 = 1,00 | 4 × 0,15 = 0,60 | 4 × 0,15 = 0,60 | 5 × 0,15 = 0,75 | 4 × 0,10 = 0,40 | **4,60** |
| C — Confecção | 1,00 | 0,80 | 0,60 | 0,45 | 0,60 | 0,30 | 3,75 |
| D — Bebidas | 1,00 | 1,00 | 0,75 | 0,30 | 0,60 | 0,20 | 3,85 |
| B — Clínica | 0,75 | 0,40 | 0,45 | 0,45 | 0,30 | 0,20 | 2,55 |
| E — Restaurante | 0,50 | 0,60 | 0,45 | 0,60 | 0,30 | 0,10 | 2,55 |

### Decisões recomendadas

| Decisão | Conteúdo | Status |
|---|---|---|
| D1 | **ICP vencedor: Loja de material de construção e acabamento, Simples Nacional, 5–20 funcionários** | Decisão de MVP |
| D2 | A persona compradora é o dono (não o gerente nem o contador) | Decisão de ICP |
| D3 | O MVP foca exclusivamente em NF-e de entrada (compras) como fonte de dados; notas de saída e NFC-e ficam fora do MVP | Decisão de escopo |
| D4 | O MVP opera apenas no regime Simples Nacional; Lucro Presumido e Real ficam para fase 2 | Decisão de escopo |
| D5 | Geograficamente, o MVP começa em 1–2 estados (ex.: SP e MG) para concentrar esforço de aquisição e testar regras de ICMS estadual | Decisão de GTM |

### ICP vencedor — definição precisa

> **Dono(a) de loja de material de construção e acabamento, com 5 a 20 funcionários, faturamento mensal entre R$ 80 mil e R$ 300 mil, optante do Simples Nacional, que compra de 20 a 50 fornecedores diferentes por mês e recebe entre 60 e 200 NF-e de entrada mensalmente.**

### Justificativa detalhada da escolha

**1. Dor fiscal é concreta, frequente e quantificável**

Material de construção tem a maior densidade de complexidade fiscal do varejo brasileiro:
- **CFOP de entrada**: 1.000 (compras dentro do estado), 2.000 (interestadual), 3.000 (importação) — cada um com dezenas de subcódigos. Um fornecedor colocar CFOP 5.102 (revenda) em vez de 5.401 (industrialização) contamina crédito de ICMS.
- **ICMS Substituição Tributária**: materiais de construção estão entre os produtos mais sujeitos a ST; erro de base de cálculo ou MVA é comum.
- **NCM**: construção civil tem NCMs específicos (capítulo 68, 69, 70 da NCM); erro de classificação altera alíquota de IPI e PIS/COFINS.
- **Crédito no Simples**: embora o Simples não permita crédito amplo de ICMS/IPI, erros de CFOP afetam a apuração da DAS e podem gerar malha fina.

**2. Volume de transações alto o suficiente para gerar valor, baixo o suficiente para o MVP**

Com 60–200 NF-e/mês de entrada:
- Suficiente para o produto encontrar ao menos 1–2 inconsistências por mês, gerando recorrência de uso e percepção de valor
- Não é volume tão alto que exija infraestrutura robusta de processamento em tempo real no MVP
- Permite processamento em lote (upload de XMLs) em vez de integração em tempo real com Sefaz

**3. Dono é acessível e comprável**

- Donos de loja de material de construção participam ativamente de grupos de WhatsApp do setor (ex.: "Lojistas Associados", grupos de bairro, grupos de associação comercial)
- Frequentam feiras (Feicon, Expo Revestir) e eventos de associação comercial
- Decisão de compra é centralizada no dono; não passa por comitê ou gerente financeiro
- Ticket de R$ 97–197/mês é irrelevante frente ao faturamento

**4. MVP é o mais simples possível com esse ICP**

- Único documento: NF-e (XML padronizado nacionalmente — layout 4.00 do SPED)
- Único regime: Simples Nacional (regras unificadas via LC 123/2006)
- Regras determinísticas bem documentadas: tabela CFOP, tabela NCM/NBS, alíquotas do Simples por anexo
- Sem necessidade de integrar com prefeituras (NFS-e municipal), sem NFC-e, sem CT-e

**5. ROI é vendável em 30 segundos**

> "Você recebe 150 notas por mês dos seus fornecedores. Se uma só vier com CFOP errado, sua DAS pode sair errada e você toma multa de R$ 500 a R$ 5.000. O FiscoPilot lê todas as suas notas, acha os erros e te avisa em português claro. Custa R$ 147/mês."

Essa conversa fecha em uma visita à loja.

### Riscos e pontos de atenção

| Risco | Severidade | Mitigação |
|---|---|---|
| Loja de material de construção pode ter alta sazonalidade (obras no verão, queda no inverno), afetando volume de NF-e e percepção de valor | Baixa | O MVP mostra valor independentemente do volume; 1 erro encontrado já justifica o mês |
| Fornecedores grandes (Sodimac, Leroy Merlin, Telhanorte) emitem XMLs de alta qualidade; erros fiscais podem ser raros em compras de grandes redes | Média | Foco no comportamento de compra real da PME: a maioria compra de distribuidores regionais e atacadistas locais, que erram mais |
| Dono pode não ter o hábito de baixar XMLs; pode depender do contador para isso | Média | MVP deve ser "coloque o CNPJ e a gente busca pra você" — download automatizado via Sefaz com certificado digital (feature essencial) |
| Concentrar em um setor limita TAM (Total Addressable Market) no curto prazo | Baixa | É deliberado: MVP precisa de foco. Material de construção sozinho tem >200 mil lojas no Brasil — TAM de R$ 24M/mês em potencial de assinatura |
| ICMS ST tem regras estaduais; MVP pode precisar de parametrização por UF | Média | Começar com 2 estados (SP e MG) e expandir UF a UF, cada uma como micro-lançamento |

---
## Etapa 1 — Definição do Problema Central

### Objetivo da etapa

Definir com precisão cirúrgica qual problema o FiscoPilot para PME resolve, para quem resolve e por que esse problema merece um produto dedicado — sem confundir com ERP, software contábil ou consultoria.

### Premissas adotadas

| # | Premissa | Justificativa |
|---|---|---|
| P1 | O dono da PME não entende de fiscal, nem quer entender | O papel dele é tocar o negócio; fiscal é obrigação acessória indesejada |
| P2 | O contador terceirizado é peça fixa do ecossistema e não será substituído | O produto não compete com o contador; complementa-o |
| P3 | A maioria das PMEs opera no Simples Nacional ou Lucro Presumido | São os regimes com menor sofisticação fiscal interna |
| P4 | Documentos fiscais eletrônicos (NF-e, NFC-e, CT-e, NFS-e) são onipresentes e subutilizados | A infraestrutura pública de dados fiscais já existe; o problema é interpretação |
| P5 | A Reforma Tributária (CBS/IBS) introduzirá complexidade adicional perceptível entre 2026-2033 | A janela de oportunidade do produto é agora |
| P6 | O MVP será vendável em até 90 dias de construção | Implica escopo restrito, stack leve e time pequeno (2-3 pessoas) |

### Definição do problema em 1 frase

> PMEs brasileiras perdem dinheiro, tempo e tranquilidade porque não existe uma ferramenta simples que traduza documentos fiscais em riscos compreensíveis antes que virem multas.

### Definição expandida

O dono da PME brasileira recebe e emite dezenas de documentos fiscais eletrônicos por mês. Esses documentos contêm dados que determinam quanto imposto ele pagará, se terá crédito, se está exposto a malha fina. Mas esses dados são inacessíveis: vêm em XML ilegível, linguagem técnica incompreensível (CFOP, NCM, CST) e ficam dispersos entre portais da Sefaz, e-mails de fornecedores, WhatsApp do contador e sistemas que não conversam entre si. O resultado é que o dono toma decisões operacionais — comprar, vender, contratar — às cegas do ponto de vista fiscal. Quando o erro aparece, já é multa. Quando o crédito não é tomado, já prescreveu. Quando a notificação chega, o medo paralisa. O FiscoPilot resolve isso sendo a primeira ferramenta que lê documentos fiscais automaticamente, detecta o que está errado ou arriscado e explica em português claro o que o dono precisa fazer — antes que o problema chegue ao fisco.

### Por que é urgente

- A Receita Federal e as Sefaz estaduais já cruzam NF-e eletronicamente em tempo real
- A Reforma Tributária (CBS/IBS) criará um novo regime de apuração que penaliza dados desorganizados
- PMEs não têm estrutura interna para compliance fiscal proativo
- O mercado ainda oferece ou ERP pesado ou planilha; não há meio-termo inteligente

### Por que é frequente

Toda operação de compra ou venda gera risco fiscal. Uma PME com 50 transações/mês está exposta a risco 50 vezes/mês. A frequência é semanal, às vezes diária.

### Por que gera disposição de pagamento

PMEs brasileiras já pagam de R$ 69 a R$ 199/mês por SaaS de gestão. O FiscoPilot se posiciona como "seguro" contra multas e "tradutor" do fiscal. Valor percebido: evita uma multa de R$ 500 a R$ 5.000. O preço mensal é irrisório comparado ao custo de um erro.

### Impacto operacional

| Dimensão | Impacto concreto |
|---|---|
| Tempo do dono | 3 a 6 horas/mês perdidas em caça a documentos fiscais e idas e vindas com contador |
| Tempo do contador | Retrabalho de correção consome 15-25% do esforço mensal |
| Atraso em decisão | Dono adia investimento/contratação por insegurança fiscal |
| Erro em cascata | Um erro de classificação (ex.: CFOP) contamina DAS, DEFIS e declarações acessórias |

### Impacto financeiro

| Fonte de perda | Estimativa conservadora por PME/ano |
|---|---|
| Multas por inconsistência | R$ 2.000 a R$ 8.000 |
| Imposto pago a maior (crédito não tomado) | R$ 1.500 a R$ 6.000 |
| Horas do dono desperdiçadas (custo de oportunidade) | R$ 3.000 a R$ 12.000 |
| Honorários contábeis extras por retrabalho | R$ 1.200 a R$ 3.600 |
| **Total estimado** | **R$ 7.700 a R$ 29.600/ano** |

### Impacto emocional para o dono da PME

| Emoção | Gatilho | Consequência |
|---|---|---|
| Ansiedade crônica | Não saber se está tudo certo até o contador avisar (ou o fisco notificar) | Evita crescer, evita contratar, evita investir |
| Impotência | Receber uma notificação fiscal e não ter ideia do que fazer | Dependência total do contador, sensação de refém |
| Raiva | Descobrir que pagou errado por 18 meses e ninguém avisou | Ruptura com contador, desconfiança generalizada |
| Vergonha | Não saber explicar para o contador o básico da própria operação | Insegurança na relação, evitação de contato |
| Medo | Saber que uma fiscalização pode quebrar a empresa | Paralisia decisória |

### Por que as soluções atuais não resolvem bem

| Solução atual | Por que falha para esse problema |
|---|---|
| ERP (ContaAzul, Omie, Bling) | Focado em emissão e contas a pagar/receber. Não analisa consistência fiscal cruzada, não explica risco em linguagem simples. |
| Escritório contábil | Vê dados retrospectivamente (mês fechado). Não monitora em tempo real. Linguajar técnico. Comunicação por e-mail/WhatsApp sem rastreabilidade. |
| Software fiscal tradicional (Mastermaq, Alterdata) | Interface hostil, voltado para contador, não para dono de PME. Exige conhecimento técnico-fiscal. |
| Planilha Excel / WhatsApp | Erro humano garantido. Sem rastreabilidade. Sem proteção. Sem inteligência. |
| Sefaz / Portal da NF-e | Consulta individual de notas. Consultar 200 notas por mês manualmente é inviável. |

**Lacuna de mercado**: não existe um produto que **traduza a complexidade fiscal** para o dono da PME em linguagem simples, com alertas proativos, antes que o problema vire multa.

### Decisões recomendadas

| Decisão | Conteúdo | Status |
|---|---|---|
| D1 | O problema central não é "automatizar fiscal", é "reduzir assimetria de informação fiscal entre dono da PME e risco real" | Decisão de MVP |
| D2 | O produto atua como uma camada de tradução entre dados fiscais brutos e compreensão do dono | Decisão de MVP |
| D3 | O contador é aliado do ecossistema, não competidor | Decisão de MVP |
| D4 | O produto nunca substitui obrigação legal do contador (assinar declarações, apurar oficialmente) | Decisão de compliance |
| D5 | Foco em risco detectável deterministicamente via regras fiscais; IA como apoio explicativo, não como motor primário | Decisão técnica |

### Riscos e pontos de atenção

| Risco | Severidade | Mitigação |
|---|---|---|
| PME não perceber o risco até tomar multa — baixo senso de urgência | Alta | Onboarding deve mostrar "riscos ocultos" reais do próprio CNPJ em segundos (efeito "raio-x imediato") |
| Contador sentir-se ameaçado pelo produto e boicotar adoção | Alta | Posicionar produto como ferramenta do contador também; gerar leads para contadores parceiros |
| Complexidade fiscal brasileira inviabilizar regras determinísticas completas | Média | Começar com ~15 regras de alto impacto e alta confiabilidade; expandir progressivamente |
| Dono da PME esperar que o produto "substitua o contador" | Média | Comunicação clara desde o onboarding: "você ainda precisa do contador; a gente te ajuda a fazer perguntas melhores" |
| Custo de aquisição de clientes (CAC) alto vs. LTV baixo | Média | MVP com venda consultiva em grupos de WhatsApp de empresários; baixo CAC inicial |

---

## Etapa 3 — Personas

### Objetivo da etapa

Criar 3 personas detalhadas e realistas — compradora, usuária principal e influenciadora — para orientar todas as decisões de produto, UX, comunicação e vendas do FiscoPilot no contexto de lojas de material de construção (Simples Nacional, 5–20 funcionários).

### Premissas adotadas

| # | Premissa | Justificativa |
|---|---|---|
| P1 | A persona compradora é o dono da loja; ele decide e paga | Não há comitê de compra em PME desse porte; autoridade é única |
| P2 | A persona compradora e a persona usuária podem ser a mesma pessoa, mas com contextos distintos de interação com o produto | O dono usa o produto para decisões estratégicas; um funcionário pode usar para tarefas operacionais (upload, triagem) |
| P3 | A persona influenciadora é o contador; ele não paga, mas pode vetar ou recomendar | Se o contador desconfiar do produto, a venda emperra |
| P4 | Todas as personas operam via WhatsApp como canal primário de comunicação rápida | Realidade do mercado brasileiro; e-mail é secundário para esse ICP |
| P5 | O nível de maturidade digital é baixo a moderado; ninguém programa, ninguém usa API, ninguém lê documentação técnica | Afeta onboarding, UX e suporte |

### Decisões recomendadas

| Decisão | Conteúdo | Status |
|---|---|---|
| D1 | Persona compradora: **Roberto**, 51 anos, dono-fundador, 2º grau completo, sabe usar WhatsApp e app de banco, não sabe o que é XML | Decisão de persona |
| D2 | Persona usuária: **Roberto** como usuário principal + **Fernanda** (auxiliar administrativo) como usuária operacional delegada | Decisão de persona |
| D3 | Persona influenciadora: **Dona Célia**, contadora, 47 anos, técnica contábil, cética, sobrecarregada, gatekeeper do risco fiscal | Decisão de persona |
| D4 | A comunicação do produto deve ser testada com as 3 personas antes de qualquer linha de código | Decisão de validação |
| D5 | O onboarding do MVP deve funcionar sem depender da Fernanda; se só o Roberto estiver disponível, ele precisa conseguir usar | Decisão de UX |

---

### PERSONA 1 — Compradora e Usuária Principal

#### **Roberto Almeida — O Dono**

| Dimensão | Descrição |
|---|---|
| **Idade** | 51 anos |
| **Formação** | Ensino médio completo. Fez curso técnico em administração há 25 anos. |
| **História** | Trabalhou como vendedor em depósito de material de construção por 12 anos. Em 2012, juntou economia + rescisão + empréstimo do sogro e abriu a própria loja. Começou com 1 funcionário. Hoje tem 9. Ele é o comprador, o financeiro, o RH e o "resolve-problema". |
| **Rotina típica** | Chega às 7h. Abre a loja. Confere pedidos do dia anterior no WhatsApp. Liga para 3 fornecedores (negociar preço de cimento, reclamar de atraso de entrega, pedir troca de nota). Atende cliente grande que só negocia com ele. Confere extrato bancário. Almoça em 20 min. À tarde, resolve pepino (funcionário faltou, cliente reclamou, máquina de cartão parou). Fecha loja às 18h. Em casa, responde WhatsApp até 21h. |
| **Contexto de trabalho** | Balcão da loja, depósito nos fundos, escritório minúsculo com mesa, computador velho e pilha de notas fiscais impressas. Barulho constante. Interrupções a cada 5 minutos. |
| **Objetivos** | 1. Fazer a loja faturar mais sem perder margem. 2. Abrir uma segunda loja antes dos 55 anos. 3. Parar de ter medo de carta da Receita Federal. 4. Ter alguém de confiança para tocar a loja quando ele viajar. 5. Conseguir dormir sem pensar em dívida, funcionário ou imposto. |
| **Medos** | 1. **Tomar uma multa fiscal que quebre o negócio**. Um amigo do ramo tomou R$ 80 mil de autuação por ICMS ST não recolhido. 2. **Perder a loja**. Tudo o que construiu está ali. Não tem plano B. 3. **Ser enganado** — por fornecedor, por funcionário, por contador. 4. **Ficar refém do contador** sem entender o que está sendo feito. 5. **Não conseguir se aposentar** porque o negócio não sobra. |
| **Frustrações** | 1. "O contador só me manda boleto. Não me explica nada. Mando pergunta e ele responde 3 dias depois." 2. "Toda vez que vou tirar nota fiscal de saída, o site da Sefaz cai ou muda a senha." 3. "Fornecedor manda nota com valor errado. Eu só descubro quando o contador reclama 2 meses depois." 4. "Não sei se estou pagando imposto certo. Pago e rezo." 5. "Me sinto burro com essas siglas — CFOP, NCM, CST. Parece que falam outra língua." |
| **Nível de maturidade digital** | **Baixo a moderado**. Usa WhatsApp intensamente (áudio, foto, grupo). Usa app de banco (extrato, Pix, boleto). Usa Tiny ERP para emitir NF-e de saída (aprendeu na raiva). Sabe anexar arquivo no WhatsApp, mas não sabe compactar em ZIP. Sabe o que é PDF. Não sabe o que é XML ("é aquele arquivo que o contador pede"). Sabe instalar app pelo Play Store. Não usa computador com frequência — prefere celular. Já caiu em golpe de boleto falso uma vez. |
| **Dispositivos** | Smartphone Android (Samsung, 2 anos de idade). Computador de mesa na loja (Windows 10, lento). Impressora térmica de nota fiscal. |
| **Gatilhos de compra** | 1. **Medo concreto**: ouvir de um colega lojista que tomou multa fiscal. 2. **Demonstração instantânea**: alguém mostrar na frente dele que "essa nota aqui está errada e você nem sabia" usando o próprio CNPJ dele. 3. **Recomendação do contador**: se Dona Célia falar "isso aqui presta", ele compra em 5 minutos. 4. **Preço que não dói**: algo entre R$ 79 e R$ 149/mês é "café pequeno" perto do risco. 5. **Primeira multa ou notificação**: depois que doer no bolso uma vez, a disposição de pagamento triplica. |
| **Objeções comuns** | 1. "Isso não é coisa que o contador já faz?" 2. "Vou ter que aprender mais um sistema? Já tenho o Tiny, o app do banco, o WhatsApp..." 3. "Isso aí me arruma mais trabalho ou menos trabalho?" 4. "Se eu pagar isso e mesmo assim tomar multa, você devolve o dinheiro?" 5. "Quanto tempo vou gastar para aprender a usar isso?" |

---

### PERSONA 2 — Usuária Operacional (Delegada)

#### **Fernanda Souza — Auxiliar Administrativo**

| Dimensão | Descrição |
|---|---|
| **Idade** | 28 anos |
| **Formação** | Ensino médio completo. Começou faculdade de Ciências Contábeis EAD, trancou no 2º semestre por falta de tempo. |
| **História** | Trabalha na loja há 3 anos. Entrou como caixa. Roberto viu que ela era organizada e confiável e promoveu para "cuidar da parte de documentos". Hoje ela faz contas a pagar, confere pedidos, organiza notas fiscais de entrada (imprime e grampeia), manda documentos para o contador via WhatsApp e lida com fornecedores para corrigir nota. Roberto confia nela mais do que em qualquer outro funcionário. |
| **Rotina típica** | Chega às 8h. Abre e-mails de fornecedores. Baixa XMLs e DANFEs. Confere se produto entregue bate com pedido e nota. Liga para 2 fornecedores pedindo carta de correção de NF-e. Separa documentos mensais do contador e envia por WhatsApp (foto do documento, às vezes PDF). Responde Dona Célia quando ela pede "cadê a nota X". Faz pagamento de boletos no app do banco. Sai às 17h. |
| **Contexto de trabalho** | Mesinha no canto do escritório da loja. Computador compartilhado com Roberto. Acumula também funções de RH simples (conferir ponto, pedir almoço). É interrompida constantemente — o telefone toca, o Roberto chama, cliente pergunta coisa no balcão. |
| **Objetivos** | 1. Ser promovida a gerente administrativa com aumento e carteira assinada como tal. 2. Terminar a faculdade de Ciências Contábeis um dia. 3. Ser reconhecida pelo Roberto como indispensável. 4. Reduzir o tempo que gasta caçando documento — odeia essa parte. 5. Ter um trabalho menos estressante no final do mês (fechamento). |
| **Medos** | 1. **Perder um documento** e a culpa cair nela (nota fiscal perdida = erro no contador = multa = bronca do Roberto). 2. **Passar vergonha** com o contador por não entender um termo técnico. 3. **Ser demitida** se fizer algo errado grave. 4. **Não dar conta** do acúmulo de funções. |
| **Frustrações** | 1. "Fornecedor manda XML por e-mail com o nome todo errado (IMG_20240528.xml). Tenho que abrir um por um." 2. "A Dona Célia pede as coisas de um jeito que eu não entendo. Ela fala 'preciso do XML do CFOP 5401' — que que é isso?" 3. "O Roberto não entende que eu não dou conta de tudo. Ele acha que é só 'apertar um botão'." 4. "O computador da loja é muito lento. Toda vez trava." 5. "No fim do mês é um caos. Pilha de papel, WhatsApp bombando, contador apressando." |
| **Nível de maturidade digital** | **Moderado** (maior que o Roberto). Sabe usar Excel básico (tabelas, soma, filtro). Sabe baixar XML de e-mail, salvar em pasta, renomear arquivo. Sabe converter foto em PDF no celular. Já usou Tiny ERP, app de banco, planilha Google. Sabe pesquisar no Google quando tem dúvida. Não sabe o que é certificado digital A1/A3, nem como instalar. Não programa. Tem celular iPhone (usado, da irmã). |
| **Dispositivos** | Computador da loja (Windows). Celular iPhone. Impressora jato de tinta. |
| **Gatilhos de adoção** | 1. **Redução clara de trabalho repetitivo**: se ela vê que o produto elimina "abrir 110 XMLs na mão", ela pede pro Roberto comprar. 2. **Interface mais fácil que o Tiny ERP**: se ela achar bonito e simples, adota rápido. 3. **Aprovação da Dona Célia**: se o contador validar, ela fica tranquila. 4. **Treinamento curto**: se aprender em 15 minutos, defende o produto internamente. 5. **Status**: usar "software de inteligência fiscal" a faz sentir que está evoluindo na carreira. |
| **Objeções comuns** | 1. "Isso vai substituir meu trabalho?" (medo de ser demitida). 2. "Vou ter que alimentar mais um sistema além de tudo que já faço?" 3. "Tem que funcionar no meu celular porque o computador da loja é ruim." 4. "Se eu fizer alguma coisa errada nesse sistema, vai dar problema fiscal?" 5. "O Roberto vai achar que agora eu posso acumular mais coisa ainda." |

---

### PERSONA 3 — Influenciadora

#### **Dona Célia — A Contadora**

| Dimensão | Descrição |
|---|---|
| **Idade** | 47 anos |
| **Formação** | Técnica em Contabilidade (CRC ativo). Não tem nível superior. |
| **História** | Trabalha com contabilidade desde os 19 anos. Abriu o próprio escritório aos 32. Hoje atende ~40 empresas (90% Simples Nacional). A equipe é ela + 2 assistentes (uma estagiária). A carteira inclui 7 lojas de material de construção. Ela sabe tudo de Simples Nacional, DAS, DEFIS, DIRF. Mas está sobrecarregada e trabalha 12h/dia na época de entrega de declaração. |
| **Rotina típica** | Chega ao escritório às 8h. Responde WhatsApp de clientes ("Dona Célia, qual o valor da minha DAS esse mês?"). Confere documentos enviados pelos clientes — muitos chegam errados, incompletos, fora do prazo. Apura DAS. Emite guias. Corrige declarações. À tarde, atende fiscalização de um cliente que caiu na malha fina. Sai às 20h. Leva trabalho para casa no fim de semana. |
| **Contexto de trabalho** | Escritório pequeno em sala comercial. 3 mesas, 3 computadores. Pilhas de papel. Sistema Alterdata (antigo, mas ela domina). WhatsApp Web aberto o dia inteiro. Ar-condicionado quebrado metade do ano. |
| **Objetivos** | 1. Reduzir retrabalho causado por cliente que manda documento errado ou atrasado. 2. Conseguir atender mais clientes com a mesma equipe (escalar receita do escritório). 3. Dormir sem medo de ter errado algo que vai dar multa para o cliente. 4. Não perder cliente para escritório maior que oferece "tecnologia". 5. Tirar férias de verdade pela primeira vez em 5 anos. |
| **Medos** | 1. **Cometer um erro fiscal grave** e o cliente ser autuado — a culpa cai nela, mesmo quando o erro veio do cliente. 2. **Perder relevância**: sente que os escritórios maiores estão usando "inteligência artificial" e ela está ficando para trás. 3. **Perder o cliente Roberto**: ele paga em dia, é leal, é 7% do faturamento do escritório. 4. **Ser responsabilizada legalmente** por erro em declaração (risco de processo ético no CRC). 5. **Burnout**: já sente os sintomas, mas não pode parar. |
| **Frustrações** | 1. "Cliente manda 50 fotos de nota fiscal pelo WhatsApp. Tenho que digitar tudo na mão. Isso não é trabalho de contador, é trabalho de digitador." 2. "Toda vez que explico algo para o Roberto, ele finge que entendeu e depois faz algo errado de novo." 3. "Esses sistemas novos são caros e complicados. O Alterdata é horrível, mas é o que eu sei usar." 4. "Fornecedor emite nota errada e sobra para mim corrigir. Isso não é justo." 5. "Se eu cobrasse por hora extra, tava rica. Mas não posso repassar isso para cliente Simples." |
| **Nível de maturidade digital** | **Médio** (domínio técnico-profundo em sistemas contábeis, baixo em tecnologia nova). Sabe usar Alterdata, sistema da Receita Federal (e-CAC, EFD), Sefaz, portais de prefeitura (NFS-e). Sabe baixar e instalar certificado digital. Sabe importar/exportar SPED. Sabe o que é API ("mas nunca usei uma"). Não sabe programar. Não usa ferramentas modernas (Slack, Notion). Tem medo de "nuvem" ("e se vazar dado de cliente?"). Usa WhatsApp Web o dia todo. E-mail no Outlook. |
| **Dispositivos** | Computador desktop (Windows 10, i3, 8GB RAM). Celular Android. Certificados digitais A1 e A3 (dela e de clientes, tudo em um cofre físico). |
| **Gatilhos de recomendação** | 1. **Reduzir trabalho operacional dela**: se o produto entregar dados organizados em vez de fotos de WhatsApp, ela abraça. 2. **Aumentar a qualidade dos dados que chegam**: se o Roberto passar a mandar só o que está inconsistente, em vez de tudo, ela ganha 10h/mês. 3. **Não ameaçar o papel dela**: se o produto se posicionar como "ferramenta que ajuda o contador a fazer um trabalho melhor", sem falar em "substituir contador". 4. **Aumentar ticket médio do escritório**: se ela puder oferecer "análise fiscal proativa" como serviço premium usando o Copiloto como ferramenta interna. 5. **Primeiro mês grátis para o escritório**: contadores são early adopters de ferramentas quando o custo é zero e o benefício é óbvio. |
| **Objeções comuns** | 1. "Isso não vai gerar mais retrabalho para mim? Vou ter que corrigir o que essa ferramenta apontar?" 2. "Essa ferramenta vai recomendar coisa errada e o cliente vai me cobrar." 3. "Se o cliente usar isso, ele vai ficar questionando tudo que eu faço." 4. "Vocês têm CRC? Se não têm, não podem dar orientação fiscal." (alerta regulatório real) 5. "Já uso Alterdata. Isso integra? Se não integrar, vou ter que digitar tudo de novo?" |

### Riscos e pontos de atenção

| Risco | Severidade | Mitigação |
|---|---|---|
| A Fernanda sentir que o produto ameaça o emprego dela — pode resistir ativamente ou sabotar adoção | Alta | Posicionar o produto como "assistente da Fernanda", não substituto. Mostrar que ela ganha tempo para fazer a parte mais estratégica (negociar com fornecedor, não caçar XML). |
| Dona Célia interpretar o produto como "cliente questionando meu trabalho" e vetar | Alta | Construir interface e relatórios que o contador aprove; incluir modo "compartilhar com contador"; nunca dizer "seu contador está errado", mas sim "esse documento parece inconsistente — sugerimos confirmar com seu contador". |
| Roberto comprar e delegar 100% para Fernanda, que não tem poder de decisão — produto fica órfão | Média | Onboarding deve engajar o Roberto na primeira experiência (raio-x de 5 min com as notas dele). Depois, ele pode delegar o operacional mantendo o hábito semanal de abrir o dashboard. |
| Nível de maturidade digital baixo do Roberto pode gerar abandono no onboarding | Média | Onboarding via WhatsApp: "Roberto, me manda os XMLs da semana aqui no WhatsApp que eu já processo e te mostro." Sem login, sem senha, sem tutorial. Se funcionar, ele migra para o app. |
| Dona Célia pode levantar a questão regulatória de que só contador habilitado pode dar orientação fiscal | Alta | Todas as recomendações do produto devem vir com disclaimer explícito: "Esta é uma análise preliminar automática. Confirme com seu contador antes de tomar qualquer ação." |

---

## Etapa 4 — Jobs to be Done

### Objetivo da etapa

Mapear os trabalhos (jobs) que Roberto, Fernanda e Dona Célia precisam realizar — nos níveis funcional, emocional e social — e priorizar qual job o MVP do FiscoPilot deve resolver primeiro. Toda decisão de funcionalidade nas próximas etapas deriva desta priorização.

### Premissas adotadas

| # | Premissa | Justificativa |
|---|---|---|
| P1 | Jobs são estáveis ao longo do tempo; soluções mudam, jobs não | O que Roberto precisa fazer independe da tecnologia; o "como" é que evolui |
| P2 | Um job só é válido se for observável — alguém conseguiria ver a pessoa executando ou evitando aquele job no mundo real | Evita abstrações como "ter paz de espírito" sem contexto concreto |
| P3 | Job funcional, emocional e social coexistem em toda interação com o produto; a priorização define qual será atendido primeiro no MVP | O MVP não consegue atender todos os jobs de uma vez |
| P4 | O contador (Dona Célia) é persona influenciadora, não usuária pagante do MVP; seus jobs devem ser atendidos indiretamente | O produto não será vendido para contadores na fase 1; mas precisa da benção deles |
| P5 | Formato obrigatório: "Quando [situação concreta], eu quero [ação específica], para [resultado observável]" | Clareza e testabilidade |

### Decisões recomendadas

| Decisão | Conteúdo | Status |
|---|---|---|
| D1 | O job principal do MVP é: "Quando recebo NF-e de fornecedor, quero saber se alguma delas tem inconsistência fiscal que pode me gerar multa, para corrigir antes que o mês feche" | Decisão de MVP |
| D2 | Os jobs da Fernanda (ingestão de XML) são pré-condição para o job do Roberto (entender risco); o MVP precisa atender os dois | Decisão de MVP |
| D3 | Os jobs da Dona Célia (receber dados organizados) são consequência do produto funcionar bem para Roberto e Fernanda; não serão funcionalidades dedicadas no MVP | Decisão de escopo |
| D4 | Jobs emocionais são atendidos como consequência dos jobs funcionais, não como features separadas | Decisão de produto |
| D5 | Jobs sociais serão endereçados via comunicação e posicionamento, não via funcionalidade no MVP | Decisão de GTM |

### Top 10 Jobs Funcionais

| # | Job funcional | Persona | Formato JTBD |
|---|---|---|---|
| **JF1** | Ingerir NF-e de entrada em lote | Fernanda | Quando chego na loja de manhã e tenho 15 XMLs novos de fornecedores no e-mail, **eu quero** carregar todos de uma vez só (arrastar pasta, encaminhar e-mail ou subir ZIP), **para** não precisar abrir cada XML individualmente e digitar dados à mão. |
| **JF2** | Saber se há inconsistência fiscal grave | Roberto | Quando recebo NF-e dos meus fornecedores durante o mês, **eu quero** saber se alguma delas tem um erro fiscal que pode gerar multa, **para** pedir correção ao fornecedor antes que o contador feche o mês e declare errado. |
| **JF3** | Entender o erro em linguagem simples | Roberto | Quando o sistema aponta que uma NF-e "está com CFOP divergente", **eu quero** que ele me explique o que isso significa em dinheiro e consequência real (ex.: "se corrigir, você evita pagar R$ 340 a mais na DAS"), **para** eu decidir se vale a pena correr atrás do fornecedor ou não. |
| **JF4** | Saber exatamente o que fazer com cada problema | Roberto + Fernanda | Quando descubro uma inconsistência, **eu quero** que o sistema me diga o próximo passo concreto ("ligue para o fornecedor e peça carta de correção com CFOP 5102"), **para** eu não ficar paralisado sem saber o que fazer. |
| **JF5** | Enviar dados organizados para o contador | Fernanda | Quando o mês está fechando e a Dona Célia pede "os documentos do mês", **eu quero** gerar um resumo do que foi conferido, do que foi corrigido e do que ainda está pendente, **para** ela não me ligar 3 vezes pedindo documento que eu já mandei. |
| **JF6** | Registrar histórico de ações tomadas | Roberto | Quando corrijo um problema com fornecedor ou decido ignorar um alerta de baixo risco, **eu quero** registrar essa decisão com data e motivo, **para** se um dia a Receita questionar, eu ter prova de que não foi omissão — foi decisão informada. |
| **JF7** | Priorizar problemas por gravidade financeira | Roberto | Quando o sistema encontra 7 inconsistências no mês, **eu quero** ver quais vão me custar mais caro se eu não corrigir, **para** focar nas 2 que realmente importam e não perder tempo com as 5 que são irrelevantes. |
| **JF8** | Reconciliar NF-e recebida vs. pedido de compra | Fernanda | Quando a mercadoria chega na loja, **eu quero** bater o XML da nota contra o que eu pedi (produto, quantidade, valor), **para** não pagar por coisa que veio errada e não deixar o estoque ficar errado. |
| **JF9** | Verificar se fornecedor é idôneo fiscalmente | Roberto | Quando começo a comprar de um fornecedor novo, **eu quero** saber se as NF-e dele costumam vir corretas ou se ele tem histórico de nota problemática, **para** decidir se vale a pena manter esse fornecedor ou trocar. |
| **JF10** | Preparar documentação para fiscalização | Roberto | Quando chega uma notificação da Sefaz pedindo explicação sobre NF-e de 8 meses atrás, **eu quero** encontrar rapidamente todas as notas daquele período e o que foi feito com cada uma, **para** responder a fiscalização em 24h sem desespero e sem depender exclusivamente do contador. |

### Top 5 Jobs Emocionais

| # | Job emocional | Persona | Formato JTBD |
|---|---|---|---|
| **JE1** | Sentir-se no controle do risco fiscal | Roberto | Quando olho para a pilha de 110 NF-e do mês e não faço ideia se tem erro ali, **eu quero** sentir que tenho visibilidade sobre o que está acontecendo, **para** não sentir aquela angústia de "será que tem bomba escondida nesse bolo de papel?". |
| **JE2** | Sentir-se competente ao falar com o contador | Roberto | Quando a Dona Célia me liga falando de "CFOP" e "alíquota interestadual", **eu quero** sentir que entendo o básico do que ela está dizendo, **para** não me sentir burro e não ter que ficar concordando sem entender nada. |
| **JE3** | Sentir-se produtiva, não desperdiçada | Fernanda | Quando passo 40 minutos abrindo XMLs e conferindo nota contra pedido manualmente, **eu quero** sentir que meu tempo está sendo bem usado em algo que realmente exige inteligência humana, **para** não chegar em casa exausta e com sensação de que "qualquer um faria isso". |
| **JE4** | Sentir-se valorizada como profissional | Dona Célia | Quando o Roberto me manda 50 fotos de WhatsApp com nota fiscal torta e eu tenho que digitar tudo, **eu quero** sentir que sou tratada como profissional qualificada que analisa risco fiscal, **para** não me sentir uma digitadora de R$ 1.800/mês. |
| **JE5** | Dormir sem medo de surpresa fiscal | Roberto | Quando apago a luz às 22h, **eu quero** conseguir dormir sem aquele pensamento intrusivo "e se amanhã chegar carta da Receita?", **para** acordar com energia para tocar o negócio em vez de acordar ansioso. |

### Top 5 Jobs Sociais

| # | Job social | Persona | Formato JTBD |
|---|---|---|---|
| **JS1** | Ser visto como empresário profissional, não amador | Roberto | Quando encontro outros lojistas no almoço da associação comercial, **eu quero** ser percebido como alguém que tem o negócio organizado fiscalmente, **para** não ser aquele cara de quem falam "o Roberto é bom, mas a contabilidade dele é uma bagunça". |
| **JS2** | Ser percebida como indispensável para o negócio | Fernanda | Quando o Roberto comenta com o gerente do banco ou com a Dona Célia sobre a operação da loja, **eu quero** que ele diga "a Fernanda resolve" com orgulho, **para** eu sentir segurança no meu emprego e reconhecimento real. |
| **JS3** | Ser vista como contadora moderna e confiável | Dona Célia | Quando outros contadores da cidade comentam que "escritório pequeno vai sumir", **eu quero** ser vista como a profissional que usa ferramentas inteligentes e entrega mais que os grandes, **para** reter clientes como o Roberto e atrair novos por recomendação. |
| **JS4** | Evitar ser culpado publicamente por erro fiscal | Roberto | Quando um fornecedor emite nota errada e o fisco notifica, **eu quero** ter registro de que eu detectei e alertei o fornecedor, **para** não ser julgado como negligente ("o Roberto não confere nada") pelo contador, pelo fornecedor ou pelo fiscal. |
| **JS5** | Pertencer ao grupo de empresários que "crescem com segurança" | Roberto | Quando vejo colegas lojistas expandindo (abrindo filial, comprando ponto), **eu quero** sentir que pertenço ao grupo que consegue crescer porque tem o fiscal sob controle, **para** não me sentir estagnado por medo de "crescer e quebrar com imposto". |

### Ranking dos Jobs Mais Importantes para o MVP

| Rank | Job | Código | Bloqueante? | Impacto fiscal | Factibilidade | Pontuação |
|---|---|---|---|---|---|---|
| **1** | Saber se há inconsistência fiscal grave | JF2 | Sim — sem isso, produto = 0 | Altíssimo | Alta (regras determinísticas) | **MVP obrigatório** |
| **2** | Ingerir NF-e de entrada em lote | JF1 | Sim — sem ingerir dados, JF2 não roda | Indireto | Alta (parser de XML maduro) | **MVP obrigatório** |
| **3** | Entender o erro em linguagem simples | JF3 | Quase — se não entende, não age; se não age, não há valor | Altíssimo | Média (IA generativa para explicação) | **MVP obrigatório** |
| **4** | Priorizar problemas por gravidade financeira | JF7 | Não — pode mostrar tudo sem priorizar, mas com péssima UX | Alto | Alta (ranking numérico simples) | **MVP recomendado** |
| **5** | Saber exatamente o que fazer com cada problema | JF4 | Não — mas sem isso, a jornada quebra após JF3 | Alto | Média (exige curadoria manual de ações por tipo de erro) | **MVP desejável** |
| **6** | Enviar dados organizados para o contador | JF5 | Não — atende Dona Célia indiretamente | Médio | Média (PDF exportável) | **MVP se possível** |
| **7** | Sentir-se no controle do risco fiscal | JE1 | Não — é consequência de JF2+JF3 funcionarem | Emocional | Alta (UX focada em clareza visual) | **Atendido indiretamente** |
| **8** | Reconciliar NF-e vs. pedido de compra | JF8 | Não — é funcionalidade de ERP, não core do Copiloto | Baixo | Baixa (exige integração com pedidos) | **Fora do MVP** |
| **9** | Verificar idoneidade fiscal de fornecedor | JF9 | Não — é funcionalidade avançada | Médio | Média (exige histórico acumulado) | **Fora do MVP** |
| **10** | Registrar histórico de ações tomadas | JF6 | Não — mas importante para auditoria | Indireto | Alta (log de eventos simples) | **MVP se trivial** |

### Job Principal que o MVP Deve Resolver Primeiro

> **JF2: Quando recebo NF-e de fornecedor durante o mês, eu quero saber se alguma delas tem inconsistência fiscal que pode me gerar multa, para pedir correção ao fornecedor antes que o contador feche o mês e declare errado.**

**Por que este e não outro?**

| Alternativa | Por que foi preterida |
|---|---|
| JF1 (Ingerir NF-e) | JF1 é meio, não fim. O dono não acorda querendo "ingerir XML" — ele quer saber se tem problema. JF1 é infraestrutura necessária para JF2 existir. |
| JF3 (Entender o erro) | JF3 é fundamental, mas é etapa 2 da cadeia. Primeiro o sistema precisa detectar (JF2) para depois explicar (JF3). Detectar é deterministicamente mais viável que explicar. |
| JF8 (Reconciliar NF-e) | Isso é feature de ERP (Tiny, Bling, Omie). Não é o diferencial do Copiloto. Entrar nesse terreno dilui a proposta de valor. |
| JE1 (Sentir-se no controle) | Jobs emocionais são atendidos como efeito colateral dos funcionais. Se JF2+JF3 funcionarem, JE1 é consequência automática. |

**Mecanismo de entrega do job principal (esboço para etapas futuras):**

1. Fernanda carrega XMLs do mês (upload via web ou encaminha por e-mail/WhatsApp)
2. Sistema parseia XMLs e extrai campos fiscais relevantes (CNPJ emitente, CFOP, NCM, CST, valor, alíquota, UF)
3. Motor de regras determinísticas compara contra tabelas de referência (CFOP esperado por tipo de operação, NCM vs. anexo do Simples, etc.)
4. Sistema retorna dashboard: "110 notas analisadas. 3 com inconsistência. 1 de alto risco."
5. Roberto vê no celular, em português: "A nota do Fornecedor CimentoBom (R$ 8.400) veio com CFOP 6102, mas pelo seu regime deveria ser 1102. Risco: pagar R$ 1.008 a mais na DAS. Sugestão: peça carta de correção."

**Teste de validação do job principal:**

- Pegar 50 NF-e reais de uma loja de material de construção
- Processar manualmente com as 5 regras principais
- Mostrar para 3 donos de loja e perguntar: "Isso te ajudaria?" e "Você pagaria R$ 97/mês por isso?"
- Se 2 de 3 disserem sim, job validado. Se não, pivotar.

### Riscos e pontos de atenção

| Risco | Severidade | Mitigação |
|---|---|---|
| JF2 depende de JF1 (ingestão); se a ingestão for difícil, o job principal nunca roda | Alta | MVP deve ter 3 canais de ingestão: (1) upload ZIP de XMLs, (2) encaminhar e-mail com XMLs para um e-mail do Copiloto, (3) WhatsApp: manda os arquivos e o sistema processa. |
| JF3 depende de IA generativa; se a explicação sair errada, o produto perde credibilidade na hora | Alta | MVP deve usar IA apenas para parafrasear uma explicação templateada; o diagnóstico (JF2) é 100% determinístico. Se a IA alucinar, o diagnóstico-base ainda estará correto. |
| Se o motor de regras tiver baixa cobertura (ex.: detecta só 30% dos erros), o produto pode gerar falsa sensação de segurança | Média | Comunicação explícita: "Analisamos X tipos de inconsistência. Outros riscos podem existir. Consulte seu contador." |
| Jobs da Fernanda podem ser ignorados se o Roberto pular direto para o resultado — mas alguém precisa operar o sistema | Média | MVP precisa funcionar em dois modos: (a) auto-serviço (Fernanda opera, Roberto consome dashboard) e (b) founder-assisted (Roberto manda XMLs pelo WhatsApp e recebe relatório pronto — sem tocar no app) |

---

## Etapa 5 — Proposta de Valor

### Objetivo da etapa

Construir uma proposta de valor nítida, testável e diferenciada que traduza o job principal (JF2 — detectar inconsistências fiscais em NF-e de entrada) em uma promessa concreta que um dono de loja de material de construção entenda em 10 segundos e pela qual esteja disposto a pagar.

### Premissas adotadas

| # | Premissa | Justificativa |
|---|---|---|
| P1 | A proposta de valor deve funcionar em uma conversa de WhatsApp — canal real de aquisição do MVP | Se não couber em 3 mensagens de WhatsApp, não fecha venda nesse ICP |
| P2 | A proposta fala com o Roberto (dono), não com a Fernanda (auxiliar) nem com a Dona Célia (contadora) | Quem paga é o Roberto; a proposta precisa convencê-lo primeiro |
| P3 | A diferenciação mais forte não é contra concorrente direto (não existe), mas contra o comportamento atual: "não fazer nada e torcer para não dar merda" | O maior concorrente é a inércia e a falsa sensação de que "o contador resolve tudo" |
| P4 | A proposta de valor do MVP não pode prometer o que não entrega em 90 dias: sem NFS-e, sem Lucro Real, sem integração em tempo real com Sefaz, sem substituição do contador | Prometer além do MVP quebra confiança no primeiro mês de uso |
| P5 | A proposta deve ser validada antes de escrever código — mostrar a 5 donos de loja reais e medir intenção de compra | Validação de valor precede validação de produto |

### Decisões recomendadas

| Decisão | Conteúdo | Status |
|---|---|---|
| D1 | Proposta de valor central: "Saiba se suas notas fiscais de compra têm erro — antes que o erro vire multa" | Decisão de MVP |
| D2 | Posicionamento: camada de inteligência entre o ERP e o contador — não substitui nenhum dos dois | Decisão estratégica |
| D3 | Diferenciação primária: "tradução do fiscal para português claro" — é o que nenhum concorrente faz | Decisão estratégica |
| D4 | Tagline: "FiscoPilot — suas notas fiscais explicadas." | Decisão de comunicação |
| D5 | A mensagem de demo deve incluir obrigatoriamente um "raio-x ao vivo" com dados reais do prospect | Decisão de vendas |

### Proposta de valor em 1 frase

> **O FiscoPilot lê suas notas fiscais de compra, encontra o que está errado e te explica em português claro o que fazer — antes que o erro vire multa.**

### Proposta expandida

Toda semana você recebe dezenas de notas fiscais dos seus fornecedores. Cada nota tem códigos como CFOP, NCM, CST e alíquotas que você não entende — e nem deveria entender. Mas se qualquer um desses códigos vier errado, você pode pagar imposto a mais ou cair na malha fina da Receita. Seu contador só vê isso no fim do mês. Às vezes nem vê. O FiscoPilot analisa cada nota no momento em que você carrega, cruza com as regras do Simples Nacional e te mostra: "3 notas com problema. 1 grave. Se você corrigir essa aqui, economiza R$ 340 na DAS desse mês." Você não precisa aprender fiscal. Você precisa saber o que fazer. É para isso que serve o Copiloto.

### Tagline

> **Suas notas fiscais explicadas.**

### Promessa principal

> **Se houver erro fiscal nas suas notas de compra, a gente te avisa em português claro — com o impacto em reais e o que fazer. Em menos de 2 minutos.**

### Diferenciação

#### Contra ERP (Tiny, Bling, Omie, ContaAzul)

> ERPs organizam sua operação. O Copiloto organiza seu risco fiscal. O ERP emite nota; o Copiloto audita a nota que você recebeu. São complementares — e nossos clientes usam os dois.

#### Contra escritório contábil

> Seu contador é essencial e continuará sendo. Mas ele vê seus dados 1 vez por mês, depois que tudo já aconteceu. O Copiloto te acompanha durante o mês e te ajuda a chegar na conversa com o contador sabendo o que perguntar — em vez de só ouvir e concordar.

#### Contra software fiscal tradicional (Mastermaq, Alterdata)

> Softwares fiscais foram feitos para contadores. O Copiloto foi feito para você, que não sabe — nem quer saber — o que significa CFOP 5401. A gente traduz o fiscales para o português do seu negócio.

#### Contra planilhas e processos manuais (WhatsApp, caderninho, Excel)

> Sua planilha não sabe o que é uma nota fiscal. Ela não detecta CFOP errado, não cruza NCM com anexo do Simples, não calcula risco de multa. E toda vez que a Fernanda digita algo errado, ninguém percebe — até o fisco perceber.

### Mensagem central para homepage

> **Suas notas fiscais de compra analisadas em minutos.**
>
> Você carrega os XMLs. A gente lê, cruza com as regras do Simples Nacional e te mostra em linguagem simples: o que está certo, o que está errado e o que você precisa fazer. Antes que o mês feche. Antes que vire multa.
>
> *FiscoPilot — Para donos de loja que querem dormir tranquilos.*

### Mensagem central para demo comercial

> **Roteiro (3 minutos):**
>
> 1. *"Roberto, você sabe quantas notas fiscais de compra você recebeu esse mês?"*
> 2. *"E quantas delas estão com algum erro que pode te dar dor de cabeça?"*
> 3. *"Me manda os XMLs desse mês aqui no WhatsApp."*
> 4. (Processa em tela) *"Pronto. 87 notas analisadas. 4 com inconsistência. Essa aqui — do Distribuidora X — veio com CFOP errado. Se não corrigir, você paga R$ 412 a mais na DAS. Quer que eu te mostre exatamente o que falar para o fornecedor?"*
> 5. *"Isso custa R$ 97 por mês. Menos que o almoço de vocês dois. Quer testar esse mês?"*

### Riscos e pontos de atenção

| Risco | Severidade | Mitigação |
|---|---|---|
| A promessa "a gente te avisa" pode ser interpretada como garantia de cobertura total — se o produto não detectar um erro que depois gera multa, o Roberto pode responsabilizar o Copiloto | Alta | Disclaimer visível em toda tela de resultado: "Análise automática preliminar. Cobre X tipos de inconsistência. Confirmar com contador." + cláusula contratual clara de limitação de responsabilidade |
| A tagline "suas notas fiscais explicadas" pode atrair PMEs de qualquer setor com qualquer documento — desalinhamento com o escopo real do MVP (só NF-e, só Simples Nacional) | Média | A homepage precisa filtrar expectativa já no subtítulo: "Para lojas de material de construção no Simples Nacional" |
| O "teste grátis" com dados reais do prospect na demo pode expor o founder a risco se o processamento falhar ou mostrar resultado errado ao vivo | Média | Ter um "plano B" para demo: usar dados anonimizados pré-processados de uma loja similar se a importação falhar |
| A diferenciação contra contador pode soar como ataque — e Dona Célia é gatekeeper | Alta | Toda comunicação deve incluir reforço explícito: "Seu contador é parceiro, não concorrente. A gente complementa o trabalho dele." |

---

## Etapa 6 — Recorte do MVP

### Objetivo da etapa

Definir o menor produto vendável possível — o "FiscoPilot MVP" — com escopo cirúrgico, construível em 90 dias por uma equipe de 2 a 3 pessoas, que gere valor perceptível na primeira semana de uso e justifique uma cobrança mensal a partir do primeiro mês.

### Premissas adotadas

| # | Premissa | Justificativa |
|---|---|---|
| P1 | Time de construção: 1 founder full-stack + 1 engenheiro back-end + 1 designer UX (part-time) | Perfil típico de startup em estágio zero; o founder cobre vendas, produto e parte do código |
| P2 | 90 dias corridos = ~65 dias úteis efetivos de desenvolvimento | Descontando vendas, feedback de beta, ajustes e imprevistos |
| P3 | O MVP será usado em beta fechado com 3 a 5 lojas antes de qualquer cobrança — 15 dias de beta gratuito | Validação de valor antes de monetização; gera depoimentos para venda |
| P4 | Escopo é ditado pelo job JF2: detectar inconsistências fiscais em NF-e de entrada | Tudo que não contribui diretamente para esse job está fora do MVP |
| P5 | A primeira venda será feita pessoalmente pelo founder, não via self-service | Investimento em onboarding guiado reduz barreira de maturidade digital do ICP |

### Decisões recomendadas

| Decisão | Conteúdo | Status |
|---|---|---|
| D1 | **Funcionalidade nuclear**: processar upload de XMLs de NF-e e retornar um dashboard com inconsistências detectadas, explicadas em português simples, com impacto estimado em reais e sugestão de ação | Decisão de MVP |
| D2 | Ingestão de XMLs via 2 canais: (a) upload ZIP na interface web, (b) envio para e-mail dedicado do Copiloto | Decisão de MVP |
| D3 | WhatsApp como canal de ingestão fica para a semana 10-12, se houver folga; MVP começa com web + e-mail | Decisão de priorização |
| D4 | Onboarding 100% guiado pelo founder nos primeiros 10 clientes — sem self-service, sem tutorial, sem vídeo | Decisão de GTM |
| D5 | Beta fechado (gratuito por 15 dias) começa na semana 8; primeira venda (R$ 97/mês) na semana 10 | Decisão de cronograma |

### Problema exato do MVP

> Donos de loja de material de construção no Simples Nacional recebem entre 60 e 200 NF-e de compra por mês e não têm como saber, antes do fechamento contábil, quais dessas notas contêm erros fiscais que podem gerar pagamento de imposto a maior ou risco de multa — porque os dados estão trancados em arquivos XML ilegíveis e em linguagem técnica inacessível.

### Recorte funcional

| Camada | O que faz |
|---|---|
| **Ingestão** | Recebe arquivos XML de NF-e via upload ZIP (web) ou e-mail dedicado. Armazena em bucket. Dispara processamento. |
| **Parser** | Extrai do XML: chave de acesso, CNPJ emitente, CNPJ destinatário, CFOP, NCM de cada item, CST PIS/COFINS, ICMS, valor total, valor itens, data de emissão, UF. Armazena em banco estruturado. |
| **Motor de regras** | Roda as 8 regras determinísticas sobre cada nota. Classifica resultado: OK / ATENÇÃO / RISCO ALTO. Atribui score de risco (0-100). |
| **Gerador de explicação** | Para cada inconsistência detectada, monta uma explicação em template: "O campo [X] está [Y]. O esperado pela regra [Z] é [W]. Impacto estimado: R$ [V]. Sugestão: [Ação]." |
| **Dashboard** | Exibe: total de notas processadas, resumo (OK / com ressalva / risco), lista de inconsistências ordenada por gravidade. Filtro por período. Exportação de resumo em PDF. |
| **Relatório do contador** | PDF simples com lista de notas, inconsistências encontradas e ações sugeridas — para a Fernanda enviar para Dona Célia. |

### Fluxo principal do usuário

```
1. FERNANDA: Acessa app.copilotofiscal.com pelo celular ou computador da loja
2. FERNANDA: Clica em "Carregar notas"
3. FERNANDA: Seleciona arquivo ZIP com XMLs do mês (ou arrasta para área de upload)
4. SISTEMA: Exibe barra de progresso: "Processando 87 notas..."
5. SISTEMA: Em ~15 segundos, exibe dashboard
6. ROBERTO: Abre no celular o link que o sistema enviou por WhatsApp
7. ROBERTO: Vê: "87 notas analisadas. 4 com inconsistência. 1 grave."
8. ROBERTO: Clica na inconsistência grave — "CFOP divergente na nota #12345"
9. ROBERTO: Lê: "Fornecedor X emitiu com CFOP 6102. No Simples Nacional deveria ser 1102. Se não corrigir, você paga ~R$ 412 a mais na DAS deste mês."
10. ROBERTO: Clica em "O que fazer?"
11. ROBERTO: Lê: "1. Ligue para o fornecedor. 2. Peça carta de correção com CFOP 1102. 3. Peça para reemitir a NF-e. 4. Avise Dona Célia sobre a correção."
12. ROBERTO: Marca tarefa como "Em andamento". Volta na semana seguinte, marca como "Resolvido".
13. FERNANDA: No fim do mês, clica em "Exportar relatório do contador" e envia PDF para Dona Célia.
```

### Funcionalidade nuclear

> **Upload de XMLs + detecção de inconsistências + explicação em português com impacto em reais.**

### O que entra

| Funcionalidade | Prioridade | Esforço estimado (dias) |
|---|---|---|
| Upload de XML via ZIP (web) | P0 — obrigatório | 4 |
| Upload de XML via e-mail dedicado | P0 — obrigatório | 5 |
| Parser de NF-e (modelo 55, layout 4.00) | P0 — obrigatório | 8 |
| Motor de 8 regras determinísticas | P0 — obrigatório | 12 |
| Gerador de explicação templateada + paráfrase via LLM (opcional) | P0 — obrigatório | 6 |
| Dashboard web responsivo (mobile-first) | P0 — obrigatório | 10 |
| Exportação de PDF (relatório do contador) | P1 — importante | 4 |
| Notificação por WhatsApp (resumo pós-processamento) | P1 — importante | 5 |
| Histórico de ações (marcar como resolvido/pendente/ignorado) | P1 — importante | 4 |
| Multi-tenant lógico (organização > usuários) | P1 — importante | 5 |
| Autenticação (login/senha, sessão) | P0 — obrigatório | 5 |
| Log de auditoria (quem fez o quê, quando) | P2 — desejável | 4 |

**Esforço total estimado**: 72 dias de desenvolvimento. Folga de 18 dias para QA, ajustes e imprevistos dentro dos 90 dias.

### Regras fiscais do MVP — as 8 essenciais

| # | Regra | Tipo |
|---|---|---|
| **R1** | CFOP de entrada inconsistente com o regime (ex.: CFOP 6102 para Simples Nacional deveria ser 1102) | Determinística |
| **R2** | Alíquota de ICMS destacada no XML diferente da alíquota esperada para o produto/NCM | Determinística |
| **R3** | NCM do produto inconsistente com o tipo de mercadoria esperado para material de construção | Determinística |
| **R4** | CNPJ do emitente com situação cadastral irregular na Receita Federal | Determinística |
| **R5** | Nota com valor total divergente da soma dos itens (+ tolerância de R$ 0,05) | Determinística |
| **R6** | CST de PIS/COFINS incompatível com regime Simples Nacional | Determinística |
| **R7** | Chave de acesso da NF-e com dígito verificador inválido | Determinística |
| **R8** | ICMS ST destacado para produto que NÃO está na lista de ST do estado | Determinística |

### O que não entra

| Funcionalidade | Entra quando? | Justificativa |
|---|---|---|
| Download automático de XML via Sefaz com certificado digital | Fase 2 (mês 4-6) | Complexidade técnica alta; upload manual resolve MVP |
| Suporte a NFS-e, CT-e, NFC-e | Fase 2-3 | Cada tipo de documento é um parser diferente; NF-e cobre 80% do valor |
| Suporte a Lucro Presumido e Lucro Real | Fase 2-3 | Regras fiscais diferentes; MVP foca no Simples |
| Aplicativo nativo iOS/Android | Fase 3 | Web app responsivo cobre o MVP; PWA resolve notificações |
| Integração com ERP (Tiny, Bling, Omie) | Fase 2 | Importante para reduzir atrito de ingestão, mas não essencial para MVP |
| Módulo de contador (login separado, multi-cliente) | Fase 2 | Contador recebe PDF por enquanto |
| Motor de IA generativa para diagnóstico fiscal complexo | Fase 2-3 | MVP usa só regras determinísticas; IA generativa só parafraseia |
| Gateway de pagamento e cobrança recorrente | Fase 2 | Cobrança manual por Pix nos primeiros meses |
| Self-service / trial automatizado | Fase 2 | Onboarding guiado pelo founder |
| Dashboard de fornecedores / score de idoneidade fiscal | Fase 3 | Requer histórico acumulado; sem valor no MVP |

### Hipótese de valor

> Se o FiscoPilot detectar ao menos 1 inconsistência fiscal grave a cada 2 meses (evitando R$ 500+ em multa ou imposto pago a mais), o Roberto percebe valor suficiente para continuar pagando R$ 97/mês e recomendar o produto para outros lojistas.

### Hipótese de retenção

> Se o Roberto abrir o dashboard ao menos 1 vez por semana durante o primeiro mês, a probabilidade de renovar no segundo mês é >80%. O hábito semanal de "checar as notas" é o mecanismo de retenção — mais importante que funcionalidades novas.

### Hipótese de monetização

> Preço inicial: R$ 97/mês (plano único). Se 5 dos 10 clientes do beta converterem para pagantes, o produto gera R$ 485/mês de receita recorrente — suficiente para cobrir custos de infraestrutura e validar que há disposição de pagamento. O preço sobe para R$ 147/mês quando o produto incluir download automático de XML (Fase 2).

### Risco principal do MVP

> **O motor de regras não encontrar inconsistências suficientes nas lojas beta para gerar percepção de valor — o que inviabiliza conversão para pagamento e força pivot.**

**Mitigação**:
1. Testar as 8 regras contra 200 NF-e reais ANTES de escrever código
2. Ter 4 regras reservas prontas para ativar se as 8 iniciais tiverem baixa incidência
3. Se mesmo assim a taxa de detecção for baixa, pivotar para o segundo ICP da lista (confecção ou distribuidor de bebidas)
4. Na comunicação do beta, gerenciar expectativa: "O produto está aprendendo. Você nos ajuda a ensinar quais erros são mais comuns na sua loja."

---

## Etapa 7 — Jornada do Usuário

### Objetivo da etapa

Desenhar a jornada completa que Roberto (dono) e Fernanda (auxiliar) percorrem — do primeiro contato com o FiscoPilot até o uso semanal consolidado — identificando exatamente onde o valor é percebido, onde o abandono ameaça e como cada canal de contato opera, considerando baixa maturidade digital e uso intenso de WhatsApp.

### Premissas adotadas

| # | Premissa | Justificativa |
|---|---|---|
| P1 | O primeiro contato do Roberto com o produto NÃO é via anúncio ou busca no Google — é via founder em grupo de WhatsApp de lojistas ou indicação de colega | O ICP não busca ativamente "software fiscal" — precisa ser abordado onde já está |
| P2 | A Fernanda é quem opera o sistema no dia a dia; o Roberto consome o dashboard, mas não faz upload de arquivos | Baseado nas personas: Roberto não tem paciência/habilidade para manipular XMLs |
| P3 | A Dona Célia (contadora) aparece na jornada como influenciadora, não como usuária do sistema; ela recebe PDF, não acessa o app | Decisão de MVP: módulo do contador só na Fase 2 |
| P4 | O WhatsApp é o canal principal de comunicação, notificação e suporte; e-mail é canal secundário de ingestão de documentos | Realidade operacional do ICP e das personas |
| P5 | O onboarding é 100% guiado pelo founder nos primeiros 10 clientes; não há self-service no MVP | Decisão da Etapa 6: founder faz venda + onboarding + suporte inicial |

### Decisões recomendadas

| Decisão | Conteúdo | Status |
|---|---|---|
| D1 | A primeira experiência de valor (momento "wow") deve ocorrer na própria conversa de venda — antes mesmo de o Roberto pagar | Decisão de GTM |
| D2 | O onboarding será síncrono: founder agenda call de 15 min com Roberto + Fernanda e configura tudo junto | Decisão de MVP |
| D3 | Notificações de WhatsApp são o mecanismo primário de engajamento e retenção — não o e-mail | Decisão de produto |
| D4 | O "fim do mês" é o momento de consolidação: Fernanda exporta PDF e envia para Dona Célia — isso fecha o ciclo e gera recorrência | Decisão de produto |
| D5 | O "silêncio positivo" (semana sem inconsistências) deve ser comunicado ativamente — "essa semana, tudo certo" — para evitar que o usuário ache que o produto "não está funcionando" | Decisão de UX |

### Mapa Geral da Jornada

```
ETAPA 0        ETAPA 1         ETAPA 2          ETAPA 3           ETAPA 4            ETAPA 5
AWARENESS   →  AQUISIÇÃO   →   ONBOARDING   →  PRIMEIRO VALOR  →  USO RECORRENTE  →  EXPANSÃO

Duração:      Duração:         Duração:         Duração:           Duração:            Duração:
Dia -30 a 0   Dia 0 a 3         Dia 3 a 7        Dia 7 a 14         Dia 14 a 90         Dia 90+

Canais:       Canais:          Canais:          Canais:            Canais:             Canais:
WhatsApp      WhatsApp         WhatsApp         WhatsApp           WhatsApp            WhatsApp
Boca a boca   Visita à loja    Call guiada      App web            App web             App web
Associação    Demo ao vivo     App web          E-mail             E-mail              E-mail
comercial     E-mail                             (ingestão)         (ingestão)          Indicação
```

### Etapa 0 — Awareness (Dia -30 a 0)

| Dimensão | Descrição |
|---|---|
| **O que o Roberto faz** | Está no grupo de WhatsApp "Lojistas de Material de Construção - SP". Vê mensagem do founder: "Pessoal, quem aqui já tomou multa por causa de nota fiscal com CFOP errado?" Responde: "Eu não, mas meu amigo tomou 80 mil". O founder chama no privado. |
| **Canais de contato** | WhatsApp (grupos de lojistas, associação comercial). Boca a boca de colegas. Visita do founder a associações comerciais. Feiras do setor (Feicon). |
| **O que o sistema faz** | Nada ainda. O founder é o sistema nessa etapa. |
| **O que o Roberto sente** | Curiosidade misturada com ceticismo. "Mais um software? Deve ser complicado. Deve ser caro. Será que funciona mesmo?" |
| **Pontos de atrito** | Roberto pode ignorar a mensagem no grupo (excesso de mensagens). Pode achar que é golpe. Pode não associar a dor ao produto. |

### Etapa 1 — Aquisição (Dia 0 a 3)

| Dimensão | Descrição |
|---|---|
| **O que o founder faz** | Manda áudio no WhatsApp: "Roberto, não quero te vender nada agora. Me manda os XMLs de compra desse mês que eu te mostro uma coisa rapidinho. Não leva 3 minutos." Roberto hesita, mas manda. Manda errado (PDF em vez de XML). Founder orienta: "Pede pra Fernanda — ela sabe o que é XML." Fernanda manda o ZIP. |
| **O que o sistema faz** | O founder processa os XMLs no back-end do MVP (rodando local ou staging). Gera relatório. Tira print do dashboard. |
| **Momento "wow"** | 🔥 **Primeiro momento de valor**. Roberto vê, no próprio celular, um erro real na nota de um fornecedor que ele conhece, com impacto em reais. É tangível. É o CNPJ dele. |
| **O que o Roberto sente** | Surpresa ("como assim tem erro?"), alívio ("ainda bem que eu vi agora"), curiosidade genuína ("isso aí faz todo mês?"). |
| **Pontos de atrito** | Roberto pode não saber o que é XML — Fernanda é essencial nessa etapa. Se o sistema não encontrar inconsistência nenhuma, valor não é percebido — risco altíssimo. |
| **Métrica** | Taxa de conversão: "mandei XMLs → vi valor → agendou onboarding." Meta: >60%. |

### Etapa 2 — Onboarding (Dia 3 a 7)

| Dimensão | Descrição |
|---|---|
| **O que o founder faz** | Agenda call de 15 minutos (WhatsApp vídeo ou presencial) com Roberto + Fernanda juntos. Cria conta no back-end. Envia link mágico por WhatsApp: "Clica aqui que já entra direto." |
| **O que o Roberto faz** | Clica no link. Abre o dashboard no celular (não precisa de senha). Vê as mesmas notas da demo, agora com interface real. |
| **O que a Fernanda faz** | Acessa pelo computador da loja. O founder guia: "Aqui você carrega os XMLs. Pode arrastar a pasta ou enviar por e-mail." Ela testa com 3 XMLs. Funciona. |
| **Momento "wow"** | 🔥 **Segundo momento de valor**. Fernanda percebe que o que ela fazia em 2 horas (abrir XML por XML) o sistema fez em 15 segundos. Ela vira defensora interna. |
| **O que Roberto sente** | "Isso é mais simples do que eu imaginava." A barreira de "vou ter que aprender mais um sistema" começa a cair. |
| **O que Fernanda sente** | Alívio ("finalmente algo que me ajuda"). Preocupação ("será que vão me mandar embora?" — mitigar na hora). |
| **Pontos de atrito** | Computador lento. Fernanda com medo de demissão. Roberto ausente da call. Link mágico não abre no celular antigo. |
| **Métrica** | Taxa de ativação: fez upload + abriu dashboard. Meta: >80%. |

### Etapa 3 — Primeiro Valor (Dia 7 a 14)

| Dimensão | Descrição |
|---|---|
| **O que a Fernanda faz** | Upload de XMLs 2-3x por semana. Quando o sistema aponta inconsistência, segue orientação: liga para fornecedor, pede correção, anota no sistema. |
| **O que o Roberto faz** | Segunda-feira de manhã, recebe resumo semanal no WhatsApp. Clica. Vê inconsistência. Lê explicação. Decide ação. Leva 2 minutos. |
| **O que o sistema faz** | Processa XMLs. Roda regras. Atualiza dashboard. Envia resumo semanal via WhatsApp toda segunda-feira 8h. Alerta imediato se risco ALTO. |
| **Momento "wow"** | 🔥 **Terceiro momento de valor**. Roberto está no balcão, chega notificação no WhatsApp: "Alerta: nota do Fornecedor X (R$ 8.400) com risco alto de CFOP divergente." É a primeira vez que ele age proativamente sobre um problema fiscal antes de virar multa. |
| **O que Roberto sente** | Controle. Pela primeira vez, não está no escuro. Job emocional JE1 (sentir-se no controle) começa a ser atendido. |
| **Pontos de atrito** | Sistema não achar inconsistência nas primeiras 2 semanas. Notificações ignoradas. Falso positivo quebrando confiança. |
| **Métrica** | Tempo até primeiro alerta detectado. Meta: <7 dias. Tempo até primeira ação do Roberto. Meta: <14 dias. |

### Etapa 4 — Uso Recorrente (Dia 14 a 90)

| Dimensão | Descrição |
|---|---|
| **O que a Fernanda faz** | Ritmo estável: upload 2x por semana. Gerencia pendências. Último dia do mês: exporta PDF do contador, envia para Dona Célia no WhatsApp. |
| **O que o Roberto faz** | Segunda-feira de manhã, 2 minutos. Se tem algo grave, age. Se não tem, respira aliviado. Não acessa o dashboard além disso — e tudo bem. |
| **O que a Dona Célia faz** | Recebe PDF da Fernanda. Pela primeira vez recebe dados organizados. Liga: "Fernanda, ficou ótimo. Facilitou meu fechamento." |
| **Momento "wow"** | 🔥 **Quarto momento de valor**. Dona Célia elogia. O contador — que era risco de veto — vira promotor. Validação social poderosa para o Roberto. |
| **O que Roberto sente** | Tranquilidade. Orgulho. "Minha loja tá organizada." Job social JS1 atendido. |
| **O que Fernanda sente** | Reconhecimento. Dona Célia elogiou o trabalho dela. Medo de demissão desaparece. |
| **Pontos de atrito** | Fernanda acumular pendências. Roberto perder hábito semanal. Alerta errado (falso positivo). PDF com erro de formatação. |
| **Métrica** | WAU: Roberto abre resumo toda semana. Meta: >80%. NPS após 30 dias. Meta: >40. |

### Etapa 5 — Expansão (Dia 90+)

| Dimensão | Descrição |
|---|---|
| **O que o Roberto faz** | No almoço da associação comercial, comenta com outro lojista: "Tô usando FiscoPilot. Já me salvou de duas notas erradas. Custa 97 conto." Colega pede contato. Roberto encaminha o WhatsApp do founder. |
| **Canais** | Boca a boca (principal). WhatsApp (indicação). |
| **Métrica** | NPS. Taxa de indicação. Viralidade (k-factor). |

### Resumo: Momentos "Wow" e Risco de Abandono

| # | Etapa | Momento "Wow" | Risco de abandono | Gravidade |
|---|---|---|---|---|
| M1 | Aquisição (Dia 0) | Primeiro raio-x com dados reais, em 3 min, no WhatsApp | Sistema não encontrar inconsistência → valor = zero | 🔴 Crítico |
| M2 | Onboarding (Dia 3-7) | Fernanda vê 2h de trabalho virarem 15 segundos | Fernanda sentir medo de demissão → resistência | 🟡 Médio |
| M3 | Primeiro valor (Dia 7-14) | Roberto recebe alerta no WhatsApp e age proativamente | Notificações ignoradas / falso positivo | 🔴 Crítico |
| M4 | Uso recorrente (Dia 30) | Dona Célia elogia o relatório → contador vira promotor | Roberto perde hábito / Fernanda acumula pendências | 🟡 Médio |

### Riscos e pontos de atenção

| Risco | Severidade | Mitigação |
|---|---|---|
| O "silêncio positivo" (semanas sem inconsistências) pode ser interpretado como "produto não está funcionando" ou "não preciso disso" | Alta | Comunicação ativa toda semana, mesmo sem erros: "23 notas essa semana. Tudo certo. Seu fiscal em dia." Reforça que o "tudo certo" é resultado do monitoramento, não da sorte. |
| A jornada depende criticamente da Fernanda — se ela sair da loja, o produto morre para aquele cliente | Média | Garantir que Roberto saiba fazer upload sozinho. Ter opção "encaminhar e-mail automático" (fornecedor manda XML direto para o Copiloto). |
| Notificações de WhatsApp podem ser silenciadas ou perdidas no volume de mensagens | Média | WhatsApp Business API com template aprovado. Horário fixo (segunda 8h). Se não abrir por 2 semanas, founder liga — toque humano reengaja. |
| Se o link mágico falhar no celular antigo do Roberto (Android 8, Chrome desatualizado) | Média | Testar em dispositivos reais de baixo desempenho antes do beta. Fallback: SMS com código de 6 dígitos. |
| Dona Célia pode se sentir ameaçada ao receber relatório de máquina em vez de documentos brutos | Média | Cabeçalho no PDF: "Este relatório foi gerado como apoio à análise do contador responsável. Não substitui a validação profissional." |

---

## Etapa 8 — Funcionalidades do Produto

### Objetivo da etapa

Listar exaustivamente as funcionalidades visíveis ao usuário que compõem o FiscoPilot — do MVP (90 dias) à expansão pós-MVP (12 meses) — com descrição, prioridade, critério de aceitação, persona associada, fase de implementação e esforço estimado. Esta lista é a fonte de verdade para construção do produto.

### Premissas adotadas

| # | Premissa | Justificativa |
|---|---|---|
| P1 | "Funcionalidade" = algo que o usuário vê ou sente, não componente interno de arquitetura | Ex.: "Upload de XMLs" é funcionalidade; "fila de processamento assíncrono" é implementação (Etapa 17) |
| P2 | MVP: P0 = sem isso, a venda não fecha. P1 = sem isso, a retenção quebra em 30 dias. P2 = sem isso, o usuário não reclama no primeiro mês | Critério pragmático de priorização para MVP |
| P3 | Pós-MVP: PA = Fase A (retenção/atrio), PB = Fase B (monitoramento), PC = Fase C (inteligência), PD = Fase D (plataforma) | Priorização por fase de expansão (Etapa 35) |
| P4 | Esforço em dias de desenvolvimento de 1 pessoa sênior (8h/dia útil) | Para time de 2 devs, esforço total é aproximadamente metade dos dias corridos |
| P5 | Cada funcionalidade tem exatamente 1 critério de aceitação principal — binário, testável, sem ambiguidade | Evita funcionalidades que "nunca ficam prontas" |
| P6 | Ordem de construção segue a cadeia de dependência: sem ingestão, nada funciona; sem regras, sem valor; sem dashboard, usuário não vê nada | Construir na ordem da jornada do usuário |
| P7 | Funcionalidades pós-MVP (F36-F65) dependem do MVP funcional e em produção com ao menos 3-5 clientes | Validação de valor precede expansão |

### Decisões recomendadas

| Decisão | Conteúdo | Status |
|---|---|---|
| D1 | MVP: 16 funcionalidades P0, 7 P1, 4 P2 = 27 funcionalidades. Pós-MVP: 30 funcionalidades adicionais (F36-F65) = 57 funcionalidades totais | Decisão de escopo |
| D2 | 7 módulos: M1 (Ingestão), M2 (Processamento), M3 (Dashboard), M4 (Comunicação), M5 (Administração), M6 (Portal do Contador), M7 (Inteligência Fiscal) | Decisão de arquitetura |
| D3 | MVP: M1 → M2 → M3 → M4 → M5. Pós-MVP: M6 e M7 construídos nas Fases B-C | Decisão de execução |
| D4 | Nenhuma funcionalidade de IA generativa é P0 — o diagnóstico é 100% determinístico; IA só melhora redação das explicações | Decisão técnica |
| D5 | Funcionalidades que dependem de API externa (Sefaz, Receita Federal, ERPs) são PA-PD; o MVP funciona totalmente offline de serviços públicos | Decisão de arquitetura |

---

### MÓDULO M1 — INGESTÃO

| ID | Funcionalidade | Descrição | Prioridade | Esforço (dias) | Quem usa | Etapa da jornada | Critério de aceitação |
|---|---|---|---|---|---|---|---|
| **F01** | Upload de XML via interface web (ZIP) | Fernanda seleciona um arquivo ZIP contendo múltiplos XMLs de NF-e, clica em "Enviar", e vê progresso do upload | P0 | 4 | Fernanda | Onboarding (E2) e Uso recorrente (E4) | Arquivo ZIP com 100 XMLs de 50KB cada é enviado, processado, e barra de progresso chega a 100% em <10s |
| **F02** | Upload de XML via área de arrastar (drag & drop) | Fernanda arrasta pasta com XMLs diretamente para a área demarcada no navegador | P0 | 2 | Fernanda | Onboarding (E2) e Uso recorrente (E4) | Usuário arrasta 20 arquivos XML soltos; sistema reconhece, agrupa e processa sem erro |
| **F03** | Ingestão via e-mail dedicado | Fernanda encaminha e-mail do fornecedor (com XML anexo) para notas@copilotofiscal.com; sistema extrai anexo XML e processa | P0 | 5 | Fernanda | Uso recorrente (E4) | E-mail com 3 XMLs anexados é enviado; em <60s os documentos aparecem no dashboard da organização correta |
| **F04** | Validação de arquivo (tipo e formato) | Sistema rejeita silenciosamente arquivos que não são XML ou XML de NF-e inválido; não quebra o processamento do lote | P0 | 2 | Sistema | Onboarding (E2) e Uso recorrente (E4) | Arquivo PDF enviado no meio de ZIP com XMLs é ignorado; XMLs válidos são processados normalmente |
| **F05** | Indicador de processamento (loading + progresso) | Durante o processamento, Fernanda vê barra de progresso real | P1 | 2 | Fernanda | Onboarding (E2) e Uso recorrente (E4) | Barra atualiza a cada nota processada; se >10s, mostra mensagem "isso pode levar até 1 minuto" |
| **F06** | Histórico de uploads | Fernanda vê lista de uploads anteriores com data, quantidade de notas, status | P2 | 3 | Fernanda | Uso recorrente (E4) | Último upload no topo; clicando, vê resultado daquele lote específico |

### MÓDULO M2 — PROCESSAMENTO

| ID | Funcionalidade | Descrição | Prioridade | Esforço (dias) | Quem usa | Critério de aceitação |
|---|---|---|---|---|---|---|
| **F07** | Parser de NF-e (extração de campos) | Extrai do XML: chave, CNPJ emitente, nome emitente, CFOP, NCM, CST PIS/COFINS, ICMS, valor total, valor itens, data, UF | P0 | 8 | Sistema | 100% dos campos do Anexo I do Manual de Padrões Técnicos da NF-e (layout 4.00) extraídos corretamente |
| **F08** | Motor de regras — CFOP inconsistente (R1) | Compara CFOP com o esperado para entrada em Simples Nacional (grupo 1xxx dentro do estado, 2xxx interestadual) | P0 | 3 | Sistema | NF-e com CFOP 6102 (saída) para compra gera alerta com score >= 70 |
| **F09** | Motor de regras — Alíquota ICMS (R2) | Compara alíquota de ICMS com tabela interestadual por UF de origem/destino | P0 | 2 | Sistema | NF-e SP→MG com alíquota 18% (deveria ser 12%) gera alerta com score >= 60 |
| **F10** | Motor de regras — NCM do setor (R3) | Verifica se NCM pertence a capítulo típico de material de construção (68, 69, 70, 72, 73, 39, 40) | P0 | 2 | Sistema | NF-e com NCM 0201 (carne) para loja de material de construção gera alerta score >= 50 |
| **F11** | Motor de regras — CNPJ ativo (R4) | Consulta situação cadastral via API pública da Receita Federal | P1 | 3 | Sistema | CNPJ baixado/suspenso gera alerta score = 100; consulta cacheada 24h |
| **F12** | Motor de regras — Soma dos itens (R5) | Compara valor total com soma dos valores dos itens (tolerância R$ 0,05) | P0 | 1 | Sistema | NF-e total R$ 100 com itens R$ 95 gera alerta score >= 60 |
| **F13** | Motor de regras — CST Simples (R6) | Verifica se CST PIS/COFINS é compatível com Simples Nacional | P0 | 1 | Sistema | NF-e com CST 50 (Lucro Real) para Simples gera alerta score >= 50 |
| **F14** | Motor de regras — Chave de acesso (R7) | Valida dígito verificador da chave NF-e (algoritmo módulo 11) | P0 | 1 | Sistema | Chave inválida gera alerta "NF-e pode ser falsa" com score = 100 |
| **F15** | Motor de regras — ICMS ST indevido (R8) | Verifica se NCM consta na lista de ST do estado destino | P1 | 3 | Sistema | Parafuso (NCM 7318) com ST destacado: alerta. Cimento (NCM 2523) com ST: OK. |
| **F16** | Classificação de risco (score 0-100) | Score final = max(scores das regras violadas); classificação: 0-30 OK, 31-69 ATENÇÃO, 70-100 RISCO ALTO | P0 | 2 | Sistema | Nota que viola R1 (70) e R5 (60) recebe score 70 e classificação RISCO ALTO |

### MÓDULO M3 — DASHBOARD

| ID | Funcionalidade | Descrição | Prioridade | Esforço (dias) | Quem usa | Critério de aceitação |
|---|---|---|---|---|---|---|
| **F17** | Dashboard — visão resumida | Cards: total de notas, OK, ATENÇÃO, RISCO ALTO + 3 inconsistências mais graves | P0 | 5 | Roberto + Fernanda | Dashboard carrega <3s no 4G. Exibe resumo correto para 87 notas. |
| **F18** | Dashboard — lista detalhada de inconsistências | Lista paginada ordenada por score decrescente. Cada linha: fornecedor, valor, tipo de erro, score, status | P0 | 4 | Roberto + Fernanda | Lista mostra 4 inconsistências. Clicar abre detalhe. Ordem: maior risco primeiro. |
| **F19** | Detalhe da inconsistência | Fornecedor, número/valor/data, campo com problema, valor encontrado vs. esperado, score, impacto em R$, sugestão de ação | P0 | 4 | Roberto + Fernanda | Tela explica CFOP divergente com "Você pode pagar ~R$ 412 a mais na DAS" + botão "O que fazer?" |
| **F20** | Explicação em linguagem simples | Paráfrase em português claro (template preenchido). Nenhuma sigla sem explicação. | P0 | 3 | Roberto | Texto não contém "CFOP 6102 divergente" sem explicar o que é CFOP |
| **F21** | Ação sugerida (checklist) | Checklist de passos concretos: "1. Ligue para o fornecedor. 2. Peça carta de correção..." Usuário marca itens. | P0 | 3 | Roberto + Fernanda | Checklist 3-5 passos. Marcar check persiste. |
| **F22** | Gerenciamento de status da inconsistência | Pendente / Em andamento / Resolvida / Ignorada (com motivo obrigatório) | P1 | 2 | Fernanda | Status persiste. Ignorada exige motivo. Aparece no PDF do contador. |
| **F23** | Filtro por período | "Este mês", "mês passado", intervalo personalizado | P1 | 2 | Roberto + Fernanda | Padrão: mês atual. Intervalo funciona com datas arbitrárias. |
| **F24** | Busca por fornecedor ou chave de nota | Campo de busca textual | P2 | 2 | Fernanda | Busca retorna resultados parciais (ex.: "Cimento" acha "CimentoBom") |

### MÓDULO M4 — COMUNICAÇÃO

| ID | Funcionalidade | Descrição | Prioridade | Esforço (dias) | Quem usa | Critério de aceitação |
|---|---|---|---|---|---|---|
| **F25** | Resumo semanal via WhatsApp | Segunda 8h: "23 notas processadas. 1 inconsistência. Toque para ver." Link mágico. | P1 | 5 | Roberto | Mensagem chega pontualmente toda segunda. Dados reais. Link abre dashboard. |
| **F26** | Alerta imediato de risco alto via WhatsApp | Score >= 70: alerta imediato. Não espera resumo semanal. Máximo 1/hora. | P1 | 3 | Roberto | Alerta <2 min após processamento. Anti-spam respeitado. |
| **F27** | Notificação "tudo certo" (silêncio positivo) | Sem inconsistências: "15 notas. Nenhuma inconsistência. Seu fiscal em dia." | P1 | 1 | Roberto | Envia toda segunda mesmo com 0 inconsistências. Tom tranquilizador. |
| **F28** | Exportar relatório do contador (PDF) | PDF com cabeçalho, resumo, lista de inconsistências com status, ações, disclaimer | P0 | 4 | Fernanda | PDF <5s. Contém todas inconsistências do mês com status. Disclaimer no cabeçalho. |
| **F29** | Link mágico de acesso | Link WhatsApp que autentica automaticamente, sem senha, expira em 24h | P0 | 3 | Roberto + Fernanda | Funciona Chrome Android 8+. Abre direto no dashboard. |

### MÓDULO M5 — ADMINISTRAÇÃO

| ID | Funcionalidade | Descrição | Prioridade | Esforço (dias) | Quem usa | Critério de aceitação |
|---|---|---|---|---|---|---|
| **F30** | Criação manual de tenant/organização | Founder cria conta: CNPJ, nome fantasia, WhatsApp Roberto, e-mail Fernanda, regime, UF | P0 | 3 | Founder | Conta criada <2 min. Roberto recebe link mágico no WhatsApp. |
| **F31** | Autenticação por link mágico | Sem senha. Sessão mantida 7 dias via cookie/JWT. | P0 | 4 | Roberto + Fernanda | Sessão persiste 7 dias. Expirou → solicitar novo link. |
| **F32** | Múltiplos usuários por organização | Admin (Roberto) e Operador (Fernanda). Admin vê tudo. Operador: upload, dashboard, pendências, PDF. | P0 | 3 | Roberto + Fernanda | Fernanda não acessa endpoints de admin. Menu de admin não aparece. |
| **F33** | Papéis e permissões simples | Admin: acesso total. Operador: restrito. | P0 | 2 | Sistema | Fernanda → endpoint admin = 403 Forbidden. |
| **F34** | Log de auditoria (eventos do usuário) | Quem fez upload, marcou pendência, exportou PDF. Append-only. Acessível pelo founder. | P2 | 3 | Founder | Log consultável. Registro imutável. |
| **F35** | Log de processamento (eventos do sistema) | XML recebido (hash, chave), regra executada, score, justificativa, data/hora | P2 | 2 | Founder | Rastreabilidade completa de cada inconsistência detectada. |

---

### MÓDULO M1 — INGESTÃO (EXPANSÃO PÓS-MVP)

| ID | Funcionalidade | Descrição | Fase | Esforço (dias) | Quem usa | Critério de aceitação |
|---|---|---|---|---|---|---|
| **F36** | Ingestão por WhatsApp | Fernanda encaminha XML/ZIP recebido no WhatsApp do fornecedor para o número do FiscoPilot; sistema processa automaticamente via webhook | PA | 8 | Fernanda | XML encaminhado via WhatsApp é processado em <60s. Confirmação enviada ao remetente. Histórico visível na interface. |
| **F37** | Download automático de XML via certificado digital | Roberto faz upload do certificado A1 uma vez; sistema baixa NF-e automaticamente da Sefaz diariamente | PB | 15 | Sistema | Certificado A1 criptografado AES-256-GCM. Download diário funcional. Notas baixadas entram no pipeline. Alerta de vencimento 30/15/7 dias. |
| **F38** | Integração com ERPs brasileiros (Bling, Tiny, Omie, Conta Azul) | Conectores OAuth que leem notas fiscais diretamente do ERP do cliente, eliminando upload manual | PD | 20 | Sistema | Ao menos 2 conectores funcionais (Bling + Tiny). OAuth flow completo. Sincronização automática diária. |

---

### MÓDULO M2 — PROCESSAMENTO (EXPANSÃO PÓS-MVP)

| ID | Funcionalidade | Descrição | Fase | Esforço (dias) | Quem usa | Critério de aceitação |
|---|---|---|---|---|---|---|
| **F39** | Verificador de campos CBS/IBS nos XMLs | Detecta presença/ausência de campos da Reforma Tributária (CBS/IBS) nos XMLs quando aplicável | PD | 5 | Sistema | XMLs com campos CBS/IBS são identificados. Alertas gerados quando campos ausentes em notas que deveriam ter. |
| **F40** | Biblioteca de regras por UF e setor (pacotes) | Pacotes de regras empacotáveis: "SP material de construção", "MG material de construção", "restaurantes", "Lucro Presumido", etc. | PD | 15 | Sistema | Ao menos 3 pacotes funcionais. Pacotes ativáveis/desativáveis por organização. Motor carrega pacotes dinamicamente. |
| **F41** | Monitoramento cadastral de fornecedores | Verifica semanalmente: CNPJ ativo, inscrição estadual regular, CNAE compatível, certificado digital vencendo | PB | 10 | Sistema | Verificação semanal automática. Alertas visíveis no dashboard. Alertas críticos disparam notificação WhatsApp. |

---

### MÓDULO M3 — DASHBOARD (EXPANSÃO PÓS-MVP)

| ID | Funcionalidade | Descrição | Fase | Esforço (dias) | Quem usa | Critério de aceitação |
|---|---|---|---|---|---|---|
| **F42** | Painel de economia / risco evitado | Mostra impacto acumulado: inconsistências detectadas, valor em risco, economia potencial. Demonstra ROI continuamente. | PA | 5 | Roberto | Painel exibe valores corretos para mês/trimestre/ano. Gráfico de barras com últimos 6 meses. Atualiza em tempo real. |
| **F43** | Score de fornecedores | Dashboard com score por fornecedor baseado em 90 dias: erros, valor em risco, CNPJ irregular, recorrência de problemas | PC | 8 | Roberto | View materializada atualizada diariamente. Ranking por categoria (Confiável, Atenção, Risco). Só ativa após 90 dias de dados. |
| **F44** | Preparação para Reforma Tributária (CBS/IBS) | Score de preparação (0-100%), checklist interativo por categoria, timeline 2026-2033, PDF "sua loja está pronta?" | PD | 15 | Roberto | Score calculado. Checklist interativo. Timeline personalizada. PDF gerado. Alertas CBS/IBS nos XMLs. |
| **F45** | Gestão de pendências como Kanban | Mini-CRM de pendências: responsável, prazo, comentários, anexos, botões "enviar para contador" e "enviar para fornecedor" | PB | 12 | Fernanda + Roberto | Board com 4 colunas. Drag & drop. Comentários persistidos. Anexos uploadados. Atribuição com prazo. |

---

### MÓDULO M4 — COMUNICAÇÃO (EXPANSÃO PÓS-MVP)

| ID | Funcionalidade | Descrição | Fase | Esforço (dias) | Quem usa | Critério de aceitação |
|---|---|---|---|---|---|---|
| **F46** | Mensagem pronta para fornecedor | Sistema gera mensagem contextualizada para fornecedor quando nota tem inconsistência. Botões: copiar, WhatsApp, e-mail. | PA | 5 | Fernanda | Para cada regra R1-R8, mensagem contextual com dados reais. Botões funcionais. Status persistido. |
| **F47** | Notificação "tudo certo" mais inteligente | Quando não há inconsistências, notificação inclui contexto: número de notas, valor total, fornecedores. | PA | 2 | Roberto | Notificações W1 e W5 incluem agregações de valor_total e COUNT(DISTINCT cnpj_emitente). Tom contextual. |
| **F48** | Relatório mensal do dono ("fechamento fiscal") | PDF de 1 página para o dono: notas analisadas, valor processado, inconsistências, fornecedores problemáticos, recomendação | PA | 5 | Roberto | PDF gerado em <5s. Contém todos os dados do mês. Botão "Baixar meu mês fiscal" visível no dashboard. |
| **F49** | Notificações para contador | Sistema notifica contador quando cliente tem inconsistência crítica ou quando exportação mensal está disponível | PC | 3 | Dona Célia | Contador recebe notificação por e-mail/WhatsApp quando há alerta crítico ou exportação disponível. |

---

### MÓDULO M5 — ADMINISTRAÇÃO (EXPANSÃO PÓS-MVP)

| ID | Funcionalidade | Descrição | Fase | Esforço (dias) | Quem usa | Critério de aceitação |
|---|---|---|---|---|---|---|
| **F50** | Checklist de onboarding "raio-x fiscal" | Fluxo guiado em 5 passos: upload → análise → resultados → top 3 riscos → PDF para contador | PA | 5 | Roberto + Fernanda | Wizard de 5 passos funcional. Upload simplificado. Resultados com animação. PDF gerado no passo 5. Sessão persistida. |
| **F51** | Assistente de IA com limites claros | Chat contextual que responde perguntas sobre inconsistências. Guardrails impedem cálculo de imposto ou parecer definitivo. | PC | 10 | Roberto | Assistente responde perguntas contextuais. Guardrails funcionam. Disclaimer em toda resposta. Feedback persistido. |
| **F52** | Gerenciador de pacotes de regras | Interface para ativar/desativar pacotes de regras por organização. Catálogo de pacotes disponíveis. | PD | 5 | Founder | Catálogo visível. Pacotes ativáveis/desativáveis. Motor carrega pacotes ativos dinamicamente. |

---

### MÓDULO M6 — PORTAL DO CONTADOR (NOVO — PÓS-MVP)

| ID | Funcionalidade | Descrição | Fase | Esforço (dias) | Quem usa | Critério de aceitação |
|---|---|---|---|---|---|---|
| **F53** | Login do contador | Auth separado com CPF + senha. Portal dedicado para contadores. | PC | 3 | Dona Célia | Contador faz login com CPF + senha. Sessão persistida. Portal separado do app do lojista. |
| **F54** | Lista de clientes atendidos | Contador vê todos os clientes que o convidaram, com resumo de status fiscal | PC | 3 | Dona Célia | Lista visível com resumo por cliente. Clique abre dashboard do cliente. |
| **F55** | Dashboard do cliente (visão contador) | Contador vê dashboard completo do cliente: notas, inconsistências, pendências | PC | 2 | Dona Célia | Dashboard idêntico ao do lojista, mas read-only. Sem botões de ação (só comentários e validação). |
| **F56** | Comentários por inconsistência | Contador pode comentar em qualquer inconsistência do cliente | PC | 3 | Dona Célia | Comentários persistidos. Visíveis para lojista e contador. Thread de comentários. |
| **F57** | Botão "validado pelo contador" | Contador valida inconsistência com selo verde "Validado pelo contador" | PC | 2 | Dona Célia | Selo visível na inconsistência. Data/hora da validação. Nome do contador. |
| **F58** | Exportação mensal consolidada | Contador gera exportação mensal consolidada de todos os clientes | PC | 5 | Dona Célia | Exportação funcional. PDF consolidado. Botão "Baixar" e "Enviar por e-mail". |
| **F59** | Histórico de ações do contador | Log de comentários, validações e exportações do contador | PC | 2 | Dona Célia | Histórico visível. Filtro por cliente e período. |
| **F60** | Convite de cliente para contador | Lojista convida contador via e-mail/WhatsApp. Contador aceita e vê dashboard do cliente. | PC | 3 | Roberto + Dona Célia | Convite enviado. Contador aceita. Dashboard do cliente visível. Relação persistida. |

---

### MÓDULO M7 — INTELIGÊNCIA FISCAL (NOVO — PÓS-MVP)

| ID | Funcionalidade | Descrição | Fase | Esforço (dias) | Quem usa | Critério de aceitação |
|---|---|---|---|---|---|---|
| **F61** | Assistente de IA contextual | Chat que responde perguntas sobre inconsistências: "Explique em linguagem simples", "O que perguntar ao contador?", "Gere mensagem para fornecedor" | PC | 8 | Roberto | Assistente funcional. Botões de perguntas rápidas. Guardrails impedem parecer fiscal. Disclaimer em toda resposta. |
| **F62** | Score de fornecedores (detalhe) | Página de detalhe por fornecedor: histórico de 90 dias, problemas recorrentes, valor em risco, categoria | PC | 5 | Roberto | Detalhe visível. Histórico de 90 dias. Problemas recorrentes listados. Botão "Ver todas as notas do fornecedor". |
| **F63** | Ranking de fornecedores | Lista ordenada por categoria: "Mais confiáveis", "Mais problemáticos", "Maior valor em risco" | PC | 3 | Roberto | Ranking visível. Filtros por categoria. Clique abre detalhe do fornecedor. |
| **F64** | Simulador da Reforma Tributária | Módulo "Preparação CBS/IBS": score de preparação, checklist, timeline 2026-2033, PDF de preparação | PD | 12 | Roberto | Score calculado (0-100%). Checklist interativo. Timeline personalizada. PDF gerado. |
| **F65** | Alertas de conformidade cadastral | Alertas proativos: certificado vencendo, CNPJ inapto, IE irregular, CNAE incompatível, fornecedor recorrente com problema | PB | 5 | Roberto + Fernanda | Alertas visíveis no dashboard. Badge de contagem. Alertas críticos disparam WhatsApp. |

---

### Funcionalidades Explicitamente Excluídas do Produto

| Funcionalidade excluída | Motivo | Quando entra |
|---|---|---|
| Cadastro self-service | Onboarding guiado pelo founder nos primeiros 10 clientes | Fase 2 (mês 4) — não no escopo atual |
| App nativo iOS/Android | Web app responsivo + PWA cobre 100% das necessidades | Fase 3 (mês 9+) — avaliar após Fase D |
| Gateway de pagamento | Volume <20 clientes; Pix manual funciona | Fase 2 (mês 4) — não no escopo atual |
| Trial automatizado | Controle manual do founder | Fase 2 (mês 4) — não no escopo atual |
| Suporte a NFS-e, CT-e, NFC-e | Cada documento tem schema XML diferente | Fase 2-3 — após consolidação do NF-e |
| Edição de dados da nota pelo usuário | Risco regulatório: falsificação fiscal | **Nunca** |
| Apuração de imposto (cálculo da DAS) | Atribuição legal exclusiva do contador | **Nunca** |
| Envio de obrigações acessórias (SPED, DIRF) | Atribuição exclusiva do contador habilitado | **Nunca** |
| Substituição do contador | Produto complementa, não substitui | **Nunca** |

**Nota:** As seguintes funcionalidades, antes excluídas do MVP, agora fazem parte do roadmap pós-MVP (Etapa 35): download automático de XML via Sefaz (F37), ingestão via WhatsApp (F36), integração com ERP (F38), módulo de contador (F53-F60), IA generativa (F51, F61), dashboard de fornecedores (F43, F62, F63), suporte a Lucro Presumido (F40).

### Ordem de Construção (Sprint Plan)

#### MVP (90 dias — Semanas 1-12)

| Sprint (2 semanas) | Funcionalidades | Marco |
|---|---|---|
| **Sprint 1** (Sem 1-2) | F01, F02, F04, F30, F31, F32 | **M1**: Upload + Auth funcionando |
| **Sprint 2** (Sem 3-4) | F07, F12, F14, F16, F29 | **M2**: Parser + validação básica |
| **Sprint 3** (Sem 5-6) | F08, F09, F10, F13 | **M3**: 5 regras fiscais rodando |
| **Sprint 4** (Sem 7-8) | F17, F18, F19, F20, F21 | **M4 — MVP Interno**: Dashboard completo |
| **Sprint 5** (Sem 9-10) | F03, F05, F22, F28, F33 | **M5 — Beta**: Produto usável em beta |
| **Sprint 6** (Sem 11-12) | F25, F26, F27, P1s/P2s remanescentes, QA | **M6 — Lançamento**: MVP completo |

#### Pós-MVP — Fase A: Retenção e Redução de Atrito (Mês 4-5, ~30 dias)

| Sprint (2 semanas) | Funcionalidades | Marco |
|---|---|---|
| **Sprint 7** (Sem 13-14) | F46, F47, F50 | Mensagem fornecedor + tudo certo inteligente + onboarding raio-x |
| **Sprint 8** (Sem 15-16) | F42, F48, F36 | Painel economia + relatório dono + ingestão WhatsApp |

#### Pós-MVP — Fase B: Monitoramento Contínuo (Mês 5-7, ~40 dias)

| Sprint (2 semanas) | Funcionalidades | Marco |
|---|---|---|
| **Sprint 9** (Sem 17-18) | F37 (parte 1), F65 | Download automático XML (certificado + scheduler) + alertas cadastrais |
| **Sprint 10** (Sem 19-20) | F37 (parte 2), F41 | Download automático (Sefaz WS + fila) + monitoramento cadastral |
| **Sprint 11** (Sem 21-22) | F45 | Kanban de pendências completo |

#### Pós-MVP — Fase C: Inteligência e Ecossistema (Mês 7-9, ~35 dias)

| Sprint (2 semanas) | Funcionalidades | Marco |
|---|---|---|
| **Sprint 12** (Sem 23-24) | F53, F54, F55, F60 | Portal do contador (login + lista clientes + dashboard + convite) |
| **Sprint 13** (Sem 25-26) | F56, F57, F58, F59, F49 | Portal do contador (comentários + validação + exportação + histórico) |
| **Sprint 14** (Sem 27-28) | F43, F62, F63, F51, F61 | Score fornecedores + assistente IA |

#### Pós-MVP — Fase D: Plataforma e Escala (Mês 9-12, ~50 dias)

| Sprint (2 semanas) | Funcionalidades | Marco |
|---|---|---|
| **Sprint 15** (Sem 29-30) | F39, F64, F44 | Verificador CBS/IBS + simulador Reforma Tributária |
| **Sprint 16** (Sem 31-32) | F38 (parte 1), F40 (parte 1) | Integração ERP (Bling + Tiny) + biblioteca de regras (base) |
| **Sprint 17** (Sem 33-34) | F38 (parte 2), F40 (parte 2) | Integração ERP (Omie + Conta Azul) + pacotes setoriais |
| **Sprint 18** (Sem 35-36) | F52, QA geral, otimizações | Gerenciador de pacotes + QA + lançamento Fase D |

### Riscos e pontos de atenção

#### Riscos do MVP (Sprints 1-6)

| Risco | Severidade | Mitigação |
|---|---|---|
| Sprint 2 (parser NF-e) pode estourar esforço — XML tem dezenas de namespaces e variações por UF | Alta | Usar biblioteca open source brasileira (nfe-io, python-nfe, BR-NFe). Alocar 2 dias de buffer. |
| Sprint 5 (WhatsApp Business API) pode ter atraso de aprovação do Meta | Média | Iniciar cadastro na Semana 1. Fallback: SMS ou PWA push notification. |
| Funcionalidades P1 do M4 (WhatsApp) impactam retenção mas estão no Sprint 6 | Média | Se Sprint 5 atrasar, cortar F03/F05 para liberar dias para WhatsApp. |
| 16 funcionalidades P0 pode ser alto para 90 dias | Média | 6 P0 são regras fiscais simples (7 dias total). Esforço concentrado no parser (8d) e dashboard (16d). |

#### Riscos da Fase A — Retenção (Sprints 7-8)

| Risco | Severidade | Mitigação |
|---|---|---|
| WhatsApp Business API pode rejeitar webhook de ingestão de documentos (F36) | Média | Testar com conta de teste da Meta antes de implementar. Fallback: e-mail para notas@copilotofiscal.com |
| Painel de economia (F42) pode superestimar impacto financeiro se `estimated_impact` estiver errado | Média | Sempre usar "~" (aproximado). Disclaimer: "Estimativa conservadora. Confirme com seu contador." |
| Templates de mensagem (F46) podem soar robóticos ou formais demais para WhatsApp | Média | Testar com 5 donos de loja reais. Ajustar tom para linguagem coloquial brasileira |

#### Riscos da Fase B — Monitoramento (Sprints 9-11)

| Risco | Severidade | Mitigação |
|---|---|---|
| Webservices da Sefaz (NFeConsultaDest) têm histórico de instabilidade e downtime (F37) | Alta | Retry com backoff exponencial. Fila de downloads (pg-boss). Alerta founder se API falhar >3x |
| Armazenar certificado digital cria responsabilidade legal e risco de segurança (F37) | Alta | Criptografia AES-256-GCM. Certificado NUNCA em logs. Pen-test antes de lançar. Termo de responsabilidade |
| Kanban (F45) pode adicionar complexidade desnecessária se usuário não adotar | Média | Lançar como feature opcional. Dashboard simples continua sendo a tela principal |

#### Riscos da Fase C — Inteligência (Sprints 12-14)

| Risco | Severidade | Mitigação |
|---|---|---|
| Contador pode sentir que o portal (F53-F60) é "fiscalização do trabalho dele" | Alta | Posicionar como "ferramenta que facilita seu trabalho". Selo "Validado pelo contador" dá autoridade |
| IA (F51, F61) pode alucinar e dar orientação fiscal errada | Alta | Guardrails rígidos no prompt. Output validado antes de exibir. Fallback para template se IA falhar |
| Score de fornecedores (F43) pode gerar conflitos entre lojista e fornecedor | Média | Score é privado (só o lojista vê). Nunca enviar score para fornecedor |

#### Riscos da Fase D — Plataforma (Sprints 15-18)

| Risco | Severidade | Mitigação |
|---|---|---|
| Reforma Tributária (F64) pode ter regulamentação incompleta ou mudar | Alta | Acompanhar publicações da Receita Federal. Checklist genérico + alertas específicos quando campos CBS/IBS disponíveis |
| APIs de ERPs (F38) podem mudar sem aviso ou ter rate limits restritivos | Média | Versionamento de conectores. Testes de integração contínuos. Fallback para upload manual |
| Biblioteca de regras (F40) pode gerar inconsistência entre pacotes | Média | Pacote base (R1-R8) sempre ativo. Pacotes setoriais adicionam regras, não substituem. Testes cruzados |
| Esforço total da Fase D (~50 dias) pode exceder capacidade do time | Média | Priorizar F38 (ERPs) — maior impacto comercial. F64 e F40 podem ser adiadas |

---

## Etapa 9 — Requisitos Funcionais

### Objetivo da etapa

Especificar cada comportamento do sistema no formato "O sistema DEVE [ação] [condição] [resultado]", eliminando ambiguidade e gerando uma especificação pronta para desenvolvimento e QA. Cada requisito é rastreável a uma funcionalidade da Etapa 8.

### Premissas adotadas

| # | Premissa | Justificativa |
|---|---|---|
| P1 | "DEVE" = comportamento obrigatório cuja ausência quebra o MVP. "NÃO DEVE" = comportamento proibido cuja presença gera risco regulatório ou de segurança | RFC 2119 adaptado ao contexto |
| P2 | Todo requisito funcional é testável — é possível escrever um teste automatizado ou manual que verifique se o requisito foi atendido | Sem testabilidade, o requisito é inútil para QA |
| P3 | Requisitos de usuário (RFU) descrevem o que o usuário vê/faz. Requisitos de sistema (RFS) descrevem processamento interno | Separação útil para front-end vs back-end |
| P4 | Cada requisito referencia exatamente 1 funcionalidade da Etapa 8 (código FXX) | Rastreabilidade bidirecional |

### Decisões recomendadas

| Decisão | Conteúdo | Status |
|---|---|---|
| D1 | 143 requisitos funcionais: 55 de usuário (RFU), 76 de sistema (RFS), 12 de contorno (RFC) | Decisão de escopo |
| D2 | Cada requisito DEVE ser rastreável a uma funcionalidade FXX e a uma fase (MVP ou A-D) | Decisão de qualidade |
| D3 | Requisitos são ordem de implementação, não ordem de numeração — a numeração segue o agrupamento por módulo | Decisão de organização |
| D4 | Requisitos pós-MVP (RFU-015+, RFS-032+) dependem do MVP funcional e em produção | Decisão de execução |

---

### MÓDULO M1 — INGESTÃO

#### Requisitos de Usuário

| ID | Requisito | Funcionalidade | Etapa |
|---|---|---|---|
| **RFU-001** | O sistema DEVE permitir que o usuário selecione um arquivo ZIP contendo um ou mais arquivos XML de NF-e, usando um seletor de arquivos nativo do navegador | F01 | E2, E4 |
| **RFU-002** | O sistema DEVE permitir que o usuário arraste um ou mais arquivos XML diretamente para uma área demarcada na interface, sem uso de seletor de arquivos | F02 | E2, E4 |
| **RFU-003** | O sistema DEVE exibir uma barra de progresso real durante o processamento, indicando "X de Y notas processadas" | F05 | E2, E4 |
| **RFU-004** | O sistema DEVE permitir que o usuário visualize uma lista dos últimos 10 uploads realizados, com data, quantidade de arquivos e status (processado / com erro / processando) | F06 | E4 |

#### Requisitos de Sistema

| ID | Requisito | Funcionalidade | Etapa |
|---|---|---|---|
| **RFS-001** | O sistema DEVE processar um arquivo ZIP contendo até 200 XMLs de NF-e em até 60 segundos | F01 | E2, E4 |
| **RFS-002** | O sistema DEVE aceitar upload de XMLs individuais arrastados (até 100 arquivos por vez), agrupando-os em um único lote de processamento | F02 | E2, E4 |
| **RFS-003** | O sistema DEVE receber e-mails enviados para o endereço dedicado, extrair anexos .xml, e vinculá-los à organização correspondente ao e-mail do remetente | F03 | E4 |
| **RFS-004** | O sistema DEVE validar que cada arquivo recebido é um XML sintaticamente válido e pertence ao namespace da NF-e antes de processar | F04 | E2, E4 |
| **RFS-005** | O sistema DEVE ignorar silenciosamente arquivos que não passarem na validação, registrando o evento em log interno, sem interromper o processamento dos demais arquivos do lote | F04 | E2, E4 |
| **RFS-006** | O sistema DEVE associar cada XML processado a um identificador único de upload, permitindo consulta futura | F06 | E4 |

### MÓDULO M2 — PROCESSAMENTO

#### Requisitos de Sistema

| ID | Requisito | Funcionalidade | Etapa |
|---|---|---|---|
| **RFS-007** | O sistema DEVE extrair do XML da NF-e (layout 4.00) os campos: chave de acesso, CNPJ emitente, nome emitente, CNPJ destinatário, CFOP, NCM de cada item, CST PIS, CST COFINS, valor ICMS, valor total, soma dos itens, data emissão, UF emitente e armazená-los em banco estruturado | F07 | E1, E2, E4 |
| **RFS-008** | O sistema DEVE executar a regra R1 (CFOP inconsistente): se o CFOP pertence ao grupo 5xxx, 6xxx ou 7xxx (operações de saída) sendo o destinatário o CNPJ da organização, gerar inconsistência com score 70 | F08 | E1, E4 |
| **RFS-009** | O sistema DEVE executar a regra R1 estendida: se o CFOP pertence ao grupo 2xxx mas a UF do emitente é igual à UF da organização, gerar inconsistência com score 40 | F08 | E1, E4 |
| **RFS-010** | O sistema DEVE executar a regra R2 (alíquota ICMS): se UF emitente ≠ UF organização, a alíquota DEVE ser 12% ou 7% conforme tabela interestadual; caso contrário, gerar inconsistência com score 60 | F09 | E1, E4 |
| **RFS-011** | O sistema DEVE executar a regra R3 (NCM fora do perfil): se NCM não pertence a capítulo de material de construção (25, 38, 39, 40, 44, 48, 68, 69, 70, 72, 73, 76, 83, 84, 85, 94), gerar inconsistência com score 50 | F10 | E1, E4 |
| **RFS-012** | O sistema DEVE executar a regra R4 (CNPJ inapto): consultar situação cadastral via API pública da RFB; se não for "ATIVA", gerar inconsistência com score 100. Consulta cacheada por 24h. | F11 | E4 |
| **RFS-013** | O sistema DEVE executar a regra R5 (soma itens): comparar soma de vProd com vNF; se diferença absoluta > R$ 0,05, gerar inconsistência com score 60 | F12 | E1, E4 |
| **RFS-014** | O sistema DEVE executar a regra R6 (CST Simples): se CST PIS/COFINS for 50-75, 98, 99 (Lucro Real/Presumido), gerar inconsistência com score 50 | F13 | E1, E4 |
| **RFS-015** | O sistema DEVE executar a regra R7 (chave de acesso): validar dígito verificador da chave de 44 dígitos via algoritmo módulo 11; se inválido, gerar inconsistência com score 100 | F14 | E1, E4 |
| **RFS-016** | O sistema DEVE executar a regra R8 (ICMS ST indevido): se vST > 0 e NCM não consta na lista de ST do estado da organização, gerar inconsistência com score 70 | F15 | E4 |
| **RFS-017** | O sistema DEVE, após executar todas as regras, calcular score final como max(scores). Score <= 30: OK. 31-69: ATENÇÃO. >= 70: RISCO ALTO. | F16 | E1, E2, E4 |

### MÓDULO M3 — DASHBOARD

#### Requisitos de Usuário

| ID | Requisito | Funcionalidade | Etapa |
|---|---|---|---|
| **RFU-005** | O sistema DEVE exibir na tela inicial: total de notas no mês, quantidades por classificação (OK/ATENÇÃO/RISCO ALTO), e cards das 3 inconsistências de maior score | F17 | E1, E3, E4 |
| **RFU-006** | O sistema DEVE exibir lista completa e paginada de inconsistências, ordenada por score decrescente, 20 itens por página | F18 | E3, E4 |
| **RFU-007** | O sistema DEVE exibir, ao clicar em uma inconsistência: dados da nota, descrição do problema em linguagem simples, valor esperado vs. encontrado, score, impacto financeiro estimado, e botão "O que fazer?" com checklist de ações | F19, F20, F21 | E3, E4 |
| **RFU-008** | O sistema DEVE permitir alterar status da inconsistência entre Pendente, Em andamento, Resolvida, Ignorada. Ao selecionar "Ignorada", exigir motivo (mínimo 10 caracteres) | F22 | E3, E4 |
| **RFU-009** | O sistema DEVE permitir filtrar o dashboard por período predefinido (este mês, mês passado) ou intervalo de datas personalizado | F23 | E4 |
| **RFU-010** | O sistema DEVE permitir busca textual por nome do fornecedor (parcial) ou chave de acesso da NF-e (exata a partir de 10 dígitos) | F24 | E4 |

#### Requisitos de Sistema

| ID | Requisito | Funcionalidade | Etapa |
|---|---|---|---|
| **RFS-018** | O sistema DEVE gerar explicação em linguagem simples usando template: "O campo [nome] da nota [número] do fornecedor [nome] está com [valor encontrado]. O esperado pela regra [nome] é [valor esperado]. Impacto estimado: [cálculo]. Sugestão: [ação]." Nenhuma sigla técnica sem explicação entre parênteses na primeira ocorrência. | F20 | E3, E4 |
| **RFS-019** | O sistema DEVE calcular impacto financeiro: (a) CFOP/alíquota: diferença aplicada sobre valor da nota, (b) demais regras: mensagem qualitativa ("risco de multa" / "risco de autuação") | F19 | E3, E4 |
| **RFS-020** | O sistema DEVE carregar o dashboard (visão resumida) em até 3 segundos em conexão 4G, para até 500 notas processadas no mês | F17 | E3, E4 |
| **RFS-021** | O sistema DEVE manter status e checklist de cada inconsistência persistidos em banco após fechamento do navegador | F21, F22 | E3, E4 |

### MÓDULO M4 — COMUNICAÇÃO

#### Requisitos de Usuário

| ID | Requisito | Funcionalidade | Etapa |
|---|---|---|---|
| **RFU-011** | O sistema DEVE permitir exportar relatório PDF com cabeçalho (nome loja, mês), resumo de notas, lista de inconsistências com status, e disclaimer de análise automática preliminar | F28 | E4 |
| **RFU-012** | O sistema DEVE permitir solicitar reenvio do link mágico de acesso via botão na tela de login | F29 | E2, E4 |

#### Requisitos de Sistema

| ID | Requisito | Funcionalidade | Etapa |
|---|---|---|---|
| **RFS-022** | O sistema DEVE enviar, toda segunda-feira às 08:00 (horário de Brasília), mensagem WhatsApp para o Roberto com resumo da semana anterior e link mágico para o dashboard | F25 | E3, E4 |
| **RFS-023** | O sistema DEVE enviar alerta imediato via WhatsApp quando uma nota receber score >= 70, com limite de 1 alerta por hora por destinatário | F26 | E3, E4 |
| **RFS-024** | O sistema DEVE enviar resumo semanal mesmo com 0 inconsistências: "[N] notas processadas. Nenhuma inconsistência. Seu fiscal em dia." | F27 | E4 |
| **RFS-025** | O sistema DEVE gerar PDF do contador em até 5s, com disclaimer obrigatório: "Este relatório foi gerado pelo FiscoPilot como apoio à análise do contador responsável. Trata-se de uma análise automática preliminar que não substitui a validação profissional. Confirme todas as informações com seu contador antes de qualquer ação." | F28 | E4 |
| **RFS-026** | O sistema DEVE gerar links mágicos com expiração de 24h. Ao clicar, usuário autenticado automaticamente e redirecionado ao dashboard. Sessão mantida por 7 dias via cookie seguro HttpOnly. | F29 | E2, E4 |

### MÓDULO M5 — ADMINISTRAÇÃO

#### Requisitos de Usuário

| ID | Requisito | Funcionalidade | Etapa |
|---|---|---|---|
| **RFU-013** | O sistema DEVE permitir que Admin visualize e gerencie usuários da organização (adicionar, remover, alterar papel) | F32 | E2, E4 |
| **RFU-014** | O sistema DEVE exibir menus diferentes conforme papel: Admin vê "Configurações" e "Equipe"; Operador não vê esses menus | F33 | E2, E4 |

#### Requisitos de Sistema

| ID | Requisito | Funcionalidade | Etapa |
|---|---|---|---|
| **RFS-027** | O sistema DEVE permitir que o founder crie uma organização informando: CNPJ (14 dígitos, validado), nome fantasia, WhatsApp do admin, e-mail do operador, regime (Simples Nacional), UF | F30 | E2 |
| **RFS-028** | O sistema DEVE validar que o CNPJ informado possui 14 dígitos e dígitos verificadores consistentes | F30 | E2 |
| **RFS-029** | O sistema DEVE bloquear acesso de Operador a endpoints de admin, retornando HTTP 403 Forbidden | F33 | E4 |
| **RFS-030** | O sistema DEVE registrar em log de auditoria append-only: uploads, alterações de status, exportações de PDF, criação/remoção de usuários | F34 | E4 |
| **RFS-031** | O sistema DEVE registrar em log de processamento: hash SHA-256 do XML, chave de acesso, data/hora, regras executadas, resultado de cada regra, score final. Não acessível ao usuário final. | F35 | E1, E2, E4 |

---

### MÓDULO M1 — INGESTÃO (EXPANSÃO PÓS-MVP)

#### Requisitos de Usuário

| ID | Requisito | Funcionalidade | Fase |
|---|---|---|---|
| **RFU-015** | O sistema DEVE permitir que o usuário encaminhe arquivos XML ou ZIP via WhatsApp para o número dedicado do FiscoPilot, recebendo confirmação de processamento em até 60 segundos | F36 | PA |
| **RFU-016** | O sistema DEVE exibir histórico de ingestões via WhatsApp com data, hora, nome do arquivo, status (processado/com erro) e link para o dashboard | F36 | PA |
| **RFU-017** | O sistema DEVE permitir upload de certificado digital A1 (arquivo .pfx ou .p12) com senha, exibindo CNPJ do titular, data de validade e status de conexão com a Sefaz | F37 | PB |
| **RFU-018** | O sistema DEVE exibir alertas visuais de vencimento do certificado digital: verde (>30 dias), amarelo (7-30 dias), vermelho (<7 dias ou vencido) | F37 | PB |

#### Requisitos de Sistema

| ID | Requisito | Funcionalidade | Fase |
|---|---|---|---|
| **RFS-032** | O sistema DEVE receber webhooks da WhatsApp Business API, validar assinatura HMAC-SHA256, extrair mídia (XML/ZIP) e processar via pipeline de ingestão existente | F36 | PA |
| **RFS-033** | O sistema DEVE associar automaticamente mensagens WhatsApp a organizações via número de telefone do remetente (campo `whatsapp` da tabela `users`) | F36 | PA |
| **RFS-034** | O sistema DEVE criptografar certificados digitais A1 com AES-256-GCM antes de armazenar no banco, usando chave derivada de variável de ambiente `CERTIFICATE_ENCRYPTION_KEY` | F37 | PB |
| **RFS-035** | O sistema DEVE executar job diário (02:00 BRT) que autentica na Sefaz via certificado A1, consulta NF-e emitidas contra o CNPJ da organização nas últimas 24h, baixa XMLs e processa via pipeline | F37 | PB |
| **RFS-036** | O sistema DEVE implementar fila de downloads (pg-boss) com retry exponencial (1min, 5min, 15min, 1h) e máximo 3 tentativas por sessão de download | F37 | PB |
| **RFS-037** | O sistema DEVE integrar com APIs OAuth2 de ERPs brasileiros (Bling, Tiny, Omie, Conta Azul), armazenando tokens criptografados e renovando automaticamente via refresh_token | F38 | PD |

---

### MÓDULO M2 — PROCESSAMENTO (EXPANSÃO PÓS-MVP)

#### Requisitos de Sistema

| ID | Requisito | Funcionalidade | Fase |
|---|---|---|---|
| **RFS-038** | O sistema DEVE detectar presença de campos CBS/IBS nos XMLs de NF-e quando aplicável (notas emitidas a partir de 2026 com regime tributário CBS/IBS) | F39 | PD |
| **RFS-039** | O sistema DEVE gerar alerta de conformidade quando XML deveria conter campos CBS/IBS (baseado em data de emissão e regime) mas estes estão ausentes | F39 | PD |
| **RFS-040** | O sistema DEVE carregar pacotes de regras dinamicamente baseado em `organization_rule_packs` ativos, executando regras do pacote base (R1-R8) + regras dos pacotes setoriais habilitados | F40 | PD |
| **RFS-041** | O sistema DEVE executar job semanal (domingo 03:00 BRT) que consulta API da Receita Federal para verificar situação cadastral (CNPJ ativo, IE regular, CNAE compatível) de todos os fornecedores dos últimos 90 dias | F41 | PB |
| **RFS-042** | O sistema DEVE gerar alerta cadastral crítico (score 100) quando fornecedor tem CNPJ inapto/suspenso/baixado, e alerta de atenção (score 50) para IE irregular ou CNAE incompatível | F41 | PB |

---

### MÓDULO M3 — DASHBOARD (EXPANSÃO PÓS-MVP)

#### Requisitos de Usuário

| ID | Requisito | Funcionalidade | Fase |
|---|---|---|---|
| **RFU-019** | O sistema DEVE exibir painel "Riscos Evitados" com: total de inconsistências detectadas no mês/trimestre/ano, valor em risco (soma de `estimated_impact`), taxa de resolução (%) | F42 | PA |
| **RFU-020** | O sistema DEVE exibir gráfico de barras com histórico de riscos evitados dos últimos 6 meses, permitindo comparação mensal | F42 | PA |
| **RFU-021** | O sistema DEVE exibir ranking de fornecedores por categoria: "Mais confiáveis" (0 inconsistências), "Atenção" (1-2 inconsistências), "Risco" (3+ inconsistências ou score >= 70) | F43 | PC |
| **RFU-022** | O sistema DEVE exibir página de detalhe do fornecedor com: total de notas em 90 dias, inconsistências por tipo, valor em risco, problemas recorrentes, botão "Ver todas as notas" | F43 | PC |
| **RFU-023** | O sistema DEVE exibir score de preparação para Reforma Tributária (0-100%) baseado em checklist interativo com categorias: Cadastro, Sistemas, Processos, Tributação | F44 | PD |
| **RFU-024** | O sistema DEVE exibir timeline visual 2026-2033 com marcos da Reforma Tributária (CBS, IBS, transição) personalizados para o regime da organização | F44 | PD |
| **RFU-025** | O sistema DEVE exibir board Kanban com 4 colunas (Pendente, Em andamento, Resolvida, Ignorada) e permitir drag & drop de inconsistências entre colunas | F45 | PB |
| **RFU-026** | O sistema DEVE permitir adicionar comentários, anexos (PDF/imagem até 10MB), atribuição de responsável e prazo em cada inconsistência via Kanban | F45 | PB |

#### Requisitos de Sistema

| ID | Requisito | Funcionalidade | Fase |
|---|---|---|---|
| **RFS-043** | O sistema DEVE calcular `risco_evitado = SUM(estimated_impact) WHERE status = 'RESOLVIDA'` e `risco_detectado = SUM(estimated_impact) WHERE classification = 'RISCO_ALTO'` para período especificado | F42 | PA |
| **RFS-044** | O sistema DEVE atualizar view materializada `supplier_scores` diariamente via cron (04:00 BRT) com dados dos últimos 90 dias | F43 | PC |
| **RFS-045** | O sistema DEVE classificar fornecedores em 3 categorias: CONFIÁVEL (0 inconsistências), ATENCAO (taxa de erro <= 20%), RISCO (taxa de erro > 20% ou inconsistências de score >= 70) | F43 | PC |
| **RFS-046** | O sistema DEVE calcular score de preparação CBS/IBS baseado em: (a) campos CBS/IBS presentes nos XMLs, (b) itens do checklist marcados como concluídos, (c) alertas de conformidade resolvidos | F44 | PD |
| **RFS-047** | O sistema DEVE persistir estado do Kanban (coluna, responsável, prazo, comentários, anexos) em tabelas `inconsistency_assignments`, `inconsistency_comments`, `inconsistency_attachments` | F45 | PB |
| **RFS-048** | O sistema DEVE validar tamanho máximo de anexos (10MB) e tipos permitidos (PDF, PNG, JPG) antes de upload, rejeitando arquivos inválidos com mensagem de erro clara | F45 | PB |

---

### MÓDULO M4 — COMUNICAÇÃO (EXPANSÃO PÓS-MVP)

#### Requisitos de Usuário

| ID | Requisito | Funcionalidade | Fase |
|---|---|---|---|
| **RFU-027** | O sistema DEVE gerar mensagem contextualizada para fornecedor quando inconsistência é detectada, com botões: "Copiar", "Enviar por WhatsApp", "Enviar por e-mail" | F46 | PA |
| **RFU-028** | O sistema DEVE exibir preview da mensagem antes de enviar, permitindo edição manual do texto | F46 | PA |
| **RFU-029** | O sistema DEVE incluir contexto rico em notificações "tudo certo": número de notas processadas, valor total em compras, quantidade de fornecedores distintos | F47 | PA |
| **RFU-030** | O sistema DEVE permitir download de relatório mensal do dono (PDF 1 página) com: notas analisadas, valor processado, inconsistências, fornecedores problemáticos, recomendação | F48 | PA |
| **RFU-031** | O sistema DEVE exibir botão "Baixar meu mês fiscal" no dashboard, visível para usuários ADMIN | F48 | PA |
| **RFU-032** | O sistema DEVE notificar contador via e-mail/WhatsApp quando cliente tem inconsistência crítica (score >= 70) ou quando exportação mensal está disponível | F49 | PC |

#### Requisitos de Sistema

| ID | Requisito | Funcionalidade | Fase |
|---|---|---|---|
| **RFS-049** | O sistema DEVE gerar mensagem para fornecedor usando templates por regra (R1-R8) com placeholders: `{fornecedor}`, `{numero}`, `{cfop_encontrado}`, `{cfop_esperado}`, `{impacto}` | F46 | PA |
| **RFS-050** | O sistema DEVE persistir status de mensagens enviadas (GENERATED, COPIED, SENT_WHATSAPP, SENT_EMAIL, DELIVERED, READ) em tabela `supplier_messages` | F46 | PA |
| **RFS-051** | O sistema DEVE calcular agregações para notificações "tudo certo": `COUNT(nfe_documents)`, `SUM(valor_total)`, `COUNT(DISTINCT cnpj_emitente)` para período da semana | F47 | PA |
| **RFS-052** | O sistema DEVE gerar PDF do relatório mensal do dono em até 5 segundos usando pdfkit, incluindo gráficos de barras (notas por semana, inconsistências por tipo) | F48 | PA |
| **RFS-053** | O sistema DEVE incluir disclaimer no rodapé do relatório do dono: "Este relatório é uma análise automática preliminar. Confirme com seu contador antes de tomar decisões fiscais." | F48 | PA |
| **RFS-054** | O sistema DEVE enviar notificação para contador quando: (a) inconsistência com score >= 70 detectada, (b) exportação mensal gerada, (c) lojista convida contador para portal | F49 | PC |

---

### MÓDULO M5 — ADMINISTRAÇÃO (EXPANSÃO PÓS-MVP)

#### Requisitos de Usuário

| ID | Requisito | Funcionalidade | Fase |
|---|---|---|---|
| **RFU-033** | O sistema DEVE exibir wizard de onboarding em 5 passos: (1) upload XMLs, (2) processamento, (3) resultados, (4) top 3 riscos, (5) PDF para contador | F50 | PA |
| **RFU-034** | O sistema DEVE permitir pular wizard de onboarding, mas exibir botão "Retomar onboarding" no dashboard até conclusão | F50 | PA |
| **RFU-035** | O sistema DEVE exibir botão "Perguntar à IA" em páginas de inconsistência, abrindo chat contextual com botões de perguntas rápidas | F51 | PC |
| **RFU-036** | O sistema DEVE exibir disclaimer em toda resposta da IA: "Esta é uma orientação preliminar. Confirme com seu contador antes de agir." | F51 | PC |
| **RFU-037** | O sistema DEVE exibir catálogo de pacotes de regras disponíveis com descrição, setor, UF, regime, e botão "Ativar/Desativar" | F52 | PD |

#### Requisitos de Sistema

| ID | Requisito | Funcionalidade | Fase |
|---|---|---|---|
| **RFS-055** | O sistema DEVE persistir estado do wizard de onboarding em tabela `onboarding_sessions`, permitindo retomar de onde parou | F50 | PA |
| **RFS-056** | O sistema DEVE gerar PDF automaticamente no passo 5 do wizard usando dados do primeiro upload (batch_id armazenado em `onboarding_sessions`) | F50 | PA |
| **RFS-057** | O sistema DEVE enviar perguntas contextuais para OpenRouter API com system prompt que inclui guardrails: (a) nunca calcular imposto, (b) nunca dar parecer definitivo, (c) sempre recomendar contador | F51 | PC |
| **RFS-058** | O sistema DEVE validar output da IA antes de exibir: (a) não contém cálculo de imposto, (b) não contém parecer definitivo, (c) contém disclaimer. Se inválido, retornar fallback template. | F51 | PC |
| **RFS-059** | O sistema DEVE carregar pacotes de regras de tabela `rule_packs` onde `is_active = true` e habilitados para organização via `organization_rule_packs` | F52 | PD |

---

### MÓDULO M6 — PORTAL DO CONTADOR (NOVO — PÓS-MVP)

#### Requisitos de Usuário

| ID | Requisito | Funcionalidade | Fase |
|---|---|---|---|
| **RFU-038** | O sistema DEVE permitir login de contador via CPF + senha em portal separado (`/accountant/login`) | F53 | PC |
| **RFU-039** | O sistema DEVE permitir registro de contador com: nome, CPF, e-mail, senha, CRC (opcional), WhatsApp (opcional) | F53 | PC |
| **RFU-040** | O sistema DEVE exibir lista de clientes atendidos pelo contador com: nome da loja, CNPJ, total de notas no mês, inconsistências pendentes, última atividade | F54 | PC |
| **RFU-041** | O sistema DEVE permitir buscar clientes por nome ou CNPJ na lista do contador | F54 | PC |
| **RFU-042** | O sistema DEVE exibir dashboard completo do cliente (idêntico ao do lojista) em modo read-only para contador | F55 | PC |
| **RFU-043** | O sistema DEVE permitir que contador adicione comentários em qualquer inconsistência do cliente, visíveis para lojista e contador | F56 | PC |
| **RFU-044** | O sistema DEVE exibir thread de comentários por inconsistência com autor (contador/lojista/sistema), data/hora e texto | F56 | PC |
| **RFU-045** | O sistema DEVE permitir que contador valide inconsistência com botão "Validado pelo contador", exibindo selo verde + data/hora + nome do contador | F57 | PC |
| **RFU-046** | O sistema DEVE permitir que contador gere exportação mensal consolidada de todos os clientes em PDF único | F58 | PC |
| **RFU-047** | O sistema DEVE exibir histórico de ações do contador: comentários, validações, exportações com filtro por cliente e período | F59 | PC |
| **RFU-048** | O sistema DEVE permitir que lojista convide contador via e-mail/WhatsApp, exibindo campo "Convidar contador" no perfil da organização | F60 | PC |

#### Requisitos de Sistema

| ID | Requisito | Funcionalidade | Fase |
|---|---|---|---|
| **RFS-060** | O sistema DEVE autenticar contador via JWT separado (campo `accountant_id` no payload) com expiração de 7 dias | F53 | PC |
| **RFS-061** | O sistema DEVE validar CPF usando algoritmo de dígitos verificadores antes de criar conta de contador | F53 | PC |
| **RFS-062** | O sistema DEVE retornar lista de clientes via JOIN entre `accountant_clients` (status = 'ACTIVE') e `organizations`, incluindo agregações de `nfe_documents` e `inconsistencies` | F54 | PC |
| **RFS-063** | O sistema DEVE validar que contador só acessa dados de clientes onde `accountant_clients.accountant_id = contador_logado` e `status = 'ACTIVE'` | F55 | PC |
| **RFS-064** | O sistema DEVE persistir comentários em tabela `accountant_comments` com `author_type = 'ACCOUNTANT'` e notificar lojista via WhatsApp | F56 | PC |
| **RFS-065** | O sistema DEVE persistir validação em tabela `accountant_comments` com `is_validation = true` e `validated_at = now()`, atualizando campo `validated_by_accountant` em `inconsistencies` | F57 | PC |
| **RFS-066** | O sistema DEVE gerar PDF consolidado de múltiplos clientes em até 10 segundos, agrupando por cliente e incluindo resumo executivo | F58 | PC |
| **RFS-067** | O sistema DEVE persistir exportações em tabela `accountant_monthly_exports` com status (PENDING, GENERATING, READY, DOWNLOADED) e URL do PDF | F58 | PC |
| **RFS-068** | O sistema DEVE retornar histórico de ações do contador via query em `accountant_comments` e `accountant_monthly_exports` com filtro por `accountant_id`, `organization_id` e período | F59 | PC |
| **RFS-069** | O sistema DEVE enviar convite para contador via e-mail (com link de aceite) e WhatsApp (com mensagem pré-formatada), persistindo em `accountant_clients` com status 'PENDING' | F60 | PC |

---

### MÓDULO M7 — INTELIGÊNCIA FISCAL (NOVO — PÓS-MVP)

#### Requisitos de Usuário

| ID | Requisito | Funcionalidade | Fase |
|---|---|---|---|
| **RFU-049** | O sistema DEVE exibir chat de IA contextual com botões de perguntas rápidas: "Explique em linguagem simples", "O que perguntar ao contador?", "Gere mensagem para fornecedor" | F61 | PC |
| **RFU-050** | O sistema DEVE exibir histórico de conversas com IA, permitindo retomar conversas anteriores por inconsistência | F61 | PC |
| **RFU-051** | O sistema DEVE permitir feedback (thumbs up/down) em respostas da IA para melhorar qualidade | F61 | PC |
| **RFU-052** | O sistema DEVE exibir página de detalhe do fornecedor com: histórico de 90 dias (notas, inconsistências, valores), problemas recorrentes, categoria (Confiável/Atenção/Risco) | F62 | PC |
| **RFU-053** | O sistema DEVE exibir botão "Ver todas as notas do fornecedor" que filtra lista de notas por CNPJ do emitente | F62 | PC |
| **RFU-054** | O sistema DEVE exibir ranking de fornecedores com filtros: "Mais confiáveis", "Mais problemáticos", "Maior valor em risco", ordenável por colunas | F63 | PC |
| **RFU-055** | O sistema DEVE exibir simulador da Reforma Tributária com: score de preparação (0-100%), checklist interativo, timeline 2026-2033, botão "Gerar PDF de preparação" | F64 | PD |

#### Requisitos de Sistema

| ID | Requisito | Funcionalidade | Fase |
|---|---|---|---|
| **RFS-070** | O sistema DEVE enviar contexto da inconsistência (regra, valores, impacto) para IA junto com pergunta do usuário, limitando resposta a 150 palavras | F61 | PC |
| **RFS-071** | O sistema DEVE persistir conversas com IA em tabela `ai_conversations` com: pergunta, resposta, modelo usado, tokens, latência, feedback | F61 | PC |
| **RFS-072** | O sistema DEVE implementar rate limit de 10 perguntas por hora por usuário para evitar abuso da API de IA | F61 | PC |
| **RFS-073** | O sistema DEVE retornar dados de fornecedor via query em `supplier_scores` (view materializada) + JOIN com `nfe_documents` e `inconsistencies` dos últimos 90 dias | F62 | PC |
| **RFS-074** | O sistema DEVE calcular problemas recorrentes do fornecedor via GROUP BY em `inconsistencies.rule_id` com COUNT(*) >= 3 | F62 | PC |
| **RFS-075** | O sistema DEVE retornar ranking de fornecedores via query em `supplier_scores` com ORDER BY dinâmico (categoria, error_rate, total_risk_value) e paginação | F63 | PC |
| **RFS-076** | O sistema DEVE gerar PDF de preparação para Reforma Tributária em até 5 segundos, incluindo: score, checklist com status, timeline personalizada, recomendações | F64 | PD |

---

### REQUISITOS DE CONTORNO (RFC) — O que o sistema NÃO DEVE fazer

| ID | Requisito | Risco mitigado |
|---|---|---|
| **RFC-001** | O sistema NÃO DEVE permitir que qualquer usuário edite campos extraídos de uma NF-e (CFOP, NCM, valores, CNPJ) | Falsificação de documento fiscal (Lei 8.137/90) |
| **RFC-002** | O sistema NÃO DEVE calcular, apurar ou gerar guias de imposto (DAS, ICMS, PIS, COFINS, IPI) | Exercício ilegal da profissão contábil (Decreto-Lei 9.295/46) |
| **RFC-003** | O sistema NÃO DEVE enviar, transmitir ou protocolizar obrigações acessórias em nome do contribuinte (SPED, EFD, DIRF, DCTF, DEFIS) | Representação indevida perante o fisco |
| **RFC-004** | O sistema NÃO DEVE armazenar, solicitar ou processar certificado digital (A1/A3) do cliente | Uso indevido de certificado digital; LGPD |
| **RFC-005** | O sistema NÃO DEVE afirmar ou sugerir que substitui o contador, em qualquer texto de interface, notificação ou relatório | Falsa sensação de segurança |
| **RFC-006** | O sistema NÃO DEVE classificar inconsistência como "erro fiscal comprovado" sem o qualificador "análise automática preliminar" visível na mesma tela | Usuário tomar decisão baseada em falso positivo |
| **RFC-007** | O sistema NÃO DEVE expor dados de uma organização para usuários de outra organização, independentemente de papel | Violação de sigilo fiscal entre clientes; LGPD |
| **RFC-008** | O sistema NÃO DEVE armazenar conteúdo completo do XML da NF-e por mais de 5 anos, devendo permitir exclusão lógica após esse período mediante solicitação do cliente | LGPD (minimização de dados); prazo decadencial CTN (Art. 173) |
| **RFC-009** | O sistema NÃO DEVE expor certificado digital A1 do cliente em logs, responses de API, ou qualquer interface — apenas metadados (CNPJ titular, data de validade, status) | Uso indevido de certificado digital; LGPD |
| **RFC-010** | O sistema NÃO DEVE permitir que assistente de IA calcule imposto devido, gere guias de pagamento, ou emita parecer fiscal definitivo — apenas explicar inconsistências detectadas pelo motor de regras | Exercício ilegal da profissão contábil; responsabilidade civil |
| **RFC-011** | O sistema NÃO DEVE expor score de fornecedores para outros fornecedores ou terceiros — apenas para usuários da organização proprietária dos dados | Conflito comercial; LGPD |
| **RFC-012** | O sistema NÃO DEVE armazenar tokens OAuth de ERPs em texto puro — sempre criptografados com AES-256-GCM usando chave derivada de variável de ambiente | Vazamento de credenciais; segurança |

### Riscos e pontos de atenção

| Risco | Severidade | Mitigação |
|---|---|---|
| Templates de explicação (RFS-018) podem gerar textos robóticos ou confusos com dados atípicos | Média | Testar com 20 inconsistências reais antes do beta; validar com 3 usuários do ICP |
| Lista de capítulos NCM da regra R3 (RFS-011) pode ser incompleta | Média | Tratar R3 como "sugestão de verificação" (score 50, não 100); permitir founder adicionar capítulos à lista branca |
| Impacto financeiro estimado (RFS-019) pode estar errado para casos complexos (ex.: redução de base de cálculo) | Média | Incluir sempre "estimado" e "confirme com seu contador" ao lado do valor em reais |
| Limite de 1 alerta/hora (RFS-023) pode atrasar detecção de segundo problema grave | Baixa | Uploads são manuais (2-3x/semana); cenário improvável no MVP. Revisar Fase 2. |
| Validação de CNPJ (RFS-028) não garante existência real na RFB | Baixa | Aceitável; RFS-012 complementa com consulta de CNPJ ativo |

#### Riscos dos requisitos pós-MVP (Fases A-D)

| Risco | Severidade | Mitigação |
|---|---|---|
| Criptografia de certificados A1 (RFS-034) pode falhar se `CERTIFICATE_ENCRYPTION_KEY` for comprometida | Alta | Rotação de chave a cada 6 meses. Pen-test antes de lançar. Armazenar chave em cofre (AWS Secrets Manager ou similar) |
| Job diário de download da Sefaz (RFS-035) pode falhar silenciosamente se API da Sefaz mudar | Alta | Monitoramento de health check do job. Alerta se 3 dias consecutivos sem download. Fallback para upload manual |
| View materializada `supplier_scores` (RFS-044) pode ficar desatualizada se cron falhar | Média | Refresh manual via botão na interface. Alerta se refresh falhar. Timestamp visível "Atualizado em DD/MM HH:MM" |
| Assistente de IA (RFS-057, RFS-070) pode alucinar e dar orientação fiscal errada mesmo com guardrails | Alta | Validação de output (RFS-058) com regex para detectar cálculo de imposto. Fallback para template se inválido. Disclaimer em toda resposta |
| Integração com ERPs (RFS-037) pode quebrar se API do ERP mudar sem versionamento | Alta | Testes de integração contínuos. Monitoramento de health check por conector. Fallback para upload manual se conector falhar |
| Portal do contador (RFS-060-RFS-069) pode criar superfície de ataque adicional (auth separado) | Média | Rate limit de login (3 tentativas/15min). 2FA na Fase D. Monitoramento de tentativas de login suspeitas |
| Kanban (RFS-047) pode adicionar complexidade desnecessária se usuário não adotar | Média | Lançar como feature opcional. Dashboard simples continua sendo tela principal. Métricas de adoção antes de expandir |
| Pacotes de regras setoriais (RFS-040) podem gerar inconsistência entre pacotes (mesma nota, resultados diferentes) | Média | Pacote base (R1-R8) sempre ativo. Pacotes setoriais adicionam regras, não substituem. Testes cruzados entre pacotes |

---

## Etapa 10 — Requisitos Não Funcionais

### Objetivo da etapa

Especificar os atributos de qualidade do FiscoPilot MVP — desempenho, disponibilidade, segurança, usabilidade, compatibilidade, escalabilidade e manutenibilidade — com metas numéricas testáveis, adequadas a um produto de 90 dias operado por time de 2-3 pessoas e usado por PMEs de baixa maturidade digital.

### Premissas adotadas

| # | Premissa | Justificativa |
|---|---|---|
| P1 | O MVP atenderá no máximo 20 organizações nos primeiros 3 meses pós-lançamento | Ritmo de venda manual pelo founder: ~5-7 clientes/mês |
| P2 | Volume máximo por loja: 200 NF-e/mês, 50KB por XML, pico de 3 uploads por semana | Dados do ICP (Etapa 2); cenário conservador |
| P3 | O produto rodará em cloud (VPS única ou PaaS) com custo mensal < R$ 300 | Restrição de bootstrap; sem investimento externo |
| P4 | 95% dos acessos serão via smartphone Android (Chrome) em conexão 4G ou Wi-Fi de baixa qualidade | Perfil do ICP (Etapa 3): Roberto usa celular Samsung de 2 anos |
| P5 | O time não terá SRE dedicado; o founder é o responsável por infra e incidentes | Manutenibilidade é tão crítica quanto desempenho |
| P6 | Não há exigência de certificação ISO, SOC2 ou PCI-DSS no MVP | O produto não processa pagamentos nem armazena dados de cartão |

### Decisões recomendadas

| Decisão | Conteúdo | Status |
|---|---|---|
| D1 | SLA de disponibilidade: 99% (downtime máximo de 7h/mês), com janela de manutenção domingo 00h-04h | Decisão de MVP |
| D2 | Stack de infraestrutura: VPS Linux 4GB RAM, 2 vCPU, 80GB SSD, PostgreSQL + aplicação no mesmo host | Decisão técnica |
| D3 | Processamento síncrono de XMLs (sem fila); se >200 notas, processar em chunks sequenciais | Decisão técnica |
| D4 | Sem cache (Redis) no MVP; consultas diretas ao PostgreSQL com índices adequados | Decisão técnica |
| D5 | Backup diário automático do banco; retenção de 7 dias; restore manual pelo founder | Decisão de MVP |

### Requisitos de Desempenho

| ID | Requisito | Meta |
|---|---|---|
| **RNF-D01** | O sistema DEVE processar um lote de até 200 XMLs de NF-e em no máximo 60 segundos | ≤60s para 200 XMLs |
| **RNF-D02** | O sistema DEVE carregar a tela inicial do dashboard (visão resumida) em no máximo 3 segundos em conexão 4G | ≤3s |
| **RNF-D03** | O sistema DEVE carregar a lista detalhada de inconsistências (até 50 itens) em no máximo 2s após o dashboard | ≤2s |
| **RNF-D04** | O sistema DEVE gerar o PDF do relatório do contador (até 200 notas) em no máximo 5 segundos | ≤5s |
| **RNF-D05** | O sistema DEVE responder a requisições GET em no máximo 500ms no servidor (p95) | p95 ≤500ms |
| **RNF-D06** | O sistema DEVE enviar notificação WhatsApp de alerta de risco alto em no máximo 2 minutos após processamento | ≤120s |
| **RNF-D07** | O sistema DEVE suportar upload de arquivo ZIP de até 50MB | ≤50MB |

### Requisitos de Disponibilidade

| ID | Requisito | Meta |
|---|---|---|
| **RNF-A01** | O sistema DEVE estar disponível 99% do tempo (downtime máximo de 7h18min/mês) | 99% |
| **RNF-A02** | Manutenções DEVEM ocorrer exclusivamente domingo 00h-04h (horário de Brasília) | Domingo 00h-04h |
| **RNF-A03** | Backup automático completo do banco 1x/dia, retenção mínima de 7 dias | 1 backup/dia, 7 dias |
| **RNF-A04** | Restauração a partir do backup mais recente em no máximo 4 horas | ≤4h |
| **RNF-A05** | Health check HTTP 200 indicando aplicação e banco operacionais | /health → 200 OK |

### Requisitos de Segurança

| ID | Requisito | Meta |
|---|---|---|
| **RNF-S01** | Toda comunicação DEVE usar TLS 1.2 ou superior | TLS ≥1.2 |
| **RNF-S02** | Dados de NF-e DEVEM ser criptografados em repouso com AES-256 | AES-256 |
| **RNF-S03** | Senhas DEVEM usar bcrypt (cost ≥10); tokens de sessão JWT HMAC-SHA256 com expiração 7 dias | bcrypt ≥10, JWT |
| **RNF-S04** | Endpoints autenticados DEVEM retornar 401 (sem token) ou 403 (sem permissão) | 401 / 403 |
| **RNF-S05** | Rate limiting: máximo 20 requisições/minuto por IP para API pública | 20 req/min/IP |
| **RNF-S06** | Sanitização de entradas contra XSS e SQL Injection (parameterized queries) | Zero vulnerabilidades OWASP Top 10 |
| **RNF-S07** | Log de tentativas de acesso negadas; alerta se >10 falhas em 5 min | Alerta de força bruta |
| **RNF-S08** | Dados pessoais NÃO DEVEM aparecer em logs de aplicação em produção | Ausência de dados sensíveis em logs |
| **RNF-S09** | Content Security Policy (CSP) restritiva, permitindo apenas scripts/styles do próprio domínio | CSP header presente |

### Requisitos de Usabilidade

| ID | Requisito | Meta |
|---|---|---|
| **RNF-U01** | Totalmente operável em tela de 360px de largura, sem scroll horizontal | 360px |
| **RNF-U02** | Máximo 2 cliques/toques para chegar à ação principal de qualquer tela | ≤2 cliques |
| **RNF-U03** | Linguagem em português do Brasil, nível ensino médio, sem jargão técnico-fiscal sem explicação | 100% compreensão em teste com ICP |
| **RNF-U04** | Contraste mínimo de 4.5:1 para texto normal (WCAG 2.1 AA pragmático) | Contraste ≥4.5:1 |
| **RNF-U05** | Feedback visual imediato para toda ação do usuário em até 200ms | ≤200ms |
| **RNF-U06** | Funcionamento em orientação retrato (portrait) em smartphone | Retrato |
| **RNF-U07** | Tamanho mínimo de 16px para corpo de texto em mobile | ≥16px |
| **RNF-U08** | Zero interações baseadas em hover, duplo clique, clique direito, atalhos de teclado ou gestos complexos | Apenas toque simples |

### Requisitos de Compatibilidade

| ID | Requisito | Meta |
|---|---|---|
| **RNF-C01** | Funcionamento correto no Chrome ≥90 no Android ≥8 | Chrome ≥90, Android ≥8 |
| **RNF-C02** | Funcionamento correto no Chrome ≥90 em desktop Windows 10 | Chrome ≥90, Windows 10 |
| **RNF-C03** | Funcional (com degradação aceitável) no Safari iOS 15+ | Safari iOS ≥15 |
| **RNF-C04** | Zero dependência de plugins, extensões ou configurações especiais do navegador | HTML5, CSS3, JS vanilla |
| **RNF-C05** | Tamanho total da página inicial ≤500KB compactado (gzip) | ≤500KB gzip |
| **RNF-C06** | JavaScript no primeiro carregamento ≤50KB (first load JS) | ≤50KB |

### Requisitos de Escalabilidade

| ID | Requisito | Meta |
|---|---|---|
| **RNF-E01** | Suporte a 20 organizações e 40 usuários sem degradação de desempenho | 20 orgs, 40 usuários |
| **RNF-E02** | Banco suportar até 50.000 NF-e armazenadas antes de exigir otimização | 50.000 NF-e |
| **RNF-E03** | Capacidade de escala vertical (RAM/CPU) sem alteração de código | Redimensionamento de VPS |
| **RNF-E04** | Migração para fila assíncrona deve exigir refatoração de no máximo 2 módulos | ≤2 módulos |
| **RNF-E05** | Pool de conexões de banco com limite configurável, iniciando em 20 | Pool size = 20 |

### Requisitos de Manutenibilidade

| ID | Requisito | Meta |
|---|---|---|
| **RNF-M01** | Deploy com 1 comando, incluindo migração de banco e restart, em no máximo 5 minutos | 1 comando, ≤5min |
| **RNF-M02** | Configurações de ambiente em arquivos .env, nunca hard-coded | .env por ambiente |
| **RNF-M03** | Cobertura mínima de 70% de testes unitários nos módulos de regras (M2) e parser (M2) | ≥70% |
| **RNF-M04** | Logs em JSON estruturado: timestamp, nível, módulo, mensagem, traceId | JSON estruturado |
| **RNF-M05** | Guia de estilo documentado (ESLint/Ruff) com verificação automatizada em CI | Linter no CI |
| **RNF-M06** | README de setup permitindo novo desenvolvedor rodar localmente em ≤30 min | ≤30min |
| **RNF-M07** | Índices para queries frequentes em tabelas com >1.000 registros | Índices adequados |
| **RNF-M08** | Script de seed com dados de exemplo (3 lojas, 100 NF-e cada, distribuição OK/ATENÇÃO/RISCO) | Seed funcional |

### Riscos e pontos de atenção

| Risco | Severidade | Mitigação |
|---|---|---|
| Processamento síncrono de 200 XMLs em 60s pode ser inviável se parser for ineficiente ou regras envolverem chamadas externas | Média | Usar parser SAX/streaming (não DOM). Cachear consultas externas. Se inviável, meta de 120s. |
| Meta de 500KB de página inicial conflita com dashboard visualmente rico | Baixa | MVP não precisa de dashboard rico — cards simples com ícones Unicode. Zero frameworks pesados. |
| 99% de disponibilidade com VPS única e sem SRE é agressivo | Média | VPS com SSD e snapshot automático. Procedimento documentado de restore. 99% é meta, não garantia contratual. |
| Requisitos de usabilidade podem ser subestimados — diferença entre "funciona" e "Roberto usa sozinho" é grande | Alta | Testar com 3 usuários reais do ICP antes do beta. Se ≥2 de 3 não completarem upload sozinhos, refatorar UX. |

---

## Etapa 11 — Regras de Negócio

### Objetivo da etapa

Especificar em profundidade as 8 regras fiscais do MVP — sua fonte legal, lógica exata de avaliação, tabelas de referência, falsos positivos esperados e comportamento de fallback — para que o motor de regras seja implementado com fidelidade à legislação brasileira e transparência para auditoria.

### Premissas adotadas

| # | Premissa | Justificativa |
|---|---|---|
| P1 | O MVP opera exclusivamente no regime Simples Nacional (LC 123/2006) | Decisão da Etapa 2 e Etapa 6 |
| P2 | As regras avaliam apenas NF-e de entrada (compras), modelo 55, layout 4.00 | Escopo do MVP; notas de saída não são analisadas |
| P3 | Tabelas de referência são carregadas estaticamente no MVP, sem atualização automática em tempo real | Simplificação para MVP; atualização manual pelo founder |
| P4 | Regra determinística = resultado binário baseado em legislação ou tabela oficial | Nenhuma regra usa IA ou inferência estatística |
| P5 | Quando o sistema não puder determinar o resultado, DEVE classificar como NÃO AVALIADO | Melhor não avaliar do que gerar falso positivo |

### Decisões recomendadas

| Decisão | Conteúdo | Status |
|---|---|---|
| D1 | As 7 regras determinísticas são implementadas como funções puras (mesma entrada → mesma saída), sem estado externo | Decisão técnica |
| D2 | A regra RN-03 (NCM) é a única com natureza heurística e recebe score 50, com label "sugestão de verificação" | Decisão de produto |
| D3 | As tabelas de referência são versionadas no repositório como arquivos JSON ou CSV, com data de vigência no nome | Decisão de manutenibilidade |
| D4 | Cada execução de regra registra no log de processamento (RFS-031): regra executada, dados de entrada, resultado, justificativa | Decisão de auditoria |

---

### REGRA RN-01 — CFOP de Entrada Inconsistente com o Regime

| Campo | Conteúdo |
|---|---|
| **Tipo** | Determinística |
| **Gatilho** | Toda NF-e processada |
| **Condições** | (a) Primeiro dígito do CFOP = 5, 6 ou 7 (operações de saída): INCONSISTÊNCIA score 70. (b) Primeiro dígito = 1, 2 ou 3 (entrada): OK. (c) CFOP do grupo 2xxx (interestadual) mas UF emitente = UF organização: INCONSISTÊNCIA score 40. |
| **Score** | 70 (CFOP de saída) / 40 (CFOP interestadual indevido) |
| **Fontes oficiais** | Convênio SINIEF s/nº 1970 (Tabela CFOP). LC 123/2006. Manual NF-e Anexo I. |
| **Tabela de referência** | `cfop_table.json`: CFOPs com primeiro dígito, grupo, tipo (entrada/saída), descrição |
| **Falsos positivos** | Fornecedor do Simples emite com CFOP 5.102 (correto para ele). A regra dispara corretamente — para o destinatário, CFOP de entrada seria diferente. NÃO é falso positivo. |
| **Fallback** | CFOP ausente ou ilegível → NÃO AVALIAR |
| **Exemplo real** | Fornecedor MG emite com CFOP 6102. Destinatário SP deveria receber como 2102. Score 70. |

### REGRA RN-02 — Alíquota de ICMS Interestadual Incorreta

| Campo | Conteúdo |
|---|---|
| **Tipo** | Determinística |
| **Gatilho** | NF-e com UF emitente ≠ UF organização (operação interestadual) |
| **Condições** | (a) Determinar alíquota esperada pela Resolução Senado 22/1989: 12% (Sul/Sudeste origem) ou 7% (N/NE/CO/ES para Sul/Sudeste). (b) Calcular alíquota efetiva = vICMS / vNF × 100. (c) Se diferença > 2pp: INCONSISTÊNCIA score 60. |
| **Score** | 60 |
| **Fontes oficiais** | Resolução Senado Federal 22/1989. EC 87/2015. LC 123/2006 Art. 13 §1º XIII. |
| **Tabela de referência** | `icms_aliquota_interestadual.json`: matriz UF origem × UF destino = alíquota |
| **Falsos positivos** | Operações com redução de base de cálculo; ICMS ST presente (vST > 0); CST ICMS 40/41/50 (isento/suspenso) |
| **Fallback** | Se vST > 0 → NÃO AVALIAR (delegar para RN-08). Se CST ICMS = 40, 41, 50 → NÃO AVALIAR. |
| **Exemplo real** | Fornecedor SP → loja MG com alíquota 18%. Esperado 12%. Diferença 6pp → score 60. |

### REGRA RN-03 — NCM Fora do Perfil de Material de Construção

| Campo | Conteúdo |
|---|---|
| **Tipo** | Heurística (única regra não determinística do MVP) |
| **Gatilho** | Toda NF-e processada |
| **Condições** | Nenhum item da NF-e tem NCM nos capítulos 25, 38, 39, 40, 44, 48, 68, 69, 70, 72, 73, 76, 83, 84, 85, 94 → INCONSISTÊNCIA score 50 |
| **Score** | 50 |
| **Fontes oficiais** | Tabela TIPI (Decreto Federal). Convênio ICMS ST material de construção. |
| **Tabela de referência** | `ncm_capitulos_construcao.json`: lista de capítulos NCM típicos |
| **Falsos positivos** | Produtos de limpeza, EPI, elétricos, ferramentas — Alta probabilidade. Por isso score 50 e mensagem sugestiva. |
| **Fallback** | NCM 0000 ou ausente → NÃO AVALIAR. NCM com <4 dígitos → NÃO AVALIAR. |
| **Exemplo real** | NF-e com NCM 3925 (plástico construção) → OK. NF-e com NCM 9603 (vassouras) → score 50. |

### REGRA RN-04 — CNPJ do Emitente com Situação Irregular

| Campo | Conteúdo |
|---|---|
| **Tipo** | Determinística (depende de API externa) |
| **Gatilho** | Toda NF-e processada (com cache de 24h por CNPJ) |
| **Condições** | Consultar API pública da RFB. Se situação ≠ "ATIVA" → INCONSISTÊNCIA score 100 |
| **Score** | 100 |
| **Fontes oficiais** | IN RFB 1.863/2018 (CNPJ). Portal Nacional Redesim. |
| **Tabela de referência** | Consulta dinâmica via API. Cache local TTL 24h. |
| **Falsos positivos** | API RFB indisponível; CNPJ baixado mas nota emitida antes da baixa |
| **Fallback** | API indisponível (timeout >10s ou 5xx) → usar cache se <7 dias, senão NÃO AVALIAR |
| **Exemplo real** | Fornecedor com CNPJ suspenso por omissão → score 100. |

### REGRA RN-05 — Valor Total Divergente da Soma dos Itens

| Campo | Conteúdo |
|---|---|
| **Tipo** | Determinística |
| **Gatilho** | Toda NF-e processada |
| **Condições** | \|vNF - soma(vProd)\| > R$ 0,05 (ou R$ 0,10 para >20 itens) → INCONSISTÊNCIA score 60 |
| **Score** | 60 |
| **Fontes oficiais** | Manual NF-e Seção 4.4 (Grupo Totais). Convênio SINIEF s/nº 1970. |
| **Tabela de referência** | Nenhuma — validação aritmética interna ao XML |
| **Falsos positivos** | Arredondamento em notas com 30+ itens (mitigado por tolerância ampliada). Desconto não rateado nos itens (inconsistência genuína). |
| **Fallback** | det vazio ou campos ausentes → NÃO AVALIAR |
| **Exemplo real** | 3 itens somam R$ 999 mas vNF = R$ 1.050. Diferença R$ 51 → score 60. |

### REGRA RN-06 — CST PIS/COFINS Incompatível com Simples Nacional

| Campo | Conteúdo |
|---|---|
| **Tipo** | Determinística |
| **Gatilho** | Toda NF-e processada |
| **Condições** | CST PIS/COFINS ∈ {50-75, 98} (típicos Lucro Real/Presumido) → INCONSISTÊNCIA score 50 |
| **Score** | 50 |
| **Fontes oficiais** | IN RFB 1.911/2019 (CST PIS/COFINS). LC 123/2006. Manual NF-e Anexo I. |
| **Tabelas de referência** | `cst_pis_cofins_simples.json` / `cst_pis_cofins_lucro_real.json` |
| **Falsos positivos** | Fornecedor Lucro Presumido emite com CST 50 (correto para ele). A nota está ok, mas o Roberto não toma crédito. Inconsistência informativa. |
| **Fallback** | CST ausente ou = 99 → NÃO AVALIAR |
| **Exemplo real** | Fornecedora tintas (Lucro Presumido) emite com CST 50 para loja Simples → score 50 informativo. |

### REGRA RN-07 — Chave de Acesso da NF-e Inválida

| Campo | Conteúdo |
|---|---|
| **Tipo** | Determinística |
| **Gatilho** | Toda NF-e processada |
| **Condições** | Chave ≠ 44 dígitos OU dígito verificador (módulo 11) inválido → INCONSISTÊNCIA score 100 |
| **Score** | 100 |
| **Fontes oficiais** | Manual NF-e Anexo II (Cálculo Dígito Verificador). Portaria CAT 162/2008. |
| **Tabela de referência** | Nenhuma — algoritmo auto-contido |
| **Falsos positivos** | Praticamente zero |
| **Fallback** | Chave com <44 dígitos → score 100. Chave ausente → NÃO AVALIAR. |
| **Exemplo real** | XML adulterado com valor modificado sem reemissão → chave não confere → score 100. |

### REGRA RN-08 — ICMS ST Destacado Indevidamente

| Campo | Conteúdo |
|---|---|
| **Tipo** | Determinística |
| **Gatilho** | NF-e com vST (ICMS ST) > 0 |
| **Condições** | vST > 0 E NCM do item não consta na lista de ST do estado da organização → INCONSISTÊNCIA score 70 |
| **Score** | 70 |
| **Fontes oficiais** | Convênio ICMS 142/2018. Convênios estaduais de ST. LC 123/2006 Art. 13 §1º XIII "a". |
| **Tabela de referência** | `icms_st_por_uf.json`: UF → lista de NCMs com ST. Atualização manual trimestral. |
| **Falsos positivos** | Convênios/protocolos específicos entre estados para produtos não listados nacionalmente. Score 70 (não 100) + ressalva na mensagem. |
| **Fallback** | UF sem lista ST cadastrada → NÃO AVALIAR. vST = 0 → NÃO AVALIAR. |
| **Exemplo real** | Parafusos (NCM 7318) com ST destacado → não consta na lista de SP → score 70. |

### Tabelas de Referência do MVP

| Tabela | Arquivo | Fonte | Atualização |
|---|---|---|---|
| **CFOP** | `cfop_table.json` | Convênio SINIEF s/nº 1970 | Manual (quando houver mudança) |
| **Alíquotas interestaduais** | `icms_aliquota_interestadual.json` | Res. Senado 22/1989 | Manual (estável) |
| **Capítulos NCM construção** | `ncm_capitulos_construcao.json` | Definição founder base ICP | Manual (ajustável) |
| **CST PIS/COFINS** | `cst_pis_cofins_simples.json` | IN RFB 1.911/2019 | Manual (estável) |
| **ICMS ST por UF** | `icms_st_por_uf.json` | Convênio 142/2018 + legislação estadual | Manual trimestral |

### Riscos e pontos de atenção

| Risco | Severidade | Mitigação |
|---|---|---|
| RN-03 (NCM) tem alta taxa de falso positivo para lojas com itens de limpeza, EPI e ferramentas | Média | Score 50. Mensagem sugestiva. Fase 2: permitir usuário desligar regras específicas. |
| RN-08 (ICMS ST) depende de tabela por UF que muda frequentemente | Alta | MVP: apenas 2 UFs (SP e MG). Atualização manual trimestral. Fase 3: automatizar scraping. |
| RN-02 (alíquota ICMS) complexa para notas com múltiplos CSTs | Média | Avaliar item a item. Reportar primeiro divergente e mencionar "outros itens com mesmo problema". |
| RN-04 (CNPJ inapto) depende de API RFB com histórico de instabilidade | Média | Cache 24h + fallback 7 dias. Alerta founder se API falhar >3x consecutivas. |
| Reforma Tributária pode invalidar regras PIS/COFINS e ICMS a partir de 2027 | Baixa | Regras válidas para MVP em 2026. Preparar versionamento de regras por período de vigência (Fase 2). |

---

## Etapa 12 — Casos de Uso

### Objetivo da etapa

Descrever 10 cenários concretos de interação do usuário com o Copiloto Fiscal MVP, cobrindo os momentos críticos da jornada (demo, onboarding, detecção, ação, exportação, semanas sem erro) e os cenários de falha (upload quebrado, link expirado, sistema sem inconsistências).

### Premissas adotadas

| # | Premissa | Justificativa |
|---|---|---|
| P1 | Casos de uso são narrativas de interação real, não especificações de sistema | Complementam os requisitos funcionais (Etapa 9) com contexto humano |
| P2 | Os atores são as personas definidas na Etapa 3: Roberto (dono), Fernanda (auxiliar), Dona Célia (contadora), Founder | Nomes concretos forçam realismo |
| P3 | Cada caso de uso cobre exatamente 1 objetivo do usuário | Um caso de uso = uma necessidade real da persona |
| P4 | Fluxos alternativos representam falhas ou desvios realistas — não cobrem 100% das exceções técnicas | Foco no que o usuário percebe, não em edge cases de sistema |

### Decisões recomendadas

| Decisão | Conteúdo | Status |
|---|---|---|
| D1 | Os 10 casos de uso cobrem 100% dos momentos críticos da jornada e 3 cenários de falha | Decisão de cobertura |
| D2 | Cada caso de uso é testável manualmente antes de qualquer automação de QA | Decisão de qualidade |
| D3 | Os fluxos alternativos não são exaustivos — são os 2-3 desvios mais prováveis em produção | Decisão de pragmatismo |

---

### UC-01 — Primeiro Raio-X (Demo Comercial)

| Campo | Conteúdo |
|---|---|
| **Nome** | Primeiro raio-x — demonstração comercial ao vivo |
| **Atores** | Founder, Roberto (dono), Fernanda (auxiliar) |
| **Pré-condição** | Founder já teve o primeiro contato com Roberto via WhatsApp. Roberto demonstrou interesse. Fernanda tem acesso aos XMLs do mês. |
| **Fluxo principal** | 1. Founder envia áudio: "Roberto, me manda os XMLs de compra desse mês." 2. Roberto encaminha para Fernanda: "Manda os XMLs." 3. Fernanda compacta em ZIP, envia pelo WhatsApp. 4. Founder faz upload no back-end do Copiloto. 5. Sistema processa 87 XMLs em ~15s. Dashboard: "87 notas. 4 inconsistências. 1 risco alto." 6. Founder envia print: "Essa nota do Distribuidora X — CFOP errado. Se não corrigir, R$ 412 a mais na DAS. Quer testar?" 7. Roberto reconhece o fornecedor, vê valor em reais. "Caramba. Quanto custa?" |
| **Fluxo alternativo A** | Fernanda envia PDF em vez de XML → Founder orienta: "XML é o arquivo que vem no e-mail, termina com .xml." |
| **Fluxo alternativo B** | Sistema não encontra inconsistência → Founder: "Dessa vez tá ok. Monitora mês que vem." Venda não fecha, relacionamento fica aberto. |
| **Pós-condição** | Roberto agenda onboarding ou fica em follow-up. |

### UC-02 — Primeiro Acesso e Onboarding Guiado

| Campo | Conteúdo |
|---|---|
| **Nome** | Primeiro acesso e onboarding guiado pelo founder |
| **Atores** | Founder, Roberto, Fernanda |
| **Pré-condição** | Roberto aceitou testar. Founder criou organização manualmente no back-end. |
| **Fluxo principal** | 1. Founder agenda call WhatsApp 15 min, 8h. 2. Envia link mágico para Roberto. 3. Roberto clica, abre dashboard no celular sem login. "Bem-vindo, Casa Forte. 87 notas. 4 inconsistências." 4. Founder guia: "Verde ok. Amarelo atenção. Vermelho risco." 5. Founder envia link para Fernanda. 6. Fernanda acessa pelo computador. 7. Founder guia: "Clica em Carregar notas. Arrasta os XMLs aqui." 8. Fernanda testa com 3 XMLs. Processa em 5s. Dashboard atualiza. 9. Founder: "Pronto. Toda nota nova, faz isso. Roberto recebe resumo toda segunda no WhatsApp." 10. "15 dias grátis. Depois R$ 97/mês." |
| **Fluxo alternativo A** | Computador da loja trava → Fernanda usa celular. Founder orienta e-mail: "Manda para notas@copilotofiscal.com." |
| **Fluxo alternativo B** | Link mágico expira → Roberto chama founder. Founder reenvia. |
| **Pós-condição** | Roberto e Fernanda ativados. Período de teste de 15 dias iniciado. |

### UC-03 — Upload Semanal de XMLs e Conferência

| Campo | Conteúdo |
|---|---|
| **Nome** | Upload semanal de XMLs pela Fernanda |
| **Atores** | Fernanda |
| **Pré-condição** | Fernanda passou pelo onboarding. Terça-feira, 8 e-mails de fornecedores com XMLs. |
| **Fluxo principal** | 1. Fernanda baixa 8 XMLs para a pasta do mês. 2. Abre Copiloto Fiscal (sessão ativa). 3. Clica "Carregar notas". Arrasta os 8 XMLs. 4. Sistema: "Processando 8 notas..." Em ~3s: "98 notas este mês. 1 nova inconsistência (atenção)." 5. Fernanda clica: "CST PIS/COFINS incompatível. Score 50. Fornecedor é Lucro Presumido." 6. Fernanda pensa: "Vou confirmar com Dona Célia no fim do mês." Continua o trabalho. |
| **Fluxo alternativo A** | 1 arquivo corrompido → Sistema processa 7, ignora 1. "7 notas processadas. 1 arquivo ignorado." |
| **Fluxo alternativo B** | Fernanda encaminha e-mails para notas@copilotofiscal.com. 2 min depois, dashboard atualizado. |
| **Pós-condição** | Notas processadas. Dashboard atualizado. Nenhuma ação urgente. |

### UC-04 — Detecção de Inconsistência Grave e Ação Corretiva

| Campo | Conteúdo |
|---|---|
| **Nome** | Detecção de inconsistência de risco alto e ação corretiva |
| **Atores** | Roberto, Fernanda |
| **Pré-condição** | Fernanda fez upload. NF-e CimentoBom R$ 8.400 com CFOP 6102 (saída) em vez de 1102 (entrada). Score 70. |
| **Fluxo principal** | 1. Sistema processa, detecta score 70. 2. Envia alerta WhatsApp: "⚠️ Alerta: CimentoBom R$ 8.400 com risco alto de CFOP divergente." 3. Roberto no balcão, vê vibração. Atende cliente. Depois clica no link. 4. Lê: "CFOP 6102 (saída). Esperado 1102 (entrada). Impacto: ~R$ 1.008 a mais na DAS." 5. Clica "O que fazer?": checklist de 4 passos. 6. Encaminha para Fernanda: "Resolve isso. Liga pro CimentoBom." 7. Fernanda marca "Em andamento", liga, pede correção. 8. 2 dias depois, fornecedor reemite NF-e corrigida. Fernanda faz upload, marca como "Resolvida". |
| **Fluxo alternativo A** | Fornecedor se recusa → Fernanda marca "Pendente" e anota: "Fornecedor recusou. Falar com Dona Célia." |
| **Fluxo alternativo B** | Roberto não vê o alerta → (ver UC-10). |
| **Pós-condição** | Inconsistência resolvida ou escalada. Histórico registrado. Jobs JF2 + JE1 atendidos. |

### UC-05 — Semana Sem Inconsistências ("Silêncio Positivo")

| Campo | Conteúdo |
|---|---|
| **Nome** | Semana sem inconsistências — o "silêncio positivo" |
| **Atores** | Roberto |
| **Pré-condição** | 23 XMLs processados na semana. Zero inconsistências. Segunda-feira 8h. |
| **Fluxo principal** | 1. Sistema envia resumo WhatsApp: "📊 23 notas processadas. Nenhuma inconsistência. ✅ Seu fiscal está em dia." 2. Roberto lê em 5s. Não clica. Respira aliviado. 3. Vai abrir a loja. |
| **Fluxo alternativo A** | 3ª semana consecutiva sem erros. Roberto questiona valor. Founder explica: "É igual seguro. Você paga exatamente para não precisar usar." |
| **Fluxo alternativo B** | Roberto não abre WhatsApp na segunda. Mensagem fica lá. Não afeta uso. |
| **Pós-condição** | Hábito semanal mantido. JE1 reforçado. |

### UC-06 — Exportação de Relatório e Envio ao Contador

| Campo | Conteúdo |
|---|---|
| **Nome** | Exportação do relatório mensal do contador |
| **Atores** | Fernanda, Dona Célia |
| **Pré-condição** | Dia 28 de maio. 112 notas. 5 inconsistências (3 resolvidas, 1 em andamento, 1 ignorada). |
| **Fluxo principal** | 1. Fernanda acessa Copiloto. Clica "Exportar para contador". 2. Seleciona "Maio 2026". Clica "Gerar PDF". 3. Sistema gera PDF em ~3s. 4. Fernanda baixa, confere rapidamente. 5. Abre WhatsApp Web, envia para Dona Célia: "Segue relatório de maio. 3 corrigidos, 1 em andamento, 1 ignorado." 6. Dona Célia responde: "Ficou ótimo! Facilitou muito." 7. Fernanda sorri. Primeiro fechamento não caótico em 3 anos. |
| **Fluxo alternativo A** | Erro ao gerar PDF → Fernanda tenta de novo. Se falhar 2x, avisa founder. |
| **Fluxo alternativo B** | Fernanda esquece de exportar → Dona Célia cobra no dia 30. Fernanda faz correndo. |
| **Pós-condição** | Dona Célia recebe dados organizados. Confiança loja-contador aumenta. Dona Célia vira promotora (M4 da jornada). |

### UC-07 — Upload Falha (Arquivo Corrompido ou Formato Errado)

| Campo | Conteúdo |
|---|---|
| **Nome** | Falha no upload — arquivo em formato errado |
| **Atores** | Fernanda |
| **Pré-condição** | 10 arquivos selecionados: 2 PDFs de boletos, 1 XML de NFS-e, 7 XMLs de NF-e válidos. |
| **Fluxo principal** | 1. Fernanda arrasta pasta com 10 arquivos. 2. Sistema valida. 3 PDFs/NFS-e são ignorados. 7 XMLs processados. 3. Dashboard: "7 novas notas. 3 arquivos ignorados (formato não suportado)." 4. Fernanda vê mensagem, vê que as 7 notas esperadas chegaram. Continua. |
| **Fluxo alternativo A** | Fernanda clica em "3 arquivos ignorados". Vê lista: "boleto.pdf (não é XML)", "nota_servico.xml (NFS-e não suportado)". |
| **Fluxo alternativo B** | ZIP corrompido → Sistema: "Não foi possível abrir. Tente baixar novamente." Fernanda baixa de novo. Funciona. |
| **Pós-condição** | Apenas XMLs válidos processados. Log registra ignorados para debug. |

### UC-08 — Link Mágico Expirado e Reenvio

| Campo | Conteúdo |
|---|---|
| **Nome** | Link mágico de acesso expira e usuário solicita reenvio |
| **Atores** | Roberto |
| **Pré-condição** | Roberto recebeu link na segunda, não abriu. Terça-feira 16h quer acessar. |
| **Fluxo principal** | 1. Roberto clica no link antigo. 2. Sistema: "Link expirado por segurança. Solicite um novo abaixo." Botão "Enviar novo link" visível. 3. Roberto clica. 4. Sistema envia novo link via WhatsApp. 5. Roberto recebe em 5s, clica, abre dashboard. |
| **Fluxo alternativo A** | Roberto trocou de número → Link vai para número antigo. Chama founder: "Troquei de número." Founder atualiza no back-end. |
| **Fluxo alternativo B** | Roberto usa WhatsApp pessoal, mas cadastro está no número da loja → Abre WhatsApp da loja e o link está lá. |
| **Pós-condição** | Roberto acessa dashboard. Experiência "link expirado" é indolor — sem frustração de senha. |

### UC-09 — Sistema Não Encontra Inconsistências por 3 Semanas

| Campo | Conteúdo |
|---|---|
| **Nome** | Três semanas consecutivas sem inconsistências |
| **Atores** | Roberto, Founder |
| **Pré-condição** | 55 notas em 3 semanas. Zero inconsistências. |
| **Fluxo principal** | 1. Semanas 1-3: resumos "Nenhuma inconsistência." 2. Roberto começa a questionar valor. 3. Founder percebe na métrica e envia WhatsApp: "Roberto, 55 notas sem erro! Isso é ótimo — seus fornecedores estão certinhos. Continua monitorando." 4. Roberto pensa: "Se parar de monitorar, não vou saber quando der erro." Continua. |
| **Fluxo alternativo A** | Roberto decide cancelar. Founder: "Deixa eu rodar regras extras antes." Ativa regras reserva. Se nada, cancela com porta aberta. |
| **Pós-condição** | Roberto mantém assinatura ou cancela temporariamente. Founder aprende sobre cobertura das regras. |

### UC-10 — Roberto Ignora Alerta Grave e Founder Intervém

| Campo | Conteúdo |
|---|---|
| **Nome** | Alerta grave ignorado e intervenção humana do founder |
| **Atores** | Roberto, Founder |
| **Pré-condição** | Alerta score 100 (CNPJ suspenso) enviado há 48h. Status "Pendente". Roberto não abriu. |
| **Fluxo principal** | 1. Founder vê no painel admin: alerta score 100 pendente há 48h. 2. Envia WhatsApp: "Roberto, vi que tem alerta importante — CNPJ da Areal Brita suspenso. Já resolveu?" 3. Roberto responde: "Esqueci totalmente. Deixa eu ver." 4. Abre dashboard, liga para fornecedor. 5. Fornecedor explica que é erro cadastral. Roberto marca "Em andamento". 6. Founder vê atualização. |
| **Fluxo alternativo A** | Roberto não responde founder → Founder liga para a loja. Fernanda atende: "Deixa eu falar com ele." Alerta resolvido. |
| **Pós-condição** | Alerta grave não fica sem resposta. Roberto percebe que o produto tem gente por trás. Confiança aumenta. |

### Riscos e pontos de atenção

| Risco | Severidade | Mitigação |
|---|---|---|
| UC-10 (intervenção humana) não escala para >20 clientes | Baixa (MVP) | Para MVP, 1-2 intervenções/semana é factível. Fase 2: automatizar regra de escalação. |
| UC-09 (3 semanas sem inconsistências) pode ser comum se cobertura das 8 regras for baixa | Média | Monitorar taxa de detecção por loja. Se <1/mês em >50% das lojas, expandir regras. |
| UC-08 (link expirado) pode frustrar se usuário não souber solicitar reenvio | Baixa | Tela de "link expirado" deve ter botão "Enviar novo link" como elemento mais visível. |

---

## Etapa 13 — Arquitetura de Informação

### Objetivo da etapa

Definir a estrutura de navegação, o mapa de telas e a hierarquia de informação do Copiloto Fiscal MVP — garantindo que o Roberto (dono, baixa maturidade digital, celular) encontre o que precisa em no máximo 2 toques e que a Fernanda (auxiliar, computador) execute tarefas operacionais sem se perder.

### Premissas adotadas

| # | Premissa | Justificativa |
|---|---|---|
| P1 | O MVP é um web app responsivo (mobile-first), não um app nativo | Decisão da Etapa 6: sem app nativo no MVP |
| P2 | O menu principal tem no máximo 3 itens visíveis para o Roberto | RNF-U02: ≤2 cliques para ação principal; menu enxuto evita paralisia de escolha |
| P3 | Hierarquia "Hub & Spoke": tela central (dashboard) e ramificações curtas para tarefas específicas | Padrão mobile consagrado; evita navegação profunda |
| P4 | Telas de Roberto (Admin) e Fernanda (Operador) são as mesmas, com diferença de menu | RFS-033: permissões por papel |
| P5 | Nomenclatura usa verbos no imperativo e substantivos concretos, português claro, nível ensino médio | RNF-U03: linguagem acessível |

### Decisões recomendadas

| Decisão | Conteúdo | Status |
|---|---|---|
| D1 | Navegação principal: bottom nav bar com 3 itens: "Resumo", "Notas", "Carregar". Sempre visível. | Decisão de UX |
| D2 | O item "Carregar" é o botão de ação primária global — visualmente destacado (cor primária) | Decisão de UX |
| D3 | Não há menu "Configurações" para o Roberto no MVP. Configurações são feitas pelo founder no back-end | Decisão de escopo |
| D4 | O botão "Exportar para contador" fica no topo da tela "Notas", visível sem scroll | Decisão de UX |

### Mapa de Telas do MVP

7 telas no total:

```
T0 — LINK EXPIRADO (só aparece se token inválido)
       │
       ▼
T1 — DASHBOARD (HOME) — "Resumo"
       │  ├── Cards: total notas, OK, ATENÇÃO, RISCO ALTO
       │  ├── Top 3 inconsistências graves
       │  └── Link "Ver todas as notas"
       │
   ┌───┼───┐
   │       │           │
   ▼       ▼           ▼
T2 — NOTAS    T6 — CARREGAR    T1 (já está)
Lista completa   Upload XMLs
de inconsist.   (ação rápida)
   │
   ▼
T3 — DETALHE da inconsistência + checklist
   │
   ▼
T4 — AÇÃO ("O que fazer" expandido)

T5 — EXPORTANDO (modal de progresso do PDF)
```

### Bottom Nav Bar (presente em T1, T2, T3, T4, T6)

```
[📊 Resumo]    [📋 Notas]    [➕ Carregar]
```

- Sempre visível (position: fixed)
- Item ativo: cor primária; inativos: cinza
- "Carregar" é visualmente destacado
- NÃO há menu "Mais" ou "..." — se não cabe em 3, não entra no MVP

### Descrição de Cada Tela

#### T1 — DASHBOARD (Resumo)

| Campo | Conteúdo |
|---|---|
| **Propósito** | Responder em 3s: "Tem algum problema que preciso resolver agora?" |
| **URL** | `/dashboard` |
| **Conteúdo** | 1. Saudação + nome da loja. 2. Card de resumo: 4 números (total, OK verde, ATENÇÃO amarelo, RISCO ALTO vermelho). 3. Seção "Precisa de atenção": 3 cards com inconsistências mais graves (fornecedor, valor, erro resumido, score, seta ">"). Se 0: "Tudo certo este mês! ✅". 4. Botão "Ver todas as notas". |
| **Ações** | Toque em card → T3. "Ver todas" → T2. Bottom nav → Resumo, Notas, Carregar. |
| **Estados** | Normal, sem inconsistências, sem notas carregadas, carregando (skeleton), erro. |

#### T2 — NOTAS (Lista de Inconsistências)

| Campo | Conteúdo |
|---|---|
| **Propósito** | "Quais notas têm problema? Quais já resolvi?" |
| **URL** | `/notas` |
| **Conteúdo** | 1. Topo: período (dropdown de meses) + botão "Exportar PDF". 2. Lista paginada, ordenada por score. Cada linha: fornecedor, valor, erro resumido, badge de score, status, seta ">". 3. Rodapé: "X inconsistências em Y notas". |
| **Ações** | Toque na linha → T3. Filtro de período. Busca por fornecedor/chave. "Exportar PDF" → T5. Bottom nav. |
| **Estados** | Com inconsistências, sem inconsistências, carregando, erro. |

#### T3 — DETALHE DA INCONSISTÊNCIA

| Campo | Conteúdo |
|---|---|
| **Propósito** | "O que está errado? Quanto custa? O que fazer?" |
| **URL** | `/notas/:id` |
| **Conteúdo** | 1. Top bar "← Voltar". 2. Card da nota: fornecedor, número, data, valor (grande). 3. Card do problema: descrição em português, valores encontrado vs. esperado, score com cor, impacto em R$. 4. Status: dropdown (Pendente/Em andamento/Resolvida/Ignorada). 5. Botão "O que fazer?" (grande, cor de destaque). 6. Última atualização. |
| **Ações** | Alterar status. "O que fazer?" → T4 expande. ← Voltar → T2. Bottom nav. |

#### T4 — AÇÃO ("O que fazer")

| Campo | Conteúdo |
|---|---|
| **Propósito** | "Passos concretos para resolver este problema." |
| **Conteúdo** | Checklist numerada de 3-6 passos com checkboxes. Ex.: "☐ 1. Ligue para CimentoBom. ☐ 2. Peça carta de correção. ☐ 3. Solicite reemissão. ☐ 4. Faça upload da nota corrigida." |
| **Estados** | Nenhum passo concluído, parcial, todos concluídos ("Tudo resolvido! ✅"). |

#### T5 — EXPORTANDO (Modal)

| Campo | Conteúdo |
|---|---|
| **Propósito** | "Gerando o PDF. Aguarde." |
| **Conteúdo** | Spinner + "Gerando relatório do contador...". Concluído: "Relatório pronto! [Baixar PDF]". Erro: "Não foi possível. [Tentar novamente]". |

#### T6 — CARREGAR NOTAS (Upload)

| Campo | Conteúdo |
|---|---|
| **Propósito** | "Enviar XMLs para análise." |
| **URL** | `/carregar` |
| **Conteúdo** | 1. Área de upload com borda tracejada, ícone de documento, "Arraste os arquivos XML ou ZIP aqui". 2. Botão "ou selecione do computador". 3. Dica: "Você também pode encaminhar os XMLs por e-mail para notas@copilotofiscal.com". 4. Após seleção: barra de progresso "Processando X de Y notas...". 5. Concluído: "X notas processadas!" + link "Ver resumo →". Se ignorados: "Y arquivos ignorados [Ver quais →]". |
| **Estados** | Vazio, processando, concluído, erro total. |

#### T0 — LINK EXPIRADO

| Campo | Conteúdo |
|---|---|
| **Propósito** | "Link expirou. Solicite um novo." |
| **Conteúdo** | "Este link expirou por segurança." + botão grande "Enviar novo link de acesso". "O novo link será enviado para seu WhatsApp." |
| **Estados** | Token expirado, link enviado com sucesso, erro no envio. |

### Hierarquia de Informação

| Ação do Roberto | Toques | Tela |
|---|---|---|
| Ver se tem problema | 0 (abre o app) | T1 |
| Ver detalhe de uma inconsistência | 1 (toque no card) | T3 |
| Ver todas as inconsistências | 1 (Ver todas) | T2 |
| Ver checklist de ação | 1 (O que fazer) | T4 |
| Carregar notas (Fernanda) | 1 (nav Carregar) | T6 |

### Nomenclatura — Glossário de Interface

| Termo técnico | Como aparece para o Roberto |
|---|---|
| Dashboard | **Resumo** |
| NF-e | **Nota fiscal** |
| XML | **Arquivo da nota** ou **XML** |
| CFOP | **Código da operação fiscal (CFOP)** |
| NCM | **Classificação fiscal do produto (NCM)** |
| Inconsistência | **Problema** ou **ponto de atenção** |
| Score | **Nível de atenção** (verde/amarelo/vermelho) |
| Upload | **Carregar notas** |
| Exportar PDF | **Baixar relatório do contador** |
| Processar | **Analisar** |

### Árvore de Rotas (Visão Dev)

```
/
├── /login?expired=true → T0
├── /dashboard → T1
├── /notas → T2
│   └── /notas/:id → T3 → expande → T4
├── /carregar → T6
└── /api/notas/:id/exportar-pdf → T5
```

### Riscos e pontos de atenção

| Risco | Severidade | Mitigação |
|---|---|---|
| 3 itens no bottom nav pode ser pouco na Fase 2 | Baixa | Fase 2: sub-abas ou menu "Mais" com base já habituada |
| T1 pode poluir com >10 inconsistências no mês | Média | Badge no ícone "Notas" com contagem de pendências |
| Roberto acessar T6 (Carregar) por engano | Média | Texto direto: "Arraste XMLs aqui". Onboarding ensina que é tarefa da Fernanda |
| Nome "Notas" pode confundir com "notas de saída" ou "anotações" | Baixa | Founder explica no onboarding. Testar "Problemas" ou "Pendências" no futuro |
| Checklist T4 inline pode ter problemas de scroll em celular | Baixa | Testar em 3 dispositivos Android reais antes do beta |

---

### Expansão Pós-MVP — Novas Telas (T10-T23)

**Objetivo:** Adicionar 14 novas telas para suportar as 30 funcionalidades pós-MVP (F36-F65), organizadas por fase de implementação.

#### Mapa de Telas Atualizado (MVP + Pós-MVP)

```
MVP (T0-T6):
T0 — LINK EXPIRADO
T1 — DASHBOARD (HOME)
T2 — NOTAS (Lista de Inconsistências)
T3 — DETALHE da inconsistência
T4 — AÇÃO ("O que fazer")
T5 — EXPORTANDO (modal PDF)
T6 — CARREGAR NOTAS (Upload)

Pós-MVP Fase A (T10-T13):
T10 — ONBOARDING RAIO-X (wizard 5 passos)
T11 — MENSAGEM PARA FORNECEDOR (modal)
T12 — PAINEL DE ECONOMIA / RISCOS EVITADOS
T13 — RELATÓRIO MENSAL DO DONO (preview)

Pós-MVP Fase B (T14-T16):
T14 — KANBAN DE PENDÊNCIAS
T15 — CONFIGURAÇÃO DOWNLOAD AUTOMÁTICO
T16 — ALERTAS CADASTRAIS

Pós-MVP Fase C (T17-T20):
T17 — PORTAL DO CONTADOR (login)
T18 — PORTAL DO CONTADOR (dashboard clientes)
T19 — SCORE DE FORNECEDORES
T20 — ASSISTENTE IA (chat panel)

Pós-MVP Fase D (T21-T23):
T21 — PREPARAÇÃO REFORMA TRIBUTÁRIA
T22 — INTEGRAÇÃO ERPs
T23 — CATÁLOGO DE PACOTES DE REGRAS
```

#### Navegação Atualizada (Pós-MVP)

**Bottom Nav Bar (MVP + Fase A):**
```
[📊 Resumo]    [📋 Notas]    [➕ Carregar]
```

**Bottom Nav Bar (Fase B+):**
```
[📊 Resumo]    [📋 Notas]    [📌 Pendências]    [➕ Carregar]
```

**Menu Lateral (Fase C+ — acessível via ícone ☰ no header):**
```
┌─────────────────────┐
│ 📊 Resumo           │
│ 📋 Notas            │
│ 📌 Pendências       │
│ ➕ Carregar         │
│ ─────────────────── │
│ 💰 Economia         │  ← T12
│ 🏢 Fornecedores     │  ← T19
│ 🤖 Assistente IA    │  ← T20
│ 📄 Relatório Mensal │  ← T13
│ ⚙️ Configurações    │  ← T15, T16, T22, T23
│ 👤 Perfil           │
└─────────────────────┘
```

**Portal do Contador (separado — T17, T18):**
```
[🏢 Clientes]    [📊 Dashboard]    [📄 Exportações]
```

---

#### Descrição das Novas Telas

##### T10 — ONBOARDING RAIO-X (Fase A)

| Campo | Conteúdo |
|---|---|
| **Propósito** | Guiar novo usuário em 5 passos: upload → análise → resultados → top 3 riscos → PDF para contador |
| **URL** | `/onboarding` |
| **Conteúdo** | Wizard de 5 passos com barra de progresso. Passo 1: upload simplificado (sem menus). Passo 2: animação de processamento. Passo 3: resultados com números grandes. Passo 4: cards dos top 3 riscos. Passo 5: botão "Baixar PDF" + "Enviar por WhatsApp". |
| **Ações** | Avançar/retroceder passos. Pular wizard (botão discreto). Retomar wizard (botão no dashboard até conclusão). |
| **Estados** | Passo 1 (upload), Passo 2 (processando), Passo 3 (resultados), Passo 4 (top riscos), Passo 5 (PDF), concluído. |

##### T11 — MENSAGEM PARA FORNECEDOR (Fase A)

| Campo | Conteúdo |
|---|---|
| **Propósito** | Gerar mensagem contextualizada para fornecedor quando inconsistência é detectada |
| **URL** | Modal acessível via T3 (Detalhe da Inconsistência) |
| **Conteúdo** | 1. Preview da mensagem gerada (texto editável). 2. Botões: "Copiar", "Enviar por WhatsApp", "Enviar por e-mail". 3. Status da mensagem (gerada, copiada, enviada, entregue). |
| **Ações** | Editar texto. Copiar para clipboard. Enviar via WhatsApp (abre compartilhamento). Enviar via e-mail (abre cliente de e-mail). Fechar modal. |
| **Estados** | Gerando mensagem, preview pronto, enviando, enviada, erro no envio. |

##### T12 — PAINEL DE ECONOMIA / RISCOS EVITADOS (Fase A)

| Campo | Conteúdo |
|---|---|
| **Propósito** | Demonstrar ROI continuamente: inconsistências detectadas, valor em risco, economia potencial |
| **URL** | `/economia` |
| **Conteúdo** | 1. Card principal: "Riscos Evitados" com valor em R$ (grande). 2. Métricas: total detectadas, resolvidas, pendentes. 3. Gráfico de barras: últimos 6 meses (detectados vs resolvidos). 4. Filtro: mês/trimestre/ano. |
| **Ações** | Alterar período (dropdown). Exportar PDF do relatório de economia. Voltar ao dashboard. |
| **Estados** | Com dados (gráfico + métricas), sem dados ("Ainda não há dados suficientes"), carregando. |

##### T13 — RELATÓRIO MENSAL DO DONO (Fase A)

| Campo | Conteúdo |
|---|---|
| **Propósito** | Preview do relatório mensal de 1 página para o dono antes de baixar |
| **URL** | `/relatorio-mensal` |
| **Conteúdo** | 1. Preview visual do PDF (1 página A4). 2. Seletor de mês (dropdown). 3. Botão "Baixar PDF" (grande). 4. Botão "Enviar por WhatsApp". |
| **Ações** | Selecionar mês. Baixar PDF. Enviar por WhatsApp. Voltar ao dashboard. |
| **Estados** | Preview pronto, gerando PDF, erro na geração, sem dados para o mês selecionado. |

##### T14 — KANBAN DE PENDÊNCIAS (Fase B)

| Campo | Conteúdo |
|---|---|
| **Propósito** | Mini-CRM de pendências fiscais: responsável, prazo, comentários, anexos |
| **URL** | `/pendencias` |
| **Conteúdo** | 1. Board com 4 colunas: Pendente, Em andamento, Resolvida, Ignorada. 2. Cards de inconsistências em cada coluna (fornecedor, valor, score, responsável, prazo). 3. Filtros: responsável, prazo, score. 4. Botão "Nova pendência" (manual). |
| **Ações** | Drag & drop entre colunas. Clique no card → abre painel lateral com detalhes, comentários, anexos. Atribuir responsável. Definir prazo. Adicionar comentário. Upload anexo. |
| **Estados** | Board vazio, board com cards, arrastando card, painel lateral aberto, salvando alterações. |

##### T15 — CONFIGURAÇÃO DOWNLOAD AUTOMÁTICO (Fase B)

| Campo | Conteúdo |
|---|---|
| **Propósito** | Configurar download automático de XMLs via certificado digital A1 |
| **URL** | `/configuracoes/download-automatico` |
| **Conteúdo** | 1. Status do certificado (válido/vencendo/vencido) com data de validade. 2. Botão "Upload certificado A1" (se não há certificado). 3. Toggle "Download automático" (ativo/inativo). 4. Frequência (diário/semanal). 5. Horário preferido. 6. Histórico de downloads (últimos 10). |
| **Ações** | Upload certificado (modal com senha). Ativar/desativar download automático. Alterar frequência/horário. Ver detalhes de download específico. |
| **Estados** | Sem certificado, certificado válido, certificado vencendo, certificado vencido, download ativo, download inativo, histórico vazio. |

##### T16 — ALERTAS CADASTRAIS (Fase B)

| Campo | Conteúdo |
|---|---|
| **Propósito** | Mini-monitor cadastral: certificado vencendo, CNPJ inapto, IE irregular, CNAE incompatível |
| **URL** | `/alertas-cadastrais` |
| **Conteúdo** | 1. Lista de alertas com severidade (crítico/atenção/info). 2. Cada alerta: tipo, entidade (fornecedor/organização), mensagem, data. 3. Filtros: severidade, tipo, lido/não lido. 4. Botão "Marcar como lido" em cada alerta. |
| **Ações** | Marcar alerta como lido. Descartar alerta. Ver detalhes do alerta (modal). Filtrar por severidade/tipo. |
| **Estados** | Sem alertas, alertas críticos, alertas de atenção, alertas informativos, todos lidos. |

##### T17 — PORTAL DO CONTADOR (LOGIN) (Fase C)

| Campo | Conteúdo |
|---|---|
| **Propósito** | Login separado para contadores (CPF + senha) |
| **URL** | `/contador/login` |
| **Conteúdo** | 1. Campo CPF (com máscara). 2. Campo senha. 3. Botão "Entrar". 4. Link "Esqueci minha senha". 5. Link "Sou contador, quero me cadastrar". |
| **Ações** | Login. Recuperar senha (envia e-mail). Cadastro (vai para `/contador/cadastro`). |
| **Estados** | Formulário vazio, validando credenciais, login bem-sucedido, credenciais inválidas, conta bloqueada. |

##### T18 — PORTAL DO CONTADOR (DASHBOARD CLIENTES) (Fase C)

| Campo | Conteúdo |
|---|---|
| **Propósito** | Lista de clientes atendidos pelo contador com resumo de status fiscal |
| **URL** | `/contador/dashboard` |
| **Conteúdo** | 1. Lista de clientes (nome, CNPJ, total notas mês, inconsistências pendentes, última atividade). 2. Busca por nome/CNPJ. 3. Filtro: com pendências, sem pendências, inativos. 4. Botão "Exportar todos" (PDF consolidado). |
| **Ações** | Clique no cliente → abre dashboard do cliente (read-only). Exportar PDF consolidado. Buscar cliente. Filtrar lista. |
| **Estados** | Lista com clientes, lista vazia, buscando, filtrando, exportando PDF. |

##### T19 — SCORE DE FORNECEDORES (Fase C)

| Campo | Conteúdo |
|---|---|
| **Propósito** | Dashboard com score por fornecedor baseado em 90 dias |
| **URL** | `/fornecedores` |
| **Conteúdo** | 1. Ranking por categoria: "Mais confiáveis", "Atenção", "Risco". 2. Cards de fornecedores (nome, CNPJ, score, categoria, total notas 90d, valor em risco). 3. Filtros: categoria, UF, valor mínimo. 4. Busca por nome/CNPJ. |
| **Ações** | Clique no fornecedor → abre detalhe (T19.1). Filtrar por categoria. Buscar fornecedor. Ordenar por score/valor/notas. |
| **Estados** | Com dados (ranking + cards), sem dados ("Ainda não há dados suficientes — precisamos de 90 dias de histórico"), carregando. |

##### T20 — ASSISTENTE IA (CHAT PANEL) (Fase C)

| Campo | Conteúdo |
|---|---|
| **Propósito** | Chat contextual que responde perguntas sobre inconsistências |
| **URL** | Painel lateral acessível via T3 (Detalhe da Inconsistência) ou botão flutuante no dashboard |
| **Conteúdo** | 1. Histórico de conversas (scroll). 2. Campo de input de pergunta. 3. Botões de perguntas rápidas: "Explique em linguagem simples", "O que perguntar ao contador?", "Gere mensagem para fornecedor". 4. Disclaimer em toda resposta. 5. Feedback (thumbs up/down). |
| **Ações** | Digitar pergunta. Clicar em pergunta rápida. Enviar feedback. Copiar resposta. Fechar painel. |
| **Estados** | Painel fechado, painel aberto (vazio), painel aberto (com histórico), digitando, aguardando resposta, resposta pronta, erro na resposta. |

##### T21 — PREPARAÇÃO REFORMA TRIBUTÁRIA (Fase D)

| Campo | Conteúdo |
|---|---|
| **Propósito** | Simulador de preparação para Reforma Tributária (CBS/IBS) |
| **URL** | `/reforma-tributaria` |
| **Conteúdo** | 1. Score de preparação (0-100%) com gauge circular. 2. Checklist interativo por categoria (Cadastro, Sistemas, Processos, Tributação). 3. Timeline 2026-2033 com marcos personalizados. 4. Alertas CBS/IBS nos XMLs. 5. Botão "Gerar PDF de preparação". |
| **Ações** | Marcar itens do checklist como concluídos. Ver detalhes de cada item (modal). Gerar PDF. Ver timeline. |
| **Estados** | Score baixo (0-40%), score médio (41-70%), score alto (71-100%), checklist vazio, checklist parcial, checklist completo. |

##### T22 — INTEGRAÇÃO ERPs (Fase D)

| Campo | Conteúdo |
|---|---|
| **Propósito** | Conectar ERPs brasileiros (Bling, Tiny, Omie, Conta Azul) para leitura automática de notas |
| **URL** | `/configuracoes/erps` |
| **Conteúdo** | 1. Grid de ERPs suportados com logos. 2. Status de cada conexão (conectado/desconectado/erro). 3. Botão "Conectar" para cada ERP. 4. Última sincronização (data/hora). 5. Botão "Sincronizar agora". |
| **Ações** | Conectar ERP (OAuth flow). Desconectar ERP. Sincronizar manualmente. Ver logs de sincronização. |
| **Estados** | Sem conexões, conexão ativa, conexão com erro, sincronizando, sincronização concluída, OAuth em andamento. |

##### T23 — CATÁLOGO DE PACOTES DE REGRAS (Fase D)

| Campo | Conteúdo |
|---|---|
| **Propósito** | Ativar/desativar pacotes de regras por UF e setor |
| **URL** | `/configuracoes/pacotes-regras` |
| **Conteúdo** | 1. Lista de pacotes disponíveis (nome, descrição, setor, UF, regime). 2. Toggle "Ativado/Desativado" para cada pacote. 3. Detalhe do pacote (modal com lista de regras incluídas). 4. Pacotes ativos destacados no topo. |
| **Ações** | Ativar/desativar pacote. Ver detalhes do pacote. Buscar pacote por nome/setor/UF. |
| **Estados** | Lista com pacotes, lista vazia, ativando/desativando, erro na ativação. |

---

#### Hierarquia de Informação Atualizada (Pós-MVP)

| Ação do Roberto | Toques | Tela |
|---|---|---|
| Ver se tem problema | 0 (abre o app) | T1 |
| Ver detalhe de uma inconsistência | 1 (toque no card) | T3 |
| Ver todas as inconsistências | 1 (Ver todas) | T2 |
| Ver checklist de ação | 1 (O que fazer) | T4 |
| Carregar notas (Fernanda) | 1 (nav Carregar) | T6 |
| Ver economia/riscos evitados | 2 (menu lateral → Economia) | T12 |
| Ver score de fornecedores | 2 (menu lateral → Fornecedores) | T19 |
| Perguntar à IA | 2 (menu lateral → Assistente IA) | T20 |
| Ver relatório mensal | 2 (menu lateral → Relatório Mensal) | T13 |
| Gerenciar pendências (Kanban) | 1 (nav Pendências) | T14 |
| Configurar download automático | 3 (menu lateral → Configurações → Download) | T15 |
| Ver alertas cadastrais | 3 (menu lateral → Configurações → Alertas) | T16 |
| Conectar ERP | 3 (menu lateral → Configurações → ERPs) | T22 |
| Ativar pacotes de regras | 3 (menu lateral → Configurações → Pacotes) | T23 |
| Preparação Reforma Tributária | 2 (menu lateral → Reforma) | T21 |

**Portal do Contador (Dona Célia):**

| Ação do Contador | Toques | Tela |
|---|---|---|
| Login | 0 (acessa URL) | T17 |
| Ver lista de clientes | 1 (após login) | T18 |
| Ver dashboard do cliente | 2 (clique no cliente) | T18.1 |
| Comentar em inconsistência | 3 (cliente → inconsistência → comentário) | T18.2 |
| Validar inconsistência | 3 (cliente → inconsistência → validar) | T18.2 |
| Exportar PDF consolidado | 2 (botão "Exportar todos") | T18 |

---

#### Nomenclatura Atualizada — Glossário de Interface (Pós-MVP)

| Termo técnico | Como aparece para o Roberto |
|---|---|
| Dashboard | **Resumo** |
| NF-e | **Nota fiscal** |
| XML | **Arquivo da nota** ou **XML** |
| CFOP | **Código da operação fiscal (CFOP)** |
| NCM | **Classificação fiscal do produto (NCM)** |
| Inconsistência | **Problema** ou **ponto de atenção** |
| Score | **Nível de atenção** (verde/amarelo/vermelho) |
| Upload | **Carregar notas** |
| Exportar PDF | **Baixar relatório do contador** |
| Processar | **Analisar** |
| Kanban | **Pendências** |
| Supplier Score | **Score de fornecedores** |
| AI Assistant | **Assistente IA** |
| Digital Certificate | **Certificado digital** |
| ERP Integration | **Integração com sistema** |
| Rule Pack | **Pacote de regras** |
| Tax Reform | **Reforma Tributária** |

---

#### Árvore de Rotas Atualizada (Visão Dev — Pós-MVP)

```
MVP:
/
├── /login?expired=true → T0
├── /dashboard → T1
├── /notas → T2
│   └── /notas/:id → T3 → expande → T4
├── /carregar → T6
└── /api/notas/:id/exportar-pdf → T5

Fase A:
├── /onboarding → T10
├── /notas/:id/mensagem → T11 (modal)
├── /economia → T12
└── /relatorio-mensal → T13

Fase B:
├── /pendencias → T14
├── /configuracoes/download-automatico → T15
└── /alertas-cadastrais → T16

Fase C:
├── /contador/login → T17
├── /contador/dashboard → T18
│   └── /contador/clientes/:orgId → T18.1
│       └── /contador/clientes/:orgId/inconsistencias/:id → T18.2
├── /fornecedores → T19
└── /assistente-ia → T20 (painel lateral)

Fase D:
├── /reforma-tributaria → T21
├── /configuracoes/erps → T22
└── /configuracoes/pacotes-regras → T23
```

---

### Riscos e pontos de atenção (Expansão Pós-MVP)

| Risco | Severidade | Mitigação |
|---|---|---|
| 14 novas telas podem sobrecarregar navegação se não organizadas corretamente | Alta | Menu lateral só aparece na Fase C+. Bottom nav mantém 3-4 itens. Testar com 5 usuários antes de cada fase |
| Kanban (T14) pode ser complexo para usuários com baixa maturidade digital | Média | Lançar como feature opcional. Dashboard simples continua sendo tela principal. Tutorial interativo no primeiro acesso |
| Portal do contador (T17, T18) separado pode confundir contadores | Média | Link claro no e-mail de convite. Onboarding guiado para contadores. Suporte via WhatsApp |
| Assistente IA (T20) pode gerar expectativas irreais sobre capacidades | Alta | Disclaimer em toda resposta. Botões de perguntas rápidas limitam escopo. Guardrails impedem cálculo de imposto |
| Menu lateral com muitas opções pode causar paralisia de escolha | Média | Itens do menu aparecem gradualmente conforme fases. "Configurações" agrupa opções avançadas |
| Onboarding raio-x (T10) pode ser pulado por usuários apressados | Baixa | Botão "Retomar onboarding" visível no dashboard até conclusão. Benefícios claros em cada passo |

---

## Etapa 14 — UX do Produto

### Objetivo da etapa

Definir o sistema visual, os padrões de interação, o tom de voz e o tratamento de estados da interface do Copiloto Fiscal MVP — de forma que o Roberto confie no produto nos primeiros 30 segundos de uso e a Fernanda complete tarefas sem hesitação.

### Premissas adotadas

| # | Premissa | Justificativa |
|---|---|---|
| P1 | O design é utilitário, não expressivo — confiança vem de clareza, não de beleza | Roberto não se impressiona com animações; ele quer entender rápido |
| P2 | A interface usa componentes familiares (padrão Android/Material Design leve) | Familiaridade reduz carga cognitiva |
| P3 | Toda cor tem significado funcional, não decorativo | Vermelho = risco. Verde = ok. Azul = ação. Cinza = inativo |
| P4 | O produto é mobile-first com progressive enhancement para desktop | RNF-U01: operável em 360px |
| P5 | Interface construída para toque: áreas mínimas 48×48px, sem hover states | RNF-U08: zero interações baseadas em mouse |

### Decisões recomendadas

| Decisão | Conteúdo | Status |
|---|---|---|
| D1 | Paleta: azul petróleo escuro (confiança) + verde bandeira (ok) + âmbar (atenção) + vermelho tijolo (risco) | Decisão de design |
| D2 | Fonte: Inter — boa legibilidade em telas pequenas, suporte a português, gratuita | Decisão de design |
| D3 | Ícones: Phosphor Icons (fill para ações, regular para navegação) — licença MIT | Decisão de design |
| D4 | Tom de voz: segunda pessoa ("você"), frases curtas (máx. 15 palavras), sem exclamação exceto confirmação | Decisão de UX writing |
| D5 | Zero modais de confirmação para ações reversíveis; usar desfazer (undo) em vez de "tem certeza?" | Decisão de UX |

### Princípios de Design da Interface

| # | Princípio | Significado |
|---|---|---|
| **P1** | **Clareza acima de tudo** | Se o Roberto não entendeu em 5s, o design falhou |
| **P2** | **Uma ação principal por tela** | Dashboard = ver resumo. Detalhe = decidir. Upload = enviar |
| **P3** | **Cor só com significado** | Cinza neutro. Verde ok. Amarelo atenção. Vermelho aja. Azul clique |
| **P4** | **Feedback imediato** | Toda ação tem resposta <200ms. Loading com indicador real |
| **P5** | **Progressive disclosure** | Resumo primeiro. Detalhe a 1 toque. Ação a 1 toque do detalhe |
| **P6** | **Toque como primeira classe** | Área mínima 48×48px. Distância mínima entre tocáveis 16px |
| **P7** | **Português claro, sem juridiquês** | "Código da operação está diferente", não "CFOP divergente" |
| **P8** | **Respeito à senha zero** | Sem login tradicional. Sem "esqueci senha". Link mágico resolve |

### Sistema Visual

#### Paleta de Cores

| Nome | Hex | Uso |
|---|---|---|
| **Azul Petróleo** (Primária) | `#0D3B66` | Botões, links, nav ativo, cabeçalhos |
| **Azul Claro** (Primária clara) | `#1A5C8A` | Hover/pressed state de botões |
| **Verde Bandeira** (Sucesso) | `#2D6A4F` | Score OK, status Resolvida, badges verdes |
| **Verde Claro** (Sucesso fundo) | `#D8F3DC` | Fundo de cards OK |
| **Âmbar** (Atenção) | `#B8860B` | Score ATENÇÃO, status Em andamento |
| **Âmbar Claro** (Atenção fundo) | `#FFF3CD` | Fundo de cards ATENÇÃO |
| **Vermelho Tijolo** (Risco) | `#9B2226` | Score RISCO ALTO, alertas urgentes |
| **Vermelho Claro** (Risco fundo) | `#F8D7DA` | Fundo de cards RISCO ALTO |
| **Cinza Escuro** (Texto) | `#1A1A1A` | Corpo de texto, títulos |
| **Cinza Médio** (Secundário) | `#6B7280` | Labels, metadados, timestamps |
| **Cinza Claro** (Fundo) | `#F3F4F6` | Background geral |
| **Branco** (Superfície) | `#FFFFFF` | Fundo de cards, modais, área de upload |

#### Tipografia (Inter)

| Elemento | Tamanho (mobile) | Peso |
|---|---|---|
| Título de tela | 20px | Semi Bold (600) |
| Subtítulo / Seção | 16px | Medium (500) |
| Corpo de texto | 16px | Regular (400) |
| Texto secundário | 14px | Regular (400) |
| Valor monetário | 28px | Bold (700) |
| Botão primário | 16px | Semi Bold (600) |
| Badge / Chip | 12px | Medium (500) |
| Disclaimer / Legal | 12px | Regular (400) |

Altura de linha: 1.5 corpo, 1.25 títulos.

#### Espaçamento

| Elemento | Valor |
|---|---|
| Margem lateral mobile | 16px |
| Margem lateral desktop | 24px (máx. largura: 480px) |
| Espaçamento entre cards | 12px |
| Padding interno card | 16px |
| Border radius cards/botões | 8px |
| Área mínima de toque | 48×48px |
| Distância mínima entre tocáveis | 16px |
| Largura máxima de linha | 72 caracteres (~360px) |

### Padrões de Interação

| Interação | Comportamento |
|---|---|
| **Toque em item da lista** | Push com slide da direita (200ms) |
| **"← Voltar"** | Pop com slide da esquerda (200ms) |
| **Bottom nav** | Troca imediata sem animação, scroll ao topo |
| **Back button Android** | Pop na pilha; se home (T1), sai do app |
| **Pull to refresh** | Apenas T1 e T2 |
| **Upload: arrastar arquivos** | Borda sólida azul, upload automático ao soltar |
| **Upload: "Cancelar"** | Interrompe; processados permanecem, não processados descartados |
| **Toque em card** | Highlight 100ms, navega para detalhe |
| **Scroll na lista** | Scroll infinito, +20 itens no fim |
| **Mudar status** | Dropdown abre 4 opções. Selecionar = imediato, sem confirmação. Toast no topo |
| **"Ignorada"** | Campo de motivo expande com foco automático |
| **Checkbox checklist** | Bounce 300ms, persiste imediatamente |

### Tom de Voz da Interface

**Personalidade**: Calmo, direto, respeitoso. Como um contador de confiança que explica com paciência.

| Situação | Ruim ❌ | Bom ✅ |
|---|---|---|
| Sem notas no mês | "Nenhum dado disponível" | "Você ainda não carregou notas este mês. [Carregar agora →]" |
| Sem inconsistências | "0 erros encontrados" | "87 notas analisadas. Nenhum problema encontrado. ✅" |
| Inconsistência detectada | "Erro: CFOP divergente. Score 70." | "O código da operação fiscal (CFOP) é de saída, mas deveria ser de entrada. Isso pode gerar imposto a mais." |
| Upload concluído | "Upload successful" | "15 notas analisadas. 1 ponto de atenção encontrado. [Ver resumo →]" |
| Link expirado | "HTTP 401" | "Seu link expirou por segurança. [Enviar novo link →]" |
| Erro servidor | "Internal Server Error 500" | "Algo deu errado. Já fomos avisados. Tente de novo em alguns minutos." |

**Regras de ouro**: Nunca use sigla sem explicar. Nunca diga "erro" quando puder dizer "ponto de atenção". Nunca deixe o usuário sem próximo passo. Nunca use "clique aqui" — use o nome da ação.

### Tratamento de Estados

| Estado | Abordagem |
|---|---|
| **Loading (dados)** | Skeleton screen com shimmer (1.5s por ciclo), nunca tela branca |
| **Loading (processamento)** | Barra de progresso real com porcentagem e mensagem |
| **Vazio — sem notas** | Ícone documento + "+". "Carregar agora →" |
| **Vazio — sem inconsistências** | Ícone check verde. "Seu fiscal está em dia." |
| **Erro rede/servidor** | Ícone nuvem com "!". Explicação em português. Botão "Tentar novamente" |
| **Erro upload** | Mensagem específica conforme o erro. Nunca "Erro desconhecido" |
| **Erro link mágico** | "Não foi possível enviar. Fale com a gente pelo WhatsApp [(11) 9XXXX-XXXX]" |
| **Sucesso — upload** | Toast verde 3s: "15 notas analisadas ✅" |
| **Sucesso — status** | Toast: "Marcado como [status]" |

### Microinterações que Geram Confiança

| # | Microinteração | Por que gera confiança |
|---|---|---|
| M1 | Números do dashboard (total, OK, ATENÇÃO, RISCO) contam de 0 ao valor real em 500ms | Dados frescos, não cache antigo |
| M2 | Score exibido como barra colorida horizontal (verde→amarelo→vermelho) preenchida até o valor | Intuitivo, sem precisar entender número |
| M3 | Checkbox com bounce (110%→100% em 200ms) ao marcar | Reforço tátil-visual de progresso |
| M4 | Status "Resolvida": card inteiro fade para verde claro 1s, depois volta | Feedback emocional de tarefa cumprida |
| M5 | Disclaimer consistente em toda tela de detalhe | Transparência = confiança |
| M6 | Campo "Não verificado — [motivo]" em cinza quando regra não pôde ser avaliada | Transparência sobre limitações |
| M7 | "Atualizado em 15/05 às 14:30" sempre visível no dashboard | Usuário sabe se dados são frescos |
| M8 | "O que significa?" ao lado de toda sigla fiscal (CFOP, NCM, CST) | Ensina sem sair da tela |

### Riscos e pontos de atenção

| Risco | Severidade | Mitigação |
|---|---|---|
| Contraste pode não ser suficiente para Roberto (51 anos, possível presbiopia) | Média | Validar WCAG 4.5:1. Testar com usuários >45 anos antes do beta |
| Skeleton screens podem aumentar tempo percebido se shimmer for lento | Baixa | Shimmer rápido (1.5s/ciclo). Se dados <2s, mostrar direto |
| Tom informal ("a gente", "você") pode soar amador em produto fiscal | Média | Testar com 3 donos de loja: "Passa confiança ou parece amador?" |
| Inter pode não carregar em conexão lenta | Baixa | font-display: swap. Fallback: system-ui, -apple-system |
| Animações podem pesar no Android antigo do Roberto | Baixa | Usar só transform e opacity (GPU). Medir FPS em dispositivo real. <30fps → remover |

---

## Etapa 15 — Telas do MVP

### Objetivo da etapa

Definir cada tela visível ao usuário no FiscoPilot MVP, com mockup textual em ASCII de alta fidelidade, hierarquia de elementos, conteúdo esperado e comportamento — orientando implementação front-end e validação com usuários beta.

### Premissas adotadas

| # | Premissa | Justificativa |
|---|---|---|
| P1 | O MVP tem 7 telas essenciais (P0) + 2 telas de suporte (P1) | Derivado da Arquitetura de Informação (Etapa 13) e Funcionalidades (Etapa 8) |
| P2 | Cada tela é descrita no formato mobile-first (360px de largura) com comportamento responsivo até ~768px | RNF-U01: operável em viewport 360px |
| P3 | As telas seguem o sistema visual definido na Etapa 14 (cores, tipografia, espaçamento, tom de voz) | Coerência com design system |
| P4 | O conteúdo dos cards usa microcopy definido na Etapa 14 (Tom de Voz) — sem siglas não explicadas | Clareza para Roberto (maturidade digital baixa) |
| P5 | Todas as telas incluem disclaimer fixo no rodapé: "Análise preliminar automática. Confirme com seu contador." | Compliance regulatório e gestão de expectativa |

### Decisões recomendadas

| Decisão | Conteúdo | Status |
|---|---|---|
| D1 | 9 telas no MVP: 7 P0 (Dashboard, Upload, Lista de Notas, Detalhe da Nota, Detalhe de Inconsistência, Relatório do Contador, Link Mágico/Login) + 2 P1 (Perfil/Configuração, Histórico de Uploads) | Decisão de MVP |
| D2 | Todas as telas de conteúdo fiscal exibem disclaimer fixo no rodapé | Decisão de compliance |
| D3 | Navegação principal: bottom tab bar com 3 ícones (Dashboard, Notas, Perfil). Upload acessível via FAB (botão flutuante) no Dashboard e Notas | Decisão de UX |
| D4 | Não há tela de "Configurações fiscais" no MVP — parâmetros (regime, UF) são definidos pelo founder no onboarding | Decisão de escopo |
| D5 | Tela de "Relatório do Contador" é uma preview + botão de download, não uma tela interativa | Decisão de UX |

---

### TELA T1 — DASHBOARD (Home)

**Quem usa:** Roberto (principal), Fernanda (secundário)
**Quando:** Todo acesso. Principal ponto de contato.

```
┌──────────────────────────────────┐
│  FiscoPilot            [Perfil] │  ← Header fixo
├──────────────────────────────────┤
│  Olá, Roberto          Maio 2026│  ← Saudação + mês corrente
│                                  │
│  ┌──────────────────────────────┐│
│  │  📋 143 notas este mês      ││  ← Card resumo geral
│  │  Processadas em 15/05 14:30 ││
│  └──────────────────────────────┘│
│                                  │
│  ┌────────┐ ┌────────┐ ┌──────┐ │
│  │   ✅   │ │   ⚠️   │ │  🔴  │ │  ← Cards de status (3 colunas)
│  │   138  │ │    3   │ │   2   │ │
│  │  OK    │ │ Atenção│ │ Risco │ │
│  └────────┘ └────────┘ └──────┘ │
│                                  │
│  ── PONTOS DE ATENÇÃO ──         │  ← Seção de inconsistências
│                                  │
│  ┌──────────────────────────────┐│
│  │ 🔴 RISCO ALTO         R$ 412││  ← Card 1: maior risco primeiro
│  │ Distribuidora CimentoBom    ││
│  │ Código da operação diverge  ││     Ordenado por score decrescente
│  │ Nota #3521 · 10/05          ││
│  │                    Ver →   ││  ← Link para detalhe
│  └──────────────────────────────┘│
│                                  │
│  ┌──────────────────────────────┐│
│  │ ⚠️ ATENÇÃO             R$ 87││  ← Card 2
│  │ Telhanorte ABC              ││
│  │ Valor total não bate com    ││
│  │ a soma dos itens            ││
│  │ Nota #3518 · 12/05          ││
│  │                    Ver →   ││
│  └──────────────────────────────┘│
│                                  │
│  ┌──────────────────────────────┐│
│  │ ⚠️ ATENÇÃO             R$ —││  ← Card 3
│  │ Pisos e Revestimentos Sul   ││
│  │ Classificação fiscal do     ││
│  │ produto parece estranha     ││
│  │ Nota #3498 · 05/05          ││
│  │                    Ver →   ││
│  └──────────────────────────────┘│
│                                  │
│  ────────────────────────────── │
│  ⓘ Análise preliminar. Confirme │  ← Disclaimer fixo
│  com seu contador.              │
├──────────────────────────────────┤
│  [🏠 Home]  [📄 Notas]  [👤 Perfil] │  ← Bottom tab bar fixa
└──────────────────────────────────┘
       ┌───┐
       │ + │  ← FAB: Upload de notas
       └───┘
```

**Estado: vazio (sem inconsistências)**

```
┌──────────────────────────────────┐
│  FiscoPilot            [Perfil] │
├──────────────────────────────────┤
│  Olá, Roberto          Maio 2026│
│                                  │
│  ┌──────────────────────────────┐│
│  │  📋 87 notas este mês       ││
│  │  Processadas em 15/05 14:30 ││
│  └──────────────────────────────┘│
│                                  │
│  ┌────────┐ ┌────────┐ ┌──────┐ │
│  │   ✅   │ │   ⚠️   │ │  🔴  │ │
│  │   87   │ │    0   │ │   0   │ │
│  │  OK    │ │ Atenção│ │ Risco │ │
│  └────────┘ └────────┘ └──────┘ │
│                                  │
│       ┌────────────────────┐     │
│       │        ✅          │     │
│       │                    │     │
│       │  Nenhum problema   │     │
│       │  encontrado este   │     │
│       │  mês. Seu fiscal   │     │
│       │  está em dia.      │     │
│       │                    │     │
│       └────────────────────┘     │
│                                  │
│  ⓘ Análise preliminar. Confirme  │
│  com seu contador.               │
├──────────────────────────────────┤
│  [🏠 Home]  [📄 Notas]  [👤 Perfil] │
└──────────────────────────────────┘
```

**Comportamento:**
- Cards de status (OK / Atenção / Risco) animam contagem de 0 ao valor real em 500ms (M1)
- Lista de inconsistências mostra apenas as do mês corrente; scroll infinito se >10
- Toque no card → T5 (Detalhe da Inconsistência)
- FAB "+" → T2 (Upload) com slide up
- Pull to refresh recarrega dashboard

---

### TELA T2 — UPLOAD DE NOTAS

**Quem usa:** Fernanda (principal)
**Quando:** 2-3x por semana

```
┌──────────────────────────────────┐
│  ← Voltar     Carregar Notas    │  ← Header com voltar
├──────────────────────────────────┤
│                                  │
│                                  │
│       ┌────────────────────┐     │
│       │                    │     │
│       │    📤              │     │  ← Área de drop zone
│       │                    │     │     (borda tracejada azul)
│       │  Arraste seus      │     │
│       │  arquivos XML      │     │
│       │  ou ZIP aqui       │     │
│       │                    │     │
│       │  ou                │     │
│       │  [Selecionar       │     │  ← Botão para seletor nativo
│       │   arquivos]        │     │
│       │                    │     │
│       └────────────────────┘     │
│                                  │
│  Dica: você também pode enviar   │
│  os XMLs por e-mail para         │
│  notas@copilotofiscal.com        │  ← Canal alternativo
│                                  │
│  ── ÚLTIMOS ENVIOS ──            │  ← Histórico recente (F06, P2)
│                                  │
│  📤 15/05 · 87 notas · Processado│
│  📤 12/05 · 32 notas · Processado│
│  📤 08/05 · 56 notas · Processado│
│                                  │
├──────────────────────────────────┤
│  ⓘ Análise preliminar. Confirme  │
│  com seu contador.               │
└──────────────────────────────────┘
```

**Estado: processando**

```
       ┌────────────────────┐
       │                    │
       │   Processando...   │
       │                    │
       │  ████████░░░  67%  │  ← Barra de progresso real
       │  58 de 87 notas    │
       │                    │
       │  Isso leva menos   │
       │  de 1 minuto       │
       │                    │
       └────────────────────┘
```

**Estado: concluído**

```
       ┌────────────────────┐
       │       ✅           │
       │   87 notas         │
       │   analisadas       │
       │                    │
       │   3 pontos de      │
       │   atenção          │
       │                    │
       │  [Ver resumo →]    │
       │  [Carregar mais]   │
       └────────────────────┘
```

**Comportamento:**
- Drop zone aceita .xml e .zip. Arquivos inválidos ignorados silenciosamente (F04)
- Se arquivo >100MB: mensagem "O arquivo é muito grande. Tente dividir em lotes menores."
- Ao concluir processamento, toast: "87 notas analisadas ✅"
- Toque em "Ver resumo" → navega para T1 (Dashboard)

---

### TELA T3 — LISTA DE NOTAS

**Quem usa:** Fernanda (principal), Roberto (eventual)
**Quando:** Conferir quais notas foram processadas, buscar nota específica

```
┌──────────────────────────────────┐
│  ← Voltar        Notas          │  ← Header
├──────────────────────────────────┤
│  ┌──────────────────────────────┐│
│  │ 🔍 Buscar por fornecedor    ││  ← Campo de busca (F24, P2)
│  └──────────────────────────────┘│
│                                  │
│  ┌ Mai 2026 ──────── [Filtrar] ┐│  ← Seletor de mês/intervalo
│                                  │
│  ┌──────────────────────────────┐│
│  │ 🔴 Distribuidora CimentoBom ││  ← Item com indicador de risco
│  │    Nota #3521 · 10/05       ││
│  │    R$ 8.400 · Score 85      ││     Ordenação: risco > data
│  │                      Ver → ││
│  └──────────────────────────────┘│
│                                  │
│  ┌──────────────────────────────┐│
│  │ ⚠️ Telhanorte ABC           ││
│  │    Nota #3518 · 12/05       ││
│  │    R$ 3.200 · Score 62      ││
│  │                      Ver → ││
│  └──────────────────────────────┘│
│                                  │
│  ┌──────────────────────────────┐│
│  │ ✅ C&C Materiais            ││
│  │    Nota #3515 · 09/05       ││
│  │    R$ 1.150 · OK            ││
│  │                      Ver → ││
│  └──────────────────────────────┘│
│                                  │
│  ┌──────────────────────────────┐│
│  │ ✅ Ferragens do Zé          ││
│  │    Nota #3512 · 08/05       ││
│  │    R$ 2.890 · OK            ││
│  │                      Ver → ││
│  └──────────────────────────────┘│
│                                  │
│  ── Exibindo 4 de 143 notas ──   │
│                                  │
├──────────────────────────────────┤
│  ⓘ Análise preliminar. Confirme  │
│  com seu contador.               │
├──────────────────────────────────┤
│  [🏠 Home]  [📄 Notas]  [👤 Perfil] │
└──────────────────────────────────┘
       ┌───┐
       │ + │  ← FAB: Upload
       └───┘
```

**Estado: vazio (mês sem notas)**

```
       ┌────────────────────┐
       │       📄           │
       │                    │
       │  Você ainda não    │
       │  carregou notas    │
       │  este mês.         │
       │                    │
       │  [Carregar agora →]│
       │                    │
       └────────────────────┘
```

**Comportamento:**
- Padrão: mês atual. Filtro abre date picker nativo
- Scroll infinito: +20 itens ao chegar ao fim
- Indicador de risco (🔴⚠️✅) visível à esquerda
- Toque em item → T4 (Detalhe da Nota)
- Busca filtra por nome do fornecedor (contém)

---

### TELA T4 — DETALHE DA NOTA

**Quem usa:** Fernanda, Roberto
**Quando:** Ao clicar em uma nota específica na lista (T3)

```
┌──────────────────────────────────┐
│  ← Voltar     Nota #3521        │  ← Header
├──────────────────────────────────┤
│  ┌──────────────────────────────┐│
│  │ Distribuidora CimentoBom     ││
│  │ CNPJ 12.345.678/0001-90     ││
│  │ Data: 10/05/2026             ││
│  │ Valor: R$ 8.400,00           ││
│  │ Chave: 3521 0510 1234...     ││
│  └──────────────────────────────┘│
│                                  │
│  ── INCONSISTÊNCIAS (1) ──       │
│                                  │
│  ┌──────────────────────────────┐│
│  │ 🔴 RISCO ALTO    Score 85   ││
│  │                              ││
│  │ O código da operação fiscal  ││
│  │ (CFOP) é de saída, mas       ││
│  │ deveria ser de entrada para  ││
│  │ o Simples Nacional.          ││
│  │                              ││
│  │ Encontrado: CFOP 6102 (saída)││
│  │ Esperado: CFOP 1102 (entrada)││
│  │                              ││
│  │ 💰 Impacto estimado:         ││
│  │    Você pode pagar até       ││
│  │    R$ 412 a mais na DAS      ││
│  │    deste mês.                ││
│  │                              ││
│  │ [O que significa CFOP?]      ││  ← Tooltip explicativo (M8)
│  │ [O que fazer? →]             ││  ← Link para checklist
│  └──────────────────────────────┘│
│                                  │
│  ── ITENS DA NOTA ──             │
│  ┌──────────────────────────────┐│
│  │ Cimento CP-II 50kg          ││
│  │ Qtd: 200 · NCM: 2523.29.00 ││
│  │ Valor un.: R$ 42,00         ││
│  │ Total: R$ 8.400,00          ││
│  └──────────────────────────────┘│
│                                  │
│  ⓘ Esta análise não substitui   │
│  a validação do seu contador.   │
│                                  │
│  ⓘ Análise preliminar. Confirme  │
│  com seu contador.               │
└──────────────────────────────────┘
```

**Estado: nota sem inconsistências**

```
│  ┌──────────────────────────────┐│
│  │ ✅ Nenhum problema          ││
│  │    encontrado nesta nota    ││
│  └──────────────────────────────┘│
```

**Comportamento:**
- Se a nota tem inconsistências, elas aparecem em seção destacada acima dos itens
- Tooltip "O que significa CFOP?" expande inline: "CFOP é o Código Fiscal de Operações e Prestações. Indica o tipo de operação (compra, venda, devolução)."
- "O que fazer?" → expande checklist inline (T5) ou navega para T5

---

### TELA T5 — DETALHE DA INCONSISTÊNCIA + CHECKLIST

**Quem usa:** Roberto (principal), Fernanda
**Quando:** Ao clicar em inconsistência específica (T1 ou T4)

```
┌──────────────────────────────────┐
│  ← Voltar   Ponto de Atenção    │  ← Header
├──────────────────────────────────┤
│  🔴 RISCO ALTO · Score 85       │  ← Badge de classificação
│                                  │
│  ── O QUE ACONTECEU ──           │
│                                  │
│  O código da operação fiscal     │
│  (CFOP) da nota #3521 do         │
│  fornecedor Distribuidora        │
│  CimentoBom está como CFOP       │
│  6102 — que é código de saída    │
│  (venda).                        │
│                                  │
│  Para o Simples Nacional,        │
│  compras dentro do estado        │
│  deveriam usar CFOP 1102         │
│  (compra para comercialização).  │
│                                  │
│  ── O QUE ISSO SIGNIFICA ──      │
│                                  │
│  Se esse código não for          │
│  corrigido, a DAS deste mês      │
│  pode sair com valor errado.     │
│                                  │
│  Impacto estimado: ~R$ 412,00    │
│  a mais de imposto.              │
│                                  │
│  ── O QUE FAZER ──               │
│                                  │
│  ☐ 1. Ligue para a Distribuidora│  ← Checklist interativo (F21)
│     CimentoBom — (11) 99999-9999│
│                                  │
│  ☐ 2. Peça uma carta de correção│
│     com CFOP 1102               │
│                                  │
│  ☐ 3. Peça para reemitir a nota │
│     fiscal com o código correto │
│                                  │
│  ☑ 4. Avise a Dona Célia sobre  │  ← Item já marcado
│     essa correção               │
│                                  │
│  ── STATUS ──                    │
│  [Pendente ▾]                    │  ← Dropdown (F22)
│                                  │     Pendente / Em andamento /
│                                  │     Resolvida / Ignorada
│  [Marcar como Resolvida]         │  ← Botão de ação rápida
│                                  │
│  ── HISTÓRICO ──                 │  ← Log de ações (JF6)
│  15/05 14:30 · Fernanda mudou   │
│  status para "Em andamento"     │
│  15/05 14:28 · Sistema detectou │
│  inconsistência (R1: CFOP)      │
│                                  │
│  ⓘ Análise preliminar. Confirme  │
│  com seu contador.               │
└──────────────────────────────────┘
```

**Estado: status "Ignorada" — expande campo de motivo**

```
│  ── MOTIVO ──                    │
│  ┌──────────────────────────────┐│
│  │ Por que você decidiu ignorar ││
│  │ este alerta?                 ││
│  │ ┌──────────────────────────┐ ││
│  │ │ Já falei com o contador  │ ││
│  │ │ e ele disse que está ok  │ ││
│  │ │ para o meu regime        │ ││
│  │ └──────────────────────────┘ ││
│  └──────────────────────────────┘│
│  [Confirmar]                     │
│                                  │
│  ⚠️ Ao ignorar, você assume a   │
│  responsabilidade por esta      │
│  decisão fiscal.                │
```

**Comportamento:**
- Checklist: checkboxes com bounce animado (M3). Persiste imediatamente
- Todos os 4 itens marcados → sugestão automática: "Todos os passos concluídos. Deseja marcar como Resolvida?"
- Dropdown de status: Pendente (padrão), Em andamento, Resolvida, Ignorada
- Se "Ignorada": expande campo de motivo obrigatório
- Status "Resolvida": card inteiro fade verde (M4)
- Histórico mostra últimas 5 ações, formato: "data hora · quem · o quê"

---

### TELA T6 — RELATÓRIO DO CONTADOR

**Quem usa:** Fernanda
**Quando:** Fim do mês, antes de enviar documentos para Dona Célia

```
┌──────────────────────────────────┐
│  ← Voltar   Relatório do Mês    │  ← Header
├──────────────────────────────────┤
│  ── MAIO 2026 ──                 │
│                                  │
│  ┌──────────────────────────────┐│
│  │ 📋 Resumo do Mês            ││
│  │                              ││
│  │ Notas processadas:     143  ││
│  │ Sem problemas:          138  ││
│  │ Pontos de atenção:        3  ││
│  │ Risco alto:               2  ││
│  │ Resolvidos:               3  ││
│  │ Pendentes:                2  ││
│  └──────────────────────────────┘│
│                                  │
│  ── INCONSISTÊNCIAS ──           │
│                                  │
│  ┌──────────────────────────────┐│
│  │ 🔴 Distribuidora CimentoBom ││
│  │    Nota #3521 · R$ 8.400    ││
│  │    CFOP divergente          ││
│  │    Status: Em andamento     ││
│  └──────────────────────────────┘│
│                                  │
│  ┌──────────────────────────────┐│
│  │ 🔴 Pisos e Revestimentos    ││
│  │    Nota #3498 · R$ 5.200    ││
│  │    NCM suspeito             ││
│  │    Status: Pendente         ││
│  └──────────────────────────────┘│
│                                  │
│  ┌──────────────────────────────┐│
│  │ ⚠️ Telhanorte ABC           ││
│  │    Nota #3518 · R$ 3.200    ││
│  │    Valor divergente         ││
│  │    Status: Resolvida ✅     ││
│  └──────────────────────────────┘│
│                                  │
│  ┌──────────────────────────────┐│
│  │ ⚠️ Este relatório foi       ││
│  │ gerado como apoio à análise ││  ← Disclaimer do contador
│  │ do contador responsável.    ││
│  │ Não substitui a validação   ││
│  │ profissional.               ││
│  └──────────────────────────────┘│
│                                  │
│  ┌──────────────────────────────┐│
│  │      [Baixar PDF]           ││  ← Botão de download
│  └──────────────────────────────┘│
│                                  │
│  ┌──────────────────────────────┐│
│  │      [Enviar por WhatsApp]  ││  ← Botão de compartilhamento
│  └──────────────────────────────┘│
├──────────────────────────────────┤
│  ⓘ Análise preliminar. Confirme  │
│  com seu contador.               │
└──────────────────────────────────┘
```

**Comportamento:**
- PDF gerado <5s (F28). Nome do arquivo: `FiscoPilot_Relatorio_Maio2026_LojaXYZ.pdf`
- PDF inclui: cabeçalho com logo, CNPJ da loja, período, disclaimer, resumo numérico, tabela de inconsistências com status
- "Enviar por WhatsApp" → abre WhatsApp Web ou app com mensagem pré-preenchida: "Dona Célia, segue o relatório fiscal de Maio/2026 da loja. [link do PDF]"
- Mês padrão: mês anterior fechado

---

### TELA T7 — LINK MÁGICO / LOGIN

**Quem usa:** Roberto, Fernanda
**Quando:** Primeiro acesso ou sessão expirada

```
┌──────────────────────────────────┐
│                                  │
│          [Logo FiscoPilot]       │
│                                  │
│     Suas notas fiscais           │
│     explicadas.                  │  ← Tagline
│                                  │
│  ┌──────────────────────────────┐│
│  │                              ││
│  │  Digite seu WhatsApp:        ││
│  │  ┌──────────────────────────┐││
│  │  │ (11) 9XXXX-XXXX         │││  ← Campo com máscara
│  │  └──────────────────────────┘││
│  │                              ││
│  │  [Enviar link de acesso]     ││  ← Botão primário
│  │                              ││
│  └──────────────────────────────┘│
│                                  │
│  Ou acesse pelo link que         │
│  enviamos no seu WhatsApp.       │
│                                  │
├──────────────────────────────────┤
│  Ao acessar, você concorda com   │
│  os Termos de Uso.               │
└──────────────────────────────────┘
```

**Estado: link enviado**

```
┌──────────────────────────────────┐
│                                  │
│          [Logo FiscoPilot]       │
│                                  │
│         📱                      │
│                                  │
│     Enviamos um link de          │
│     acesso para o seu            │
│     WhatsApp.                    │
│                                  │
│     (11) 9XXXX-1234              │
│                                  │
│     Toque no link para entrar.   │
│                                  │
│     Não recebeu?                 │
│     [Reenviar link]              │
│                                  │
│     [Usar outro número]          │
│                                  │
└──────────────────────────────────┘
```

**Estado: link expirado**

```
┌──────────────────────────────────┐
│                                  │
│     🔒                          │
│                                  │
│     Seu link expirou por         │
│     segurança.                   │
│                                  │
│     Links de acesso valem        │
│     por 24 horas.                │
│                                  │
│     [Enviar novo link]           │
│                                  │
└──────────────────────────────────┘
```

**Comportamento:**
- Sem senha, sem "esqueci senha". Apenas WhatsApp + link mágico (F31)
- Link expira em 24h. Token JWT válido por 7 dias
- Se já tem sessão ativa: redireciona direto para T1 (Dashboard)

---

### TELA T8 — PERFIL / CONFIGURAÇÃO (P1)

**Quem usa:** Roberto (admin), Fernanda (operador — visão reduzida)
**Quando:** Eventual

**Visão Admin (Roberto):**

```
┌──────────────────────────────────┐
│  ← Voltar        Perfil         │  ← Header
├──────────────────────────────────┤
│  ┌──────────────────────────────┐│
│  │ 👤 Roberto Almeida (Admin)  ││  ← Nome + papel
│  │ WhatsApp: (11) 99999-1234   ││
│  └──────────────────────────────┘│
│                                  │
│  ── EQUIPE ──                    │  ← Seção admin apenas
│  ┌──────────────────────────────┐│
│  │ 👤 Roberto Almeida          ││
│  │    Admin                     ││
│  └──────────────────────────────┘│
│  ┌──────────────────────────────┐│
│  │ 👤 Fernanda Souza           ││
│  │    Operador                  ││
│  └──────────────────────────────┘│
│  [+ Convidar pessoa]             │  ← Só admin vê
│                                  │
│  ── LOJA ──                      │
│  ┌──────────────────────────────┐│
│  │ Material de Construção ABC  ││
│  │ CNPJ 12.345.678/0001-90     ││
│  │ Simples Nacional · Anexo I  ││
│  │ Estado: SP                  ││
│  └──────────────────────────────┘│
│                                  │
│  ── CONTA ──                     │
│  [Sair da conta]                 │
│                                  │
└──────────────────────────────────┘
```

**Visão Operador (Fernanda):**

```
┌──────────────────────────────────┐
│  ← Voltar        Perfil         │
├──────────────────────────────────┤
│  ┌──────────────────────────────┐│
│  │ 👤 Fernanda Souza (Operador)││
│  │ WhatsApp: (11) 98888-5678   ││
│  └──────────────────────────────┘│
│                                  │
│  ── LOJA ──                      │
│  ┌──────────────────────────────┐│
│  │ Material de Construção ABC  ││
│  │ CNPJ 12.345.678/0001-90     ││
│  │ Simples Nacional · Anexo I  ││
│  │ Estado: SP                  ││
│  └──────────────────────────────┘│
│                                  │
│  ── CONTA ──                     │
│  [Sair da conta]                 │
│                                  │
└──────────────────────────────────┘
```

**Comportamento:**
- Visão Fernanda não mostra seção Equipe nem botão "Convidar pessoa"
- Dados da loja são somente-leitura para ambos (definidos pelo founder)

---

### TELA T9 — HISTÓRICO DE UPLOADS (P1)

**Quem usa:** Fernanda
**Quando:** Verificar status de uploads passados (F06, P2)

```
┌──────────────────────────────────┐
│  ← Voltar   Histórico           │  ← Header
├──────────────────────────────────┤
│  ── MAIO 2026 ──                 │
│                                  │
│  ┌──────────────────────────────┐│
│  │ 📤 15/05 · 14:30            ││
│  │    87 notas · Processado ✅ ││
│  │    3 pontos de atenção      ││
│  └──────────────────────────────┘│
│                                  │
│  ┌──────────────────────────────┐│
│  │ 📤 12/05 · 09:15            ││
│  │    32 notas · Processado ✅ ││
│  │    1 ponto de atenção       ││
│  └──────────────────────────────┘│
│                                  │
│  ┌──────────────────────────────┐│
│  │ 📤 08/05 · 16:40            ││
│  │    56 notas · Com erro ⚠️   ││  ← Alguns XMLs inválidos
│  │    52 OK · 4 ignorados      ││
│  └──────────────────────────────┘│
│                                  │
│  ── ABRIL 2026 ──                │
│  ┌──────────────────────────────┐│
│  │ 📤 28/04 · 11:20            ││
│  │    61 notas · Processado ✅ ││
│  └──────────────────────────────┘│
│                                  │
└──────────────────────────────────┘
```

**Estado: vazio (sem uploads anteriores)**

```
│       ┌────────────────────┐     │
│       │       📄           │     │
│       │                    │     │
│       │  Nenhum upload     │     │
│       │  registrado ainda. │     │
│       │                    │     │
│       │  [Carregar notas →]│     │
│       │                    │     │
│       └────────────────────┘     │
```

**Comportamento:**
- Agrupado por mês, ordenado do mais recente ao mais antigo
- Toque em um upload → navega para T1 com filtro aplicado para aquele lote

---

### Resumo de Telas e Estados

| Tela | Código | Prioridade | Estados |
|---|---|---|---|
| Dashboard (Home) | T1 | P0 | Normal, vazio (sem notas), vazio (sem inconsistências), loading (skeleton), erro |
| Upload de Notas | T2 | P0 | Pronto, processando (progresso), concluído, erro upload |
| Lista de Notas | T3 | P0 | Normal, vazio (mês sem notas), erro, loading |
| Detalhe da Nota | T4 | P0 | Normal, sem inconsistências, loading |
| Detalhe da Inconsistência | T5 | P0 | Checklist interativo, histórico, mudança de status, ignorada com motivo |
| Relatório do Contador | T6 | P0 | Normal, gerando PDF, erro geração |
| Link Mágico (Login) | T7 | P0 | Solicitar link, link enviado, link expirado, erro envio |
| Perfil / Configuração | T8 | P1 | Visão admin, visão operador |
| Histórico de Uploads | T9 | P1 | Normal, vazio, erro |

### Navegação entre Telas

```
T7 (Login) ──link mágico──→ T1 (Dashboard)
                                │
                    ┌───────────┼───────────┐
                    │           │           │
                    ▼           ▼           ▼
                T2 (Upload)  T3 (Notas)  T6 (Relatório)
                    │           │
                    │           ▼
                    │       T4 (Detalhe Nota)
                    │           │
                    │           ▼
                    │       T5 (Detalhe Inconsistência)
                    │
                    ▼
                T9 (Histórico Uploads)

Tab Bar: [Home (T1)]  [Notas (T3)]  [Perfil (T8)]
FAB (+):  → T2 (Upload) a partir de T1 ou T3
```

### Riscos e pontos de atenção

| Risco | Severidade | Mitigação |
|---|---|---|
| Muitas telas podem confundir o Roberto (ele só usa T1 e T5, mas a navegação pode poluir) | Média | Bottom tab bar tem só 3 ícones. Upload via FAB proeminente. Telas secundárias (T6, T8, T9) acessíveis via menu discreto |
| Checklist de ações (T5) ficar desatualizado conforme regras evoluem | Média | Checklist usa template por tipo de erro. Templates versionados. Atualizar 1 template = todas as instâncias atualizadas |
| PDF do contador (T6) não abrir no WhatsApp Web em celulares antigos | Baixa | PDF gerado em tamanho A4 otimizado. Testar no Android 8 (Chrome + WhatsApp) |
| Tela de link mágico depender de envio de WhatsApp (se API falhar, usuário não entra) | Média | Fallback: SMS com código de 6 dígitos. Exibir número de suporte: "Fale conosco: (11) 9XXXX-XXXX" |
| Scroll infinito na T3 pode perder performance com 500+ notas | Baixa | MVP tem ~200 notas/mês. Implementar virtualização se necessário (react-virtual) |
| ASCII mockups não capturam feedback visual de microinterações (bounce, fade, shimmer) | Baixa | Complementar com protótipo clicável no Figma antes do Sprint 4. Mockups ASCII são suficientes para briefing de desenvolvimento |

---

### Telas Pós-MVP (T10-T23)

As seguintes telas serão implementadas nas fases A-D do roadmap pós-MVP. Cada tela segue o sistema visual da Etapa 14 e os princípios de design definidos.

---

#### TELA T10 — ONBOARDING RAIO-X (Fase A)

**Quem usa:** Roberto (principal), Fernanda (secundário)
**Quando:** Primeiro acesso de nova organização

```
┌──────────────────────────────────┐
│  FiscoPilot                      │
├──────────────────────────────────┤
│                                  │
│  Bem-vindo ao FiscoPilot!        │
│                                  │
│  Vamos fazer um raio-x fiscal    │
│  da sua loja em 5 passos.        │
│                                  │
│  ┌──────────────────────────────┐│
│  │  ● ○ ○ ○ ○                   ││  ← Indicador de progresso
│  │  1   2 3 4 5                 ││
│  └──────────────────────────────┘│
│                                  │
│  ── PASSO 1: CARREGAR NOTAS ──   │
│                                  │
│  ┌──────────────────────────────┐│
│  │                              ││
│  │       📤                     ││  ← Drop zone simplificado
│  │                              ││     (sem menus, sem histórico)
│  │  Arraste seus XMLs aqui      ││
│  │  ou                          ││
│  │  [Selecionar arquivos]       ││
│  │                              ││
│  └──────────────────────────────┘│
│                                  │
│  💡 Dica: peça para sua auxiliar │
│  ou contador os arquivos .xml    │
│  dos últimos 30 dias.            │
│                                  │
│  [Pular]              [Avançar →]│
│                                  │
└──────────────────────────────────┘
```

**Estado: Passo 2 (processando)**

```
┌──────────────────────────────────┐
│  FiscoPilot                      │
├──────────────────────────────────┤
│                                  │
│  ┌──────────────────────────────┐│
│  │  ● ● ○ ○ ○                   ││
│  │  1   2 3 4 5                 ││
│  └──────────────────────────────┘│
│                                  │
│  ── PASSO 2: ANALISANDO ──       │
│                                  │
│       ┌────────────────────┐     │
│       │                    │     │
│       │   ⏳               │     │  ← Animação de processamento
│       │                    │     │
│       │   Analisando       │     │
│       │   87 notas...      │     │
│       │                    │     │
│       │   ████████░░ 80%   │     │  ← Barra de progresso
│       │                    │     │
│       └────────────────────┘     │
│                                  │
└──────────────────────────────────┘
```

**Estado: Passo 3 (resultados)**

```
┌──────────────────────────────────┐
│  FiscoPilot                      │
├──────────────────────────────────┤
│                                  │
│  ┌──────────────────────────────┐│
│  │  ● ● ● ○ ○                   ││
│  │  1   2 3 4 5                 ││
│  └──────────────────────────────┘│
│                                  │
│  ── PASSO 3: RESULTADOS ──       │
│                                  │
│  Analisamos 87 notas fiscais.    │
│                                  │
│  ┌────────┐ ┌────────┐ ┌──────┐ │
│  │   ✅   │ │   ⚠️   │ │  🔴  │ │
│  │   83   │ │    3   │ │   1   │ │
│  │  OK    │ │ Atenção│ │ Risco │ │
│  └────────┘ └────────┘ └──────┘ │
│                                  │
│  Encontramos 4 pontos de         │
│  atenção que precisam da         │
│  sua revisão.                    │
│                                  │
│  [← Voltar]          [Avançar →] │
│                                  │
└──────────────────────────────────┘
```

**Estado: Passo 4 (top 3 riscos)**

```
┌──────────────────────────────────┐
│  FiscoPilot                      │
├──────────────────────────────────┤
│                                  │
│  ┌──────────────────────────────┐│
│  │  ● ● ● ● ○                   ││
│  │  1   2 3 4 5                 ││
│  └──────────────────────────────┘│
│                                  │
│  ── PASSO 4: TOP 3 RISCOS ──     │
│                                  │
│  ┌──────────────────────────────┐│
│  │ 🔴 RISCO ALTO         R$ 412││
│  │ Distribuidora CimentoBom    ││
│  │ Código da operação diverge  ││
│  │ Nota #3521 · 10/05          ││
│  └──────────────────────────────┘│
│                                  │
│  ┌──────────────────────────────┐│
│  │ ⚠️ ATENÇÃO             R$ 87││
│  │ Telhanorte ABC              ││
│  │ Valor total não bate        ││
│  │ Nota #3518 · 12/05          ││
│  └──────────────────────────────┘│
│                                  │
│  ┌──────────────────────────────┐│
│  │ ⚠️ ATENÇÃO              R$ —││
│  │ Pisos e Revestimentos Sul   ││
│  │ Classificação fiscal        ││
│  │ Nota #3498 · 05/05          ││
│  └──────────────────────────────┘│
│                                  │
│  [← Voltar]          [Avançar →] │
│                                  │
└──────────────────────────────────┘
```

**Estado: Passo 5 (PDF para contador)**

```
┌──────────────────────────────────┐
│  FiscoPilot                      │
├──────────────────────────────────┤
│                                  │
│  ┌──────────────────────────────┐│
│  │  ● ● ● ● ●                   ││
│  │  1   2 3 4 5                 ││
│  └──────────────────────────────┘│
│                                  │
│  ── PASSO 5: RELATÓRIO ──        │
│                                  │
│  Pronto! Seu raio-x fiscal       │
│  está completo.                  │
│                                  │
│  ┌──────────────────────────────┐│
│  │  📄                          ││
│  │                              ││
│  │  Relatório Fiscal            ││  ← Preview do PDF
│  │  Maio 2026                   ││
│  │                              ││
│  │  87 notas analisadas         ││
│  │  4 pontos de atenção         ││
│  │  1 risco alto                ││
│  │                              ││
│  └──────────────────────────────┘│
│                                  │
│  Envie este PDF para seu         │
│  contador revisar.               │
│                                  │
│  ┌──────────────────────────────┐│
│  │      [Baixar PDF]            ││
│  └──────────────────────────────┘│
│                                  │
│  ┌──────────────────────────────┐│
│  │   [Enviar por WhatsApp]      ││
│  └──────────────────────────────┘│
│                                  │
│  [← Voltar]          [Concluir ✓]│
│                                  │
└──────────────────────────────────┘
```

**Comportamento:**
- Wizard de 5 passos com barra de progresso visual
- Botão "Pular" discreto (texto pequeno, cor cinza)
- Botão "Retomar onboarding" visível no dashboard até conclusão
- Sessão persistida em `onboarding_sessions` (pode retomar se sair)
- PDF gerado automaticamente no passo 5 usando dados do primeiro upload

---

#### TELA T11 — MENSAGEM PARA FORNECEDOR (Fase A)

**Quem usa:** Fernanda (principal), Roberto (secundário)
**Quando:** Ao clicar em "Gerar mensagem" na tela de detalhe da inconsistência (T5)

```
┌──────────────────────────────────┐
│  ← Voltar    Mensagem Fornecedor │
├──────────────────────────────────┤
│                                  │
│  ── MENSAGEM GERADA ──           │
│                                  │
│  ┌──────────────────────────────┐│
│  │                              ││
│  │  Olá, Distribuidora          ││  ← Texto editável
│  │  CimentoBom.                 ││
│  │                              ││
│  │  Recebemos a NF-e nº 3521    ││
│  │  e identificamos possível    ││
│  │  divergência no código da    ││
│  │  operação fiscal (CFOP).     ││
│  │                              ││
│  │  O código registrado foi     ││
│  │  6102, mas nosso sistema     ││
│  │  indica que o correto        ││
│  │  seria 1102.                 ││
│  │                              ││
│  │  Poderiam verificar e, se    ││
│  │  necessário, emitir carta    ││
│  │  de correção?                ││
│  │                              ││
│  │  Obrigado.                   ││
│  │                              ││
│  └──────────────────────────────┘│
│                                  │
│  ✏️ Você pode editar o texto     │
│  acima antes de enviar.          │
│                                  │
│  ── ENVIAR VIA ──                │
│                                  │
│  ┌──────────────────────────────┐│
│  │  📋 Copiar para clipboard    ││
│  └──────────────────────────────┘│
│                                  │
│  ┌──────────────────────────────┐│
│  │  💬 Enviar por WhatsApp      ││
│  └──────────────────────────────┘│
│                                  │
│  ┌──────────────────────────────┐│
│  │  ✉️ Enviar por e-mail        ││
│  └──────────────────────────────┘│
│                                  │
│  Status: Gerada                  │
│                                  │
└──────────────────────────────────┘
```

**Estado: Mensagem enviada**

```
┌──────────────────────────────────┐
│  ← Voltar    Mensagem Fornecedor │
├──────────────────────────────────┤
│                                  │
│  ── MENSAGEM ENVIADA ──          │
│                                  │
│       ┌────────────────────┐     │
│       │        ✅          │     │
│       │                    │     │
│       │  Mensagem enviada  │     │
│       │  por WhatsApp      │     │
│       │  em 15/05 14:32    │     │
│       │                    │     │
│       └────────────────────┘     │
│                                  │
│  ── HISTÓRICO ──                 │
│                                  │
│  15/05 14:32 · Enviada WhatsApp  │
│  15/05 14:30 · Gerada pelo       │
│                sistema           │
│                                  │
│  [Fechar]                        │
│                                  │
└──────────────────────────────────┘
```

**Comportamento:**
- Modal acessível via T5 (Detalhe da Inconsistência)
- Texto pré-preenchido com template da regra (R1-R8) + dados da nota
- Campo de texto editável (textarea)
- Botões de ação: Copiar, WhatsApp, E-mail
- Status persistido em `supplier_messages` (GENERATED, COPIED, SENT_WHATSAPP, SENT_EMAIL, DELIVERED, READ)
- WhatsApp: abre compartilhamento nativo do sistema
- E-mail: abre cliente de e-mail com texto pré-preenchido

---

#### TELA T12 — PAINEL DE ECONOMIA / RISCOS EVITADOS (Fase A)

**Quem usa:** Roberto (principal)
**Quando:** Menu lateral → "Economia"

```
┌──────────────────────────────────┐
│  ☰ FiscoPilot                    │
├──────────────────────────────────┤
│                                  │
│  ── RISCOS EVITADOS ──           │
│                                  │
│  ┌──────────────────────────────┐│
│  │                              ││
│  │  Este mês o FiscoPilot       ││
│  │  encontrou 4 inconsistências ││
│  │  em R$ 18.430 de notas.      ││
│  │                              ││
│  │  Impacto potencial           ││
│  │  estimado:                   ││
│  │                              ││
│  │      ~R$ 1.240               ││  ← Valor grande, cor verde
│  │                              ││
│  │  3 resolvidos · 1 pendente   ││
│  │                              ││
│  └──────────────────────────────┘│
│                                  │
│  ── MÉTRICAS ──                  │
│                                  │
│  ┌──────────────────────────────┐│
│  │  Total detectadas       12   ││
│  │  Resolvidas              9   ││
│  │  Pendentes               2   ││
│  │  Ignoradas               1   ││
│  │  Taxa de resolução    75%    ││
│  └──────────────────────────────┘│
│                                  │
│  ── HISTÓRICO (6 MESES) ──       │
│                                  │
│  Mai 2026  ~R$ 1.240  ████░░    │
│  Abr 2026  ~R$   890  ███░░░    │
│  Mar 2026  ~R$ 2.100  ██████░   │
│  Fev 2026  ~R$   340  █░░░░░    │
│  Jan 2026  ~R$   670  ██░░░░    │
│  Dez 2025  ~R$ 1.450  ████░░    │
│                                  │
│  ── PERÍODO ──                   │
│  [Este mês ▾]                    │
│                                  │
│  [Exportar PDF]                  │
│                                  │
└──────────────────────────────────┘
```

**Comportamento:**
- Card principal com valor em R$ (grande, cor verde)
- Métricas: total detectadas, resolvidas, pendentes, ignoradas, taxa de resolução
- Gráfico de barras com últimos 6 meses (detectados vs resolvidos)
- Filtro de período: mês/trimestre/ano
- Botão "Exportar PDF" gera relatório de economia
- Cálculo: `risco_evitado = SUM(estimated_impact) WHERE status = 'RESOLVIDA'`

---

#### TELA T13 — RELATÓRIO MENSAL DO DONO (Fase A)

**Quem usa:** Roberto (principal)
**Quando:** Menu lateral → "Relatório Mensal"

```
┌──────────────────────────────────┐
│  ☰ FiscoPilot                    │
├──────────────────────────────────┤
│                                  │
│  ── RELATÓRIO MENSAL ──          │
│                                  │
│  ┌──────────────────────────────┐│
│  │  Maio 2026 ▾                 ││  ← Seletor de mês
│  └──────────────────────────────┘│
│                                  │
│  ── PREVIEW ──                   │
│                                  │
│  ┌──────────────────────────────┐│
│  │  FiscoPilot                  ││
│  │  Seu Mês Fiscal              ││
│  │  Casa Forte · Maio 2026      ││
│  │                              ││
│  │  NOTAS ANALISADAS            ││
│  │       143                    ││
│  │                              ││
│  │  VALOR PROCESSADO            ││
│  │  R$ 284.500                  ││
│  │                              ││
│  │  INCONSISTÊNCIAS             ││
│  │       5                      ││
│  │                              ││
│  │  RISCOS RESOLVIDOS           ││
│  │       3                      ││
│  │                              ││
│  │  FORNECEDORES                ││
│  │  PROBLEMÁTICOS               ││
│  │       2                      ││
│  │                              ││
│  │  PENDÊNCIAS ABERTAS          ││
│  │       2                      ││
│  │                              ││
│  │  TOP 3 FORNECEDORES          ││
│  │  1. CimentoBom (3 notas)     ││
│  │  2. Telhanorte (1 nota)      ││
│  │  3. Pisos Sul (1 nota)       ││
│  │                              ││
│  │  RECOMENDAÇÃO                ││
│  │  "Atenção ao fornecedor      ││
│  │  CimentoBom. Considere       ││
│  │  pedir carta de correção."   ││
│  │                              ││
│  │  ⓘ Análise preliminar.       ││
│  │  Confirme com seu contador.  ││
│  └──────────────────────────────┘│
│                                  │
│  ┌──────────────────────────────┐│
│  │      [Baixar PDF]            ││
│  └──────────────────────────────┘│
│                                  │
│  ┌──────────────────────────────┐│
│  │   [Enviar por WhatsApp]      ││
│  └──────────────────────────────┘│
│                                  │
└──────────────────────────────────┘
```

**Comportamento:**
- Preview visual do PDF (1 página A4)
- Seletor de mês (dropdown)
- Botão "Baixar PDF" (grande, cor primária)
- Botão "Enviar por WhatsApp" (abre compartilhamento)
- PDF gerado em até 5 segundos usando pdfkit
- Inclui gráficos de barras (notas por semana, inconsistências por tipo)
- Disclaimer no rodapé: "Este relatório é uma análise automática preliminar. Confirme com seu contador antes de tomar decisões fiscais."

---

#### TELA T14 — KANBAN DE PENDÊNCIAS (Fase B)

**Quem usa:** Fernanda (principal), Roberto (secundário)
**Quando:** Bottom nav → "Pendências"

```
┌──────────────────────────────────┐
│  ☰ FiscoPilot                    │
├──────────────────────────────────┤
│                                  │
│  ── PENDÊNCIAS FISCAIS ──        │
│                                  │
│  Filtros: [Todos ▾] [Prazo ▾]   │
│                                  │
│  ┌──────────────────────────────┐│
│  │  PENDENTE (3)                ││
│  │  ┌────────────────────────┐  ││
│  │  │ 🔴 CimentoBom          │  ││
│  │  │ R$ 8.400 · CFOP        │  ││
│  │  │ Fernanda · Prazo: 20/05│  ││
│  │  └────────────────────────┘  ││
│  │  ┌────────────────────────┐  ││
│  │  │ 🔴 Areal Brita         │  ││
│  │  │ R$ 5.200 · CNPJ        │  ││
│  │  │ Roberto · Prazo: 22/05 │  ││
│  │  └────────────────────────┘  ││
│  │  ┌────────────────────────┐  ││
│  │  │ ⚠️ Pisos Sul           │  ││
│  │  │ R$ 520 · NCM           │  ││
│  │  │ Sem responsável        │  ││
│  │  └────────────────────────┘  ││
│  └──────────────────────────────┘│
│                                  │
│  ┌──────────────────────────────┐│
│  │  EM ANDAMENTO (2)            ││
│  │  ┌────────────────────────┐  ││
│  │  │ ⚠️ Telhanorte          │  ││
│  │  │ R$ 3.200 · Valor       │  ││
│  │  │ Roberto · Prazo: 25/05 │  ││
│  │  └────────────────────────┘  ││
│  │  ┌────────────────────────┐  ││
│  │  │ ⚠️ C&C Materiais       │  ││
│  │  │ R$ 1.150 · Soma        │  ││
│  │  │ Fernanda · Prazo: 28/05│  ││
│  │  └────────────────────────┘  ││
│  └──────────────────────────────┘│
│                                  │
│  ┌──────────────────────────────┐│
│  │  RESOLVIDA (5)               ││
│  │  ┌────────────────────────┐  ││
│  │  │ ✅ Ferragens do Zé     │  ││
│  │  │ R$ 2.890 · CST         │  ││
│  │  │ Resolvida em 12/05     │  ││
│  │  └────────────────────────┘  ││
│  │  ...                         ││
│  └──────────────────────────────┘│
│                                  │
│  ┌──────────────────────────────┐│
│  │  IGNORADA (1)                ││
│  │  ┌────────────────────────┐  ││
│  │  │ ⚠️ Pisos Sul           │  ││
│  │  │ R$ 520 · NCM           │  ││
│  │  │ Motivo: contador ok    │  ││
│  │  └────────────────────────┘  ││
│  └──────────────────────────────┘│
│                                  │
├──────────────────────────────────┤
│  [🏠 Home] [📋 Notas] [📌 Pend.] │
└──────────────────────────────────┘
```

**Painel lateral (ao clicar em card)**

```
┌──────────────────────────────────┐
│  ← Voltar    CimentoBom          │
├──────────────────────────────────┤
│                                  │
│  🔴 RISCO ALTO · Score 85        │
│                                  │
│  NF-e #3521 · R$ 8.400           │
│  CFOP divergente                 │
│                                  │
│  ── RESPONSÁVEL ──               │
│  [Fernanda Souza ▾]              │
│                                  │
│  ── PRAZO ──                     │
│  [20/05/2026]                    │
│                                  │
│  ── STATUS ──                    │
│  [Pendente ▾]                    │
│                                  │
│  ── COMENTÁRIOS ──               │
│                                  │
│  ┌──────────────────────────────┐│
│  │  Fernanda · 15/05 14:30      ││
│  │  Liguei para fornecedor.     ││
│  │  Vão verificar e retornar    ││
│  │  até amanhã.                 ││
│  └──────────────────────────────┘│
│                                  │
│  ┌──────────────────────────────┐│
│  │  Roberto · 15/05 10:15       ││
│  │  Prioridade alta. Resolver   ││
│  │  essa semana.                ││
│  └──────────────────────────────┘│
│                                  │
│  ┌──────────────────────────────┐│
│  │  Digite um comentário...     ││
│  └──────────────────────────────┘│
│  [Enviar]                        │
│                                  │
│  ── ANEXOS ──                    │
│  📎 carta_correcao.pdf (245 KB)  │
│  [+ Adicionar anexo]             │
│                                  │
│  ── AÇÕES ──                     │
│  [Enviar para contador]          │
│  [Enviar mensagem fornecedor]    │
│                                  │
└──────────────────────────────────┘
```

**Comportamento:**
- Board com 4 colunas: Pendente, Em andamento, Resolvida, Ignorada
- Drag & drop entre colunas (mobile: swipe horizontal)
- Clique no card → abre painel lateral com detalhes
- Painel lateral: responsável, prazo, status, comentários, anexos, ações
- Comentários persistidos em `inconsistency_comments`
- Anexos persistidos em `inconsistency_attachments` (PDF/imagem até 10MB)
- Atribuição persistida em `inconsistency_assignments`
- Botões "Enviar para contador" e "Enviar mensagem fornecedor" integrados com Features #2 e #5

---

#### TELA T15 — CONFIGURAÇÃO DOWNLOAD AUTOMÁTICO (Fase B)

**Quem usa:** Roberto (principal), Fernanda (secundário)
**Quando:** Menu lateral → "Configurações" → "Download Automático"

```
┌──────────────────────────────────┐
│  ← Voltar   Download Automático  │
├──────────────────────────────────┤
│                                  │
│  ── CERTIFICADO DIGITAL ──       │
│                                  │
│  ┌──────────────────────────────┐│
│  │  🟢 Certificado válido       ││
│  │                              ││
│  │  CNPJ: 12.345.678/0001-90    ││
│  │  Titular: Casa Forte Mat.    ││
│  │  Validade: 15/08/2026        ││
│  │                              ││
│  │  [Trocar certificado]        ││
│  └──────────────────────────────┘│
│                                  │
│  ── DOWNLOAD AUTOMÁTICO ──       │
│                                  │
│  ┌──────────────────────────────┐│
│  │  Download automático         ││
│  │  [====ON====]                ││  ← Toggle
│  │                              ││
│  │  Frequência                  ││
│  │  [Diário ▾]                  ││
│  │                              ││
│  │  Horário                     ││
│  │  [02:00 ▾]                   ││
│  └──────────────────────────────┘│
│                                  │
│  ── ÚLTIMOS DOWNLOADS ──         │
│                                  │
│  ┌──────────────────────────────┐│
│  │  15/05 02:00 · 12 notas      ││
│  │  ✅ Concluído                ││
│  └──────────────────────────────┘│
│                                  │
│  ┌──────────────────────────────┐│
│  │  14/05 02:00 · 8 notas       ││
│  │  ✅ Concluído                ││
│  └──────────────────────────────┘│
│                                  │
│  ┌──────────────────────────────┐│
│  │  13/05 02:00 · 0 notas       ││
│  │  ✅ Concluído                ││
│  └──────────────────────────────┘│
│                                  │
│  [Baixar agora manualmente]      │
│                                  │
└──────────────────────────────────┘
```

**Estado: Sem certificado**

```
┌──────────────────────────────────┐
│  ← Voltar   Download Automático  │
├──────────────────────────────────┤
│                                  │
│  ── CERTIFICADO DIGITAL ──       │
│                                  │
│  ┌──────────────────────────────┐│
│  │  ⚪ Sem certificado          ││
│  │                              ││
│  │  Para baixar notas           ││
│  │  automaticamente da Sefaz,   ││
│  │  você precisa fazer upload   ││
│  │  do seu certificado digital  ││
│  │  A1.                         ││
│  │                              ││
│  │  [Upload certificado A1]     ││
│  └──────────────────────────────┘│
│                                  │
│  💡 O certificado A1 é um        │
│  arquivo .pfx ou .p12 que        │
│  você recebe da certificadora.   │
│                                  │
│  ⓘ Seu certificado é             │
│  criptografado e armazenado      │
│  com segurança. Nunca            │
│  compartilhamos seus dados.      │
│                                  │
└──────────────────────────────────┘
```

**Modal: Upload de certificado**

```
┌──────────────────────────────────┐
│  Upload Certificado A1           │
├──────────────────────────────────┤
│                                  │
│  ┌──────────────────────────────┐│
│  │  📄                          ││
│  │                              ││
│  │  certificado.pfx             ││
│  │  2.3 KB                      ││
│  │                              ││
│  └──────────────────────────────┘│
│                                  │
│  Senha do certificado           │
│  ┌──────────────────────────────┐│
│  │  ••••••••                    ││
│  └──────────────────────────────┘│
│                                  │
│  ⓘ A senha é usada apenas para   │
│  extrair o certificado e não     │
│  é armazenada.                   │
│                                  │
│  [Cancelar]        [Upload]      │
│                                  │
└──────────────────────────────────┘
```

**Comportamento:**
- Status do certificado: válido (verde), vencendo (amarelo, <30 dias), vencido (vermelho)
- Toggle para ativar/desativar download automático
- Frequência: diário/semanal
- Horário preferido (dropdown)
- Histórico dos últimos 10 downloads
- Botão "Baixar agora manualmente" (trigger manual)
- Upload certificado: modal com arquivo .pfx/.p12 + senha
- Certificado criptografado com AES-256-GCM antes de armazenar
- Job diário (02:00 BRT) autentica na Sefaz, consulta NF-e, baixa XMLs, processa via pipeline

---

#### TELA T16 — ALERTAS CADASTRAIS (Fase B)

**Quem usa:** Roberto (principal), Fernanda (secundário)
**Quando:** Menu lateral → "Alertas Cadastrais"

```
┌──────────────────────────────────┐
│  ☰ FiscoPilot                    │
├──────────────────────────────────┤
│                                  │
│  ── ALERTAS CADASTRAIS ──        │
│                                  │
│  Filtros: [Todos ▾] [Lidos ▾]    │
│                                  │
│  ┌──────────────────────────────┐│
│  │ 🔴 CRÍTICO                   ││
│  │                              ││
│  │ Certificado digital vencendo ││
│  │ Seu certificado A1 vence em  ││
│  │ 7 dias (15/08/2026).         ││
│  │                              ││
│  │ [Ver detalhes] [Marcar lido] ││
│  └──────────────────────────────┘│
│                                  │
│  ┌──────────────────────────────┐│
│  │ 🔴 CRÍTICO                   ││
│  │                              ││
│  │ CNPJ inapto                  ││
│  │ Fornecedor Areal Brita       ││
│  │ (CNPJ 12.345.678/0001-90)    ││
│  │ está com situação cadastral  ││
│  │ "INAPTA" na Receita Federal. ││
│  │                              ││
│  │ [Ver detalhes] [Marcar lido] ││
│  └──────────────────────────────┘│
│                                  │
│  ┌──────────────────────────────┐│
│  │ ⚠️ ATENÇÃO                   ││
│  │                              ││
│  │ Inscrição estadual irregular ││
│  │ Fornecedor Telhanorte ABC    ││
│  │ (IE 123.456.789.000) está    ││
│  │ com IE "BAIXADA" no Sintegra.││
│  │                              ││
│  │ [Ver detalhes] [Marcar lido] ││
│  └──────────────────────────────┘│
│                                  │
│  ┌──────────────────────────────┐│
│  │ ℹ️ INFORMAÇÃO                ││
│  │                              ││
│  │ CNAE incompatível            ││
│  │ Fornecedor Pisos Sul         ││
│  │ tem CNAE principal           ││
│  │ "4751-2/00" (comércio de     ││
│  │ tintas) incompatível com     ││
│  │ NF-e de material de          ││
│  │ construção.                  ││
│  │                              ││
│  │ [Ver detalhes] [Marcar lido] ││
│  └──────────────────────────────┘│
│                                  │
│  ┌──────────────────────────────┐│
│  │ ⚠️ ATENÇÃO                   ││
│  │                              ││
│  │ Fornecedor recorrente        ││
│  │ Distribuidora CimentoBom     ││
│  │ tem 5 inconsistências nos    ││
│  │ últimos 90 dias.             ││
│  │                              ││
│  │ [Ver detalhes] [Marcar lido] ││
│  └──────────────────────────────┘│
│                                  │
└──────────────────────────────────┘
```

**Comportamento:**
- Lista de alertas com severidade (crítico/atenção/info)
- Cada alerta: tipo, entidade (fornecedor/organização), mensagem, data
- Filtros: severidade, tipo, lido/não lido
- Botão "Marcar como lido" em cada alerta
- Botão "Ver detalhes" abre modal com informações completas
- Alertas críticos disparam notificação WhatsApp
- Job semanal (domingo 03:00 BRT) consulta API da Receita Federal para verificar situação cadastral
- Tipos de alerta: CERTIFICATE_EXPIRING, CERTIFICATE_EXPIRED, CNPJ_INAPTO, IE_IRREGULAR, CNAE_INCOMPATIVEL, SUPPLIER_RECURRENT_ISSUE

---

#### TELA T17 — PORTAL DO CONTADOR (LOGIN) (Fase C)

**Quem usa:** Dona Célia (contadora)
**Quando:** Acesso via URL `/contador/login`

```
┌──────────────────────────────────┐
│  FiscoPilot Contador             │
├──────────────────────────────────┤
│                                  │
│       ┌────────────────────┐     │
│       │  [Logo FiscoPilot] │     │
│       └────────────────────┘     │
│                                  │
│  Portal do Contador              │
│                                  │
│  Acesse os dados fiscais dos     │
│  seus clientes em um só lugar.   │
│                                  │
│  ── LOGIN ──                     │
│                                  │
│  CPF                             │
│  ┌──────────────────────────────┐│
│  │  123.456.789-00              ││
│  └──────────────────────────────┘│
│                                  │
│  Senha                           │
│  ┌──────────────────────────────┐│
│  │  ••••••••                    ││
│  └──────────────────────────────┘│
│                                  │
│  [Entrar]                        │
│                                  │
│  Esqueci minha senha             │
│                                  │
│  ──────────────────────────────  │
│                                  │
│  Sou contador, quero me          │
│  cadastrar                       │
│                                  │
└──────────────────────────────────┘
```

**Estado: Login bem-sucedido**

```
┌──────────────────────────────────┐
│  FiscoPilot Contador             │
├──────────────────────────────────┤
│                                  │
│       ┌────────────────────┐     │
│       │        ✅          │     │
│       │                    │     │
│       │  Login realizado   │     │
│       │  com sucesso!      │     │
│       │                    │     │
│       │  Redirecionando... │     │
│       │                    │     │
│       └────────────────────┘     │
│                                  │
└──────────────────────────────────┘
```

**Comportamento:**
- Campo CPF com máscara (123.456.789-00)
- Campo senha (password)
- Validação de CPF usando algoritmo de dígitos verificadores
- JWT separado para contadores (campo `accountant_id` no payload)
- Expiração de 7 dias
- Link "Esqueci minha senha" envia e-mail de recuperação
- Link "Sou contador, quero me cadastrar" vai para `/contador/cadastro`
- Rate limit: 3 tentativas/15min
- Redireciona para `/contador/dashboard` após login bem-sucedido

---

#### TELA T18 — PORTAL DO CONTADOR (DASHBOARD CLIENTES) (Fase C)

**Quem usa:** Dona Célia (contadora)
**Quando:** Após login no portal do contador

```
┌──────────────────────────────────┐
│  FiscoPilot Contador             │
├──────────────────────────────────┤
│                                  │
│  Olá, Dona Célia                 │
│                                  │
│  ── SEUS CLIENTES ──             │
│                                  │
│  Busca: [________________]       │
│                                  │
│  Filtros: [Todos ▾]              │
│                                  │
│  ┌──────────────────────────────┐│
│  │  Casa Forte Materiais        ││
│  │  CNPJ: 12.345.678/0001-90    ││
│  │                              ││
│  │  Maio 2026                   ││
│  │  📋 143 notas                ││
│  │  ⚠️ 5 pendências             ││
│  │  🔴 1 risco alto             ││
│  │                              ││
│  │  Última atividade: 15/05     ││
│  │                              ││
│  │  [Ver dashboard →]           ││
│  └──────────────────────────────┘│
│                                  │
│  ┌──────────────────────────────┐│
│  │  Ferragens do Zé             ││
│  │  CNPJ: 98.765.432/0001-10    ││
│  │                              ││
│  │  Maio 2026                   ││
│  │  📋 87 notas                 ││
│  │  ✅ 0 pendências             ││
│  │                              ││
│  │  Última atividade: 14/05     ││
│  │                              ││
│  │  [Ver dashboard →]           ││
│  └──────────────────────────────┘│
│                                  │
│  ┌──────────────────────────────┐│
│  │  Telhanorte ABC              ││
│  │  CNPJ: 45.678.901/0001-23    ││
│  │                              ││
│  │  Maio 2026                   ││
│  │  📋 234 notas                ││
│  │  ⚠️ 12 pendências            ││
│  │  🔴 3 riscos altos           ││
│  │                              ││
│  │  Última atividade: 15/05     ││
│  │                              ││
│  │  [Ver dashboard →]           ││
│  └──────────────────────────────┘│
│                                  │
│  ┌──────────────────────────────┐│
│  │      [Exportar todos]        ││
│  └──────────────────────────────┘│
│                                  │
├──────────────────────────────────┤
│  [🏢 Clientes] [📊 Dashboard]    │
│  [📄 Exportações]                │
└──────────────────────────────────┘
```

**Comportamento:**
- Lista de clientes com resumo de status fiscal
- Busca por nome ou CNPJ
- Filtros: com pendências, sem pendências, inativos
- Cada card: nome, CNPJ, total notas mês, pendências, riscos altos, última atividade
- Clique em "Ver dashboard" → abre dashboard do cliente (read-only)
- Botão "Exportar todos" gera PDF consolidado de todos os clientes
- Query: JOIN entre `accountant_clients` (status = 'ACTIVE') e `organizations`, incluindo agregações de `nfe_documents` e `inconsistencies`
- Validação: contador só acessa dados de clientes onde `accountant_clients.accountant_id = contador_logado`

---

#### TELA T19 — SCORE DE FORNECEDORES (Fase C)

**Quem usa:** Roberto (principal)
**Quando:** Menu lateral → "Fornecedores"

```
┌──────────────────────────────────┐
│  ☰ FiscoPilot                    │
├──────────────────────────────────┤
│                                  │
│  ── SCORE DE FORNECEDORES ──     │
│                                  │
│  ── RANKING POR CATEGORIA ──     │
│                                  │
│  [Mais confiáveis] [Atenção]     │
│  [Risco]                         │
│                                  │
│  ── MAIS CONFIÁVEIS ──           │
│                                  │
│  ┌──────────────────────────────┐│
│  │  ✅ C&C Materiais            ││
│  │  CNPJ: 12.345.678/0001-90    ││
│  │                              ││
│  │  90 dias                     ││
│  │  📋 45 notas                 ││
│  │  ✅ 0 inconsistências        ││
│  │  💰 R$ 0 em risco            ││
│  │                              ││
│  │  [Ver detalhe →]             ││
│  └──────────────────────────────┘│
│                                  │
│  ┌──────────────────────────────┐│
│  │  ✅ Ferragens do Zé          ││
│  │  CNPJ: 98.765.432/0001-10    ││
│  │                              ││
│  │  90 dias                     ││
│  │  📋 32 notas                 ││
│  │  ✅ 0 inconsistências        ││
│  │  💰 R$ 0 em risco            ││
│  │                              ││
│  │  [Ver detalhe →]             ││
│  └──────────────────────────────┘│
│                                  │
│  ── ATENÇÃO ──                   │
│                                  │
│  ┌──────────────────────────────┐│
│  │  ⚠️ Telhanorte ABC           ││
│  │  CNPJ: 45.678.901/0001-23    ││
│  │                              ││
│  │  90 dias                     ││
│  │  📋 28 notas                 ││
│  │  ⚠️ 2 inconsistências        ││
│  │  💰 R$ 340 em risco          ││
│  │                              ││
│  │  Problemas recorrentes:      ││
│  │  · Valor total (2x)          ││
│  │                              ││
│  │  [Ver detalhe →]             ││
│  └──────────────────────────────┘│
│                                  │
│  ── RISCO ──                     │
│                                  │
│  ┌──────────────────────────────┐│
│  │  🔴 Distribuidora CimentoBom ││
│  │  CNPJ: 78.901.234/0001-56    ││
│  │                              ││
│  │  90 dias                     ││
│  │  📋 18 notas                 ││
│  │  🔴 5 inconsistências        ││
│  │  💰 R$ 2.340 em risco        ││
│  │                              ││
│  │  Problemas recorrentes:      ││
│  │  · CFOP divergente (3x)      ││
│  │  · Alíquota ICMS (2x)        ││
│  │                              ││
│  │  [Ver detalhe →]             ││
│  └──────────────────────────────┘│
│                                  │
│  Filtros: [Categoria ▾] [UF ▾]   │
│  Busca: [________________]       │
│                                  │
└──────────────────────────────────┘
```

**Tela de detalhe do fornecedor (T19.1)**

```
┌──────────────────────────────────┐
│  ← Voltar   CimentoBom           │
├──────────────────────────────────┤
│                                  │
│  🔴 RISCO                        │
│                                  │
│  Distribuidora CimentoBom        │
│  CNPJ: 78.901.234/0001-56        │
│                                  │
│  ── ÚLTIMOS 90 DIAS ──           │
│                                  │
│  ┌──────────────────────────────┐│
│  │  📋 18 notas                 ││
│  │  🔴 5 inconsistências (28%)  ││
│  │  🔴 3 de risco alto          ││
│  │  💰 R$ 2.340 em risco        ││
│  └──────────────────────────────┘│
│                                  │
│  ── PROBLEMAS RECORRENTES ──     │
│                                  │
│  ┌──────────────────────────────┐│
│  │  CFOP divergente        3x   ││
│  │  Alíquota ICMS          2x   ││
│  └──────────────────────────────┘│
│                                  │
│  ── HISTÓRICO DE NOTAS ──        │
│                                  │
│  ┌──────────────────────────────┐│
│  │  🔴 NF-e #3521 · 10/05       ││
│  │  R$ 8.400 · CFOP             ││
│  │  [Ver →]                     ││
│  └──────────────────────────────┘│
│                                  │
│  ┌──────────────────────────────┐│
│  │  🔴 NF-e #3498 · 05/05       ││
│  │  R$ 5.200 · Alíquota         ││
│  │  [Ver →]                     ││
│  └──────────────────────────────┘│
│                                  │
│  ┌──────────────────────────────┐│
│  │  ⚠️ NF-e #3456 · 28/04       ││
│  │  R$ 3.100 · CFOP             ││
│  │  [Ver →]                     ││
│  └──────────────────────────────┘│
│                                  │
│  [Ver todas as notas →]          │
│                                  │
└──────────────────────────────────┘
```

**Comportamento:**
- Ranking por categoria: "Mais confiáveis", "Atenção", "Risco"
- Cards de fornecedores: nome, CNPJ, score, categoria, total notas 90d, valor em risco
- Filtros: categoria, UF, valor mínimo
- Busca por nome ou CNPJ
- Clique em "Ver detalhe" → abre página de detalhe do fornecedor (T19.1)
- Página de detalhe: histórico de 90 dias, problemas recorrentes, lista de notas
- Botão "Ver todas as notas" filtra lista de notas por CNPJ do emitente
- View materializada `supplier_scores` atualizada diariamente via cron (04:00 BRT)
- Classificação: CONFIÁVEL (0 inconsistências), ATENCAO (taxa de erro <= 20%), RISCO (taxa de erro > 20% ou inconsistências de score >= 70)
- Só ativa após 90 dias de dados acumulados

---

#### TELA T20 — ASSISTENTE IA (CHAT PANEL) (Fase C)

**Quem usa:** Roberto (principal), Fernanda (secundário)
**Quando:** Painel lateral acessível via T5 (Detalhe da Inconsistência) ou botão flutuante no dashboard

```
┌──────────────────────────────────┐
│  Assistente IA              [✕]  │
├──────────────────────────────────┤
│                                  │
│  ── CONVERSA ──                  │
│                                  │
│  ┌──────────────────────────────┐│
│  │  🤖 Assistente               ││
│  │                              ││
│  │  Olá! Sou o assistente do    ││
│  │  FiscoPilot. Posso te        ││
│  │  ajudar a entender essa      ││
│  │  inconsistência.             ││
│  │                              ││
│  │  O que você gostaria de      ││
│  │  saber?                      ││
│  └──────────────────────────────┘│
│                                  │
│  ┌──────────────────────────────┐│
│  │  👤 Você                     ││
│  │                              ││
│  │  Explique em linguagem       ││
│  │  simples o que está errado   ││
│  │  nessa nota.                 ││
│  └──────────────────────────────┘│
│                                  │
│  ┌──────────────────────────────┐│
│  │  🤖 Assistente               ││
│  │                              ││
│  │  Claro! A nota fiscal        ││
│  │  #3521 da Distribuidora      ││
│  │  CimentoBom tem um problema  ││
│  │  no código da operação       ││
│  │  fiscal (CFOP).              ││
│  │                              ││
│  │  O fornecedor usou o código  ││
│  │  6102, que é para vendas     ││
│  │  dentro do estado. Mas como  ││
│  │  você está comprando, o      ││
│  │  correto seria 1102          ││
│  │  (compra para                ││
│  │  comercialização).           ││
│  │                              ││
│  │  Isso pode fazer você pagar  ││
│  │  ~R$ 412 a mais de imposto   ││
│  │  nesse mês.                  ││
│  │                              ││
│  │  👍 👎                       ││  ← Feedback
│  └──────────────────────────────┘│
│                                  │
│  ── PERGUNTAS RÁPIDAS ──         │
│                                  │
│  [Explique em linguagem simples] │
│  [O que perguntar ao contador?]  │
│  [Gere mensagem para fornecedor] │
│                                  │
│  ── SUA PERGUNTA ──              │
│                                  │
│  ┌──────────────────────────────┐│
│  │  Digite sua pergunta...      ││
│  └──────────────────────────────┘│
│  [Enviar]                        │
│                                  │
│  ⓘ Esta é uma orientação         │
│  preliminar. Confirme com seu    │
│  contador antes de agir.         │
│                                  │
└──────────────────────────────────┘
```

**Comportamento:**
- Painel lateral (slide da direita)
- Histórico de conversas (scroll vertical)
- Campo de input de pergunta
- Botões de perguntas rápidas: "Explique em linguagem simples", "O que perguntar ao contador?", "Gere mensagem para fornecedor"
- Disclaimer em toda resposta: "Esta é uma orientação preliminar. Confirme com seu contador antes de agir."
- Feedback (thumbs up/down) em cada resposta
- Botão "Copiar resposta"
- Botão "Fechar" (✕) no header
- Contexto da inconsistência enviado para IA (regra, valores, impacto)
- Limite de 150 palavras por resposta
- Rate limit: 10 perguntas por hora por usuário
- Conversas persistidas em `ai_conversations` (pergunta, resposta, modelo, tokens, latência, feedback)
- Guardrails: nunca calcular imposto, nunca dar parecer definitivo, sempre recomendar contador
- Validação de output antes de exibir (regex para detectar cálculo de imposto)
- Fallback para template se IA falhar

---

#### TELA T21 — PREPARAÇÃO REFORMA TRIBUTÁRIA (Fase D)

**Quem usa:** Roberto (principal)
**Quando:** Menu lateral → "Reforma Tributária"

```
┌──────────────────────────────────┐
│  ☰ FiscoPilot                    │
├──────────────────────────────────┤
│                                  │
│  ── PREPARAÇÃO CBS/IBS ──        │
│                                  │
│  ┌──────────────────────────────┐│
│  │                              ││
│  │  Score de preparação         ││
│  │                              ││
│  │       ╭───────╮              ││
│  │      ╱  65%   ╲             ││  ← Gauge circular
│  │      ╲       ╱              ││
│  │       ╰───────╯              ││
│  │                              ││
│  │  Sua loja está parcialmente  ││
│  │  preparada para a Reforma    ││
│  │  Tributária.                 ││
│  │                              ││
│  └──────────────────────────────┘│
│                                  │
│  ── CHECKLIST ──                 │
│                                  │
│  ── CADASTRO ──                  │
│  ┌──────────────────────────────┐│
│  │  ☑ CNPJ atualizado na        ││
│  │    Receita Federal           ││
│  │  ☑ Inscrição estadual        ││
│  │    regular                   ││
│  │  ☐ CNAE principal            ││
│  │    compatível com atividade  ││
│  └──────────────────────────────┘│
│                                  │
│  ── SISTEMAS ──                  │
│  ┌──────────────────────────────┐│
│  │  ☐ ERP atualizado para       ││
│  │    suportar CBS/IBS          ││
│  │  ☑ Fornecedor principal já   ││
│  │    emite com campos CBS/IBS  ││
│  └──────────────────────────────┘│
│                                  │
│  ── PROCESSOS ──                 │
│  ┌──────────────────────────────┐│
│  │  ☑ Contador informado sobre  ││
│  │    a transição               ││
│  │  ☐ Plano de classificação    ││
│  │    de produtos revisado      ││
│  └──────────────────────────────┘│
│                                  │
│  ── TRIBUTAÇÃO ──                │
│  ┌──────────────────────────────┐│
│  │  ☐ Entendeu a diferença      ││
│  │    entre ICMS e IBS          ││
│  │  ☐ Sabe quando CBS começa    ││
│  │    a valer para o Simples    ││
│  └──────────────────────────────┘│
│                                  │
│  ── TIMELINE 2026-2033 ──        │
│                                  │
│  2026 ●─────○─────○─────○       │
│       CBS    IBS   Trans  Completo
│       teste  teste ição          │
│                                  │
│  [Ver detalhes da timeline →]    │
│                                  │
│  ── ALERTAS CBS/IBS ──           │
│                                  │
│  ┌──────────────────────────────┐│
│  │  ⚠️ 3 notas em Maio/2026     ││
│  │  deveriam ter campos CBS/IBS ││
│  │  mas estão ausentes.         ││
│  │                              ││
│  │  [Ver notas →]               ││
│  └──────────────────────────────┘│
│                                  │
│  ┌──────────────────────────────┐│
│  │   [Gerar PDF de preparação]  ││
│  └──────────────────────────────┘│
│                                  │
└──────────────────────────────────┘
```

**Comportamento:**
- Score de preparação (0-100%) com gauge circular
- Checklist interativo por categoria (Cadastro, Sistemas, Processos, Tributação)
- Cada item: checkbox + descrição
- Timeline 2026-2033 com marcos da Reforma Tributária personalizados para o regime da organização
- Alertas CBS/IBS nos XMLs (quando aplicável)
- Botão "Gerar PDF de preparação" (inclui score, checklist, timeline, recomendações)
- Score calculado baseado em: (a) campos CBS/IBS presentes nos XMLs, (b) itens do checklist marcados como concluídos, (c) alertas de conformidade resolvidos
- Checklist persistido em `reform_checklist`
- Alertas persistidos em `cbs_ibs_alerts`

---

#### TELA T22 — INTEGRAÇÃO ERPs (Fase D)

**Quem usa:** Roberto (principal), Fernanda (secundário)
**Quando:** Menu lateral → "Configurações" → "Integração ERPs"

```
┌──────────────────────────────────┐
│  ← Voltar   Integração ERPs      │
├──────────────────────────────────┤
│                                  │
│  ── ERPs SUPORTADOS ──           │
│                                  │
│  ┌──────────────────────────────┐│
│  │  [Logo Bling]                ││
│  │  Bling                       ││
│  │                              ││
│  │  🟢 Conectado                ││
│  │  Última sync: 15/05 03:00    ││
│  │                              ││
│  │  [Sincronizar agora]         ││
│  │  [Desconectar]               ││
│  └──────────────────────────────┘│
│                                  │
│  ┌──────────────────────────────┐│
│  │  [Logo Tiny]                 ││
│  │  Tiny                        ││
│  │                              ││
│  │  🟢 Conectado                ││
│  │  Última sync: 15/05 03:00    ││
│  │                              ││
│  │  [Sincronizar agora]         ││
│  │  [Desconectar]               ││
│  └──────────────────────────────┘│
│                                  │
│  ┌──────────────────────────────┐│
│  │  [Logo Omie]                 ││
│  │  Omie                        ││
│  │                              ││
│  │  ⚪ Não conectado            ││
│  │                              ││
│  │  [Conectar]                  ││
│  └──────────────────────────────┘│
│                                  │
│  ┌──────────────────────────────┐│
│  │  [Logo Conta Azul]           ││
│  │  Conta Azul                  ││
│  │                              ││
│  │  ⚪ Não conectado            ││
│  │                              ││
│  │  [Conectar]                  ││
│  └──────────────────────────────┘│
│                                  │
│  ── HISTÓRICO DE SINCRONIZAÇÃO ──│
│                                  │
│  ┌──────────────────────────────┐│
│  │  15/05 03:00 · Bling         ││
│  │  ✅ 12 notas sincronizadas   ││
│  └──────────────────────────────┘│
│                                  │
│  ┌──────────────────────────────┐│
│  │  15/05 03:00 · Tiny          ││
│  │  ✅ 8 notas sincronizadas    ││
│  └──────────────────────────────┘│
│                                  │
│  ┌──────────────────────────────┐│
│  │  14/05 03:00 · Bling         ││
│  │  ✅ 15 notas sincronizadas   ││
│  └──────────────────────────────┘│
│                                  │
└──────────────────────────────────┘
```

**Modal: Conectar ERP (OAuth flow)**

```
┌──────────────────────────────────┐
│  Conectar Omie                   │
├──────────────────────────────────┤
│                                  │
│  ┌──────────────────────────────┐│
│  │  [Logo Omie]                 ││
│  │                              ││
│  │  Você será redirecionado     ││
│  │  para o site da Omie para    ││
│  │  autorizar o acesso.         ││
│  │                              ││
│  │  O FiscoPilot poderá:        ││
│  │  · Ler notas fiscais         ││
│  │  · Ler dados de clientes     ││
│  │  · Ler dados de produtos     ││
│  │                              ││
│  │  O FiscoPilot NÃO poderá:    ││
│  │  · Criar ou editar notas     ││
│  │  · Alterar dados             ││
│  │  · Enviar obrigações         ││
│  │                              ││
│  └──────────────────────────────┘│
│                                  │
│  [Cancelar]        [Autorizar]   │
│                                  │
└──────────────────────────────────┘
```

**Comportamento:**
- Grid de ERPs suportados com logos
- Status de cada conexão: conectado (verde), desconectado (cinza), erro (vermelho)
- Botão "Conectar" para cada ERP (OAuth flow)
- Botão "Desconectar" para ERPs conectados
- Botão "Sincronizar agora" (trigger manual)
- Última sincronização (data/hora)
- Histórico de sincronização (últimos 10)
- OAuth flow: redireciona para ERP, usuário autoriza, callback salva tokens
- Tokens criptografados com AES-256-GCM
- Sincronização automática diária (job noturno)
- Notas do ERP entram no pipeline de processamento existente
- Ao menos 2 conectores funcionais (Bling + Tiny) no lançamento
- Interface `ErpConnector` padroniza implementação de novos conectores

---

#### TELA T23 — CATÁLOGO DE PACOTES DE REGRAS (Fase D)

**Quem usa:** Roberto (principal), Founder (admin)
**Quando:** Menu lateral → "Configurações" → "Pacotes de Regras"

```
┌──────────────────────────────────┐
│  ← Voltar   Pacotes de Regras    │
├──────────────────────────────────┤
│                                  │
│  ── PACOTES ATIVOS ──            │
│                                  │
│  ┌──────────────────────────────┐│
│  │  📦 Base (R1-R8)             ││
│  │  Regras universais para      ││
│  │  todas as organizações       ││
│  │                              ││
│  │  [====ON====]                ││  ← Sempre ativo
│  │                              ││
│  │  [Ver regras →]              ││
│  └──────────────────────────────┘│
│                                  │
│  ┌──────────────────────────────┐│
│  │  📦 SP Material de Construção││
│  │  Regras específicas para     ││
│  │  lojas de material de        ││
│  │  construção em São Paulo     ││
│  │                              ││
│  │  [====ON====]                ││
│  │                              ││
│  │  [Ver regras →]              ││
│  └──────────────────────────────┘│
│                                  │
│  ── PACOTES DISPONÍVEIS ──       │
│                                  │
│  ┌──────────────────────────────┐│
│  │  📦 MG Material de Construção││
│  │  Regras específicas para     ││
│  │  lojas de material de        ││
│  │  construção em Minas Gerais  ││
│  │                              ││
│  │  [OFF====]                   ││
│  │                              ││
│  │  [Ver regras →]              ││
│  └──────────────────────────────┘│
│                                  │
│  ┌──────────────────────────────┐│
│  │  📦 Restaurantes             ││
│  │  Regras para setor de        ││
│  │  alimentação e restaurantes  ││
│  │                              ││
│  │  [OFF====]                   ││
│  │                              ││
│  │  [Ver regras →]              ││
│  └──────────────────────────────┘│
│                                  │
│  ┌──────────────────────────────┐│
│  │  📦 Confecção                ││
│  │  Regras para indústria e     ││
│  │  comércio de roupas          ││
│  │                              ││
│  │  [OFF====]                   ││
│  │                              ││
│  │  [Ver regras →]              ││
│  └──────────────────────────────┘│
│                                  │
│  ┌──────────────────────────────┐│
│  │  📦 Distribuidora de Bebidas ││
│  │  Regras para distribuidoras  ││
│  │  de bebidas e alimentos      ││
│  │                              ││
│  │  [OFF====]                   ││
│  │                              ││
│  │  [Ver regras →]              ││
│  └──────────────────────────────┘│
│                                  │
│  ┌──────────────────────────────┐│
│  │  📦 Lucro Presumido          ││
│  │  Regras para organizações    ││
│  │  no regime Lucro Presumido   ││
│  │                              ││
│  │  [OFF====]                   ││
│  │                              ││
│  │  [Ver regras →]              ││
│  └──────────────────────────────┘│
│                                  │
│  Busca: [________________]       │
│  Filtros: [Setor ▾] [UF ▾]       │
│                                  │
└──────────────────────────────────┘
```

**Modal: Detalhe do pacote**

```
┌──────────────────────────────────┐
│  Pacote: SP Material Construção  │
├──────────────────────────────────┤
│                                  │
│  Setor: Material de Construção   │
│  UF: São Paulo                   │
│  Regime: Simples Nacional        │
│  Versão: 2026-01                 │
│                                  │
│  ── REGRAS INCLUÍDAS ──          │
│                                  │
│  ┌──────────────────────────────┐│
│  │  R9 · ICMS-ST específico SP  ││
│  │  Verifica se NCM consta na   ││
│  │  lista de ST do estado de    ││
│  │  São Paulo (Convênio ICMS    ││
│  │  142/2018 + legislação SP)   ││
│  └──────────────────────────────┘│
│                                  │
│  ┌──────────────────────────────┐│
│  │  R10 · Alíquota interna SP   ││
│  │  Compara alíquota de ICMS    ││
│  │  com tabela interna do       ││
│  │  estado de São Paulo         ││
│  └──────────────────────────────┘│
│                                  │
│  ┌──────────────────────────────┐│
│  │  R11 · NCM materiais SP      ││
│  │  Verifica se NCM pertence    ││
│  │  a capítulo típico de        ││
│  │  material de construção      ││
│  │  (lista expandida SP)        ││
│  └──────────────────────────────┘│
│                                  │
│  [Fechar]                        │
│                                  │
└──────────────────────────────────┘
```

**Comportamento:**
- Lista de pacotes disponíveis (nome, descrição, setor, UF, regime)
- Toggle "Ativado/Desativado" para cada pacote
- Pacotes ativos destacados no topo
- Detalhe do pacote (modal com lista de regras incluídas)
- Busca por nome/setor/UF
- Filtros: setor, UF, regime
- Pacote base (R1-R8) sempre ativo (não pode ser desativado)
- Pacotes setoriais adicionam regras, não substituem
- Motor de regras carrega pacotes ativos dinamicamente via `organization_rule_packs`
- Ao menos 3 pacotes funcionais no lançamento: SP construção, MG construção, Lucro Presumido
- Testes cruzados entre pacotes para evitar inconsistências

---

### Próximo passo recomendado

Aprovar as 9 telas aqui definidas e prosseguir para a **Etapa 16 — Microcopy**, onde cada texto de interface será refinado seguindo o tom de voz da Etapa 14.

### Prompt da próxima etapa

```
Execute a Etapa 16 — Microcopy.
Siga exatamente o formato obrigatório de resposta.
Seja específico para o mercado brasileiro e para o ICP de lojas de material de construção no Simples Nacional.
Utilize o tom de voz definido na Etapa 14: segunda pessoa, frases curtas, sem siglas não explicadas, português claro.
Entregue o microcopy para cada tela (T1 a T9) cobrindo: labels, placeholders, mensagens de estado vazio, erros, sucesso, tooltips, CTAs, e-mails transacionais e mensagens de WhatsApp.
```

---

## Etapa 16 — Microcopy

### Objetivo da etapa

Definir cada palavra, frase, label, placeholder, mensagem de erro, tooltip e comunicação transacional que aparece no FiscoPilot MVP — garantindo que o tom de voz definido na Etapa 14 seja aplicado de forma consistente em todas as telas (T1 a T9), e-mails e mensagens de WhatsApp. O microcopy deve ser compreensível para o Roberto (51 anos, ensino médio, baixa maturidade digital) sem soar infantilizado para a Fernanda ou a Dona Célia.

### Premissas adotadas

| # | Premissa | Justificativa |
|---|---|---|
| P1 | Toda sigla fiscal (CFOP, NCM, CST, DAS) é sempre acompanhada de explicação na primeira ocorrência de cada tela | Roberto não sabe o que significam; precisa aprender sem sair da tela |
| P2 | Números de impacto financeiro são sempre precedidos de "~" (aproximado) ou "até", nunca como valor exato | Imprecisão inerente à estimativa; afirmar valor exato gera risco de confiança se o cálculo real divergir |
| P3 | O produto nunca acusa o contador de erro. Frases como "seu contador errou" são proibidas | Dona Célia é gatekeeper; aliená-la quebra o produto |
| P4 | Toda mensagem de erro técnico (rede, servidor) inclui: o que aconteceu + o que o usuário deve fazer agora + canal de contato humano | Usuário com baixa maturidade digital não sabe o que fazer com "Erro 500" |
| P5 | CTAs usam verbo de ação no infinitivo informal: "Ver", "Carregar", "Baixar" — nunca "Clique aqui" | Regra de ouro da Etapa 14; consistência com padrão mobile brasileiro |

### Decisões recomendadas

| Decisão | Conteúdo | Status |
|---|---|---|
| D1 | Microcopy organizado por tela (T1-T9) + canais transacionais (e-mail, WhatsApp). Cada elemento classificado como: label, placeholder, estado, tooltip/help, CTA, erro, sucesso | Decisão de organização |
| D2 | Tom de voz: segunda pessoa ("você"), frases de até 15 palavras, zero siglas sem explicação, zero exclamação exceto confirmação de ação concluída | Decisão de UX writing |
| D3 | Disclaimer fiscal aparece em 3 níveis de visibilidade: (a) fixo no rodapé de toda tela de conteúdo, (b) inline em cards de inconsistência, (c) cabeçalho do PDF do contador | Decisão de compliance |
| D4 | E-mails transacionais têm versão texto puro (sem HTML pesado) para leitura no celular do Roberto | Decisão de comunicação |
| D5 | Mensagens de WhatsApp seguem o limite de 4096 caracteres da API e incluem sempre um CTA claro e um link mágico | Decisão técnica |

---

### T1 — DASHBOARD (HOME)

#### Labels

| Elemento | Texto | Nota |
|---|---|---|
| Saudação | `Olá, {nome}` | Nome do Roberto ou Fernanda. Sem "Bom dia" — o horário pode estar errado no celular. Se nome ausente: `Olá` |
| Mês corrente | `{Mês} {Ano}` | Ex.: `Maio 2026`. Sempre em português, sem abreviação |
| Card resumo | `{N} notas este mês` | Ex.: `143 notas este mês` |
| Timestamp | `Processadas em {DD/MM} às {HH:MM}` | Ex.: `Processadas em 15/05 às 14:30` |
| Card OK | `OK` | Abaixo do número. Verde. |
| Card Atenção | `Atenção` | Abaixo do número. Âmbar. |
| Card Risco | `Risco` | Abaixo do número. Vermelho. |
| Seção inconsistências | `Pontos de atenção` | Não usar "Erros" ou "Problemas" |
| Link para detalhe | `Ver →` | Seta para direita indica navegação |
| Tab Home | `Home` | Ícone + texto. Familiar para quem usa app de banco |
| Tab Notas | `Notas` | Ícone + texto |
| Tab Perfil | `Perfil` | Ícone + texto |
| FAB (float action button) | `+` | Ícone de adição. Tooltip ao pressionar: `Carregar notas` |

#### Estados

| Estado | Mensagem |
|---|---|
| **Vazio — sem notas no mês** | `Você ainda não carregou notas este mês. [Carregar agora →]` |
| **Vazio — notas carregadas, zero inconsistências** | `{N} notas analisadas. Nenhum problema encontrado. ✅` Subtítulo: `Seu fiscal está em dia.` |
| **Loading — skeleton** | Skeleton screen (shimmer) sem texto. Primeiro carregamento <=2s mostra dados direto |
| **Erro — rede** | `Não conseguimos atualizar seus dados. [Tentar novamente]` Subtítulo: `Se continuar, fale com a gente pelo WhatsApp.` |
| **Erro — servidor** | `Algo deu errado. Já fomos avisados. Tente de novo em alguns minutos.` |

#### Tooltips / Help

| Elemento | Tooltip |
|---|---|
| Ícone ⓘ ao lado do card "Risco" | `Risco alto: inconsistência que pode gerar multa ou imposto a mais. Resolva o quanto antes.` |
| Ícone ⓘ ao lado do card "Atenção" | `Ponto de atenção: inconsistência que merece conferência, mas com menor urgência.` |
| Link "O que significa?" em card de inconsistência | Expande inline com definição em português claro (ex.: `CFOP é o código que identifica o tipo de operação fiscal — se é compra, venda, devolução, etc.`) |

#### Disclaimer fixo (rodapé)

```
ⓘ Análise preliminar automática. Confirme com seu contador.
```

---

### T2 — UPLOAD DE NOTAS

#### Labels

| Elemento | Texto | Nota |
|---|---|---|
| Header | `Carregar Notas` | Ação clara. Não "Upload de XML" |
| Botão voltar | `← Voltar` | Padrão em todas as telas secundárias |
| Área de drop zone | `Arraste seus arquivos XML ou ZIP aqui` | Instrução objetiva |
| Botão seletor | `Selecionar arquivos` | Abre seletor nativo do SO |
| Texto de ajuda | `Dica: você também pode enviar os XMLs por e-mail para notas@copilotofiscal.com` | Canal alternativo sempre visível |
| Seção histórico | `Últimos envios` | Aparece se há uploads anteriores |
| Contador de progresso | `{X} de {Y} notas` | Ex.: `58 de 87 notas` |
| Mensagem de tempo | `Isso leva menos de 1 minuto` | Gerencia expectativa de espera |
| Resultado — sucesso | `{N} notas analisadas` | Ex.: `87 notas analisadas` |
| Resultado — inconsistências | `{N} pontos de atenção` | Ex.: `3 pontos de atenção` |
| CTA pós-processamento | `Ver resumo →` | Navega para T1 (Dashboard) |
| CTA secundário | `Carregar mais` | Reinicia fluxo de upload |

#### Estados

| Estado | Mensagem |
|---|---|
| **Drop zone vazia (padrão)** | `Arraste seus arquivos XML ou ZIP aqui` + `ou` + `[Selecionar arquivos]` |
| **Arquivo arrastado sobre drop zone** | `Solte para começar a análise` — borda azul sólida |
| **Processando** | Barra de progresso + `{X} de {Y} notas` + `Isso leva menos de 1 minuto` |
| **Concluído — com inconsistências** | `✅ {N} notas analisadas. {M} pontos de atenção. [Ver resumo →] [Carregar mais]` |
| **Concluído — sem inconsistências** | `✅ {N} notas analisadas. Nenhum problema encontrado. [Ver resumo →] [Carregar mais]` |
| **Erro — arquivo inválido** | `Alguns arquivos não eram notas fiscais e foram ignorados. {N} notas processadas.` |
| **Erro — arquivo muito grande** | `O arquivo é muito grande. Tente dividir em lotes menores de até 200 notas.` |
| **Erro — formato não suportado** | `Este formato não é aceito. Envie arquivos .xml ou .zip.` |
| **Erro — upload falhou** | `Não foi possível processar seus arquivos. Verifique sua conexão e tente de novo.` |

#### Toast (mensagens temporárias)

| Situação | Toast |
|---|---|
| Upload iniciado | `Enviando {N} notas...` |
| Upload concluído | `{N} notas analisadas ✅` (3 segundos, verde) |
| Upload cancelado | `Envio cancelado` |

---

### T3 — LISTA DE NOTAS

#### Labels

| Elemento | Texto | Nota |
|---|---|---|
| Header | `Notas` | Simples e direto |
| Campo de busca | Placeholder: `Buscar por fornecedor` | Busca textual por nome do emitente |
| Seletor de período | `{Mês} {Ano}` com `[Filtrar]` | Ex.: `Mai 2026 [Filtrar]` |
| Indicador de risco — Risco Alto | `🔴` | Prefixo visual antes do nome do fornecedor |
| Indicador de risco — Atenção | `⚠️` | Prefixo visual |
| Indicador de risco — OK | `✅` | Prefixo visual |
| Label de score | `Score {N}` | Ex.: `Score 85`. Só aparece se score > 0 |
| Link para detalhe | `Ver →` | Consistente com T1 |
| Contador de itens | `Exibindo {X} de {Y} notas` | Ex.: `Exibindo 4 de 143 notas` |
| Botão FAB | `+` | Leva para T2 (Upload) |

#### Estados

| Estado | Mensagem |
|---|---|
| **Vazio — mês sem notas** | `Você ainda não carregou notas este mês. [Carregar agora →]` |
| **Vazio — busca sem resultados** | `Nenhuma nota encontrada para "{termo}". Tente outro nome de fornecedor.` |
| **Loading** | Skeleton com 5 linhas simulando cards de nota |
| **Erro** | `Não foi possível carregar a lista de notas. [Tentar novamente]` |

---

### T4 — DETALHE DA NOTA

#### Labels

| Elemento | Texto | Nota |
|---|---|---|
| Header | `Nota #{numero}` | Ex.: `Nota #3521` |
| Campo: Emitente | `{Nome}` | Ex.: `Distribuidora CimentoBom` |
| Campo: CNPJ | `CNPJ {numero}` | Ex.: `CNPJ 12.345.678/0001-90` |
| Campo: Data | `Data: {DD/MM/AAAA}` | Ex.: `Data: 10/05/2026` |
| Campo: Valor | `Valor: R$ {valor}` | Ex.: `Valor: R$ 8.400,00` |
| Campo: Chave | `Chave: {inicio}...` | Ex.: `Chave: 3521 0510 1234...` — truncada, toque expande |
| Seção inconsistências | `Inconsistências ({N})` | Ex.: `Inconsistências (1)` |
| Badge Risco Alto | `Risco alto` | Fundo vermelho claro |
| Badge Atenção | `Atenção` | Fundo âmbar claro |
| Score | `Score {N}` | Ex.: `Score 85` |
| Campo: Encontrado | `Encontrado: {valor}` | Ex.: `Encontrado: CFOP 6102 (saída)` |
| Campo: Esperado | `Esperado: {valor}` | Ex.: `Esperado: CFOP 1102 (entrada)` |
| Impacto estimado | `💰 Impacto estimado:` | Ícone + label. Valor em reais abaixo |
| Tooltip CFOP | `O que significa CFOP?` | Expansível inline |
| CTA ação | `O que fazer? →` | Navega para T5 |
| Seção itens | `Itens da nota` | Lista de produtos |
| Label item — Qtd | `Qtd: {N}` | Ex.: `Qtd: 200` |
| Label item — NCM | `NCM: {codigo}` | Ex.: `NCM: 2523.29.00` |
| Label item — Valor un. | `Valor un.: R$ {valor}` | Ex.: `Valor un.: R$ 42,00` |
| Label item — Total | `Total: R$ {valor}` | Ex.: `Total: R$ 8.400,00` |

#### Estados

| Estado | Mensagem |
|---|---|
| **Sem inconsistências** | `✅ Nenhum problema encontrado nesta nota.` |
| **Loading** | Skeleton com cards simulando dados da nota |
| **Erro** | `Não foi possível carregar os detalhes desta nota. [Tentar novamente]` |

#### Tooltips / Help

| Elemento | Texto expandido |
|---|---|
| `O que significa CFOP?` | `CFOP é o Código Fiscal de Operações e Prestações. É um número de 4 dígitos que indica o tipo de operação: se é compra, venda, devolução, e se foi dentro ou fora do estado.` |
| `O que significa NCM?` | `NCM é a Nomenclatura Comum do Mercosul. É um código de 8 dígitos que classifica o tipo de produto. Cada NCM tem uma alíquota de imposto diferente.` |
| `O que significa CST?` | `CST é o Código de Situação Tributária. Indica como o imposto (PIS/COFINS) deve ser calculado para aquela operação.` |

#### Disclaimer inline (dentro do card de inconsistência)

```
ⓘ Esta análise não substitui a validação do seu contador.
```

---

### T5 — DETALHE DA INCONSISTÊNCIA + CHECKLIST

#### Labels

| Elemento | Texto | Nota |
|---|---|---|
| Header | `Ponto de atenção` | Não "Erro fiscal" ou "Inconsistência" |
| Badge de classificação | `Risco alto` ou `Atenção` | Consistente com T4 |
| Score | `Score {N}` | Ex.: `Score 85` |
| Seção 1 | `O que aconteceu` | Explicação do problema |
| Seção 2 | `O que isso significa` | Consequência em português claro |
| Seção 3 | `O que fazer` | Checklist de ações |
| Campo de motivo (ignorada) | Placeholder: `Por que você decidiu ignorar este alerta?` | Obrigatório |
| Label status | `Status` | Acima do dropdown |
| Dropdown — Pendente | `Pendente` | Padrão |
| Dropdown — Em andamento | `Em andamento` | |
| Dropdown — Resolvida | `Resolvida` | |
| Dropdown — Ignorada | `Ignorada` | |
| Botão ação rápida | `Marcar como Resolvida` | Só aparece se status != Resolvida e todos os checkboxes estão marcados |
| Seção histórico | `Histórico` | Log de ações |
| Aviso ignorar | `⚠️ Ao ignorar, você assume a responsabilidade por esta decisão fiscal.` | Só visível quando status = Ignorada |
| Botão confirmar motivo | `Confirmar` | Só visível no estado de edição de motivo |

#### Checklist de ações por tipo de regra

**R1 — CFOP divergente:**

| # | Texto |
|---|---|
| ☐ | `Ligue para {fornecedor} — {telefone}` |
| ☐ | `Peça uma carta de correção com CFOP {cfop_esperado}` |
| ☐ | `Peça para reemitir a nota fiscal com o código correto` |
| ☐ | `Avise {contador} sobre essa correção` |

**R2 — Alíquota ICMS divergente:**

| # | Texto |
|---|---|
| ☐ | `Confira a alíquota de ICMS para {produto} no seu estado ({UF})` |
| ☐ | `Ligue para {fornecedor} e peça para corrigir a alíquota na nota` |
| ☐ | `Solicite nota fiscal corrigida com alíquota de {aliquota_esperada}%` |
| ☐ | `Avise {contador} sobre a divergência` |

**R3 — NCM suspeito:**

| # | Texto |
|---|---|
| ☐ | `Confira se o NCM {ncm_encontrado} está correto para {produto}` |
| ☐ | `Consulte a tabela NCM no site da Receita Federal` |
| ☐ | `Peça para {fornecedor} corrigir a classificação fiscal do produto` |
| ☐ | `Se tiver dúvida, confirme com {contador} antes de agir` |

**R5 — Valor divergente:**

| # | Texto |
|---|---|
| ☐ | `Confira o valor total com o pedido de compra original` |
| ☐ | `Ligue para {fornecedor} e informe a diferença de R$ {diferenca}` |
| ☐ | `Peça carta de correção ou nota complementar` |

**Regra genérica (fallback):**

| # | Texto |
|---|---|
| ☐ | `Entenda o que está diferente` |
| ☐ | `Entre em contato com {fornecedor}` |
| ☐ | `Peça a correção do documento fiscal` |
| ☐ | `Avise {contador} sobre a situação` |

#### Estados

| Estado | Mensagem |
|---|---|
| **Checklist concluído** | Toast: `Todos os passos concluídos ✅` + sugestão: `Deseja marcar como Resolvida? [Sim]` |
| **Status alterado** | Toast verde 3s: `Marcado como {status}` |
| **Motivo vazio ao ignorar** | Erro inline: `Informe o motivo para ignorar este alerta.` |
| **Histórico vazio** | Não exibe seção "Histórico" (impossível — sempre há ao menos 1 entrada de detecção) |
| **Loading** | Skeleton com seções simuladas |
| **Erro ao salvar** | `Não foi possível salvar. [Tentar novamente]` |

---

### T6 — RELATÓRIO DO CONTADOR

#### Labels

| Elemento | Texto | Nota |
|---|---|---|
| Header | `Relatório do mês` | Simples e funcional |
| Período | `{Mês} {Ano}` | Ex.: `Maio 2026` |
| Seção resumo | `📋 Resumo do mês` | |
| Linha: Total processadas | `Notas processadas: {N}` | Ex.: `143` |
| Linha: Sem problemas | `Sem problemas: {N}` | Ex.: `138` |
| Linha: Pontos de atenção | `Pontos de atenção: {N}` | Ex.: `3` |
| Linha: Risco alto | `Risco alto: {N}` | Ex.: `2` |
| Linha: Resolvidos | `Resolvidos: {N}` | Ex.: `3` |
| Linha: Pendentes | `Pendentes: {N}` | Ex.: `2` |
| Seção inconsistências | `Inconsistências` | |
| Botão download | `Baixar PDF` | Ação primária |
| Botão compartilhar | `Enviar por WhatsApp` | Abre WhatsApp com mensagem pré-preenchida |

#### Conteúdo do PDF

| Seção | Texto |
|---|---|
| Cabeçalho | Logo FiscoPilot + `Relatório Fiscal — {Mês}/{Ano}` |
| Identificação | `Empresa: {nome_fantasia}` / `CNPJ: {cnpj}` / `Regime: Simples Nacional` / `Período: {DD/MM/AAAA} a {DD/MM/AAAA}` |
| Disclaimer (box destacado) | `Este relatório foi gerado automaticamente pelo FiscoPilot como apoio à análise do contador responsável. Não substitui a validação profissional nem a apuração oficial dos tributos.` |
| Tabela de inconsistências | Colunas: `Nota`, `Fornecedor`, `Valor`, `Tipo de inconsistência`, `Risco`, `Status`, `Ação sugerida` |
| Rodapé | `Gerado em {DD/MM/AAAA} às {HH:MM} pelo FiscoPilot — copilotofiscal.com` |

#### Mensagem pré-preenchida WhatsApp

```
{Dona Célia / nome do contador}, segue o relatório fiscal de {Mês}/{Ano} da {nome da loja}. Já conferi o que estava pendente. [link do PDF]
```

#### Estados

| Estado | Mensagem |
|---|---|
| **Mês sem inconsistências** | Resumo mostra `0` em todos os campos de risco. Seção "Inconsistências" substituída por: `Nenhuma inconsistência encontrada em {N} notas processadas.` |
| **Gerando PDF** | `Preparando seu relatório...` com spinner |
| **Erro geração PDF** | `Não foi possível gerar o PDF. [Tentar novamente]` |

---

### T7 — LINK MÁGICO / LOGIN

#### Labels

| Elemento | Texto | Nota |
|---|---|---|
| Tagline | `Suas notas fiscais explicadas.` | Reforço da proposta de valor |
| Label campo | `Digite seu WhatsApp:` | |
| Placeholder campo | `(11) 9XXXX-XXXX` | Máscara de telefone brasileiro |
| Botão primário | `Enviar link de acesso` | Ação clara |
| Texto alternativo | `Ou acesse pelo link que enviamos no seu WhatsApp.` | |
| Termos | `Ao acessar, você concorda com os Termos de Uso.` | Link em "Termos de Uso" |

#### Estados

| Estado | Mensagem |
|---|---|
| **Link enviado** | `Enviamos um link de acesso para o seu WhatsApp.` + `{numero mascarado}` + `Toque no link para entrar.` |
| **Não recebeu** | Botão: `Reenviar link` |
| **Usar outro número** | Botão: `Usar outro número` |
| **Link expirado** | `Seu link expirou por segurança. Links de acesso valem por 24 horas. [Enviar novo link]` |
| **Número não encontrado** | `Este WhatsApp não está cadastrado. Fale com a gente: (11) 9XXXX-XXXX.` |
| **Erro envio** | `Não foi possível enviar o link. Tente de novo ou fale com a gente pelo WhatsApp: (11) 9XXXX-XXXX.` |
| **WhatsApp inválido** | `Este número de WhatsApp não parece válido. Confira e tente de novo.` |

---

### T8 — PERFIL / CONFIGURAÇÃO (P1)

#### Labels (Visão Admin)

| Elemento | Texto | Nota |
|---|---|---|
| Header | `Perfil` | |
| Nome + papel | `{nome} (Admin)` ou `{nome} (Operador)` | |
| Campo WhatsApp | `WhatsApp: {numero}` | Somente leitura |
| Seção equipe | `Equipe` | Só admin vê |
| Botão convidar | `+ Convidar pessoa` | Futuro — não funcional no MVP, exibido como disabled com tooltip: `Em breve` |
| Seção loja | `Loja` | |
| Loja: nome | `{nome_fantasia}` | |
| Loja: CNPJ | `CNPJ {numero}` | |
| Loja: regime | `{regime} · {anexo}` | Ex.: `Simples Nacional · Anexo I` |
| Loja: estado | `Estado: {UF}` | Ex.: `Estado: SP` |
| Seção conta | `Conta` | |
| Botão sair | `Sair da conta` | Confirmação: toast "Você saiu da conta" |

#### Labels (Visão Operador)

Mesmo que admin, exceto: sem seção "Equipe", sem botão "Convidar pessoa".

---

### T9 — HISTÓRICO DE UPLOADS (P1)

#### Labels

| Elemento | Texto | Nota |
|---|---|---|
| Header | `Histórico` | |
| Agrupamento | `{Mês} {Ano}` | Ex.: `Maio 2026` |
| Item — data/hora | `📤 {DD/MM} · {HH:MM}` | Ex.: `📤 15/05 · 14:30` |
| Item — qtd processadas | `{N} notas · Processado ✅` | Ex.: `87 notas · Processado ✅` |
| Item — qtd com erro parcial | `{N} notas · Com erro ⚠️` | Quando alguns XMLs inválidos |
| Item — detalhe erro | `{N} OK · {M} ignorados` | Ex.: `52 OK · 4 ignorados` |
| Item — pontos de atenção | `{N} pontos de atenção` | Só aparece se > 0 |

#### Estados

| Estado | Mensagem |
|---|---|
| **Vazio** | `Nenhum upload registrado ainda. [Carregar notas →]` |
| **Loading** | Skeleton com 3 linhas por mês |
| **Erro** | `Não foi possível carregar o histórico. [Tentar novamente]` |

---

### E-MAILS TRANSACIONAIS

O MVP envia 3 tipos de e-mail. Todos em texto puro (sem HTML), remetente `FiscoPilot <notas@copilotofiscal.com>`.

#### E1 — Confirmação de ingestão por e-mail

**Assunto:** `FiscoPilot — {N} notas recebidas e em análise`

**Corpo:**
```
Olá,

Recebemos {N} notas fiscais que você enviou para notas@copilotofiscal.com.

Elas estão sendo analisadas agora. Isso leva menos de 1 minuto.

Quando terminar, você pode ver o resultado no app:
{link_magico}

Equipe FiscoPilot
```

#### E2 — Resumo de processamento concluído

**Assunto:** `FiscoPilot — {N} notas analisadas ({M} pontos de atenção)`

**Corpo (com inconsistências):**
```
Olá,

Analisamos {N} notas fiscais da sua loja.

Resultado:
- {X} sem problemas
- {Y} com pontos de atenção
- {Z} com risco alto

Veja o que precisa da sua atenção:
{link_magico}

Importante: esta é uma análise preliminar automática. Confirme com seu contador antes de tomar qualquer ação.

Equipe FiscoPilot
```

**Corpo (sem inconsistências):**
```
Olá,

Analisamos {N} notas fiscais da sua loja.

Nenhum problema encontrado. Seu fiscal está em dia.

Acompanhe pelo app:
{link_magico}

Equipe FiscoPilot
```

#### E3 — Link mágico de acesso

**Assunto:** `FiscoPilot — Seu link de acesso`

**Corpo:**
```
Olá,

Aqui está seu link de acesso ao FiscoPilot:

{link_magico}

Este link é pessoal e expira em 24 horas. Não compartilhe com outras pessoas.

Se você não pediu este link, ignore esta mensagem.

Equipe FiscoPilot
```

---

### MENSAGENS DE WHATSAPP

Todas as mensagens usam template aprovado no WhatsApp Business API. Remetente: nome do negócio verificado.

#### W1 — Resumo semanal (toda segunda-feira, 8h)

**Template:** `fiscopilot_resumo_semanal`

```
📊 FiscoPilot — Resumo da semana

{periodo}: {N} notas processadas.

{N_ok} sem problemas · {N_atencao} pontos de atenção · {N_risco} risco alto

{Se há risco > 0:} ⚠️ {N_risco} questões precisam da sua atenção.
{Se 0 inconsistências:} ✅ Nenhum problema encontrado. Seu fiscal em dia.

{link_magico}
```

#### W2 — Alerta de risco alto (imediato, após processamento)

**Template:** `fiscopilot_alerta_risco_alto`

```
🚨 FiscoPilot — Ponto de atenção

{fornecedor} · Nota #{numero} · R$ {valor}

{tipo_inconsistencia_curto}

Impacto estimado: ~R$ {impacto}

{link_magico_detalhe}
```

Exemplo real:
```
🚨 FiscoPilot — Ponto de atenção

Distribuidora CimentoBom · Nota #3521 · R$ 8.400

Código da operação fiscal (CFOP) divergente

Impacto estimado: ~R$ 412

{link_magico}
```

#### W3 — Confirmação de upload processado

**Template:** `fiscopilot_upload_concluido`

```
✅ FiscoPilot — {N} notas analisadas

{N_ok} sem problemas
{N_pontos} pontos de atenção encontrados

{link_magico}
```

#### W4 — Lembrete de pendências (quinta-feira, 14h)

**Template:** `fiscopilot_lembrete_pendencias`

```
📋 FiscoPilot — Você tem {N} pendências

{N_risco} de risco alto ainda sem resolver.

O mês está acabando — veja o que falta:
{link_magico}
```

Só envia se houver ao menos 1 pendência com score >= 70 e status "Pendente" há mais de 3 dias.

#### W5 — Silêncio positivo (segunda-feira, sem inconsistências)

**Template:** `fiscopilot_silencio_positivo`

```
✅ FiscoPilot — Tudo certo essa semana

{N} notas processadas. Nenhum problema encontrado.

Seu fiscal está em dia.

{link_magico}
```

#### W6 — Convite para membro da equipe (admin convida Fernanda)

**Template:** `fiscopilot_convite_equipe`

```
👋 Olá, {nome}!

{admin} te convidou para acessar o FiscoPilot da {loja}.

Você poderá carregar notas e acompanhar as análises.

{link_magico}

Equipe FiscoPilot
```

---

### REGRAS GERAIS DE MICROCOPY

#### Lista de proibições (nunca usar)

| ❌ Proibido | ✅ Alternativa |
|---|---|
| `Erro fiscal` | `Ponto de atenção` ou `Inconsistência` |
| `Seu contador errou` | `Confirmar com seu contador` |
| `Clique aqui` | Use o nome da ação: `Ver`, `Carregar`, `Baixar` |
| `Dados inválidos` | Explique o que está errado: `Formato não aceito` ou `Número fora do padrão` |
| `Erro 500 / Erro 401` | `Algo deu errado. [Ação concreta]` |
| `Sistema indisponível` | `Estamos em manutenção. Voltamos em alguns minutos.` |
| `Consulte o manual` | `Fale com a gente pelo WhatsApp: (11) 9XXXX-XXXX` |
| `Usuário não autorizado` | `Você não tem permissão para acessar esta página.` |
| `Timeout` | `A conexão está lenta. Tentando de novo...` |

#### Lista de obrigações (sempre usar)

| ✅ Regra | Exemplo |
|---|---|
| Sigla sempre acompanhada de explicação na 1ª ocorrência da tela | `CFOP (código da operação fiscal)` |
| Valor monetário sempre com R$ e separador de milhar | `R$ 1.008,00` |
| Data sempre em formato brasileiro | `15/05/2026` |
| Horário sempre 24h | `14:30` |
| Nome do fornecedor sempre por extenso (nunca só CNPJ) | `Distribuidora CimentoBom`, não `12.345.678/0001-90` |
| Impacto sempre aproximado | `~R$ 412` ou `até R$ 412` |
| Contato humano sempre disponível em mensagens de erro | `Fale com a gente pelo WhatsApp: (11) 9XXXX-XXXX` |

#### Tom de voz — exemplos por contexto

| Contexto | Tom | Exemplo |
|---|---|---|
| Boa notícia | Calmo, reforço positivo | `Nenhum problema encontrado. Seu fiscal está em dia.` |
| Alerta | Direto, sem alarmismo | `O código da operação fiscal está diferente do esperado. Isso pode gerar imposto a mais.` |
| Erro técnico | Assumir responsabilidade, dar próximo passo | `Algo deu errado. Já fomos avisados. Tente de novo em alguns minutos.` |
| Ação concluída | Confirmação breve | `Marcado como Resolvida ✅` |
| Decisão do usuário | Respeito, sem julgamento | `Ao ignorar, você assume a responsabilidade por esta decisão fiscal.` |
| Educação fiscal | Paciente, nunca condescendente | `CFOP é o código que identifica o tipo de operação fiscal — se é compra, venda, devolução.` |

---

### Riscos e pontos de atenção

| Risco | Severidade | Mitigação |
|---|---|---|
| Microcopy pode soar informal demais em contexto fiscal e gerar desconfiança | Média | Validar com 3 donos de loja reais: "Esse texto passa confiança?" Ajustar tom se necessário sem perder clareza |
| Checklist de ações ficar desatualizado quando mudar regra fiscal (ex.: Reforma Tributária) | Média | Templates de checklist versionados e mapeados por regra. Revisão trimestral do microcopy com contador consultor |
| Mensagens de WhatsApp excederem limite de 4096 caracteres | Baixa | Templates são enxutos por definição. Testar comprimento com dados reais antes de submeter à Meta |
| Usuário não entender a diferença entre "Pendente", "Em andamento", "Resolvida" e "Ignorada" | Média | Tooltip no dropdown: `Pendente: ainda não mexeu. Em andamento: já começou a resolver. Resolvida: fornecedor corrigiu. Ignorada: decidiu não corrigir.` |
| Texto de tooltips muito longo quebrar layout em celular antigo | Baixa | Tooltip expansível inline, não popover. Máximo 3 linhas (~150 caracteres) |

---

### Próximo passo recomendado

Com o microcopy definido, avançar para o **Bloco 3 — Tecnologia e IA**, começando pela **Etapa 17 — Arquitetura Técnica de Alto Nível**.

### Prompt da próxima etapa

```
Execute a Etapa 17 — Arquitetura Técnica de Alto Nível.
Siga exatamente o formato obrigatório de resposta.
Considere o escopo do MVP definido nas Etapas 6, 8 e 9.
Assuma time de 2-3 pessoas, 90 dias de construção, stack moderna mas pragmática.
Defina: diagrama de componentes, fluxo de dados, decisões de infraestrutura, separação de responsabilidades, estratégia de deploy e ambientes.
Regra: não usar IA onde regra determinística é suficiente. Toda recomendação de IA deve ser auditável.
```

---

---

## Etapa 17 — Arquitetura Técnica de Alto Nível

### Objetivo da etapa

Definir a arquitetura técnica do FiscoPilot MVP — componentes, fluxos de dados, infraestrutura, persistência e comunicação entre serviços — respeitando o escopo de 16 funcionalidades P0, 90 dias de construção, time de 2-3 pessoas, e o princípio de que regras determinísticas têm primazia sobre IA generativa.

### Premissas adotadas

| # | Premissa | Justificativa |
|---|---|---|
| P1 | Time: 1 founder full-stack (React + Node) + 1 engenheiro back-end + 1 designer UX part-time. O founder é o único com acesso a produção nas semanas 1-8 | Startup estágio zero; o founder acumula DevOps inicial |
| P2 | O MVP processa até 200 NF-e por lote, com pico de 5 uploads/dia por tenant na fase beta (3-5 lojas) | Volume baixo permite escolhas mais simples de infraestrutura |
| P3 | Nenhuma dependência de serviços públicos da Receita Federal ou Sefaz em tempo real no MVP — regras operam offline contra tabelas de referência versionadas | RNF-12 (Etapa 10): sem chamadas externas que possam quebrar o core do produto |
| P4 | Arquitetura modular monolítica (monorepo, deploy único), não microsserviços | Time de 2 devs não tem capacidade operacional para orquestrar múltiplos serviços |
| P5 | PostgreSQL como banco único — sem cache distribuído, sem fila dedicada, sem search engine separada no MVP | Complexidade operacional deve ser mínima; PostgreSQL cobre todas as necessidades com <500MB de dados |

### Análise

O FiscoPilot é essencialmente um **pipeline de processamento de documentos com interface web**. O fluxo central é:

```
Upload → Validação → Parsing XML → Motor de Regras → Persistência → Dashboard → Notificação
```

**Trade-offs analisados:**

| Decisão | Alternativa A (escolhida) | Alternativa B (descartada) | Justificativa |
|---|---|---|---|
| Arquitetura | Monolito modular (monorepo, 1 deploy) | Microsserviços (3-5 serviços independentes) | 2 devs não operam Kubernetes; monolito bem modularizado é suficiente até ~500 tenants |
| Linguagem back-end | TypeScript + Node.js (Fastify) | Python (FastAPI) | TypeScript unifica front/back, reduzindo carga cognitiva. XML parsing com fast-xml-parser é maduro. Se o time dominasse Python, seria igualmente válido |
| Banco de dados | PostgreSQL 16 | MongoDB ou Firebase | Dados fiscais são rigidamente estruturados (tabelas, relações, constraints). Schema de NF-e é conhecido e estável. JSONB para flexibilidade nos XMLs brutos |
| Processamento | Síncrono no request (200 XMLs < 60s) | Fila assíncrona (Redis/BullMQ) | Volume do MVP não justifica complexidade de fila. Timeout do request configurado para 120s. Se >200 notas, paginação no upload |
| File storage | Disco local + backup S3 semanal | S3 como storage primário | 5 lojas × 200 XMLs/mês × 50KB = 50MB/mês. Disco local do servidor é suficiente. Backup S3 para Disaster Recovery |
| Autenticação | JWT com link mágico (passwordless) | OAuth / login+senha / social login | Roberto não tem senha de nada. WhatsApp é o único canal confiável. JWT assinado com HMAC-SHA256, expira 7 dias |
| Hospedagem | VPS única (Hetzner/DigitalOcean $20-40/mês) | Vercel + Supabase + AWS | Custo fixo baixo, latência previsível, sem vendor lock-in. Migração para cloud gerenciada na Fase 2 se necessário |

### Decisões recomendadas

| Decisão | Conteúdo | Status |
|---|---|---|
| D1 | **Monorepo único** com 3 pacotes: `web` (Next.js PWA), `api` (Fastify + TypeScript), `shared` (tipos, validações, constantes) | Decisão de arquitetura |
| D2 | **Monolito modular**: api é um único processo, mas com módulos internos desacoplados: ingest, parser, rules, dashboard, notify | Decisão de arquitetura |
| D3 | **PostgreSQL 16** como banco único, com JSONB para armazenamento do XML bruto e schema relacional para dados extraídos | Decisão de persistência |
| D4 | **Processamento síncrono** no MVP. Timeout 120s. Se lote >200 notas, orientar divisão em uploads menores | Decisão de engenharia |
| D5 | **Deploy em VPS única** via Docker Compose (1 container api + 1 PostgreSQL). CI/CD com GitHub Actions → push to VPS | Decisão de infraestrutura |
| D6 | **Tabelas de referência fiscal versionadas** em código (arquivos CSV/JSON no repositório), não em banco | Decisão de manutenibilidade |
| D7 | **IA generativa é serviço externo opcional** (OpenRouter/OpenAI). Se API de IA estiver offline, explicação templateada cobre 100% dos casos | Decisão de resiliência |
| D8 | **Zero dependência de serviços do governo** no MVP. CNPJ consultado via cache estático da Receita (arquivo público) | Decisão de autonomia |

### Entregáveis

---

#### 5.1 Diagrama de Componentes

```
┌──────────────────────────────────────────────────────────────────┐
│                        USUÁRIOS                                   │
│                                                                    │
│   Roberto (Celular)          Fernanda (PC Loja)                   │
│       │                            │                               │
│       │ WhatsApp / PWA             │ Web Upload                     │
│       ▼                            ▼                               │
│ ┌──────────┐              ┌───────────────┐                       │
│ │ WhatsApp │              │   Cloudflare   │                       │
│ │ Business │◄─────────────│   DNS + Proxy  │                       │
│ │   API    │              │ (app.fiscopilot│                       │
│ │  (Meta)  │              │      .com)     │                       │
│ └────┬─────┘              └───────┬───────┘                       │
│      │                            │                                 │
│      │         ┌──────────────────┘                                 │
│      │         │                                                    │
│      ▼         ▼                                                    │
│ ┌──────────────────────────────────────────┐                      │
│ │              VPS (Docker Host)            │                      │
│ │                                           │                      │
│ │  ┌─────────────────────────────────────┐ │                      │
│ │  │        Container: fiscopilot-api     │ │                      │
│ │  │        (Node.js + Fastify + TS)      │ │                      │
│ │  │                                      │ │                      │
│ │  │  ┌──────────┐  ┌──────────┐        │ │                      │
│ │  │  │ Ingest   │  │  Parser  │        │ │                      │
│ │  │  │ Module   │──┤  Module  │        │ │                      │
│ │  │  │          │  │          │        │ │                      │
│ │  │  │· Upload  │  │· XML→JSON│        │ │                      │
│ │  │  │· E-mail  │  │· Valida  │        │ │                      │
│ │  │  │  receiver│  │  schema  │        │ │                      │
│ │  │  └────┬─────┘  └────┬─────┘        │ │                      │
│ │  │       │             │               │ │                      │
│ │  │       │     ┌───────┘               │ │                      │
│ │  │       │     ▼                       │ │                      │
│ │  │  ┌────┴───────────┐               │ │                      │
│ │  │  │   Rule Engine   │               │ │                      │
│ │  │  │                 │               │ │                      │
│ │  │  │ · CFOP checker  │               │ │                      │
│ │  │  │ · ICMS checker  │               │ │                      │
│ │  │  │ · NCM checker   │               │ │                      │
│ │  │  │ · CNPJ checker  │               │ │                      │
│ │  │  │ · Value checker  │               │ │                      │
│ │  │  │ · CST checker   │               │ │                      │
│ │  │  │ · Chave checker │               │ │                      │
│ │  │  │ · ST checker    │               │ │                      │
│ │  │  └────────┬────────┘               │ │                      │
│ │  │           │                         │ │                      │
│ │  │     ┌─────┴─────┐                  │ │                      │
│ │  │     ▼           ▼                  │ │                      │
│ │  │ ┌────────┐ ┌──────────┐           │ │                      │
│ │  │ │Explain │ │ Notify   │           │ │                      │
│ │  │ │Module  │ │ Module   │           │ │                      │
│ │  │ │        │ │          │           │ │                      │
│ │  │ │·Templat│ │·WhatsApp │           │ │                      │
│ │  │ │·LLM opt│ │·E-mail   │           │ │                      │
│ │  │ └────────┘ └──────────┘           │ │                      │
│ │  │                                      │ │                      │
│ │  │  ┌─────────────────────────────┐    │ │                      │
│ │  │  │     REST API Routes          │    │ │                      │
│ │  │  │                              │    │ │                      │
│ │  │  │  GET  /api/dashboard         │    │ │                      │
│ │  │  │  POST /api/upload            │    │ │                      │
│ │  │  │  GET  /api/notes             │    │ │                      │
│ │  │  │  GET  /api/notes/:id         │    │ │                      │
│ │  │  │  GET  /api/inconsistencies/:id│   │ │                      │
│ │  │  │  PATCH /api/inconsistencies/  │    │ │                      │
│ │  │  │        :id/status            │    │ │                      │
│ │  │  │  GET  /api/report/pdf        │    │ │                      │
│ │  │  │  POST /api/auth/magic-link   │    │ │                      │
│ │  │  │  GET  /api/auth/verify       │    │ │                      │
│ │  │  └─────────────────────────────┘    │ │                      │
│ │  └─────────────────────────────────────┘ │                      │
│ │                                           │                      │
│ │  ┌─────────────────────────────────────┐ │                      │
│ │  │    Container: fiscopilot-web         │ │                      │
│ │  │    (Next.js PWA + React)             │ │                      │
│ │  │                                      │ │                      │
│ │  │    SSR para Dashboard inicial        │ │                      │
│ │  │    Service Worker para PWA offline   │ │                      │
│ │  │    Proxy reverso: Nginx              │ │                      │
│ │  └─────────────────────────────────────┘ │                      │
│ │                                           │                      │
│ │  ┌─────────────────────────────────────┐ │                      │
│ │  │    Container: PostgreSQL 16          │ │                      │
│ │  │    Volume: /data/postgres            │ │                      │
│ │  │    Backup diário → S3 (AWS/minio)    │ │                      │
│ │  └─────────────────────────────────────┘ │                      │
│ │                                           │                      │
│ │  ┌─────────────────────────────────────┐ │                      │
│ │  │    Container: Postfix (recebe e-mail)│ │                      │
│ │  │    Volumes: /data/xml-uploads        │ │                      │
│ │  └─────────────────────────────────────┘ │                      │
│ └──────────────────────────────────────────┘                      │
│                                                                     │
│  ┌──────────────────────────────────────────┐                     │
│  │     Serviços Externos (opcionais)         │                     │
│  │                                           │                     │
│  │  · OpenRouter API (LLM, opcional)         │                     │
│  │  · WhatsApp Business Cloud API (Meta)     │                     │
│  │  · AWS S3 (backup)                        │                     │
│  │  · Sentry (error tracking)                │                     │
│  └──────────────────────────────────────────┘                     │
└──────────────────────────────────────────────────────────────────┘
```

---

#### 5.2 Fluxo de Dados — Upload e Processamento

```
                          ┌───────────┐
                          │  Fernanda │
                          └─────┬─────┘
                                │
                    ┌───────────┼───────────┐
                    │           │           │
                    ▼           ▼           ▼
              Upload ZIP   Drag & Drop   E-mail para
              (POST /api/   (POST /api/  notas@...
                upload)      upload)         │
                    │           │           │
                    └───────────┼───────────┘
                                │
                                ▼
                    ┌─────────────────────┐
                    │  INGEST MODULE      │
                    │                     │
                    │ 1. Validate file    │
                    │    (is .xml or .zip)│
                    │ 2. Extract ZIP      │
                    │ 3. Filter non-XML   │
                    │    files silently   │
                    │ 4. Hash each XML    │
                    │    (SHA-256)        │
                    │ 5. Dedup by chave   │
                    │    de acesso        │
                    │ 6. Store raw XML    │
                    │    on disk + DB     │
                    └─────────┬───────────┘
                              │
                              ▼
                    ┌─────────────────────┐
                    │  PARSER MODULE      │
                    │                     │
                    │ 1. Parse XML → JSON │
                    │    (fast-xml-parser)│
                    │ 2. Extract fields   │
                    │    (chave, CNPJ,    │
                    │     CFOP, NCM, CST, │
                    │     ICMS, valor,    │
                    │     itens, data, UF)│
                    │ 3. Validate schema  │
                    │    (layout 4.00)    │
                    │ 4. Flag notas       │
                    │    canceladas       │
                    └─────────┬───────────┘
                              │
                              ▼
                    ┌─────────────────────┐
                    │  RULE ENGINE         │
                    │                     │
                    │ ┌─────────────────┐ │
                    │ │ R1: CFOP check  │ │
                    │ │ R2: ICMS check  │ │
                    │ │ R3: NCM check   │ │
                    │ │ R4: CNPJ check  │ │
                    │ │ R5: Value check │ │
                    │ │ R6: CST check   │ │
                    │ │ R7: Chave check │ │
                    │ │ R8: ST check    │ │
                    │ └────────┬────────┘ │
                    │          │          │
                    │     ┌────┴────┐     │
                    │     ▼         ▼     │
                    │  Score OK    Score  │
                    │  0-30        31-100 │
                    └─────────┬───────────┘
                              │
                              ▼
                    ┌─────────────────────┐
                    │  PERSISTENCE         │
                    │                     │
                    │ INSERT INTO:         │
                    │  · nfe_documents    │
                    │  · nfe_items        │
                    │  · inconsistencies  │
                    │  · audit_log        │
                    └─────────┬───────────┘
                              │
                    ┌─────────┴─────────┐
                    ▼                   ▼
          ┌──────────────────┐  ┌──────────────────┐
          │ EXPLAIN MODULE    │  │ NOTIFY MODULE     │
          │                   │  │                   │
          │ 1. Match template │  │ 1. Score >= 70?   │
          │    por regra +    │  │    → W2 (alerta)  │
          │    preencher com  │  │ 2. Sempre:        │
          │    dados da nota  │  │    → W3 (resumo)  │
          │ 2. Opcional:      │  │ 3. Segunda 8h:    │
          │    LLM parafraseia│  │    → W1 (semanal) │
          │    template para  │  │                   │
          │    texto natural  │  │                   │
          └──────────────────┘  └──────────────────┘
```

---

#### 5.3 Modelo de Domínio Lógico (Entidades)

```
┌─────────────────────────────────────────────────────┐
│                                                      │
│  ┌───────────────┐       ┌───────────────────┐      │
│  │  organization  │       │      user          │      │
│  │────────────────│       │────────────────────│      │
│  │ id (UUID)      │──┐    │ id (UUID)           │      │
│  │ cnpj           │  │    │ organization_id (FK)│      │
│  │ nome_fantasia  │  │    │ nome                │      │
│  │ regime         │  │    │ whatsapp            │      │
│  │ anexo_simples  │  │    │ role (admin/op)     │      │
│  │ uf             │  │    │ created_at          │      │
│  │ created_at     │  │    └─────────────────────┘      │
│  └───────┬───────┘  │                                  │
│          │          │                                  │
│          │    ┌─────┘                                  │
│          │    │                                        │
│          ▼    ▼                                        │
│  ┌───────────────────┐    ┌──────────────────────┐    │
│  │  nfe_document     │    │   nfe_item            │    │
│  │───────────────────│    │───────────────────────│    │
│  │ id (UUID)         │──┐ │ id (UUID)              │    │
│  │ organization_id   │  │ │ nfe_document_id (FK)   │    │
│  │ chave_acesso      │  │ │ codigo_produto         │    │
│  │ numero            │  │ │ descricao              │    │
│  │ data_emissao      │  │ │ ncm                    │    │
│  │ cnpj_emitente     │  │ │ cfop                   │    │
│  │ nome_emitente     │  │ │ quantidade             │    │
│  │ valor_total       │  │ │ valor_unitario         │    │
│  │ cfop              │  │ │ valor_total            │    │
│  │ ncm_principal     │  │ │ cst_pis                │    │
│  │ cst_pis           │  │ │ cst_cofins             │    │
│  │ cst_cofins        │  │ │ aliquota_icms          │    │
│  │ aliquota_icms     │  │ │ icms_st                │    │
│  │ icms_valor        │  │ │ icms_valor             │    │
│  │ icms_st           │  │ └───────────────────────┘    │
│  │ uf_emitente       │  │                               │
│  │ xml_raw (JSONB)   │  │                               │
│  │ status_nfe        │  │                               │
│  │ created_at         │  │                               │
│  └────────┬──────────┘  │                               │
│           │             │                               │
│           │   ┌─────────┘                               │
│           │   │                                         │
│           ▼   ▼                                         │
│  ┌───────────────────────┐                              │
│  │  inconsistency        │                              │
│  │───────────────────────│                              │
│  │ id (UUID)              │                              │
│  │ nfe_document_id (FK)   │                              │
│  │ organization_id (FK)   │                              │
│  │ rule_id ("R1"..."R8") │                              │
│  │ score (0-100)          │                              │
│  │ classification         │                              │
│  │   ('OK'|'ATENCAO'|     │                              │
│  │    'RISCO_ALTO')       │                              │
│  │ found_value            │                              │
│  │ expected_value         │                              │
│  │ estimated_impact (R$)  │                              │
│  │ explanation_text       │                              │
│  │ status ('PENDENTE'|    │                              │
│  │   'EM_ANDAMENTO'|      │                              │
│  │   'RESOLVIDA'|         │                              │
│  │   'IGNORADA')          │                              │
│  │ ignore_reason          │                              │
│  │ checklist_json (JSONB) │                              │
│  │ created_at             │                              │
│  │ updated_at             │                              │
│  │ resolved_at            │                              │
│  └───────────────────────┘                              │
│                                                          │
│  ┌───────────────────────┐                              │
│  │  audit_log            │                              │
│  │───────────────────────│                              │
│  │ id (UUID)              │                              │
│  │ organization_id (FK)   │                              │
│  │ user_id (FK, nullable) │                              │
│  │ event_type             │                              │
│  │ entity_type            │                              │
│  │ entity_id              │                              │
│  │ details (JSONB)        │                              │
│  │ ip_address             │                              │
│  │ created_at             │                              │
│  └───────────────────────┘                              │
│                                                          │
│  ┌───────────────────────┐                              │
│  │  magic_link           │                              │
│  │───────────────────────│                              │
│  │ id (UUID)              │                              │
│  │ user_id (FK)           │                              │
│  │ token (hashed)         │                              │
│  │ expires_at             │                              │
│  │ used_at                │                              │
│  │ created_at             │                              │
│  └───────────────────────┘                              │
│                                                          │
│  ┌───────────────────────┐                              │
│  │  upload_batch         │                              │
│  │───────────────────────│                              │
│  │ id (UUID)              │                              │
│  │ organization_id (FK)   │                              │
│  │ user_id (FK)           │                              │
│  │ source ('web'|'email') │                              │
│  │ total_files            │                              │
│  │ processed              │                              │
│  │ ignored                │                              │
│  │ status                 │                              │
│  │ created_at             │                              │
│  └───────────────────────┘                              │
│                                                          │
└─────────────────────────────────────────────────────┘
```

---

#### 5.4 Infraestrutura e Deploy

```
┌────────────────────────────────────────────┐
│           VPS (Hetzner CX22)                │
│         2 vCPU · 4GB RAM · 40GB SSD         │
│           Ubuntu 22.04 LTS                  │
│                                             │
│  ┌─────────────────────────────────────┐   │
│  │         Docker Compose               │   │
│  │                                      │   │
│  │  ┌──────────┐  ┌──────────┐         │   │
│  │  │  fiscopilot│  │  postgres │         │   │
│  │  │   -api     │  │   :16     │         │   │
│  │  │   :3001    │  │   :5432   │         │   │
│  │  └──────────┘  └──────────┘         │   │
│  │                                      │   │
│  │  ┌──────────┐  ┌──────────┐         │   │
│  │  │  fiscopilot│  │  nginx    │         │   │
│  │  │   -web     │  │   :80/443 │         │   │
│  │  │   :3000    │  │   reverse  │         │   │
│  │  └──────────┘  │   proxy    │         │   │
│  │                └──────────┘         │   │
│  │                                      │   │
│  │  Volumes:                            │   │
│  │   · postgres_data:/var/lib/postgres  │   │
│  │   · xml_uploads:/data/xml            │   │
│  │                                      │   │
│  │  Networks:                            │   │
│  │   · internal (api+db)                │   │
│  │   · public (nginx↔internet)          │   │
│  └─────────────────────────────────────┘   │
│                                             │
│  Cron jobs (host):                          │
│   · 02:00: pg_dump → S3 (backup diário)     │
│   · 08:00 seg: trigger resumo semanal        │
│   · 14:00 qui: trigger lembrete pendências   │
│   · 03:00 dom: vacuum analyze                │
│                                             │
└────────────────────────────────────────────┘

SERVIÇOS EXTERNOS:

┌─────────────┐   ┌──────────────┐   ┌─────────────┐
│  WhatsApp   │   │   OpenRouter  │   │  AWS S3     │
│  Business   │   │   (LLM API)   │   │  (backup)   │
│  Cloud API  │   │   OPCIONAL    │   │             │
│  (Meta)     │   │              │   │  Bucket:    │
│             │   │  Modelo:     │   │  fiscopilot │
│  ~R$ 0,05/  │   │  GPT-4o-mini │   │  -backups   │
│  mensagem*  │   │  ou Claude   │   │             │
│             │   │  Haiku       │   │  ~R$ 5/mês  │
│             │   │              │   │             │
│             │   │  ~R$ 15/mês  │   │             │
└─────────────┘   └──────────────┘   └─────────────┘
```

**Custo mensal estimado (MVP — 5 tenants):**

| Recurso | Custo estimado |
|---|---|
| VPS (Hetzner CX22) | R$ 120/mês (~€22) |
| Domínio (.com.br) | R$ 40/ano → R$ 3/mês |
| WhatsApp Business API | R$ 25/mês (~500 msgs) |
| OpenRouter (LLM, opcional) | R$ 15/mês |
| AWS S3 (backup ~50MB/mês) | R$ 5/mês |
| Sentry (free tier) | R$ 0 |
| **Total** | **~R$ 168/mês** |

---

#### 5.5 Ambientes

| Ambiente | Domínio | Branch | Deploy | Uso |
|---|---|---|---|---|
| **dev** | `localhost:3000` | `main` | Docker Compose local | Desenvolvimento diário |
| **staging** | `staging.copilotofiscal.com` | `staging` | GitHub Actions → VPS (porta 3002) | Testes de integração, demo para beta testers |
| **prod** | `app.copilotofiscal.com` | `main` (tagged release) | GitHub Actions manual trigger | Clientes pagantes |

**CI/CD (GitHub Actions):**

```
push main → lint + typecheck + test
              │
              ▼
         build Docker image
              │
              ▼
         push to GitHub Container Registry
              │
              ▼
         ssh VPS → docker compose pull && docker compose up -d (staging)

tag v*.*.* → mesmo fluxo, mas deploy para prod (manual approval)
```

---

#### 5.6 Estrutura do Monorepo

```
fiscopilot/
├── apps/
│   ├── web/                    # Next.js PWA (React)
│   │   ├── src/
│   │   │   ├── app/           # App Router (pages)
│   │   │   ├── components/    # UI components
│   │   │   └── hooks/         # Custom hooks
│   │   ├── public/
│   │   │   ├── manifest.json  # PWA manifest
│   │   │   └── sw.js          # Service Worker
│   │   ├── tailwind.config.ts
│   │   ├── next.config.ts
│   │   └── package.json
│   │
│   └── api/                    # Fastify + TypeScript
│       ├── src/
│       │   ├── modules/
│       │   │   ├── auth/       # Magic link, JWT
│       │   │   ├── ingest/     # Upload, e-mail receiver
│       │   │   ├── parser/     # XML → JSON
│       │   │   ├── rules/      # Rule engine (R1-R8)
│       │   │   ├── dashboard/  # Aggregation queries
│       │   │   ├── notify/     # WhatsApp, e-mail
│       │   │   └── report/     # PDF generation
│       │   ├── db/
│       │   │   ├── migrations/ # Drizzle ORM
│       │   │   └── schema.ts
│       │   ├── config/
│       │   │   └── env.ts      # Variáveis de ambiente
│       │   └── server.ts       # Entry point
│       ├── Dockerfile
│       └── package.json
│
├── packages/
│   └── shared/                  # Tipos, validações, constantes
│       ├── src/
│       │   ├── types/          # NfeDocument, Inconsistency, etc.
│       │   ├── validators/     # Zod schemas
│       │   └── constants/      # Regimes, tabelas fiscais
│       └── package.json
│
├── data/                        # Tabelas de referência fiscal
│   ├── cfop.csv                 # Tabela CFOP oficial
│   ├── ncm_materiais.csv        # NCMs de material de construção
│   ├── aliquotas_icms.csv       # Alíquotas interestaduais
│   ├── st_estados.csv           # Listas de ST por UF
│   └── cnpj_irregular.csv       # Cache CNPJs irregulares (opcional)
│
├── docker-compose.yml
├── docker-compose.prod.yml
├── .github/
│   └── workflows/
│       ├── ci.yml               # Lint, test, typecheck
│       └── deploy.yml           # Build + deploy
├── turbo.json                   # Turborepo config
├── package.json                 # Workspace root
└── README.md
```

---

#### 5.7 Estratégia de Resiliência

| Cenário | Comportamento |
|---|---|
| **WhatsApp API offline** | Notificações enfileiradas em tabela `pending_notifications`, retry exponencial (1min, 5min, 15min, 1h). Dashboard e upload funcionam normalmente |
| **LLM API offline** | Fallback para explicação templateada. Template já cobre 100% dos cenários. LLM é apenas melhoria cosmética |
| **PostgreSQL lento** | Read replicas não necessárias no MVP. Índices em: `organization_id`, `chave_acesso`, `data_emissao`, `status`. Queries paginadas |
| **Disco cheio (XMLs)** | Rotação de XMLs > 90 dias movidos para S3. Query no banco mantém referência. Monitoramento: alerta se disco > 80% |
| **Docker crash** | `restart: unless-stopped` no compose. Healthcheck HTTP em `/api/health`. Uptime Robot (free) monitora |
| **Ataque brute force (magic link)** | Rate limit: 3 solicitações por número a cada 15 minutos. Tokens expiram em 24h |
| **Perda total da VPS** | Backup diário no S3. Recuperação: provisionar nova VPS + docker compose up + pg_restore. RTO estimado: 2h |

---

### Expansão Pós-MVP — Novos Módulos (Fases A-D)

**Objetivo:** Adicionar 12 novos módulos para suportar as 30 funcionalidades pós-MVP (F36-F65), mantendo a arquitetura modular monolítica.

#### Diagrama de Componentes Atualizado (Pós-MVP)

```
┌──────────────────────────────────────────────────────────────────┐
│                        USUÁRIOS                                   │
│                                                                    │
│   Roberto      Fernanda      Dona Célia     Founder              │
│   (Celular)    (PC Loja)     (Portal)       (Admin)              │
│       │            │             │              │                 │
│       │ WhatsApp   │ Web         │ Web          │ Web             │
│       │ / PWA      │ Upload      │ Portal       │ Admin           │
│       ▼            ▼             ▼              ▼                 │
│ ┌──────────┐              ┌───────────────┐                       │
│ │ WhatsApp │              │   Cloudflare   │                       │
│ │ Business │◄─────────────│   DNS + Proxy  │                       │
│ │   API    │              │ (app.fiscopilot│                       │
│ │  (Meta)  │              │      .com)     │                       │
│ └────┬─────┘              └───────┬───────┘                       │
│      │                            │                                 │
│      │         ┌──────────────────┘                                 │
│      │         │                                                    │
│      ▼         ▼                                                    │
│ ┌──────────────────────────────────────────┐                      │
│ │              VPS (Docker Host)            │                      │
│ │                                           │                      │
│ │  ┌─────────────────────────────────────┐ │                      │
│ │  │        Container: fiscopilot-api     │ │                      │
│ │  │        (Node.js + Fastify + TS)      │ │                      │
│ │  │                                      │ │                      │
│ │  │  MÓDULOS MVP:                        │ │                      │
│ │  │  ┌──────────┐  ┌──────────┐        │ │                      │
│ │  │  │ Ingest   │  │  Parser  │        │ │                      │
│ │  │  │ Module   │──┤  Module  │        │ │                      │
│ │  │  │          │  │          │        │ │                      │
│ │  │  │· Upload  │  │· XML→JSON│        │ │                      │
│ │  │  │· E-mail  │  │· Valida  │        │ │                      │
│ │  │  │  receiver│  │  schema  │        │ │                      │
│ │  │  └────┬─────┘  └────┬─────┘        │ │                      │
│ │  │       │             │               │ │                      │
│ │  │       │     ┌───────┘               │ │                      │
│ │  │       │     ▼                       │ │                      │
│ │  │  ┌────┴───────────┐               │ │                      │
│ │  │  │   Rule Engine   │               │ │                      │
│ │  │  │                 │               │ │                      │
│ │  │  │ · R1-R8 (base)  │               │ │                      │
│ │  │  │ · R9-R20 (packs)│               │ │                      │
│ │  │  └────────┬────────┘               │ │                      │
│ │  │           │                         │ │                      │
│ │  │     ┌─────┴─────┐                  │ │                      │
│ │  │     ▼           ▼                  │ │                      │
│ │  │ ┌────────┐ ┌──────────┐           │ │                      │
│ │  │ │Explain │ │ Notify   │           │ │                      │
│ │  │ │Module  │ │ Module   │           │ │                      │
│ │  │ │        │ │          │           │ │                      │
│ │  │ │·Templat│ │·WhatsApp │           │ │                      │
│ │  │ │·LLM opt│ │·E-mail   │           │ │                      │
│ │  │ └────────┘ └──────────┘           │ │                      │
│ │  │                                      │ │                      │
│ │  │  NOVOS MÓDULOS (Pós-MVP):           │ │                      │
│ │  │  ┌──────────────────────────────┐   │ │                      │
│ │  │  │ messages/      (Fase A)      │   │ │                      │
│ │  │  │ savings/       (Fase A)      │   │ │                      │
│ │  │  │ whatsapp-ingest/ (Fase A)    │   │ │                      │
│ │  │  │ onboarding/    (Fase A)      │   │ │                      │
│ │  │  │ sefaz/         (Fase B)      │   │ │                      │
│ │  │  │ kanban/        (Fase B)      │   │ │                      │
│ │  │  │ cadastral/     (Fase B)      │   │ │                      │
│ │  │  │ accountant/    (Fase C)      │   │ │                      │
│ │  │  │ suppliers/     (Fase C)      │   │ │                      │
│ │  │  │ reform/        (Fase D)      │   │ │                      │
│ │  │  │ erp/           (Fase D)      │   │ │                      │
│ │  │  │ rules/packs/   (Fase D)      │   │ │                      │
│ │  │  └──────────────────────────────┘   │ │                      │
│ │  │                                      │ │                      │
│ │  │  ┌─────────────────────────────┐    │ │                      │
│ │  │  │     REST API Routes          │    │ │                      │
│ │  │  │                              │    │ │                      │
│ │  │  │  MVP: 13 endpoints           │    │ │                      │
│ │  │  │  Pós-MVP: +~65 endpoints     │    │ │                      │
│ │  │  │  Total: ~78 endpoints        │    │ │                      │
│ │  │  └─────────────────────────────┘    │ │                      │
│ │  └─────────────────────────────────────┘ │                      │
│ │                                           │                      │
│ │  ┌─────────────────────────────────────┐ │                      │
│ │  │    Container: fiscopilot-web         │ │                      │
│ │  │    (Next.js PWA + React)             │ │                      │
│ │  │                                      │ │                      │
│ │  │    MVP: 9 telas (T0-T9)              │ │                      │
│ │  │    Pós-MVP: +14 telas (T10-T23)      │ │                      │
│ │  │    Total: 23 telas                   │ │                      │
│ │  │                                      │ │                      │
│ │  │    Portal do Contador (T17-T18)      │ │                      │
│ │  │    separado em /contador/*           │ │                      │
│ │  └─────────────────────────────────────┘ │                      │
│ │                                           │                      │
│ │  ┌─────────────────────────────────────┐ │                      │
│ │  │    Container: PostgreSQL 16          │ │                      │
│ │  │    Volume: /data/postgres            │ │                      │
│ │  │    Backup diário → S3 (AWS/minio)    │ │                      │
│ │  │                                      │ │                      │
│ │  │    MVP: 10 tabelas                   │ │                      │
│ │  │    Pós-MVP: +23 tabelas + 1 view     │ │                      │
│ │  │    Total: 34 tabelas                 │ │                      │
│ │  └─────────────────────────────────────┘ │                      │
│ │                                           │                      │
│ │  ┌─────────────────────────────────────┐ │                      │
│ │  │    Container: Postfix (recebe e-mail)│ │                      │
│ │  │    Volumes: /data/xml-uploads        │ │                      │
│ │  └─────────────────────────────────────┘ │                      │
│ └──────────────────────────────────────────┘                      │
│                                                                     │
│  ┌──────────────────────────────────────────┐                     │
│  │     Serviços Externos (opcionais)         │                     │
│  │                                           │                     │
│  │  MVP:                                     │                     │
│  │  · OpenRouter API (LLM, opcional)         │                     │
│  │  · WhatsApp Business Cloud API (Meta)     │                     │
│  │  · AWS S3 (backup)                        │                     │
│  │  · Sentry (error tracking)                │                     │
│  │                                           │                     │
│  │  Pós-MVP:                                 │                     │
│  │  · Sefaz WS (download automático XML)     │                     │
│  │  · APIs ERP (Bling, Tiny, Omie, ContaAzul)│                     │
│  │  · API Receita Federal (CNPJ, IE)         │                     │
│  │  · Sintegra (inscrição estadual)          │                     │
│  └──────────────────────────────────────────┘                     │
└──────────────────────────────────────────────────────────────────┘
```

---

#### Fluxo de Dados Atualizado — Download Automático (Fase B)

```
┌─────────────────────────────────────────────────────────────────┐
│                    DOWNLOAD AUTOMÁTICO (SEFAZ)                    │
└─────────────────────────────────────────────────────────────────┘

                          ┌───────────┐
                          │  Cron Job │
                          │  02:00 BRT│
                          └─────┬─────┘
                                │
                                ▼
                    ┌─────────────────────┐
                    │  SEFAZ MODULE       │
                    │                     │
                    │ 1. Busca            │
                    │    organizations    │
                    │    com certificado  │
                    │    A1 ativo         │
                    │ 2. Para cada org:   │
                    │    a. Descriptografa│
                    │       certificado   │
                    │       (AES-256-GCM) │
                    │    b. Autentica na  │
                    │       Sefaz WS      │
                    │       (SOAP)        │
                    │    c. Consulta NF-e │
                    │       emitidas      │
                    │       contra CNPJ   │
                    │       (últimas 24h) │
                    │    d. Baixa XMLs    │
                    │    e. Processa via  │
                    │       pipeline      │
                    │       existente     │
                    │ 3. Atualiza         │
                    │    sefaz_download_  │
                    │    sessions         │
                    │ 4. Notifica         │
                    │    usuário via      │
                    │    WhatsApp         │
                    └─────────┬───────────┘
                              │
                              ▼
                    ┌─────────────────────┐
                    │  PIPELINE EXISTENTE │
                    │                     │
                    │  Ingest → Parser →  │
                    │  Rules → Persist →  │
                    │  Notify             │
                    └─────────────────────┘
```

---

#### Fluxo de Dados Atualizado — Ingestão por WhatsApp (Fase A)

```
┌─────────────────────────────────────────────────────────────────┐
│                    INGESTÃO POR WHATSAPP                         │
└─────────────────────────────────────────────────────────────────┘

                          ┌───────────┐
                          │ Fernanda  │
                          │ encaminha │
                          │ XML/ZIP   │
                          │ via WA    │
                          └─────┬─────┘
                                │
                                ▼
                    ┌─────────────────────┐
                    │  WhatsApp Business  │
                    │  Cloud API (Meta)   │
                    │                     │
                    │  Envia webhook:     │
                    │  POST /api/v1/      │
                    │  whatsapp/webhook   │
                    └─────────┬───────────┘
                              │
                              ▼
                    ┌─────────────────────┐
                    │  WHATSAPP-INGEST    │
                    │  MODULE             │
                    │                     │
                    │  1. Valida          │
                    │     assinatura      │
                    │     HMAC-SHA256     │
                    │  2. Extrai mídia    │
                    │     (XML/ZIP)       │
                    │  3. Download via    │
                    │     WhatsApp Media  │
                    │     API             │
                    │  4. Identifica org  │
                    │     via whatsapp    │
                    │     do remetente    │
                    │  5. Processa via    │
                    │     pipeline        │
                    │     existente       │
                    │  6. Envia           │
                    │     confirmação     │
                    │     via WhatsApp    │
                    └─────────┬───────────┘
                              │
                              ▼
                    ┌─────────────────────┐
                    │  PIPELINE EXISTENTE │
                    │                     │
                    │  Ingest → Parser →  │
                    │  Rules → Persist →  │
                    │  Notify             │
                    └─────────────────────┘
```

---

#### Estrutura de Monorepo Atualizada (Pós-MVP)

```
fiscopilot/
├── apps/
│   ├── web/                    # Next.js PWA (React)
│   │   ├── src/
│   │   │   ├── app/           # App Router (pages)
│   │   │   │   ├── (auth)/    # T0, T7 (login, link expirado)
│   │   │   │   ├── dashboard/ # T1 (dashboard)
│   │   │   │   ├── notas/     # T2, T3, T4 (lista, detalhe, ação)
│   │   │   │   ├── carregar/  # T6 (upload)
│   │   │   │   ├── onboarding/ # T10 (wizard raio-x) ← NOVO
│   │   │   │   ├── economia/  # T12 (painel economia) ← NOVO
│   │   │   │   ├── relatorio-mensal/ # T13 (relatório dono) ← NOVO
│   │   │   │   ├── pendencias/ # T14 (kanban) ← NOVO
│   │   │   │   ├── fornecedores/ # T19 (score fornecedores) ← NOVO
│   │   │   │   ├── reforma-tributaria/ # T21 (preparação CBS/IBS) ← NOVO
│   │   │   │   ├── contador/  # T17, T18 (portal contador) ← NOVO
│   │   │   │   └── configuracoes/ # T15, T16, T22, T23 ← NOVO
│   │   │   ├── components/    # UI components
│   │   │   └── hooks/         # Custom hooks
│   │   ├── public/
│   │   │   ├── manifest.json  # PWA manifest
│   │   │   └── sw.js          # Service Worker
│   │   ├── tailwind.config.ts
│   │   ├── next.config.ts
│   │   └── package.json
│   │
│   └── api/                    # Fastify + TypeScript
│       ├── src/
│       │   ├── modules/
│       │   │   ├── auth/       # Magic link, JWT
│       │   │   ├── ingest/     # Upload, e-mail receiver
│       │   │   ├── parser/     # XML → JSON
│       │   │   ├── rules/      # Rule engine (R1-R8)
│       │   │   │   └── packs/  # Pacotes de regras (R9-R20) ← NOVO
│       │   │   ├── dashboard/  # Aggregation queries
│       │   │   ├── notify/     # WhatsApp, e-mail
│       │   │   ├── report/     # PDF generation
│       │   │   ├── messages/   # Mensagem para fornecedor ← NOVO
│       │   │   ├── savings/    # Painel economia/riscos evitados ← NOVO
│       │   │   ├── whatsapp-ingest/ # Ingestão por WhatsApp ← NOVO
│       │   │   ├── onboarding/ # Wizard raio-x ← NOVO
│       │   │   ├── sefaz/      # Download automático XML ← NOVO
│       │   │   ├── kanban/     # Gestão de pendências ← NOVO
│       │   │   ├── cadastral/  # Alertas cadastrais ← NOVO
│       │   │   ├── accountant/ # Portal do contador ← NOVO
│       │   │   ├── suppliers/  # Score de fornecedores ← NOVO
│       │   │   ├── reform/     # Preparação Reforma Tributária ← NOVO
│       │   │   └── erp/        # Integração ERPs ← NOVO
│       │   ├── db/
│       │   │   ├── migrations/ # Drizzle ORM
│       │   │   └── schema.ts
│       │   ├── config/
│       │   │   └── env.ts      # Variáveis de ambiente
│       │   └── server.ts       # Entry point
│       ├── Dockerfile
│       └── package.json
│
├── packages/
│   └── shared/                  # Tipos, validações, constantes
│       ├── src/
│       │   ├── types/          # NfeDocument, Inconsistency, etc.
│       │   ├── validators/     # Zod schemas
│       │   └── constants/      # Regimes, tabelas fiscais
│       └── package.json
│
├── data/                        # Tabelas de referência fiscal
│   ├── cfop.csv                 # Tabela CFOP oficial
│   ├── ncm_materiais.csv        # NCMs de material de construção
│   ├── aliquotas_icms.csv       # Alíquotas interestaduais
│   ├── st_estados.csv           # Listas de ST por UF
│   ├── cnpj_irregular.csv       # Cache CNPJs irregulares (opcional)
│   └── rule_packs/              # Pacotes de regras ← NOVO
│       ├── base.json            # R1-R8 (sempre ativo)
│       ├── sp-construcao.json   # R9-R11 (SP material construção)
│       ├── mg-construcao.json   # R12-R14 (MG material construção)
│       └── lucro-presumido.json # R15-R20 (Lucro Presumido)
│
├── docker-compose.yml
├── docker-compose.prod.yml
├── .github/
│   └── workflows/
│       ├── ci.yml               # Lint, test, typecheck
│       └── deploy.yml           # Build + deploy
├── turbo.json                   # Turborepo config
├── package.json                 # Workspace root
└── README.md
```

---

#### Estratégia de Resiliência Expandida (Pós-MVP)

| Cenário | Comportamento |
|---|---|
| **Sefaz WS offline** (Fase B) | Fila de downloads (pg-boss) com retry exponencial (1min, 5min, 15min, 1h). Alerta se 3 dias consecutivos sem download. Fallback para upload manual |
| **Certificado A1 vencido** (Fase B) | Alerta cadastral 30/15/7 dias antes. Download automático desativado. Notificação WhatsApp para usuário |
| **API ERP offline** (Fase D) | Retry com backoff exponencial. Alerta se conector falhar >3x. Fallback para upload manual. Health check por conector |
| **API Receita Federal offline** (Fase B) | Cache de 7 dias por CNPJ. Batch processing noturno (não em tempo real). Alerta se API falhar >3x consecutivas |
| **View materializada desatualizada** (Fase C) | Refresh manual via botão na interface. Alerta se cron falhar. Timestamp visível "Atualizado em DD/MM HH:MM" |
| **IA alucina resposta** (Fase C) | Validação de output com regex (detecta cálculo de imposto). Fallback para template se inválido. Disclaimer em toda resposta |
| **Kanban não adotado** (Fase B) | Feature opcional. Dashboard simples continua sendo tela principal. Métricas de adoção antes de expandir |
| **Portal contador confundido** (Fase C) | Link claro no e-mail de convite. Onboarding guiado para contadores. Suporte via WhatsApp |

---

### Riscos e pontos de atenção (Expansão Pós-MVP)

| Risco | Severidade | Mitigação |
|---|---|---|
| 12 novos módulos podem sobrecarregar monolito se não modularizados corretamente | Alta | Cada módulo é auto-contido (routes, services, repositories). Testes de integração por módulo. Code review rigoroso |
| Download automático (Sefaz WS) pode falhar silenciosamente se API mudar | Alta | Monitoramento de health check do job. Alerta se 3 dias consecutivos sem download. Fallback para upload manual |
| Criptografia de certificados A1 pode falhar se `CERTIFICATE_ENCRYPTION_KEY` for comprometida | Alta | Rotação de chave a cada 6 meses. Pen-test antes de lançar. Armazenar chave em cofre (AWS Secrets Manager) |
| Integração com ERPs pode quebrar se API do ERP mudar sem versionamento | Alta | Testes de integração contínuos. Monitoramento de health check por conector. Fallback para upload manual |
| 23 novas tabelas podem degradar performance se índices não otimizados | Média | Revisão de índices antes de cada fase. Query analysis com `EXPLAIN ANALYZE`. Particionamento se necessário |
| Portal do contador (auth separado) pode criar superfície de ataque adicional | Média | Rate limit de login (3 tentativas/15min). 2FA na Fase D. Monitoramento de tentativas de login suspeitas |
| View materializada `supplier_scores` pode ficar desatualizada se cron falhar | Média | Refresh manual via botão na interface. Alerta se refresh falhar. Timestamp visível |
| Pacotes de regras setoriais podem gerar inconsistência entre pacotes | Média | Pacote base (R1-R8) sempre ativo. Pacotes setoriais adicionam regras, não substituem. Testes cruzados entre pacotes |
| Assistente de IA pode alucinar e dar orientação fiscal errada mesmo com guardrails | Alta | Validação de output com regex. Fallback para template se inválido. Disclaimer em toda resposta. Feedback loop |
| Custo de infra pode crescer mais que receita se features não converterem em vendas | Média | Cada fase deve gerar ao menos 5 novos clientes ou permitir aumento de preço (R$ 97 → R$ 147 → R$ 197) |

---

### Riscos e pontos de atenção (MVP)

| Risco | Severidade | Mitigação |
|---|---|---|
| Processamento síncrono de 200 XMLs pode exceder timeout do request (120s) se CPU for lenta | Média | Benchmark com 200 XMLs reais na CX22. Se >90s, implementar fila com pg-boss (PostgreSQL como broker) — 2 dias adicionais |
| Fast-xml-parser pode não cobrir 100% das variações de namespace de NF-e emitidas por sistemas legados (SAP, Protheus) | Alta | Testar com XMLs de 5 ERPs diferentes antes do Sprint 2. Ter fallback: regex extraction para campos críticos se schema divergir |
| VPS única = single point of failure. Se cair, todos os tenants ficam offline | Média | Aceitável para MVP com 5 tenants. Plano de migração para arquitetura multi-zone na Fase 2 se necessário |
| Docker Compose em VPS única exige que o founder saiba SSH e operações básicas de sysadmin | Média | Documentar runbook de operações (deploy, rollback, backup restore). Automatizar tudo via GitHub Actions |
| PostgreSQL sem réplica = risco de perda de dados entre backups | Baixa | Backup diário. WAL arquivado a cada 15 min. Perda máxima aceitável: 24h de dados. Clientes podem reenviar XMLs |
| Tabelas fiscais (CFOP, NCM) desatualizadas gerando falsos positivos/negativos | Média | Versionamento no Git. Script de atualização semestral. Release notes com changelog de regras |

### Próximo passo recomendado

Com a arquitetura de alto nível definida, prosseguir para a **Etapa 18 — Stack Recomendada**, detalhando bibliotecas específicas, versões e justificativas técnicas para cada componente do stack.

### Prompt da próxima etapa

```
Execute a Etapa 18 — Stack Recomendada.
Siga exatamente o formato obrigatório de resposta.
Detalhe cada biblioteca e ferramenta escolhida com nome, versão, justificativa técnica e alternativa descartada.
Cubra: front-end, back-end, banco de dados, infraestrutura, CI/CD, monitoramento, testes e ferramentas de desenvolvimento.
Mantenha consistência com a arquitetura definida na Etapa 17: monorepo TypeScript, Fastify, Next.js, PostgreSQL, Docker Compose em VPS única.
```

---

## Etapa 18 — Stack Recomendada

### Objetivo da etapa

Definir cada biblioteca, ferramenta e serviço que compõe o FiscoPilot MVP, com versão específica, justificativa técnica, trade-offs considerados e alternativa descartada — garantindo que o time de 2-3 pessoas consiga executar o plano de 90 dias com consistência, baixa fricção e manutenibilidade.

### Premissas adotadas

| # | Premissa | Justificativa |
|---|---|---|
| P1 | Stack 100% TypeScript (front + back + shared) para eliminar troca de contexto de linguagem | 2 devs, 1 linguagem = menos bugs de fronteira, tipos compartilhados, refatoração segura |
| P2 | Nenhuma dependência de plataforma gerenciada (Vercel, Supabase, Planetscale) no MVP — tudo roda em VPS única via Docker Compose | Custo fixo baixo, zero vendor lock-in, controle total |
| P3 | Ferramentas gratuitas ou com tier generoso para startups: GitHub Free, Sentry Free, Uptime Robot Free, Cloudflare Free | Orçamento total de infraestrutura < R$ 200/mês |
| P4 | ORM com type-safety como requisito mandatório — sem raw SQL para queries comuns | Evita erros de runtime em queries; autocompletion no editor; migrations versionadas |
| P5 | Zero dependência de runtime Java, Python ou Ruby na VPS — apenas Node.js e PostgreSQL | Simplifica Dockerfile, reduz superfície de ataque, unifica toolchain |

### Análise

A stack foi escolhida por 3 critérios eliminatórios: (a) time de 2 devs consegue dominar, (b) funciona em VPS única de R$ 120/mês, (c) não introduz risco de abandono por complexidade. TypeScript ponta-a-ponta é o maior acelerador: tipos compartilhados entre front e back eliminam uma classe inteira de bugs (desserialização de XML fiscal, campos obrigatórios, enums de status).

O Fastify foi escolhido sobre Express por performance (2-3x mais rápido em benchmarks) e schema validation nativa — essencial para APIs que recebem upload de arquivos. O Next.js 14 com App Router foi escolhido sobre Vite+React Router porque Server Components reduzem o JS enviado ao celular antigo do Roberto, e SSR da landing page melhora SEO para aquisição futura.

Drizzle ORM foi escolhido sobre Prisma por 3 razões: (a) cold start instantâneo (Prisma carrega engine Rust que adiciona 200-500ms), (b) schemas em TypeScript puro (sem arquivo .prisma, sem code generation), (c) JSONB first-class — essencial para armazenar XML bruto e checklist dinâmico.

### Decisões recomendadas

| Decisão | Conteúdo | Status |
|---|---|---|
| D1 | **Front-end**: Next.js 14 (App Router) + React 18 + Tailwind CSS 3 + shadcn/ui | Decisão de stack |
| D2 | **Back-end**: Fastify 5 + TypeScript 5 + Drizzle ORM + Zod | Decisão de stack |
| D3 | **Banco**: PostgreSQL 16 (Docker) + Drizzle Kit para migrations + pgvector (preparação Fase 2) | Decisão de stack |
| D4 | **Monorepo**: Turborepo 2 + pnpm 9 workspaces | Decisão de stack |
| D5 | **IA**: OpenRouter como gateway unificado; modelo primário GPT-4o-mini; fallback Claude 3.5 Haiku; timeout 5s | Decisão de stack |
| D6 | **Infra**: Docker Compose (3 containers) + Nginx reverse proxy + GitHub Container Registry | Decisão de stack |
| D7 | **Testes**: Vitest (unitários) + Playwright (e2e) + Supertest (API) | Decisão de stack |
| D8 | **Monitoramento**: Sentry (erros) + pino (logs estruturados) + Uptime Robot (health check) | Decisão de stack |

---

### 5.1 FRONT-END

| Ferramenta | Versão | Justificativa | Alternativa descartada |
|---|---|---|---|
| **Next.js** | 14.2+ | App Router com Server Components reduz JS no cliente. SSR melhora LCP/SEO da landing page. PWA via next-pwa. Roteamento baseado em arquivos = menos boilerplate | **Remix**: ecossistema menor. **Vite + React Router**: exigiria SSR manual. **CRA**: obsoleto |
| **React** | 18.3+ | Server Components, Suspense para skeleton screens, useTransition para navegação suave. Ecossistema maduro | **Svelte**: menos pacotes acessíveis. **Vue**: time sem experiência. **HTMX**: não atende PWA offline |
| **TypeScript** | 5.5+ | Type-safety ponta a ponta. Tipos compartilhados via pacote `shared`. Strict mode ativado | **JS puro**: custo de manutenção proibitivo com schema de XML fiscal |
| **Tailwind CSS** | 3.4+ | Design system da Etapa 14 mapeado direto para config. Bundle pequeno (purge automático). Zero CSS não utilizado | **CSS Modules**: mais arquivos. **Styled Components**: runtime cost. **Chakra/Mantine**: pesados |
| **shadcn/ui** | latest | Componentes acessíveis (Radix UI), copiados para o código (não instalados como dependência). Customizáveis via Tailwind. Cobertura: Dialog, DropdownMenu, Tabs, Toast, Skeleton, Checkbox | **Material UI**: pesado, visual "Google". **Ant Design**: chinês, complexo. **Headless UI**: menos componentes |
| **Phosphor Icons** | 2.x | 1.000+ ícones, licença MIT, estilo fill + regular. Usado para ícones fiscais e de navegação | **Lucide**: também bom, sem ícone específico para doc fiscal. **Heroicons**: poucos ícones |
| **next-pwa** | 0.6+ | Service Worker + Web Manifest para PWA. Cache offline. Instalável na tela inicial do Android do Roberto | **Workbox direto**: mais configuração manual |
| **date-fns** | 3.x | Datas em português (locale pt-BR). Funções puras, tree-shakeable. Substitui moment.js | **Day.js**: menos funções. **Luxon**: mais pesado. **Intl nativo**: cobre 80% mas verboso |
| **react-hook-form** | 7.x | Formulários performáticos (sem re-render desnecessário). Integração nativa com Zod para validação. Essencial para upload form | **Formik**: mais lento, mais boilerplate. **TanStack Form**: muito novo |
| **@tanstack/react-query** | 5.x | Cache, refetch, optimistic updates. Essencial para dashboard com dados que mudam a cada upload. Devtools gratuitos | **SWR**: menos funcionalidades. **Redux Toolkit Query**: overkill para esse projeto |
| **zod** | 3.23+ | Validação de schema compartilhada front/back. Inferência de tipos. Usado em upload, dados de nota, formulários | **Yup**: sem type inference nativa. **Joi**: pesado. **Valibot**: ecossistema menor |

---

### 5.2 BACK-END

| Ferramenta | Versão | Justificativa | Alternativa descartada |
|---|---|---|---|
| **Fastify** | 5.x | Servidor HTTP mais rápido do Node. Schema validation nativa via JSON Schema. Plugins: CORS, rate-limit, multipart, JWT. Menos opinativo que NestJS | **Express**: mais lento, sem validação nativa. **NestJS**: pesado (decorators). **Hono**: ecossistema menor. **Elysia (Bun)**: Bun não é LTS |
| **@fastify/multipart** | 8.x | Upload de arquivos com streaming. Suporta ZIP e múltiplos XMLs. Essencial para ingestão de notas | **Multer**: Express-only. **Busboy direto**: mais boilerplate |
| **@fastify/rate-limit** | 10.x | Proteção contra brute force no magic link. 3 tentativas/15min por número. Armazenamento em memória no MVP | **express-rate-limit**: incompatível com Fastify |
| **@fastify/cors** | 10.x | CORS para desenvolvimento local (web em :3000, api em :3001). Configuração restrita em produção | Configuração manual de headers: propenso a erro |
| **fast-xml-parser** | 4.5+ | Parser de XML mais rápido do Node (benchmark comprovado). Suporta namespaces NF-e. Converte XML → JSON nativo. XPath para extração seletiva de campos | **xml2js**: 3-5x mais lento. **libxmljs**: bindings C, problemas compilação Docker. **sax**: streaming, mais complexo |
| **Drizzle ORM** | 0.33+ | SQL-like API com type-safety total. Migrations automáticas. Sem code generation como Prisma. JSONB first-class. Schemas em TypeScript puro | **Prisma**: engine Rust pesada, cold start alto. **Knex.js**: sem type-safety. **TypeORM**: lento, bugs com JSONB. **Kysely**: bom, mas Drizzle tem DX superior |
| **drizzle-kit** | 0.24+ | CLI para gerar, aplicar e versionar migrations. Push direto para dev (sem arquivos .sql). Introspect de banco existente | **Prisma Migrate**: mais lento, shadow database obrigatório |
| **pg** (node-postgres) | 8.x | Driver PostgreSQL nativo. Drizzle usa por baixo. Pool de conexões configurável | **postgres.js**: também suportado pelo Drizzle |
| **jsonwebtoken** | 9.x | Geração e verificação de JWT para magic link. HMAC-SHA256. Sem dependência de serviço externo de auth | **jose**: mais moderno, mas time conhece mais jsonwebtoken. **Auth0/Clerk**: caro, Roberto não tem e-mail |
| **pino** | 9.x | Logger JSON estruturado mais rápido do Node. Integração com pino-pretty para dev. Output compatível com Sentry | **Winston**: mais lento, configuração verbosa. **Bunyan**: abandonado |
| **pino-pretty** | 11.x | Formata logs para leitura humana em desenvolvimento. Não usado em produção (JSON puro para Sentry) | Desnecessário em prod |
| **pdfkit** | 0.15+ | Geração de PDF nativa em Node. Sem dependência de headless browser. ~50MB RAM vs 500MB do Puppeteer | **Puppeteer + HTML→PDF**: consumo de RAM 10x maior. **jsPDF**: API ruim para tabelas. **pdfmake**: declaração verbosa |
| **nodemailer** | 6.x | Envio de e-mail transacional via SMTP. Suporte a SendGrid, Mailgun, SES ou SMTP direto. Zero vendor lock-in | **Resend SDK**: lock-in. **SendGrid SDK**: lock-in. **AWS SES SDK**: lock-in |
| **archiver** | 7.x | Descompactação de ZIP recebido no upload. Suporta ZIP, TAR, GZ. Streaming (não carrega arquivo inteiro em memória) | **adm-zip**: carrega tudo em memória. **unzipper**: menos maduro. **yauzl**: baixo nível |
| **zod** | 3.23+ | Validação de input em todas as rotas Fastify. Tipos inferidos para request/response. Compartilhado com front-end | Já justificado no front-end |
| **tsx** | 4.x | Executa TypeScript diretamente em dev (hot reload com --watch). Scripts de migration, seeds, cron jobs | **ts-node**: mais lento |

---

### 5.3 BANCO DE DADOS

| Ferramenta | Versão | Justificativa | Alternativa descartada |
|---|---|---|---|
| **PostgreSQL** | 16.4-alpine (Docker) | JSONB para XML bruto e checklist. Índices GIN para busca textual (fornecedor). Constraints CHECK para enums (status, regime). CTEs para queries de dashboard. Row-Level Security preparado para multi-tenant | **MySQL 8**: JSON pior que JSONB. **SQLite**: não suporta concorrência para >1 usuário. **MongoDB**: sem transações ACID, schema flexível é risco para dados fiscais |
| **pgvector** | 0.7+ | Extensão PostgreSQL para busca vetorial. Preparação para RAG fiscal na Fase 2. Instalado mas não usado no MVP | **Pinecone/Weaviate**: serviços externos caros. pgvector é grátis e roda no mesmo banco |
| **Drizzle Kit** | 0.24+ | Migrations versionadas. Push direto em dev. Introspect de banco existente | Já justificado no back-end |

---

### 5.4 INFRAESTRUTURA E DEVOPS

| Ferramenta | Versão | Justificativa | Alternativa descartada |
|---|---|---|---|
| **Docker** | 26+ | Containerização padrão. Multi-stage build reduz imagem final. Cache de camadas acelera CI | **Podman**: menos suporte em CI/CD |
| **Docker Compose** | v2.27+ | Orquestração single-host: 3 serviços (api, web, postgres). Healthchecks. Volumes para persistência | **k8s/k3s/microk8s**: overkill absoluto para 3 containers. **Docker Swarm**: abandonado |
| **Nginx** | 1.27-alpine (Docker) | Reverse proxy. Terminação SSL (Let's Encrypt via certbot). Serve estáticos do Next.js. Rate limiting. Gzip | **Caddy**: auto-SSL é bom, mas menos controle. **Traefik**: complexo para 3 serviços |
| **GitHub Actions** | latest | CI/CD nativo do GitHub. Build + test + deploy. Secrets para env vars. 2.000 min/mês grátis | **GitLab CI**: exigiria migrar repositório. **CircleCI**: pago após tier gratuito |
| **GitHub Container Registry** | latest | Registry de imagens Docker integrado ao GitHub. Autenticação via GITHUB_TOKEN. Zero custo adicional | **Docker Hub**: limite de pulls. **AWS ECR**: custo extra |
| **Cloudflare DNS** | Free | DNS para copilotofiscal.com. Proxy com CDN, DDoS protection, SSL gratuito. Regras de redirect (www→app) | **Route53**: pago. **Namecheap DNS**: sem CDN |
| **certbot** | latest | Renovação automática de certificados SSL/TLS no Nginx. Cronjob mensal | **acme.sh**: alternativa válida. **Cloudflare Origin CA**: lock-in |
| **AWS S3** | Standard | Backup diário do PostgreSQL (pg_dump). Lifecycle policy: 7 diários + 4 semanais + 3 mensais. Custo: ~R$ 5/mês | **Backblaze B2**: mais barato, mas S3 é padrão universal. **Minio self-hosted**: mais complexo |

---

### 5.5 MONITORAMENTO E OBSERVABILIDADE

| Ferramenta | Versão | Justificativa | Alternativa descartada |
|---|---|---|---|
| **Sentry** | SaaS Free | Error tracking front + back. Source maps. Breadcrumbs para reproduzir erros. Integração nativa com Next.js e Fastify. 5.000 eventos/mês = ~160 erros/dia | **Datadog**: caro. **LogRocket**: foco em session replay. **Rollbar**: menos integrações |
| **Uptime Robot** | Free | Health check HTTP a cada 5 min em app.copilotofiscal.com/api/health. Alerta via e-mail se downtime > 1 min. 50 monitores grátis | **Pingdom**: pago. **Datadog Synthetics**: caro. **Better Uptime**: tier gratuito limitado |
| **pino** | 9.x | Logs JSON estruturados. Níveis: trace, debug, info, warn, error, fatal. Redaction automática de dados sensíveis (CPF, telefone) via serializers | Já justificado no back-end |
| **Drizzle Studio** | latest | Interface gráfica para explorar o banco em dev. Conexão direta com drizzle.config.ts. Alternativa leve ao pgAdmin | **pgAdmin**: imagem Docker 300MB. **DBeaver**: desktop, não web |

---

### 5.6 TESTES

| Ferramenta | Versão | Justificativa | Alternativa descartada |
|---|---|---|---|
| **Vitest** | 1.6+ | Test runner compatível com Vite (mesmo ecossistema do Next.js). Mais rápido que Jest. TypeScript nativo. Hooks: beforeEach, afterAll. Mocking integrado. Coverage via v8 | **Jest**: mais lento, configuração complexa com ESM. **Mocha + Chai**: sem TypeScript nativo, mais boilerplate |
| **Playwright** | 1.45+ | Testes e2e em browsers reais (Chromium, Firefox, WebKit). Grava vídeo de falhas. Screenshots. Testa PWA offline. API testing integrado | **Cypress**: sem suporte a múltiplas abas/domínios. **Puppeteer**: menos funcionalidades. **Selenium**: lento, complexo |
| **Supertest** | 7.x | Testes de integração HTTP para rotas Fastify. Assertions no status code, body, headers. Sem precisar subir servidor real | **fetch nativo**: mais boilerplate para assertions. **nock**: mock de HTTP externo, não teste de rota |
| **@faker-js/faker** | 9.x | Geração de dados realistas para testes: CNPJs, chaves NF-e, nomes de fornecedor, valores. Locale pt-BR | **Chance.js**: menos tipos. **casual**: abandonado |

---

### 5.7 FERRAMENTAS DE DESENVOLVIMENTO

| Ferramenta | Versão | Justificativa | Alternativa descartada |
|---|---|---|---|
| **pnpm** | 9.x | Gerenciador de pacotes rápido, disco-efficient (hard links). Strict mode evita imports fantasmas. Workspaces nativos para monorepo. Catalogs para versões consistentes | **npm**: mais lento, sem strict mode. **yarn**: pnpm superou em performance. **bun**: runtime novo, ainda instável |
| **Turborepo** | 2.x | Orquestração de monorepo. Cache remoto (GitHub Actions). Execução paralela de lint, test, build. Incremental: só roda o que mudou | **Nx**: mais complexo, mais features (overkill). **Lerna**: lento. **Rush**: Microsoft, complexo |
| **ESLint** | 9.x | Linting com flat config. Plugins: @typescript-eslint, eslint-plugin-react-hooks, eslint-plugin-drizzle. Regra customizada: proíbe console.log em prod | **Biome**: rápido, mas não cobre todos os plugins. **Prettier standalone**: só formata, não linta |
| **Prettier** | 3.x | Formatação de código consistente. Integrado ESLint via eslint-config-prettier. Config mínima: printWidth 100, singleQuote true | **dprint**: mais rápido, menos integrado. **Biome**: substituto futuro |
| **Husky** | 9.x | Git hooks: pre-commit (lint-staged + typecheck), commit-msg (conventional commits). Evita commits com erro | **lefthook**: alternativa válida. **simple-git-hooks**: menos maduro |
| **lint-staged** | 15.x | Roda ESLint + Prettier apenas nos arquivos staged. Rápido (não linta o projeto inteiro) | **pretty-quick**: só formatação |
| **commitlint** | 19.x | Valida mensagens de commit (conventional commits). Integrado com Husky | **commitizen**: prompt interativo, não validação |
| **dotenv-cli** | 7.x | Carrega .env antes de rodar scripts. Essencial para migrations que precisam de DATABASE_URL | **direnv**: depende de instalação no shell. **cross-env**: menos funcionalidades |

---

### 5.8 SERVIÇOS EXTERNOS

| Serviço | Plano | Custo/mês | Justificativa | Alternativa descartada |
|---|---|---|---|---|
| **WhatsApp Business Cloud API** | Pay-as-you-go | R$ 25 (~500 msgs) | API oficial da Meta. Templates aprovados. Webhook para receber mensagens (futuro). 1.000 conversas grátis/mês | **Twilio WhatsApp**: mais caro por mensagem. **WPPConnect/Unofficial**: risco de bloqueio, viola ToS |
| **OpenRouter** | Pay-as-you-go | R$ 15 | Gateway unificado para 200+ modelos. Sem lock-in de fornecedor. Fallback automático entre modelos. Rota para GPT-4o-mini e Claude Haiku | **OpenAI direto**: lock-in. **Anthropic direto**: lock-in. **Groq**: menos modelos |
| **AWS S3** | Pay-as-you-go | R$ 5 | Backup PostgreSQL. Standard Infrequent Access para backups >30 dias. Lifecycle policy automática | Já justificado na infraestrutura |
| **Sentry** | Free | R$ 0 | Error tracking. 5.000 eventos/mês = ~160 erros/dia. Suficiente para MVP com 5 tenants | Já justificado no monitoramento |
| **Uptime Robot** | Free | R$ 0 | Monitoramento. 50 monitores, 5-min interval. Alerta por e-mail | Já justificado no monitoramento |
| **Cloudflare** | Free | R$ 0 | DNS + CDN + DDoS + SSL | Já justificado na infraestrutura |
| **GitHub** | Free | R$ 0 | Repositório + Actions + Container Registry + Projects | **GitLab**: também gratuito, mas repo já está no GitHub |

**Custo total serviços externos: ~R$ 45/mês** (excluindo VPS de R$ 120/mês).

---

### Resumo Visual da Stack

```
┌─────────────────────────────────────────────────────────┐
│                    FRONT-END                              │
│  Next.js 14 · React 18 · TypeScript 5 · Tailwind CSS 3   │
│  shadcn/ui · react-query · react-hook-form · Zod          │
│  Phosphor Icons · date-fns · next-pwa                     │
├─────────────────────────────────────────────────────────┤
│                    BACK-END                               │
│  Fastify 5 · TypeScript 5 · Drizzle ORM · Zod             │
│  fast-xml-parser · pg · jsonwebtoken · pino               │
│  nodemailer · archiver · pdfkit                            │
├─────────────────────────────────────────────────────────┤
│                    BANCO DE DADOS                         │
│  PostgreSQL 16 + pgvector · Drizzle Kit                   │
├─────────────────────────────────────────────────────────┤
│                    MONOREPO                               │
│  Turborepo 2 · pnpm 9 · ESLint 9 · Prettier 3             │
│  Vitest · Playwright · Husky · lint-staged                │
├─────────────────────────────────────────────────────────┤
│                    INFRAESTRUTURA                         │
│  Docker Compose · Nginx · GitHub Actions                  │
│  GHCR · Cloudflare · AWS S3                               │
├─────────────────────────────────────────────────────────┤
│                    SERVIÇOS EXTERNOS                      │
│  WhatsApp Business API · OpenRouter · Sentry              │
│  Uptime Robot · GitHub                                    │
└─────────────────────────────────────────────────────────┘
```

---

### Versões Travadas (resumo package.json)

| Pacote | Versão | Semver |
|---|---|---|
| next | ^14.2.15 | minor |
| react | ^18.3.1 | minor |
| typescript | ^5.5.4 | minor |
| fastify | ^5.1.0 | minor |
| drizzle-orm | ^0.33.0 | minor |
| drizzle-kit | ^0.24.2 | minor |
| fast-xml-parser | ^4.5.0 | minor |
| tailwindcss | ^3.4.13 | minor |
| @tanstack/react-query | ^5.59.0 | minor |
| zod | ^3.23.8 | minor |
| vitest | ^1.6.0 | minor |
| @playwright/test | ^1.45.0 | minor |
| turborepo | ^2.1.0 | minor |
| pnpm | ^9.12.0 | minor |
| postgres (Docker) | 16.4-alpine | patch |
| node (Docker) | 22-alpine | minor |

---

### O que NÃO entra no MVP

| Ferramenta | Motivo | Quando entra |
|---|---|---|
| Redis | Sem necessidade de cache ou fila no MVP. pg-boss cobre fila se necessário | Fase 2 (se >500 tenants) |
| BullMQ / pg-boss | Processamento síncrono é suficiente para 200 XMLs. Adicionar se benchmark mostrar >90s | Fase 2 |
| NextAuth / Auth.js | Magic link customizado é mais simples e não depende de OAuth (Roberto não tem Google/Microsoft) | Fase 2 (se expandir para empresas maiores) |
| Stripe / Pagar.me | Cobrança manual via Pix nos primeiros 10 clientes. Integração de gateway adiciona 2 semanas | Fase 2 (mês 4) |
| React Email / MJML | E-mails transacionais são texto puro. Templates HTML desnecessários para 3 tipos de e-mail | Fase 2 (se onboarding automatizado) |
| tRPC / GraphQL | REST com Fastify + tipos compartilhados já garante type-safety. tRPC adicionaria complexidade | Fase 3 (se app nativo) |
| Prisma | Drizzle é mais leve, mais rápido em cold start, JSONB first-class, sem engine Rust | Nunca (decisão de arquitetura) |
| Docker Swarm / k8s | 3 containers em 1 VPS não precisam de orquestração além do Compose | Fase 3 (se multi-VPS) |
| Terraform / Pulumi | Infraestrutura é 1 VPS provisionada manualmente. IaC é overkill para esse estágio | Fase 2 (se multi-cloud) |
| DataDog / Grafana | Sentry + pino + Uptime Robot cobrem 100% das necessidades de observabilidade do MVP | Fase 3 |
| Elasticsearch | Busca textual em nome de fornecedor usa ILIKE + índice GIN no PostgreSQL. Suficiente para <10k notas | Fase 3 |
| WebSocket / SSE | Dashboard não precisa de atualização em tempo real. Polling a cada upload é suficiente | Fase 3 |

### Riscos e pontos de atenção

| Risco | Severidade | Mitigação |
|---|---|---|
| fast-xml-parser pode não cobrir 100% dos namespaces de NF-e de sistemas legados (SAP, Protheus) | Alta | Testar na Sprint 1 com XMLs de 5 ERPs diferentes. Se taxa de falha >5%, adicionar sax (parser SAX) como fallback |
| Drizzle ORM é relativamente novo (2023). Comunidade menor que Prisma. Risco de bugs em edge cases com JSONB | Média | Testar operações JSONB exaustivamente. Drizzle tem ~23k estrelas no GitHub, mantido ativamente. Plano B: Kysely (API similar) |
| WhatsApp Business API pode rejeitar templates ou atrasar aprovação (Meta) | Média | Submeter 6 templates na Semana 1. Ter fallback: SMS via Twilio (pré-cadastrado, mas não implementado). W3 e W5 são os templates críticos |
| sharp pode ter problemas de compilação em ARM64 (Apple Silicon / AWS Graviton) | Baixa | VPS é x86_64 (Hetzner CX22). Dev em Mac com Rosetta funciona. Docker multi-arch se necessário |
| pnpm strict mode pode quebrar com pacotes mal empacotados que importam dependências não declaradas | Baixa | Raro em 2026. Se ocorrer, usar `pnpm.overrides` ou `shamefully-hoist=true` como último recurso |
| OpenRouter pode ter latência alta no Brasil (servidores nos EUA/Europa) | Média | LLM é opcional — explicação templateada cobre 100% dos cenários. Timeout de 5s na chamada OpenRouter. Se latency >3s, desabilitar LLM até Fase 2 |


---

## Etapa 19 — Modelo de Dados

### Objetivo da etapa

Produzir o schema físico completo do banco de dados PostgreSQL 16 para o FiscoPilot MVP — DDL, índices, enums, constraints, triggers e políticas de acesso — traduzindo o modelo de domínio lógico da Etapa 17 em definições prontas para Drizzle ORM e drizzle-kit migrations.

### Premissas adotadas

| # | Premissa | Justificativa |
|---|---|---|
| P1 | Todo registro de entidade-fim (nfe_document, inconsistency, audit_log) pertence a uma organization via `organization_id NOT NULL` | Multi-tenant desde o dia zero; evita migração dolorosa depois |
| P2 | UUIDv7 como chave primária em todas as tabelas | UUIDv7 é temporalmente ordenável (melhor para índices B-tree que UUIDv4), gerado no servidor, sem colisão entre tenants |
| P3 | JSONB para dados semi-estruturados (xml_raw, checklist_json, details) com índices GIN onde houver query | XMLs de NF-e variam entre emissores; checklist varia por regra; audit_log.details é genérico |
| P4 | Enums como tipo nativo PostgreSQL (CREATE TYPE), não como tabelas de domínio | Menos joins, queries mais simples, type-safety no Drizzle. Mudar enum = migration. OK para domínios estáveis (status, regime, role) |
| P5 | Timestamps com timezone (timestamptz). Sempre UTC no banco; front-end converte para horário local | Evita bugs de fuso horário em operações interestaduais |
| P6 | Soft-delete não implementado no MVP — dados fiscais não se apagam. Exclusão lógica só na Fase 2 se necessário | Complexidade adicional sem ganho claro para 5 tenants |
| P7 | Constraints nomeadas explicitamente (CK_, FK_, UQ_, IDX_) para mensagens de erro legíveis e migrations reversíveis | Debug e manutenção facilitados |

### Análise

O schema reflete o pipeline central do produto: receber um lote de XMLs → extrair dados → rodar regras → persistir inconsistências → permitir ação do usuário. As decisões-chave de modelagem foram:

**UUIDv7 vs UUIDv4 vs serial:** UUIDv7 gera identificadores temporalmente ordenáveis (timestamp embutido nos primeiros 48 bits). Isso significa que inserts em tabelas com PK UUIDv7 não fragmentam o índice B-tree — performance de insert similar a serial, com as vantagens de UUID (geração descentralizada, sem colisão). PostgreSQL 16 não tem função nativa `uuid_generate_v7()`, então usamos a extensão `pg_uuidv7` ou geramos na camada de aplicação (Drizzle + `uuidv7` npm package).

**JSONB vs colunas tipadas para checklist:** O checklist de ações (Etapa 16) tem estrutura que varia por tipo de regra (R1 tem 4 passos, R5 tem 3). Armazenar como JSONB `[{ "text": "...", "done": false }]` permite flexibilidade sem alterar schema quando novas regras são adicionadas. O trade-off é perder validação de integridade no banco — mitigado pela validação Zod na aplicação.

**Índices parciais para queries quentes:** As queries mais frequentes são filtradas por `organization_id` + período + status. Índices parciais reduzem tamanho e aceleram: `WHERE organization_id = $1 AND data_emissao >= $2 AND data_emissao < $3`.

**RLS (Row-Level Security) como camada extra de segurança:** Embora a aplicação sempre filtre por `organization_id`, o RLS garante que um bug de query não exponha dados de outro tenant. Política simples: `USING (organization_id = current_setting('app.current_organization_id')::uuid)`.

### Decisões recomendadas

| Decisão | Conteúdo | Status |
|---|---|---|
| D1 | UUIDv7 como PK universal, gerado na aplicação (pacote `uuidv7` npm), armazenado como `uuid` nativo PostgreSQL | Decisão de schema |
| D2 | 8 enums nativos PostgreSQL: `organization_regime`, `simples_anexo`, `user_role`, `nfe_status`, `risk_classification`, `rule_id`, `inconsistency_status`, `upload_source` | Decisão de schema |
| D3 | 6 tabelas principais + 2 tabelas de suporte + 2 tabelas de sistema: `organizations`, `users`, `nfe_documents`, `nfe_items`, `inconsistencies`, `audit_log`, `magic_links`, `upload_batches`, `pending_notifications`, `fiscal_reference_tables` | Decisão de schema |
| D4 | Índices parciais para queries de dashboard (organization_id + data_emissao + status). Índice GIN em xml_raw e checklist_json | Decisão de performance |
| D5 | Row-Level Security ativado em todas as tabelas de tenant — bkp caso a aplicação esqueça o filtro | Decisão de segurança |
| D6 | `fiscal_reference_tables` armazena tabelas de referência (CFOP, NCM, alíquotas) versionadas. Populada por seed scripts, não pela aplicação | Decisão de arquitetura |
| D7 | `pending_notifications` como buffer de resiliência para WhatsApp API — enfileira e retry sem perder notificação | Decisão de resiliência |

### Entregáveis

---

#### 5.1 Enums

```sql
-- Regime tributário da organização
CREATE TYPE organization_regime AS ENUM (
  'SIMPLES_NACIONAL',
  'LUCRO_PRESUMIDO',
  'LUCRO_REAL'
);

-- Anexo do Simples Nacional (só aplicável se regime = SIMPLES_NACIONAL)
CREATE TYPE simples_anexo AS ENUM (
  'ANEXO_I',   -- Comércio
  'ANEXO_II',  -- Indústria
  'ANEXO_III', -- Serviços
  'ANEXO_IV',  -- Serviços específicos
  'ANEXO_V',   -- Serviços específicos
  'NA'         -- Não se aplica (Lucro Presumido/Real)
);

-- Papel do usuário na organização
CREATE TYPE user_role AS ENUM (
  'ADMIN',
  'OPERADOR'
);

-- Status da NF-e (se está ativa, cancelada, etc.)
CREATE TYPE nfe_status AS ENUM (
  'ATIVA',
  'CANCELADA',
  'DENEGADA',
  'INUTILIZADA',
  'DESCONHECIDA'
);

-- Classificação de risco da inconsistência
CREATE TYPE risk_classification AS ENUM (
  'OK',
  'ATENCAO',
  'RISCO_ALTO'
);

-- Identificador da regra que gerou a inconsistência
CREATE TYPE rule_id AS ENUM (
  'R1', -- CFOP divergente
  'R2', -- Alíquota ICMS divergente
  'R3', -- NCM suspeito
  'R4', -- CNPJ irregular
  'R5', -- Valor total divergente
  'R6', -- CST incompatível
  'R7', -- Chave de acesso inválida
  'R8'  -- ICMS ST indevido
);

-- Status de tratamento da inconsistência pelo usuário
CREATE TYPE inconsistency_status AS ENUM (
  'PENDENTE',
  'EM_ANDAMENTO',
  'RESOLVIDA',
  'IGNORADA'
);

-- Origem do upload
CREATE TYPE upload_source AS ENUM (
  'WEB',
  'EMAIL'
);
```

---

#### 5.2 DDL Completo

```sql
-- ============================================================
-- EXTENSÕES
-- ============================================================
CREATE EXTENSION IF NOT EXISTS "uuid-ossp";
CREATE EXTENSION IF NOT EXISTS "pgcrypto";
CREATE EXTENSION IF NOT EXISTS "pg_trgm";
-- CREATE EXTENSION IF NOT EXISTS "pg_uuidv7";
CREATE EXTENSION IF NOT EXISTS "vector";


-- ============================================================
-- TABELA: organizations
-- ============================================================
CREATE TABLE organizations (
  id              uuid PRIMARY KEY DEFAULT gen_random_uuid(),
  cnpj            varchar(14)  NOT NULL,
  nome_fantasia   varchar(150) NOT NULL,
  razao_social    varchar(200),
  regime          organization_regime NOT NULL DEFAULT 'SIMPLES_NACIONAL',
  anexo_simples   simples_anexo NOT NULL DEFAULT 'ANEXO_I',
  uf              char(2)      NOT NULL,
  whatsapp_dono   varchar(15),
  email_contato   varchar(255),
  created_at      timestamptz  NOT NULL DEFAULT now(),
  updated_at      timestamptz  NOT NULL DEFAULT now(),

  CONSTRAINT UQ_organizations_cnpj UNIQUE (cnpj),
  CONSTRAINT CK_organizations_anexo CHECK (
    (regime = 'SIMPLES_NACIONAL' AND anexo_simples IN ('ANEXO_I','ANEXO_II','ANEXO_III','ANEXO_IV','ANEXO_V'))
    OR (regime != 'SIMPLES_NACIONAL' AND anexo_simples = 'NA')
  )
);

CREATE INDEX IDX_organizations_cnpj ON organizations (cnpj);
CREATE INDEX IDX_organizations_uf ON organizations (uf);

COMMENT ON TABLE organizations IS 'Organização (tenant) — uma loja de material de construção';
COMMENT ON COLUMN organizations.cnpj IS 'Apenas números, 14 dígitos';
COMMENT ON COLUMN organizations.anexo_simples IS 'Anexo do Simples Nacional; NA para Lucro Presumido/Real';


-- ============================================================
-- TABELA: users
-- ============================================================
CREATE TABLE users (
  id              uuid PRIMARY KEY DEFAULT gen_random_uuid(),
  organization_id uuid         NOT NULL REFERENCES organizations(id) ON DELETE CASCADE,
  nome            varchar(150) NOT NULL,
  whatsapp        varchar(15)  NOT NULL,
  role            user_role    NOT NULL DEFAULT 'OPERADOR',
  is_active       boolean      NOT NULL DEFAULT true,
  last_login_at   timestamptz,
  created_at      timestamptz  NOT NULL DEFAULT now(),
  updated_at      timestamptz  NOT NULL DEFAULT now(),

  CONSTRAINT UQ_users_org_whatsapp UNIQUE (organization_id, whatsapp),
  CONSTRAINT CK_users_whatsapp_format CHECK (whatsapp ~ '^55[1-9][1-9][0-9]{8,9}$')
);

CREATE INDEX IDX_users_organization ON users (organization_id);
CREATE INDEX IDX_users_whatsapp ON users (whatsapp);

COMMENT ON TABLE users IS 'Usuários de uma organização (Roberto = ADMIN, Fernanda = OPERADOR)';
COMMENT ON COLUMN users.whatsapp IS 'Formato internacional sem +: 5511999991234';


-- ============================================================
-- TABELA: nfe_documents
-- ============================================================
CREATE TABLE nfe_documents (
  id                uuid PRIMARY KEY DEFAULT gen_random_uuid(),
  organization_id   uuid           NOT NULL REFERENCES organizations(id) ON DELETE CASCADE,
  upload_batch_id   uuid           REFERENCES upload_batches(id) ON DELETE SET NULL,

  chave_acesso      varchar(44)    NOT NULL,
  numero            integer        NOT NULL,
  serie             integer        NOT NULL DEFAULT 1,
  modelo            varchar(2)     NOT NULL DEFAULT '55',
  data_emissao      date           NOT NULL,
  data_entrada_saida date,

  cnpj_emitente     varchar(14)    NOT NULL,
  nome_emitente     varchar(200)   NOT NULL,
  uf_emitente       char(2)        NOT NULL,
  cnpj_destinatario varchar(14)    NOT NULL,

  valor_total       numeric(14,2)  NOT NULL,
  valor_produtos    numeric(14,2),
  valor_ipi         numeric(14,2),
  valor_icms        numeric(14,2),
  base_calculo_icms numeric(14,2),
  aliquota_icms     numeric(5,2),

  cfop              varchar(4),
  ncm_principal     varchar(8),
  cst_pis           varchar(3),
  cst_cofins        varchar(3),
  cst_icms          varchar(3),
  icms_st           boolean        NOT NULL DEFAULT false,
  icms_st_valor     numeric(14,2),

  status_nfe        nfe_status     NOT NULL DEFAULT 'ATIVA',

  xml_raw           jsonb,
  xml_hash          varchar(64),

  source            upload_source  NOT NULL DEFAULT 'WEB',
  created_at        timestamptz    NOT NULL DEFAULT now(),

  CONSTRAINT UQ_nfe_chave_acesso UNIQUE (chave_acesso),
  CONSTRAINT CK_nfe_data_emissao CHECK (data_emissao >= '2006-01-01'),
  CONSTRAINT CK_nfe_valor_total CHECK (valor_total >= 0)
);

CREATE INDEX IDX_nfe_organization ON nfe_documents (organization_id);
CREATE INDEX IDX_nfe_data_emissao ON nfe_documents (organization_id, data_emissao DESC);
CREATE INDEX IDX_nfe_status ON nfe_documents (organization_id, status_nfe) WHERE status_nfe = 'ATIVA';
CREATE INDEX IDX_nfe_emitente ON nfe_documents (organization_id, cnpj_emitente);
CREATE INDEX IDX_nfe_upload_batch ON nfe_documents (upload_batch_id) WHERE upload_batch_id IS NOT NULL;
CREATE INDEX IDX_nfe_xml_hash ON nfe_documents (xml_hash);
CREATE INDEX IDX_nfe_xml_raw_gin ON nfe_documents USING GIN (xml_raw);

COMMENT ON TABLE nfe_documents IS 'Nota Fiscal Eletrônica (NF-e) processada';
COMMENT ON COLUMN nfe_documents.xml_hash IS 'SHA-256 do XML original. Usado para evitar duplicação';
COMMENT ON COLUMN nfe_documents.xml_raw IS 'XML original convertido para JSON. Schema completo para auditoria';


-- ============================================================
-- TABELA: nfe_items
-- ============================================================
CREATE TABLE nfe_items (
  id                uuid PRIMARY KEY DEFAULT gen_random_uuid(),
  nfe_document_id   uuid           NOT NULL REFERENCES nfe_documents(id) ON DELETE CASCADE,
  organization_id   uuid           NOT NULL REFERENCES organizations(id) ON DELETE CASCADE,

  numero_item       integer        NOT NULL,
  codigo_produto    varchar(60),
  descricao         varchar(500)   NOT NULL,
  ncm               varchar(8),
  cfop              varchar(4),
  quantidade        numeric(14,4)  NOT NULL DEFAULT 1,
  unidade           varchar(6)     NOT NULL DEFAULT 'UN',
  valor_unitario    numeric(14,4)  NOT NULL,
  valor_total       numeric(14,2)  NOT NULL,
  valor_frete       numeric(14,2),

  cst_pis           varchar(3),
  cst_cofins        varchar(3),
  cst_icms          varchar(3),
  aliquota_icms     numeric(5,2),
  valor_icms        numeric(14,2),
  icms_st           boolean        NOT NULL DEFAULT false,
  icms_st_valor     numeric(14,2),

  created_at        timestamptz    NOT NULL DEFAULT now(),

  CONSTRAINT CK_nfe_items_quantidade CHECK (quantidade > 0),
  CONSTRAINT CK_nfe_items_valor_unitario CHECK (valor_unitario >= 0),
  CONSTRAINT CK_nfe_items_valor_total CHECK (valor_total >= 0)
);

CREATE INDEX IDX_nfe_items_document ON nfe_items (nfe_document_id);
CREATE INDEX IDX_nfe_items_organization ON nfe_items (organization_id);
CREATE INDEX IDX_nfe_items_ncm ON nfe_items (organization_id, ncm) WHERE ncm IS NOT NULL;
CREATE INDEX IDX_nfe_items_descricao_gin ON nfe_items USING GIN (descricao gin_trgm_ops);

COMMENT ON TABLE nfe_items IS 'Itens (produtos) de uma NF-e';


-- ============================================================
-- TABELA: inconsistencies
-- ============================================================
CREATE TABLE inconsistencies (
  id                  uuid PRIMARY KEY DEFAULT gen_random_uuid(),
  nfe_document_id     uuid           NOT NULL REFERENCES nfe_documents(id) ON DELETE CASCADE,
  organization_id     uuid           NOT NULL REFERENCES organizations(id) ON DELETE CASCADE,

  rule_id             rule_id        NOT NULL,
  score               integer        NOT NULL CHECK (score >= 0 AND score <= 100),
  classification      risk_classification NOT NULL,

  field_path          varchar(100),
  found_value         text,
  expected_value      text,
  estimated_impact    numeric(14,2),

  explanation_text    text           NOT NULL,
  explanation_llm     text,

  checklist_json      jsonb          NOT NULL DEFAULT '[]'::jsonb,

  status              inconsistency_status NOT NULL DEFAULT 'PENDENTE',
  ignore_reason       text,
  updated_by          uuid           REFERENCES users(id) ON DELETE SET NULL,
  resolved_at         timestamptz,
  created_at          timestamptz    NOT NULL DEFAULT now(),
  updated_at          timestamptz    NOT NULL DEFAULT now(),

  CONSTRAINT CK_inconsistencies_score_range CHECK (score >= 0 AND score <= 100),
  CONSTRAINT CK_inconsistencies_classification CHECK (
    (score >= 0  AND score <= 30  AND classification = 'OK')
    OR (score >= 31 AND score <= 69  AND classification = 'ATENCAO')
    OR (score >= 70 AND score <= 100 AND classification = 'RISCO_ALTO')
  ),
  CONSTRAINT CK_inconsistencies_ignore_reason CHECK (
    (status = 'IGNORADA' AND ignore_reason IS NOT NULL AND length(trim(ignore_reason)) > 0)
    OR (status != 'IGNORADA')
  )
);

CREATE INDEX IDX_inconsistencies_organization ON inconsistencies (organization_id);
CREATE INDEX IDX_inconsistencies_nfe ON inconsistencies (nfe_document_id);
CREATE INDEX IDX_inconsistencies_status ON inconsistencies (organization_id, status) WHERE status IN ('PENDENTE', 'EM_ANDAMENTO');
CREATE INDEX IDX_inconsistencies_score ON inconsistencies (organization_id, score DESC);
CREATE INDEX IDX_inconsistencies_rule ON inconsistencies (organization_id, rule_id);
CREATE INDEX IDX_inconsistencies_pending_days ON inconsistencies (organization_id, created_at)
  WHERE status = 'PENDENTE' AND created_at < now() - interval '3 days';
CREATE INDEX IDX_inconsistencies_checklist_gin ON inconsistencies USING GIN (checklist_json);

COMMENT ON TABLE inconsistencies IS 'Inconsistência fiscal detectada por uma regra';
COMMENT ON COLUMN inconsistencies.checklist_json IS 'JSON array com passos do checklist. Cada item: {order, text, done}';
COMMENT ON COLUMN inconsistencies.field_path IS 'Caminho XPath-like do campo no XML original';


-- ============================================================
-- TABELA: audit_log
-- ============================================================
CREATE TABLE audit_log (
  id                uuid PRIMARY KEY DEFAULT gen_random_uuid(),
  organization_id   uuid           NOT NULL REFERENCES organizations(id) ON DELETE CASCADE,
  user_id           uuid           REFERENCES users(id) ON DELETE SET NULL,

  event_type        varchar(50)    NOT NULL,
  entity_type       varchar(50)    NOT NULL,
  entity_id         uuid,
  details           jsonb          NOT NULL DEFAULT '{}'::jsonb,
  ip_address        inet,
  created_at        timestamptz    NOT NULL DEFAULT now()
);

CREATE INDEX IDX_audit_organization ON audit_log (organization_id);
CREATE INDEX IDX_audit_user ON audit_log (user_id) WHERE user_id IS NOT NULL;
CREATE INDEX IDX_audit_event_type ON audit_log (organization_id, event_type);
CREATE INDEX IDX_audit_entity ON audit_log (entity_type, entity_id);
CREATE INDEX IDX_audit_created ON audit_log (organization_id, created_at DESC);
CREATE INDEX IDX_audit_details_gin ON audit_log USING GIN (details);

COMMENT ON TABLE audit_log IS 'Registro imutável de eventos do sistema (auditoria)';
COMMENT ON COLUMN audit_log.details IS 'JSON flexível com dados específicos do evento';


-- ============================================================
-- TABELA: magic_links
-- ============================================================
CREATE TABLE magic_links (
  id              uuid PRIMARY KEY DEFAULT gen_random_uuid(),
  user_id         uuid           NOT NULL REFERENCES users(id) ON DELETE CASCADE,
  token_hash      varchar(64)    NOT NULL,
  expires_at      timestamptz    NOT NULL,
  used_at         timestamptz,
  created_at      timestamptz    NOT NULL DEFAULT now(),

  CONSTRAINT UQ_magic_links_token_hash UNIQUE (token_hash),
  CONSTRAINT CK_magic_links_expires CHECK (expires_at > created_at)
);

CREATE INDEX IDX_magic_links_user ON magic_links (user_id);
CREATE INDEX IDX_magic_links_active ON magic_links (token_hash)
  WHERE used_at IS NULL AND expires_at > now();

COMMENT ON TABLE magic_links IS 'Links mágicos de autenticação (passwordless)';
COMMENT ON COLUMN magic_links.token_hash IS 'SHA-256 do token. Token original enviado apenas por WhatsApp, nunca armazenado';


-- ============================================================
-- TABELA: upload_batches
-- ============================================================
CREATE TABLE upload_batches (
  id                uuid PRIMARY KEY DEFAULT gen_random_uuid(),
  organization_id   uuid           NOT NULL REFERENCES organizations(id) ON DELETE CASCADE,
  user_id           uuid           NOT NULL REFERENCES users(id) ON DELETE CASCADE,

  source            upload_source  NOT NULL DEFAULT 'WEB',
  total_files       integer        NOT NULL DEFAULT 0,
  processed         integer        NOT NULL DEFAULT 0,
  ignored           integer        NOT NULL DEFAULT 0,
  inconsistencies_found integer    NOT NULL DEFAULT 0,
  status            varchar(20)    NOT NULL DEFAULT 'PROCESSING',
  error_message     text,
  created_at        timestamptz    NOT NULL DEFAULT now(),
  completed_at      timestamptz,

  CONSTRAINT CK_upload_batches_total CHECK (total_files >= 0),
  CONSTRAINT CK_upload_batches_processed CHECK (processed >= 0 AND processed <= total_files),
  CONSTRAINT CK_upload_batches_ignored CHECK (ignored >= 0 AND ignored <= total_files)
);

CREATE INDEX IDX_upload_batches_organization ON upload_batches (organization_id);
CREATE INDEX IDX_upload_batches_user ON upload_batches (user_id);
CREATE INDEX IDX_upload_batches_created ON upload_batches (organization_id, created_at DESC);

COMMENT ON TABLE upload_batches IS 'Lote de upload de XMLs processado pelo sistema';


-- ============================================================
-- TABELA: pending_notifications
-- ============================================================
CREATE TABLE pending_notifications (
  id                uuid PRIMARY KEY DEFAULT gen_random_uuid(),
  organization_id   uuid           NOT NULL REFERENCES organizations(id) ON DELETE CASCADE,
  user_id           uuid           NOT NULL REFERENCES users(id) ON DELETE CASCADE,

  channel           varchar(20)    NOT NULL DEFAULT 'WHATSAPP',
  template_name     varchar(50)    NOT NULL,
  payload           jsonb          NOT NULL,
  status            varchar(20)    NOT NULL DEFAULT 'PENDING',
  attempts          integer        NOT NULL DEFAULT 0,
  max_attempts      integer        NOT NULL DEFAULT 5,
  last_error        text,
  next_retry_at     timestamptz,
  sent_at           timestamptz,
  created_at        timestamptz    NOT NULL DEFAULT now(),

  CONSTRAINT CK_pending_notifications_attempts CHECK (attempts >= 0 AND attempts <= max_attempts)
);

CREATE INDEX IDX_notifications_pending ON pending_notifications (status, next_retry_at)
  WHERE status = 'PENDING' AND next_retry_at <= now();
CREATE INDEX IDX_notifications_organization ON pending_notifications (organization_id);
CREATE INDEX IDX_notifications_user ON pending_notifications (user_id);

COMMENT ON TABLE pending_notifications IS 'Fila de notificações (WhatsApp, e-mail) com retry';


-- ============================================================
-- TABELA: fiscal_reference_tables
-- ============================================================
CREATE TABLE fiscal_reference_tables (
  id              uuid PRIMARY KEY DEFAULT gen_random_uuid(),
  table_name      varchar(50)    NOT NULL,
  version         varchar(20)    NOT NULL,
  data            jsonb          NOT NULL,
  is_active       boolean        NOT NULL DEFAULT true,
  activated_at    timestamptz    NOT NULL DEFAULT now(),
  created_at      timestamptz    NOT NULL DEFAULT now(),

  CONSTRAINT UQ_ref_table_version UNIQUE (table_name, version)
);

CREATE INDEX IDX_ref_table_active ON fiscal_reference_tables (table_name)
  WHERE is_active = true;

COMMENT ON TABLE fiscal_reference_tables IS 'Tabelas fiscais de referência versionadas (CFOP, NCM, alíquotas)';
COMMENT ON COLUMN fiscal_reference_tables.version IS 'Versão semestral: ano-mês (ex.: 2026-01, 2026-07)';


-- ============================================================
-- ÍNDICES ADICIONAIS (performance)
-- ============================================================

CREATE INDEX IDX_inconsistencies_dashboard
  ON inconsistencies (organization_id, classification, created_at DESC);

CREATE INDEX IDX_nfe_emitente_trgm
  ON nfe_documents USING GIN (nome_emitente gin_trgm_ops);

CREATE UNIQUE INDEX UQ_nfe_chave_org
  ON nfe_documents (organization_id, chave_acesso);


-- ============================================================
-- TRIGGERS
-- ============================================================

CREATE OR REPLACE FUNCTION fn_update_timestamp()
RETURNS trigger AS $$
BEGIN
  NEW.updated_at = now();
  RETURN NEW;
END;
$$ LANGUAGE plpgsql;

CREATE TRIGGER trg_organizations_updated
  BEFORE UPDATE ON organizations
  FOR EACH ROW EXECUTE FUNCTION fn_update_timestamp();

CREATE TRIGGER trg_users_updated
  BEFORE UPDATE ON users
  FOR EACH ROW EXECUTE FUNCTION fn_update_timestamp();

CREATE TRIGGER trg_inconsistencies_updated
  BEFORE UPDATE ON inconsistencies
  FOR EACH ROW EXECUTE FUNCTION fn_update_timestamp();

CREATE OR REPLACE FUNCTION fn_set_resolved_at()
RETURNS trigger AS $$
BEGIN
  IF NEW.status = 'RESOLVIDA' AND OLD.status != 'RESOLVIDA' THEN
    NEW.resolved_at = now();
  END IF;
  RETURN NEW;
END;
$$ LANGUAGE plpgsql;

CREATE TRIGGER trg_inconsistencies_resolved
  BEFORE UPDATE ON inconsistencies
  FOR EACH ROW EXECUTE FUNCTION fn_set_resolved_at();

CREATE OR REPLACE FUNCTION fn_set_batch_completed()
RETURNS trigger AS $$
BEGIN
  IF NEW.status IN ('COMPLETED', 'PARTIAL_ERROR', 'FAILED')
     AND OLD.status = 'PROCESSING' THEN
    NEW.completed_at = now();
  END IF;
  RETURN NEW;
END;
$$ LANGUAGE plpgsql;

CREATE TRIGGER trg_upload_batches_completed
  BEFORE UPDATE ON upload_batches
  FOR EACH ROW EXECUTE FUNCTION fn_set_batch_completed();


-- ============================================================
-- ROW-LEVEL SECURITY (RLS)
-- ============================================================

ALTER TABLE nfe_documents ENABLE ROW LEVEL SECURITY;
ALTER TABLE nfe_items ENABLE ROW LEVEL SECURITY;
ALTER TABLE inconsistencies ENABLE ROW LEVEL SECURITY;
ALTER TABLE audit_log ENABLE ROW LEVEL SECURITY;
ALTER TABLE upload_batches ENABLE ROW LEVEL SECURITY;
ALTER TABLE pending_notifications ENABLE ROW LEVEL SECURITY;

CREATE POLICY rls_tenant_isolation ON nfe_documents
  FOR ALL
  USING (organization_id = current_setting('app.current_organization_id')::uuid);

CREATE POLICY rls_tenant_isolation ON nfe_items
  FOR ALL
  USING (organization_id = current_setting('app.current_organization_id')::uuid);

CREATE POLICY rls_tenant_isolation ON inconsistencies
  FOR ALL
  USING (organization_id = current_setting('app.current_organization_id')::uuid);

CREATE POLICY rls_tenant_isolation ON audit_log
  FOR ALL
  USING (organization_id = current_setting('app.current_organization_id')::uuid);

CREATE POLICY rls_tenant_isolation ON upload_batches
  FOR ALL
  USING (organization_id = current_setting('app.current_organization_id')::uuid);

CREATE POLICY rls_tenant_isolation ON pending_notifications
  FOR ALL
  USING (organization_id = current_setting('app.current_organization_id')::uuid);
```

---

#### 5.3 Drizzle Schema (TypeScript)

```typescript
// packages/shared/src/types/enums.ts
import { pgEnum } from 'drizzle-orm/pg-core';

export const OrganizationRegime = pgEnum('organization_regime', [
  'SIMPLES_NACIONAL', 'LUCRO_PRESUMIDO', 'LUCRO_REAL',
]);

export const SimplesAnexo = pgEnum('simples_anexo', [
  'ANEXO_I', 'ANEXO_II', 'ANEXO_III', 'ANEXO_IV', 'ANEXO_V', 'NA',
]);

export const UserRole = pgEnum('user_role', ['ADMIN', 'OPERADOR']);

export const NfeStatus = pgEnum('nfe_status', [
  'ATIVA', 'CANCELADA', 'DENEGADA', 'INUTILIZADA', 'DESCONHECIDA',
]);

export const RiskClassification = pgEnum('risk_classification', [
  'OK', 'ATENCAO', 'RISCO_ALTO',
]);

export const RuleId = pgEnum('rule_id', [
  'R1', 'R2', 'R3', 'R4', 'R5', 'R6', 'R7', 'R8',
]);

export const InconsistencyStatus = pgEnum('inconsistency_status', [
  'PENDENTE', 'EM_ANDAMENTO', 'RESOLVIDA', 'IGNORADA',
]);

export const UploadSource = pgEnum('upload_source', ['WEB', 'EMAIL']);
```

```typescript
// apps/api/src/db/schema.ts — principais definições Drizzle ORM
import {
  pgTable, uuid, varchar, char, integer, numeric, text,
  boolean, date, inet, timestamp, jsonb, uniqueIndex, index,
} from 'drizzle-orm/pg-core';
import { sql } from 'drizzle-orm';
import {
  OrganizationRegime, SimplesAnexo, UserRole, NfeStatus,
  RiskClassification, RuleId, InconsistencyStatus, UploadSource,
} from '@fiscopilot/shared/types/enums';

// ============================================================
// organizations
// ============================================================
export const organizations = pgTable('organizations', {
  id:            uuid('id').defaultRandom().primaryKey(),
  cnpj:          varchar('cnpj', { length: 14 }).notNull().unique(),
  nomeFantasia:  varchar('nome_fantasia', { length: 150 }).notNull(),
  razaoSocial:   varchar('razao_social', { length: 200 }),
  regime:        OrganizationRegime('regime').notNull().default('SIMPLES_NACIONAL'),
  anexoSimples:  SimplesAnexo('anexo_simples').notNull().default('ANEXO_I'),
  uf:            char('uf', { length: 2 }).notNull(),
  whatsappDono:  varchar('whatsapp_dono', { length: 15 }),
  emailContato:  varchar('email_contato', { length: 255 }),
  createdAt:     timestamp('created_at', { withTimezone: true }).notNull().defaultNow(),
  updatedAt:     timestamp('updated_at', { withTimezone: true }).notNull().defaultNow(),
}, (table) => ({
  cnpjIdx: index('IDX_organizations_cnpj').on(table.cnpj),
  ufIdx:   index('IDX_organizations_uf').on(table.uf),
}));

// ============================================================
// users
// ============================================================
export const users = pgTable('users', {
  id:             uuid('id').defaultRandom().primaryKey(),
  organizationId: uuid('organization_id').notNull().references(() => organizations.id, { onDelete: 'cascade' }),
  nome:           varchar('nome', { length: 150 }).notNull(),
  whatsapp:       varchar('whatsapp', { length: 15 }).notNull(),
  role:           UserRole('role').notNull().default('OPERADOR'),
  isActive:       boolean('is_active').notNull().default(true),
  lastLoginAt:    timestamp('last_login_at', { withTimezone: true }),
  createdAt:      timestamp('created_at', { withTimezone: true }).notNull().defaultNow(),
  updatedAt:      timestamp('updated_at', { withTimezone: true }).notNull().defaultNow(),
}, (table) => ({
  orgWhatsappUq: uniqueIndex('UQ_users_org_whatsapp').on(table.organizationId, table.whatsapp),
  orgIdx:        index('IDX_users_organization').on(table.organizationId),
  whatsappIdx:   index('IDX_users_whatsapp').on(table.whatsapp),
}));

// ============================================================
// nfe_documents
// ============================================================
export const nfeDocuments = pgTable('nfe_documents', {
  id:               uuid('id').defaultRandom().primaryKey(),
  organizationId:   uuid('organization_id').notNull().references(() => organizations.id, { onDelete: 'cascade' }),
  uploadBatchId:    uuid('upload_batch_id'),

  chaveAcesso:      varchar('chave_acesso', { length: 44 }).notNull().unique(),
  numero:           integer('numero').notNull(),
  serie:            integer('serie').notNull().default(1),
  modelo:           varchar('modelo', { length: 2 }).notNull().default('55'),
  dataEmissao:      date('data_emissao').notNull(),
  dataEntradaSaida: date('data_entrada_saida'),

  cnpjEmitente:     varchar('cnpj_emitente', { length: 14 }).notNull(),
  nomeEmitente:     varchar('nome_emitente', { length: 200 }).notNull(),
  ufEmitente:       char('uf_emitente', { length: 2 }).notNull(),
  cnpjDestinatario: varchar('cnpj_destinatario', { length: 14 }).notNull(),

  valorTotal:       numeric('valor_total', { precision: 14, scale: 2 }).notNull(),
  valorProdutos:    numeric('valor_produtos', { precision: 14, scale: 2 }),
  valorIpi:         numeric('valor_ipi', { precision: 14, scale: 2 }),
  valorIcms:        numeric('valor_icms', { precision: 14, scale: 2 }),
  baseCalculoIcms:  numeric('base_calculo_icms', { precision: 14, scale: 2 }),
  aliquotaIcms:     numeric('aliquota_icms', { precision: 5, scale: 2 }),

  cfop:             varchar('cfop', { length: 4 }),
  ncmPrincipal:     varchar('ncm_principal', { length: 8 }),
  cstPis:           varchar('cst_pis', { length: 3 }),
  cstCofins:        varchar('cst_cofins', { length: 3 }),
  cstIcms:          varchar('cst_icms', { length: 3 }),
  icmsSt:           boolean('icms_st').notNull().default(false),
  icmsStValor:      numeric('icms_st_valor', { precision: 14, scale: 2 }),

  statusNfe:        NfeStatus('status_nfe').notNull().default('ATIVA'),
  xmlRaw:           jsonb('xml_raw'),
  xmlHash:          varchar('xml_hash', { length: 64 }),
  source:           UploadSource('source').notNull().default('WEB'),
  createdAt:        timestamp('created_at', { withTimezone: true }).notNull().defaultNow(),
}, (table) => ({
  orgIdx:        index('IDX_nfe_organization').on(table.organizationId),
  dataIdx:       index('IDX_nfe_data_emissao').on(table.organizationId, table.dataEmissao.desc()),
  statusIdx:     index('IDX_nfe_status').on(table.organizationId, table.statusNfe)
                   .where(sql`${table.statusNfe} = 'ATIVA'`),
  emitenteIdx:   index('IDX_nfe_emitente').on(table.organizationId, table.cnpjEmitente),
  xmlHashIdx:    index('IDX_nfe_xml_hash').on(table.xmlHash),
  xmlRawGin:     index('IDX_nfe_xml_raw_gin').using('gin', table.xmlRaw),
  emitenteTrgm:  index('IDX_nfe_emitente_trgm').using('gin', sql`${table.nomeEmitente} gin_trgm_ops`),
  chaveOrgUq:    uniqueIndex('UQ_nfe_chave_org').on(table.organizationId, table.chaveAcesso),
}));

// ============================================================
// nfe_items
// ============================================================
export const nfeItems = pgTable('nfe_items', {
  id:              uuid('id').defaultRandom().primaryKey(),
  nfeDocumentId:   uuid('nfe_document_id').notNull().references(() => nfeDocuments.id, { onDelete: 'cascade' }),
  organizationId:  uuid('organization_id').notNull().references(() => organizations.id, { onDelete: 'cascade' }),

  numeroItem:      integer('numero_item').notNull(),
  codigoProduto:   varchar('codigo_produto', { length: 60 }),
  descricao:       varchar('descricao', { length: 500 }).notNull(),
  ncm:             varchar('ncm', { length: 8 }),
  cfop:            varchar('cfop', { length: 4 }),
  quantidade:      numeric('quantidade', { precision: 14, scale: 4 }).notNull().default('1'),
  unidade:         varchar('unidade', { length: 6 }).notNull().default('UN'),
  valorUnitario:   numeric('valor_unitario', { precision: 14, scale: 4 }).notNull(),
  valorTotal:      numeric('valor_total', { precision: 14, scale: 2 }).notNull(),
  valorFrete:      numeric('valor_frete', { precision: 14, scale: 2 }),

  cstPis:          varchar('cst_pis', { length: 3 }),
  cstCofins:       varchar('cst_cofins', { length: 3 }),
  cstIcms:         varchar('cst_icms', { length: 3 }),
  aliquotaIcms:    numeric('aliquota_icms', { precision: 5, scale: 2 }),
  valorIcms:       numeric('valor_icms', { precision: 14, scale: 2 }),
  icmsSt:          boolean('icms_st').notNull().default(false),
  icmsStValor:     numeric('icms_st_valor', { precision: 14, scale: 2 }),

  createdAt:       timestamp('created_at', { withTimezone: true }).notNull().defaultNow(),
}, (table) => ({
  docIdx:       index('IDX_nfe_items_document').on(table.nfeDocumentId),
  orgIdx:       index('IDX_nfe_items_organization').on(table.organizationId),
  ncmIdx:       index('IDX_nfe_items_ncm').on(table.organizationId, table.ncm)
                   .where(sql`${table.ncm} IS NOT NULL`),
  descricaoGin: index('IDX_nfe_items_descricao_gin').using('gin', sql`${table.descricao} gin_trgm_ops`),
}));

// ============================================================
// inconsistencies
// ============================================================
export const inconsistencies = pgTable('inconsistencies', {
  id:               uuid('id').defaultRandom().primaryKey(),
  nfeDocumentId:    uuid('nfe_document_id').notNull().references(() => nfeDocuments.id, { onDelete: 'cascade' }),
  organizationId:   uuid('organization_id').notNull().references(() => organizations.id, { onDelete: 'cascade' }),

  ruleId:           RuleId('rule_id').notNull(),
  score:            integer('score').notNull(),
  classification:   RiskClassification('classification').notNull(),

  fieldPath:        varchar('field_path', { length: 100 }),
  foundValue:       text('found_value'),
  expectedValue:    text('expected_value'),
  estimatedImpact:  numeric('estimated_impact', { precision: 14, scale: 2 }),

  explanationText:  text('explanation_text').notNull(),
  explanationLlm:   text('explanation_llm'),
  checklistJson:    jsonb('checklist_json').notNull().default(sql`'[]'::jsonb`),

  status:           InconsistencyStatus('status').notNull().default('PENDENTE'),
  ignoreReason:     text('ignore_reason'),
  updatedBy:        uuid('updated_by').references(() => users.id, { onDelete: 'set null' }),
  resolvedAt:       timestamp('resolved_at', { withTimezone: true }),
  createdAt:        timestamp('created_at', { withTimezone: true }).notNull().defaultNow(),
  updatedAt:        timestamp('updated_at', { withTimezone: true }).notNull().defaultNow(),
}, (table) => ({
  orgIdx:        index('IDX_inconsistencies_organization').on(table.organizationId),
  nfeIdx:        index('IDX_inconsistencies_nfe').on(table.nfeDocumentId),
  statusIdx:     index('IDX_inconsistencies_status').on(table.organizationId, table.status)
                   .where(sql`${table.status} IN ('PENDENTE', 'EM_ANDAMENTO')`),
  scoreIdx:      index('IDX_inconsistencies_score').on(table.organizationId, table.score.desc()),
  ruleIdx:       index('IDX_inconsistencies_rule').on(table.organizationId, table.ruleId),
  pendingDays:   index('IDX_inconsistencies_pending_days').on(table.organizationId, table.createdAt)
                   .where(sql`${table.status} = 'PENDENTE' AND ${table.createdAt} < now() - interval '3 days'`),
  checklistGin:  index('IDX_inconsistencies_checklist_gin').using('gin', table.checklistJson),
  dashboardIdx:  index('IDX_inconsistencies_dashboard').on(table.organizationId, table.classification, table.createdAt.desc()),
}));

// ============================================================
// audit_log
// ============================================================
export const auditLog = pgTable('audit_log', {
  id:              uuid('id').defaultRandom().primaryKey(),
  organizationId:  uuid('organization_id').notNull().references(() => organizations.id, { onDelete: 'cascade' }),
  userId:          uuid('user_id').references(() => users.id, { onDelete: 'set null' }),

  eventType:       varchar('event_type', { length: 50 }).notNull(),
  entityType:      varchar('entity_type', { length: 50 }).notNull(),
  entityId:        uuid('entity_id'),
  details:         jsonb('details').notNull().default(sql`'{}'::jsonb`),
  ipAddress:       inet('ip_address'),
  createdAt:       timestamp('created_at', { withTimezone: true }).notNull().defaultNow(),
}, (table) => ({
  orgIdx:      index('IDX_audit_organization').on(table.organizationId),
  userIdx:     index('IDX_audit_user').on(table.userId).where(sql`${table.userId} IS NOT NULL`),
  eventIdx:    index('IDX_audit_event_type').on(table.organizationId, table.eventType),
  entityIdx:   index('IDX_audit_entity').on(table.entityType, table.entityId),
  createdIdx:  index('IDX_audit_created').on(table.organizationId, table.createdAt.desc()),
  detailsGin:  index('IDX_audit_details_gin').using('gin', table.details),
}));

// ============================================================
// magic_links
// ============================================================
export const magicLinks = pgTable('magic_links', {
  id:         uuid('id').defaultRandom().primaryKey(),
  userId:     uuid('user_id').notNull().references(() => users.id, { onDelete: 'cascade' }),
  tokenHash:  varchar('token_hash', { length: 64 }).notNull().unique(),
  expiresAt:  timestamp('expires_at', { withTimezone: true }).notNull(),
  usedAt:     timestamp('used_at', { withTimezone: true }),
  createdAt:  timestamp('created_at', { withTimezone: true }).notNull().defaultNow(),
}, (table) => ({
  userIdx:   index('IDX_magic_links_user').on(table.userId),
  activeIdx: index('IDX_magic_links_active').on(table.tokenHash)
               .where(sql`${table.usedAt} IS NULL AND ${table.expiresAt} > now()`),
}));

// ============================================================
// upload_batches
// ============================================================
export const uploadBatches = pgTable('upload_batches', {
  id:                    uuid('id').defaultRandom().primaryKey(),
  organizationId:        uuid('organization_id').notNull().references(() => organizations.id, { onDelete: 'cascade' }),
  userId:                uuid('user_id').notNull().references(() => users.id, { onDelete: 'cascade' }),

  source:                UploadSource('source').notNull().default('WEB'),
  totalFiles:            integer('total_files').notNull().default(0),
  processed:             integer('processed').notNull().default(0),
  ignored:               integer('ignored').notNull().default(0),
  inconsistenciesFound:  integer('inconsistencies_found').notNull().default(0),
  status:                varchar('status', { length: 20 }).notNull().default('PROCESSING'),
  errorMessage:          text('error_message'),
  createdAt:             timestamp('created_at', { withTimezone: true }).notNull().defaultNow(),
  completedAt:           timestamp('completed_at', { withTimezone: true }),
}, (table) => ({
  orgIdx:     index('IDX_upload_batches_organization').on(table.organizationId),
  userIdx:    index('IDX_upload_batches_user').on(table.userId),
  createdIdx: index('IDX_upload_batches_created').on(table.organizationId, table.createdAt.desc()),
}));

// ============================================================
// pending_notifications
// ============================================================
export const pendingNotifications = pgTable('pending_notifications', {
  id:              uuid('id').defaultRandom().primaryKey(),
  organizationId:  uuid('organization_id').notNull().references(() => organizations.id, { onDelete: 'cascade' }),
  userId:          uuid('user_id').notNull().references(() => users.id, { onDelete: 'cascade' }),

  channel:         varchar('channel', { length: 20 }).notNull().default('WHATSAPP'),
  templateName:    varchar('template_name', { length: 50 }).notNull(),
  payload:         jsonb('payload').notNull(),
  status:          varchar('status', { length: 20 }).notNull().default('PENDING'),
  attempts:        integer('attempts').notNull().default(0),
  maxAttempts:     integer('max_attempts').notNull().default(5),
  lastError:       text('last_error'),
  nextRetryAt:     timestamp('next_retry_at', { withTimezone: true }),
  sentAt:          timestamp('sent_at', { withTimezone: true }),
  createdAt:       timestamp('created_at', { withTimezone: true }).notNull().defaultNow(),
}, (table) => ({
  pendingIdx: index('IDX_notifications_pending').on(table.status, table.nextRetryAt)
                .where(sql`${table.status} = 'PENDING' AND ${table.nextRetryAt} <= now()`),
  orgIdx:     index('IDX_notifications_organization').on(table.organizationId),
  userIdx:    index('IDX_notifications_user').on(table.userId),
}));

// ============================================================
// fiscal_reference_tables
// ============================================================
export const fiscalReferenceTables = pgTable('fiscal_reference_tables', {
  id:          uuid('id').defaultRandom().primaryKey(),
  tableName:   varchar('table_name', { length: 50 }).notNull(),
  version:     varchar('version', { length: 20 }).notNull(),
  data:        jsonb('data').notNull(),
  isActive:    boolean('is_active').notNull().default(true),
  activatedAt: timestamp('activated_at', { withTimezone: true }).notNull().defaultNow(),
  createdAt:   timestamp('created_at', { withTimezone: true }).notNull().defaultNow(),
}, (table) => ({
  tableVersionUq: uniqueIndex('UQ_ref_table_version').on(table.tableName, table.version),
  activeIdx:      index('IDX_ref_table_active').on(table.tableName)
                    .where(sql`${table.isActive} = true`),
}));
```

---

#### 5.4 Estratégia de Migrations (Drizzle Kit)

```
apps/api/src/db/
├── schema.ts             # Definições Drizzle (acima)
├── migrations/           # Gerado por drizzle-kit generate
│   ├── 0000_init.sql
│   ├── 0001_seed_cfop.sql
│   └── ...
├── seeds/
│   ├── cfop.ts           # Popula fiscal_reference_tables com tabela CFOP
│   ├── ncm_materiais.ts  # Popula NCMs de material de construção
│   ├── aliquotas_icms.ts # Popula alíquotas interestaduais 2026
│   └── st_estados.ts     # Popula listas de ST por UF
└── drizzle.config.ts     # Configuração do drizzle-kit
```

**Fluxo de migrations:**
```bash
# Dev: push direto (sem gerar arquivos .sql)
pnpm drizzle-kit push

# Produção: gerar migration + aplicar
pnpm drizzle-kit generate   # → migrations/0001_xxx.sql
pnpm drizzle-kit migrate    # Aplica migrations pendentes
```

---

#### 5.5 Query Patterns (exemplos Drizzle)

```typescript
// Dashboard: contagem por classificação no mês corrente
const dashboard = await db
  .select({
    classification: inconsistencies.classification,
    count: sql<number>`count(*)::int`,
  })
  .from(inconsistencies)
  .where(and(
    eq(inconsistencies.organizationId, orgId),
    gte(inconsistencies.createdAt, startOfMonth),
    lte(inconsistencies.createdAt, endOfMonth),
  ))
  .groupBy(inconsistencies.classification);

// Lista de inconsistências ordenadas por score
const pendingIssues = await db.query.inconsistencies.findMany({
  where: and(
    eq(inconsistencies.organizationId, orgId),
    inArray(inconsistencies.status, ['PENDENTE', 'EM_ANDAMENTO']),
  ),
  orderBy: desc(inconsistencies.score),
  limit: 20,
  with: {
    nfeDocument: true,  // JOIN automático
  },
});

// Upload batch: resumo
const batchSummary = await db
  .select({
    total: count(),
    comInconsistencias: sql<number>`count(*) filter (where ${inconsistencies.classification} != 'OK')::int`,
    riscoAlto: sql<number>`count(*) filter (where ${inconsistencies.classification} = 'RISCO_ALTO')::int`,
  })
  .from(inconsistencies)
  .where(eq(inconsistencies.uploadBatchId, batchId));

// Busca textual por fornecedor (ILIKE com índice GIN trigram)
const searchResults = await db.query.nfeDocuments.findMany({
  where: and(
    eq(nfeDocuments.organizationId, orgId),
    ilike(nfeDocuments.nomeEmitente, `%${termo}%`),
  ),
  limit: 20,
});

// Notificações pendentes para envio (cron job)
const pending = await db.query.pendingNotifications.findMany({
  where: and(
    eq(pendingNotifications.status, 'PENDING'),
    lte(pendingNotifications.nextRetryAt, new Date()),
  ),
  limit: 10,
});
```

---

### Expansão Pós-MVP — Novas Tabelas (Fases A-D)

**Objetivo:** Adicionar 23 novas tabelas + 1 view materializada para suportar as 30 funcionalidades pós-MVP (F36-F65).

#### 5.6 Novas Tabelas — Fase A (Retenção e Redução de Atrito)

```sql
-- ============================================================
-- TABELA: supplier_message_templates (Feature #5)
-- ============================================================
CREATE TABLE supplier_message_templates (
  id              uuid PRIMARY KEY DEFAULT gen_random_uuid(),
  rule_id         rule_id NOT NULL,
  variant         varchar(30) NOT NULL DEFAULT 'default',
  template_text   text NOT NULL,
  is_active       boolean NOT NULL DEFAULT true,
  created_at      timestamptz NOT NULL DEFAULT now(),

  CONSTRAINT UQ_template_rule_variant UNIQUE (rule_id, variant)
);

CREATE INDEX IDX_message_templates_rule ON supplier_message_templates (rule_id) WHERE is_active = true;

COMMENT ON TABLE supplier_message_templates IS 'Templates de mensagens para fornecedores por tipo de regra';


-- ============================================================
-- TABELA: supplier_messages (Feature #5)
-- ============================================================
CREATE TABLE supplier_messages (
  id                uuid PRIMARY KEY DEFAULT gen_random_uuid(),
  organization_id   uuid NOT NULL REFERENCES organizations(id) ON DELETE CASCADE,
  inconsistency_id  uuid NOT NULL REFERENCES inconsistencies(id) ON DELETE CASCADE,
  user_id           uuid REFERENCES users(id) ON DELETE SET NULL,
  channel           varchar(20) NOT NULL,
  message_text      text NOT NULL,
  status            varchar(20) NOT NULL DEFAULT 'GENERATED',
  sent_at           timestamptz,
  created_at        timestamptz NOT NULL DEFAULT now(),

  CONSTRAINT CK_supplier_messages_channel CHECK (channel IN ('WHATSAPP', 'EMAIL', 'COPY')),
  CONSTRAINT CK_supplier_messages_status CHECK (status IN ('GENERATED', 'COPIED', 'SENT_WHATSAPP', 'SENT_EMAIL', 'DELIVERED', 'READ'))
);

CREATE INDEX IDX_supplier_messages_org ON supplier_messages (organization_id);
CREATE INDEX IDX_supplier_messages_inconsistency ON supplier_messages (inconsistency_id);
CREATE INDEX IDX_supplier_messages_status ON supplier_messages (status);

COMMENT ON TABLE supplier_messages IS 'Log de mensagens geradas/enviadas para fornecedores';


-- ============================================================
-- TABELA: whatsapp_ingestion_log (Feature #11)
-- ============================================================
CREATE TABLE whatsapp_ingestion_log (
  id                uuid PRIMARY KEY DEFAULT gen_random_uuid(),
  organization_id   uuid REFERENCES organizations(id) ON DELETE CASCADE,
  user_id           uuid REFERENCES users(id) ON DELETE SET NULL,
  whatsapp_from     varchar(20) NOT NULL,
  message_id        varchar(100) NOT NULL,
  message_type      varchar(30) NOT NULL,
  media_url         text,
  media_mime_type   varchar(100),
  processed         boolean NOT NULL DEFAULT false,
  upload_batch_id   uuid REFERENCES upload_batches(id) ON DELETE SET NULL,
  error_message     text,
  created_at        timestamptz NOT NULL DEFAULT now(),

  CONSTRAINT CK_whatsapp_message_type CHECK (message_type IN ('document', 'audio', 'text', 'image', 'video'))
);

CREATE INDEX IDX_whatsapp_ingestion_org ON whatsapp_ingestion_log (organization_id);
CREATE INDEX IDX_whatsapp_ingestion_processed ON whatsapp_ingestion_log (processed) WHERE processed = false;
CREATE INDEX IDX_whatsapp_ingestion_created ON whatsapp_ingestion_log (created_at DESC);

COMMENT ON TABLE whatsapp_ingestion_log IS 'Log de mensagens recebidas via WhatsApp Business API';


-- ============================================================
-- TABELA: onboarding_sessions (Feature #15)
-- ============================================================
CREATE TABLE onboarding_sessions (
  id                uuid PRIMARY KEY DEFAULT gen_random_uuid(),
  organization_id   uuid NOT NULL REFERENCES organizations(id) ON DELETE CASCADE,
  user_id           uuid NOT NULL REFERENCES users(id) ON DELETE CASCADE,
  current_step      integer NOT NULL DEFAULT 0,
  steps_completed   jsonb NOT NULL DEFAULT '[]'::jsonb,
  first_upload_batch_id uuid REFERENCES upload_batches(id) ON DELETE SET NULL,
  risks_found       integer DEFAULT 0,
  high_risks_found  integer DEFAULT 0,
  completed_at      timestamptz,
  created_at        timestamptz NOT NULL DEFAULT now(),

  CONSTRAINT CK_onboarding_step CHECK (current_step >= 0 AND current_step <= 5)
);

CREATE INDEX IDX_onboarding_sessions_org ON onboarding_sessions (organization_id);
CREATE INDEX IDX_onboarding_sessions_user ON onboarding_sessions (user_id);
CREATE INDEX IDX_onboarding_sessions_incomplete ON onboarding_sessions (organization_id) WHERE completed_at IS NULL;

COMMENT ON TABLE onboarding_sessions IS 'Sessões de onboarding raio-x (wizard 5 passos)';
```

---

#### 5.7 Novas Tabelas — Fase B (Monitoramento Contínuo)

```sql
-- ============================================================
-- TABELA: digital_certificates (Feature #1)
-- ============================================================
CREATE TABLE digital_certificates (
  id                uuid PRIMARY KEY DEFAULT gen_random_uuid(),
  organization_id   uuid NOT NULL REFERENCES organizations(id) ON DELETE CASCADE,
  certificate_type  varchar(5) NOT NULL,
  certificate_pem   bytea NOT NULL,
  certificate_key   bytea NOT NULL,
  encryption_iv     bytea NOT NULL,
  cnpj_titular      varchar(14) NOT NULL,
  valid_from        date NOT NULL,
  valid_until       date NOT NULL,
  is_active         boolean NOT NULL DEFAULT true,
  last_used_at      timestamptz,
  created_at        timestamptz NOT NULL DEFAULT now(),

  CONSTRAINT CK_cert_type CHECK (certificate_type IN ('A1', 'A3'))
);

CREATE INDEX IDX_digital_certificates_org ON digital_certificates (organization_id);
CREATE INDEX IDX_digital_certificates_active ON digital_certificates (organization_id) WHERE is_active = true;
CREATE INDEX IDX_digital_certificates_expiry ON digital_certificates (valid_until) WHERE is_active = true;

COMMENT ON TABLE digital_certificates IS 'Certificados digitais A1/A3 criptografados (AES-256-GCM)';
COMMENT ON COLUMN digital_certificates.certificate_pem IS 'Certificado PEM criptografado com AES-256-GCM';
COMMENT ON COLUMN digital_certificates.certificate_key IS 'Chave privada criptografada com AES-256-GCM';


-- ============================================================
-- TABELA: sefaz_download_sessions (Feature #1)
-- ============================================================
CREATE TABLE sefaz_download_sessions (
  id                uuid PRIMARY KEY DEFAULT gen_random_uuid(),
  organization_id   uuid NOT NULL REFERENCES organizations(id) ON DELETE CASCADE,
  certificate_id    uuid NOT NULL REFERENCES digital_certificates(id) ON DELETE CASCADE,
  status            varchar(20) NOT NULL DEFAULT 'PENDING',
  period_start      date NOT NULL,
  period_end        date NOT NULL,
  total_found       integer DEFAULT 0,
  total_downloaded  integer DEFAULT 0,
  total_new         integer DEFAULT 0,
  total_duplicate   integer DEFAULT 0,
  error_message     text,
  started_at        timestamptz,
  completed_at      timestamptz,
  created_at        timestamptz NOT NULL DEFAULT now(),

  CONSTRAINT CK_sefaz_download_status CHECK (status IN ('PENDING', 'CONNECTING', 'DOWNLOADING', 'COMPLETED', 'FAILED', 'PARTIAL'))
);

CREATE INDEX IDX_sefaz_download_org ON sefaz_download_sessions (organization_id);
CREATE INDEX IDX_sefaz_download_status ON sefaz_download_sessions (status) WHERE status IN ('PENDING', 'CONNECTING', 'DOWNLOADING');
CREATE INDEX IDX_sefaz_download_created ON sefaz_download_sessions (created_at DESC);

COMMENT ON TABLE sefaz_download_sessions IS 'Sessões de download automático de XMLs da Sefaz';


-- ============================================================
-- TABELA: sefaz_download_queue (Feature #1)
-- ============================================================
CREATE TABLE sefaz_download_queue (
  id                uuid PRIMARY KEY DEFAULT gen_random_uuid(),
  organization_id   uuid NOT NULL REFERENCES organizations(id) ON DELETE CASCADE,
  certificate_id    uuid NOT NULL REFERENCES digital_certificates(id) ON DELETE CASCADE,
  scheduled_at      timestamptz NOT NULL,
  period_start      date NOT NULL,
  period_end        date NOT NULL,
  status            varchar(20) NOT NULL DEFAULT 'SCHEDULED',
  attempts          integer NOT NULL DEFAULT 0,
  max_attempts      integer NOT NULL DEFAULT 3,
  created_at        timestamptz NOT NULL DEFAULT now(),

  CONSTRAINT CK_sefaz_queue_status CHECK (status IN ('SCHEDULED', 'PROCESSING', 'COMPLETED', 'FAILED')),
  CONSTRAINT CK_sefaz_queue_attempts CHECK (attempts >= 0 AND attempts <= max_attempts)
);

CREATE INDEX IDX_sefaz_queue_scheduled ON sefaz_download_queue (scheduled_at) WHERE status = 'SCHEDULED';
CREATE INDEX IDX_sefaz_queue_org ON sefaz_download_queue (organization_id);

COMMENT ON TABLE sefaz_download_queue IS 'Fila de downloads automáticos agendados (pg-boss)';


-- ============================================================
-- TABELA: inconsistency_comments (Feature #4)
-- ============================================================
CREATE TABLE inconsistency_comments (
  id                uuid PRIMARY KEY DEFAULT gen_random_uuid(),
  inconsistency_id  uuid NOT NULL REFERENCES inconsistencies(id) ON DELETE CASCADE,
  organization_id   uuid NOT NULL REFERENCES organizations(id) ON DELETE CASCADE,
  user_id           uuid REFERENCES users(id) ON DELETE SET NULL,
  author_type       varchar(20) NOT NULL,
  comment_text      text NOT NULL,
  created_at        timestamptz NOT NULL DEFAULT now(),

  CONSTRAINT CK_comment_author_type CHECK (author_type IN ('USER', 'ACCOUNTANT', 'SYSTEM'))
);

CREATE INDEX IDX_inconsistency_comments_inconsistency ON inconsistency_comments (inconsistency_id);
CREATE INDEX IDX_inconsistency_comments_org ON inconsistency_comments (organization_id);
CREATE INDEX IDX_inconsistency_comments_created ON inconsistency_comments (created_at DESC);

COMMENT ON TABLE inconsistency_comments IS 'Comentários em inconsistências (Kanban)';


-- ============================================================
-- TABELA: inconsistency_attachments (Feature #4)
-- ============================================================
CREATE TABLE inconsistency_attachments (
  id                uuid PRIMARY KEY DEFAULT gen_random_uuid(),
  inconsistency_id  uuid NOT NULL REFERENCES inconsistencies(id) ON DELETE CASCADE,
  organization_id   uuid NOT NULL REFERENCES organizations(id) ON DELETE CASCADE,
  user_id           uuid REFERENCES users(id) ON DELETE SET NULL,
  file_name         varchar(255) NOT NULL,
  file_path         text NOT NULL,
  file_size         integer NOT NULL,
  mime_type         varchar(100) NOT NULL,
  description       text,
  created_at        timestamptz NOT NULL DEFAULT now(),

  CONSTRAINT CK_attachment_size CHECK (file_size > 0 AND file_size <= 10485760) -- 10MB max
);

CREATE INDEX IDX_inconsistency_attachments_inconsistency ON inconsistency_attachments (inconsistency_id);
CREATE INDEX IDX_inconsistency_attachments_org ON inconsistency_attachments (organization_id);

COMMENT ON TABLE inconsistency_attachments IS 'Anexos (PDF/imagem) em inconsistências (Kanban)';


-- ============================================================
-- TABELA: inconsistency_assignments (Feature #4)
-- ============================================================
CREATE TABLE inconsistency_assignments (
  id                uuid PRIMARY KEY DEFAULT gen_random_uuid(),
  inconsistency_id  uuid NOT NULL REFERENCES inconsistencies(id) ON DELETE CASCADE,
  organization_id   uuid NOT NULL REFERENCES organizations(id) ON DELETE CASCADE,
  assigned_to       uuid REFERENCES users(id) ON DELETE SET NULL,
  assigned_by       uuid REFERENCES users(id) ON DELETE SET NULL,
  due_date          date,
  created_at        timestamptz NOT NULL DEFAULT now(),
  updated_at        timestamptz NOT NULL DEFAULT now(),

  CONSTRAINT UQ_assignment_per_inconsistency UNIQUE (inconsistency_id)
);

CREATE INDEX IDX_inconsistency_assignments_inconsistency ON inconsistency_assignments (inconsistency_id);
CREATE INDEX IDX_inconsistency_assignments_org ON inconsistency_assignments (organization_id);
CREATE INDEX IDX_inconsistency_assignments_assigned_to ON inconsistency_assignments (assigned_to) WHERE assigned_to IS NOT NULL;
CREATE INDEX IDX_inconsistency_assignments_due_date ON inconsistency_assignments (due_date) WHERE due_date IS NOT NULL;

COMMENT ON TABLE inconsistency_assignments IS 'Atribuição de responsável e prazo para inconsistências (Kanban)';


-- ============================================================
-- TABELA: cadastral_alerts (Feature #14)
-- ============================================================
CREATE TABLE cadastral_alerts (
  id                uuid PRIMARY KEY DEFAULT gen_random_uuid(),
  organization_id   uuid NOT NULL REFERENCES organizations(id) ON DELETE CASCADE,
  alert_type        varchar(30) NOT NULL,
  entity_type       varchar(30) NOT NULL,
  entity_cnpj       varchar(14),
  entity_name       varchar(200),
  severity          varchar(20) NOT NULL,
  message           text NOT NULL,
  details           jsonb,
  is_read           boolean NOT NULL DEFAULT false,
  dismissed_at      timestamptz,
  created_at        timestamptz NOT NULL DEFAULT now(),

  CONSTRAINT CK_cadastral_alert_type CHECK (alert_type IN ('CERTIFICATE_EXPIRING', 'CERTIFICATE_EXPIRED', 'CNPJ_INAPTO', 'CNPJ_SUSPENSO', 'IE_IRREGULAR', 'CNAE_INCOMPATIVEL', 'SUPPLIER_RECURRENT_ISSUE')),
  CONSTRAINT CK_cadastral_severity CHECK (severity IN ('INFO', 'WARNING', 'CRITICAL'))
);

CREATE INDEX IDX_cadastral_alerts_org ON cadastral_alerts (organization_id);
CREATE INDEX IDX_cadastral_alerts_unread ON cadastral_alerts (organization_id, severity) WHERE is_read = false AND dismissed_at IS NULL;
CREATE INDEX IDX_cadastral_alerts_created ON cadastral_alerts (created_at DESC);

COMMENT ON TABLE cadastral_alerts IS 'Alertas cadastrais (certificado, CNPJ, IE, CNAE, fornecedor recorrente)';


-- ============================================================
-- TABELA: cadastral_monitoring_config (Feature #14)
-- ============================================================
CREATE TABLE cadastral_monitoring_config (
  id                uuid PRIMARY KEY DEFAULT gen_random_uuid(),
  organization_id   uuid NOT NULL REFERENCES organizations(id) ON DELETE CASCADE,
  monitor_type      varchar(30) NOT NULL,
  enabled           boolean NOT NULL DEFAULT true,
  check_interval    varchar(20) NOT NULL DEFAULT 'weekly',
  last_checked_at   timestamptz,
  created_at        timestamptz NOT NULL DEFAULT now(),

  CONSTRAINT UQ_monitor_per_org UNIQUE (organization_id, monitor_type),
  CONSTRAINT CK_monitor_interval CHECK (check_interval IN ('daily', 'weekly', 'monthly'))
);

CREATE INDEX IDX_cadastral_monitoring_org ON cadastral_monitoring_config (organization_id);

COMMENT ON TABLE cadastral_monitoring_config IS 'Configuração de monitoramento cadastral por organização';
```

---

#### 5.8 Novas Tabelas — Fase C (Inteligência e Ecossistema)

```sql
-- ============================================================
-- TABELA: accountants (Feature #2)
-- ============================================================
CREATE TABLE accountants (
  id                uuid PRIMARY KEY DEFAULT gen_random_uuid(),
  nome              varchar(150) NOT NULL,
  cpf               varchar(11) NOT NULL UNIQUE,
  email             varchar(255) NOT NULL UNIQUE,
  password_hash     varchar(255) NOT NULL,
  crc_numero        varchar(30),
  crc_uf            char(2),
  whatsapp          varchar(15),
  is_active         boolean NOT NULL DEFAULT true,
  last_login_at     timestamptz,
  created_at        timestamptz NOT NULL DEFAULT now(),
  updated_at        timestamptz NOT NULL DEFAULT now(),

  CONSTRAINT CK_accountants_cpf_format CHECK (cpf ~ '^[0-9]{11}$'),
  CONSTRAINT CK_accountants_crc_uf CHECK (crc_uf IS NULL OR crc_uf ~ '^[A-Z]{2}$')
);

CREATE INDEX IDX_accountants_cpf ON accountants (cpf);
CREATE INDEX IDX_accountants_email ON accountants (email);
CREATE INDEX IDX_accountants_active ON accountants (is_active) WHERE is_active = true;

COMMENT ON TABLE accountants IS 'Contadores com acesso ao portal dedicado';
COMMENT ON COLUMN accountants.password_hash IS 'bcrypt hash (cost >= 10)';


-- ============================================================
-- TABELA: accountant_clients (Feature #2)
-- ============================================================
CREATE TABLE accountant_clients (
  id                uuid PRIMARY KEY DEFAULT gen_random_uuid(),
  accountant_id     uuid NOT NULL REFERENCES accountants(id) ON DELETE CASCADE,
  organization_id   uuid NOT NULL REFERENCES organizations(id) ON DELETE CASCADE,
  invited_by        uuid REFERENCES users(id) ON DELETE SET NULL,
  status            varchar(20) NOT NULL DEFAULT 'PENDING',
  invited_at        timestamptz NOT NULL DEFAULT now(),
  accepted_at       timestamptz,

  CONSTRAINT UQ_accountant_client UNIQUE (accountant_id, organization_id),
  CONSTRAINT CK_accountant_client_status CHECK (status IN ('PENDING', 'ACTIVE', 'REMOVED'))
);

CREATE INDEX IDX_accountant_clients_accountant ON accountant_clients (accountant_id);
CREATE INDEX IDX_accountant_clients_org ON accountant_clients (organization_id);
CREATE INDEX IDX_accountant_clients_active ON accountant_clients (accountant_id, status) WHERE status = 'ACTIVE';

COMMENT ON TABLE accountant_clients IS 'Relação contador-cliente (convite e aceite)';


-- ============================================================
-- TABELA: accountant_comments (Feature #2)
-- ============================================================
CREATE TABLE accountant_comments (
  id                uuid PRIMARY KEY DEFAULT gen_random_uuid(),
  accountant_id     uuid NOT NULL REFERENCES accountants(id) ON DELETE CASCADE,
  organization_id   uuid NOT NULL REFERENCES organizations(id) ON DELETE CASCADE,
  inconsistency_id  uuid REFERENCES inconsistencies(id) ON DELETE CASCADE,
  comment_text      text NOT NULL,
  is_validation     boolean NOT NULL DEFAULT false,
  validated_at      timestamptz,
  created_at        timestamptz NOT NULL DEFAULT now()
);

CREATE INDEX IDX_accountant_comments_accountant ON accountant_comments (accountant_id);
CREATE INDEX IDX_accountant_comments_org ON accountant_comments (organization_id);
CREATE INDEX IDX_accountant_comments_inconsistency ON accountant_comments (inconsistency_id) WHERE inconsistency_id IS NOT NULL;
CREATE INDEX IDX_accountant_comments_created ON accountant_comments (created_at DESC);

COMMENT ON TABLE accountant_comments IS 'Comentários e validações do contador em inconsistências';


-- ============================================================
-- TABELA: accountant_monthly_exports (Feature #2)
-- ============================================================
CREATE TABLE accountant_monthly_exports (
  id                uuid PRIMARY KEY DEFAULT gen_random_uuid(),
  accountant_id     uuid NOT NULL REFERENCES accountants(id) ON DELETE CASCADE,
  organization_id   uuid NOT NULL REFERENCES organizations(id) ON DELETE CASCADE,
  month             varchar(7) NOT NULL,
  status            varchar(20) NOT NULL DEFAULT 'PENDING',
  pdf_url           text,
  generated_at      timestamptz,
  downloaded_at     timestamptz,
  created_at        timestamptz NOT NULL DEFAULT now(),

  CONSTRAINT CK_accountant_export_status CHECK (status IN ('PENDING', 'GENERATING', 'READY', 'DOWNLOADED')),
  CONSTRAINT CK_accountant_export_month CHECK (month ~ '^[0-9]{4}-[0-9]{2}$')
);

CREATE INDEX IDX_accountant_exports_accountant ON accountant_monthly_exports (accountant_id);
CREATE INDEX IDX_accountant_exports_org ON accountant_monthly_exports (organization_id);
CREATE INDEX IDX_accountant_exports_status ON accountant_monthly_exports (status) WHERE status IN ('PENDING', 'GENERATING');

COMMENT ON TABLE accountant_monthly_exports IS 'Exportações mensais consolidadas do contador';


-- ============================================================
-- VIEW MATERIALIZADA: supplier_scores (Feature #3)
-- ============================================================
CREATE MATERIALIZED VIEW supplier_scores AS
SELECT
  d.organization_id,
  d.cnpj_emitente AS supplier_cnpj,
  MAX(d.nome_emitente) AS supplier_name,
  COUNT(DISTINCT d.id) AS total_notes_90d,
  SUM(d.valor_total) AS total_value_90d,
  COUNT(DISTINCT i.id) AS total_inconsistencies_90d,
  COUNT(DISTINCT i.id) FILTER (WHERE i.classification = 'RISCO_ALTO') AS high_risk_count,
  COALESCE(SUM(i.estimated_impact), 0) AS total_risk_value,
  CASE
    WHEN COUNT(DISTINCT d.id) = 0 THEN 0
    ELSE ROUND(
      COUNT(DISTINCT i.id)::numeric / COUNT(DISTINCT d.id)::numeric * 100, 1
    )
  END AS error_rate,
  CASE
    WHEN COUNT(DISTINCT i.id) = 0 THEN 'CONFIÁVEL'
    WHEN COUNT(DISTINCT i.id) FILTER (WHERE i.classification = 'RISCO_ALTO') > 0 THEN 'RISCO'
    WHEN COUNT(DISTINCT i.id)::numeric / GREATEST(COUNT(DISTINCT d.id), 1)::numeric > 0.2 THEN 'ATENCAO'
    ELSE 'CONFIÁVEL'
  END AS category
FROM nfe_documents d
LEFT JOIN inconsistencies i ON i.nfe_document_id = d.id
WHERE d.data_emissao >= CURRENT_DATE - INTERVAL '90 days'
GROUP BY d.organization_id, d.cnpj_emitente;

CREATE INDEX IDX_supplier_scores_org ON supplier_scores (organization_id, category);
CREATE INDEX IDX_supplier_scores_cnpj ON supplier_scores (organization_id, supplier_cnpj);

COMMENT ON MATERIALIZED VIEW supplier_scores IS 'Score de fornecedores baseado em 90 dias de histórico (atualizada diariamente via cron)';


-- ============================================================
-- TABELA: ai_conversations (Feature #12)
-- ============================================================
CREATE TABLE ai_conversations (
  id                uuid PRIMARY KEY DEFAULT gen_random_uuid(),
  organization_id   uuid NOT NULL REFERENCES organizations(id) ON DELETE CASCADE,
  user_id           uuid NOT NULL REFERENCES users(id) ON DELETE CASCADE,
  inconsistency_id  uuid REFERENCES inconsistencies(id) ON DELETE SET NULL,
  question          text NOT NULL,
  answer            text NOT NULL,
  model_used        varchar(50),
  tokens_used       integer,
  latency_ms        integer,
  feedback          varchar(10),
  created_at        timestamptz NOT NULL DEFAULT now(),

  CONSTRAINT CK_ai_feedback CHECK (feedback IS NULL OR feedback IN ('GOOD', 'BAD'))
);

CREATE INDEX IDX_ai_conversations_org ON ai_conversations (organization_id);
CREATE INDEX IDX_ai_conversations_user ON ai_conversations (user_id);
CREATE INDEX IDX_ai_conversations_inconsistency ON ai_conversations (inconsistency_id) WHERE inconsistency_id IS NOT NULL;
CREATE INDEX IDX_ai_conversations_created ON ai_conversations (created_at DESC);

COMMENT ON TABLE ai_conversations IS 'Histórico de conversas com assistente de IA';
```

---

#### 5.9 Novas Tabelas — Fase D (Plataforma e Escala)

```sql
-- ============================================================
-- TABELA: reform_checklist (Feature #9)
-- ============================================================
CREATE TABLE reform_checklist (
  id                uuid PRIMARY KEY DEFAULT gen_random_uuid(),
  organization_id   uuid NOT NULL REFERENCES organizations(id) ON DELETE CASCADE,
  item_key          varchar(50) NOT NULL,
  item_text         text NOT NULL,
  category          varchar(30) NOT NULL,
  is_done           boolean NOT NULL DEFAULT false,
  done_at           timestamptz,
  notes             text,
  created_at        timestamptz NOT NULL DEFAULT now(),
  updated_at        timestamptz NOT NULL DEFAULT now(),

  CONSTRAINT UQ_checklist_per_org UNIQUE (organization_id, item_key),
  CONSTRAINT CK_checklist_category CHECK (category IN ('CADASTRO', 'SISTEMAS', 'PROCESSOS', 'TRIBUTOS'))
);

CREATE INDEX IDX_reform_checklist_org ON reform_checklist (organization_id);
CREATE INDEX IDX_reform_checklist_done ON reform_checklist (organization_id, is_done);

COMMENT ON TABLE reform_checklist IS 'Checklist de preparação para Reforma Tributária (CBS/IBS)';


-- ============================================================
-- TABELA: cbs_ibs_alerts (Feature #9)
-- ============================================================
CREATE TABLE cbs_ibs_alerts (
  id                uuid PRIMARY KEY DEFAULT gen_random_uuid(),
  organization_id   uuid NOT NULL REFERENCES organizations(id) ON DELETE CASCADE,
  nfe_document_id   uuid REFERENCES nfe_documents(id) ON DELETE CASCADE,
  alert_type        varchar(30) NOT NULL,
  severity          varchar(20) NOT NULL,
  message           text NOT NULL,
  details           jsonb,
  created_at        timestamptz NOT NULL DEFAULT now(),

  CONSTRAINT CK_cbs_ibs_alert_type CHECK (alert_type IN ('CBS_FIELD_MISSING', 'IBS_FIELD_MISSING', 'CBS_IBS_INCONSISTENT', 'TRANSITION_RULE_APPLICABLE')),
  CONSTRAINT CK_cbs_ibs_severity CHECK (severity IN ('INFO', 'WARNING', 'CRITICAL'))
);

CREATE INDEX IDX_cbs_ibs_alerts_org ON cbs_ibs_alerts (organization_id);
CREATE INDEX IDX_cbs_ibs_alerts_nfe ON cbs_ibs_alerts (nfe_document_id) WHERE nfe_document_id IS NOT NULL;
CREATE INDEX IDX_cbs_ibs_alerts_created ON cbs_ibs_alerts (created_at DESC);

COMMENT ON TABLE cbs_ibs_alerts IS 'Alertas de campos CBS/IBS ausentes ou inconsistentes nos XMLs';


-- ============================================================
-- TABELA: erp_connections (Feature #10)
-- ============================================================
CREATE TABLE erp_connections (
  id                uuid PRIMARY KEY DEFAULT gen_random_uuid(),
  organization_id   uuid NOT NULL REFERENCES organizations(id) ON DELETE CASCADE,
  erp_type          varchar(20) NOT NULL,
  access_token      text NOT NULL,
  refresh_token     text,
  token_expires_at  timestamptz,
  config            jsonb NOT NULL DEFAULT '{}'::jsonb,
  is_active         boolean NOT NULL DEFAULT true,
  last_sync_at      timestamptz,
  last_sync_status  varchar(20),
  created_at        timestamptz NOT NULL DEFAULT now(),
  updated_at        timestamptz NOT NULL DEFAULT now(),

  CONSTRAINT CK_erp_type CHECK (erp_type IN ('BLING', 'OMIE', 'TINY', 'CONTA_AZUL')),
  CONSTRAINT CK_erp_sync_status CHECK (last_sync_status IS NULL OR last_sync_status IN ('SUCCESS', 'PARTIAL', 'FAILED'))
);

CREATE INDEX IDX_erp_connections_org ON erp_connections (organization_id);
CREATE INDEX IDX_erp_connections_active ON erp_connections (organization_id, is_active) WHERE is_active = true;

COMMENT ON TABLE erp_connections IS 'Conexões OAuth com ERPs brasileiros (tokens criptografados)';
COMMENT ON COLUMN erp_connections.access_token IS 'Access token criptografado com AES-256-GCM';


-- ============================================================
-- TABELA: erp_sync_logs (Feature #10)
-- ============================================================
CREATE TABLE erp_sync_logs (
  id                uuid PRIMARY KEY DEFAULT gen_random_uuid(),
  connection_id     uuid NOT NULL REFERENCES erp_connections(id) ON DELETE CASCADE,
  organization_id   uuid NOT NULL REFERENCES organizations(id) ON DELETE CASCADE,
  sync_type         varchar(20) NOT NULL,
  status            varchar(20) NOT NULL,
  total_found       integer DEFAULT 0,
  total_synced      integer DEFAULT 0,
  total_skipped     integer DEFAULT 0,
  error_message     text,
  started_at        timestamptz,
  completed_at      timestamptz,
  created_at        timestamptz NOT NULL DEFAULT now(),

  CONSTRAINT CK_erp_sync_type CHECK (sync_type IN ('FULL', 'INCREMENTAL')),
  CONSTRAINT CK_erp_sync_status CHECK (status IN ('PENDING', 'RUNNING', 'COMPLETED', 'FAILED', 'PARTIAL'))
);

CREATE INDEX IDX_erp_sync_logs_connection ON erp_sync_logs (connection_id);
CREATE INDEX IDX_erp_sync_logs_org ON erp_sync_logs (organization_id);
CREATE INDEX IDX_erp_sync_logs_status ON erp_sync_logs (status) WHERE status IN ('PENDING', 'RUNNING');
CREATE INDEX IDX_erp_sync_logs_created ON erp_sync_logs (created_at DESC);

COMMENT ON TABLE erp_sync_logs IS 'Logs de sincronização com ERPs';


-- ============================================================
-- TABELA: rule_packs (Feature #13)
-- ============================================================
CREATE TABLE rule_packs (
  id                uuid PRIMARY KEY DEFAULT gen_random_uuid(),
  pack_key          varchar(50) NOT NULL UNIQUE,
  pack_name         varchar(150) NOT NULL,
  description       text,
  sector            varchar(50) NOT NULL,
  uf                char(2),
  regime            organization_regime,
  version           varchar(20) NOT NULL,
  rules_json        jsonb NOT NULL,
  is_active         boolean NOT NULL DEFAULT true,
  activated_at      timestamptz,
  created_at        timestamptz NOT NULL DEFAULT now(),

  CONSTRAINT UQ_rule_pack_key UNIQUE (pack_key)
);

CREATE INDEX IDX_rule_packs_active ON rule_packs (is_active) WHERE is_active = true;
CREATE INDEX IDX_rule_packs_sector ON rule_packs (sector);
CREATE INDEX IDX_rule_packs_uf ON rule_packs (uf) WHERE uf IS NOT NULL;

COMMENT ON TABLE rule_packs IS 'Pacotes de regras por UF e setor (ex: SP construção, MG construção, Lucro Presumido)';
COMMENT ON COLUMN rule_packs.rules_json IS 'Array de regras: [{id, name, description, evaluate_function}]';


-- ============================================================
-- TABELA: organization_rule_packs (Feature #13)
-- ============================================================
CREATE TABLE organization_rule_packs (
  id                uuid PRIMARY KEY DEFAULT gen_random_uuid(),
  organization_id   uuid NOT NULL REFERENCES organizations(id) ON DELETE CASCADE,
  rule_pack_id      uuid NOT NULL REFERENCES rule_packs(id) ON DELETE CASCADE,
  is_enabled        boolean NOT NULL DEFAULT true,
  enabled_at        timestamptz NOT NULL DEFAULT now(),
  disabled_at       timestamptz,

  CONSTRAINT UQ_org_pack UNIQUE (organization_id, rule_pack_id)
);

CREATE INDEX IDX_org_rule_packs_org ON organization_rule_packs (organization_id);
CREATE INDEX IDX_org_rule_packs_enabled ON organization_rule_packs (organization_id, is_enabled) WHERE is_enabled = true;

COMMENT ON TABLE organization_rule_packs IS 'Pacotes de regras habilitados por organização';
```

---

### Resumo do Modelo Atualizado (MVP + Pós-MVP)

| Tabela | Registros esperados (5 tenants, 3 meses) | Tamanho estimado | Função principal |
|---|---|---|---|
| **MVP (10 tabelas)** | | | |
| `organizations` | 5 | < 10 KB | Tenants |
| `users` | 10 | < 10 KB | Usuários por tenant |
| `nfe_documents` | ~2.500 (500/tenant) | ~15 MB (com XML raw) | Documentos fiscais |
| `nfe_items` | ~25.000 (10 itens/nota) | ~8 MB | Produtos das notas |
| `inconsistencies` | ~250 (10% das notas) | ~2 MB | Problemas detectados |
| `audit_log` | ~5.000 | ~3 MB | Rastreabilidade |
| `magic_links` | ~100 | < 1 MB | Autenticação |
| `upload_batches` | ~150 | < 1 MB | Histórico de uploads |
| `pending_notifications` | ~1.000 | < 1 MB | Fila de notificações |
| `fiscal_reference_tables` | ~10 | ~5 MB | Tabelas fiscais versionadas |
| **Pós-MVP Fase A (4 tabelas)** | | | |
| `supplier_message_templates` | ~20 | < 1 MB | Templates de mensagens |
| `supplier_messages` | ~500 | < 1 MB | Log de mensagens enviadas |
| `whatsapp_ingestion_log` | ~1.000 | < 1 MB | Log de ingestão WhatsApp |
| `onboarding_sessions` | ~10 | < 1 MB | Sessões de onboarding |
| **Pós-MVP Fase B (8 tabelas)** | | | |
| `digital_certificates` | ~5 | < 1 MB | Certificados A1 criptografados |
| `sefaz_download_sessions` | ~150 | < 1 MB | Sessões de download Sefaz |
| `sefaz_download_queue` | ~50 | < 1 MB | Fila de downloads agendados |
| `inconsistency_comments` | ~1.000 | < 1 MB | Comentários em inconsistências |
| `inconsistency_attachments` | ~500 | ~5 MB | Anexos (PDF/imagem) |
| `inconsistency_assignments` | ~250 | < 1 MB | Atribuições de responsável |
| `cadastral_alerts` | ~200 | < 1 MB | Alertas cadastrais |
| `cadastral_monitoring_config` | ~10 | < 1 MB | Config de monitoramento |
| **Pós-MVP Fase C (5 tabelas + 1 view)** | | | |
| `accountants` | ~10 | < 1 MB | Contadores (portal) |
| `accountant_clients` | ~20 | < 1 MB | Relação contador-cliente |
| `accountant_comments` | ~500 | < 1 MB | Comentários do contador |
| `accountant_monthly_exports` | ~50 | < 1 MB | Exportações mensais |
| `supplier_scores` (view) | ~500 | < 1 MB | Score de fornecedores |
| `ai_conversations` | ~1.000 | < 1 MB | Conversas com IA |
| **Pós-MVP Fase D (5 tabelas)** | | | |
| `reform_checklist` | ~50 | < 1 MB | Checklist Reforma Tributária |
| `cbs_ibs_alerts` | ~100 | < 1 MB | Alertas CBS/IBS |
| `erp_connections` | ~10 | < 1 MB | Conexões ERPs |
| `erp_sync_logs` | ~500 | < 1 MB | Logs de sincronização |
| `rule_packs` | ~10 | < 1 MB | Pacotes de regras |
| `organization_rule_packs` | ~20 | < 1 MB | Pacotes habilitados por org |
| **Total** | | **~45 MB** | Bem dentro dos 40GB da VPS |

---

### Riscos e pontos de atenção (Expansão Pós-MVP)

| Risco | Severidade | Mitigação |
|---|---|---|
| 23 novas tabelas podem degradar performance se índices não otimizados | Média | Revisão de índices antes de cada fase. Query analysis com `EXPLAIN ANALYZE`. Particionamento se necessário |
| View materializada `supplier_scores` pode ficar desatualizada se cron falhar | Média | Refresh manual via botão na interface. Alerta se refresh falhar. Timestamp visível "Atualizado em DD/MM HH:MM" |
| Certificados A1 criptografados podem ser comprometidos se `CERTIFICATE_ENCRYPTION_KEY` vazar | Alta | Rotação de chave a cada 6 meses. Pen-test antes de lançar. Armazenar chave em cofre (AWS Secrets Manager) |
| Tokens OAuth de ERPs em `erp_connections` podem ser comprometidos | Alta | Criptografia AES-256-GCM. Rotação de tokens via refresh_token. Monitoramento de uso suspeito |
| JSONB em `rule_packs.rules_json` pode crescer se muitos pacotes forem adicionados | Baixa | Limite de 100 regras por pacote. Validação de tamanho no upload. Compressão se necessário |
| `inconsistency_attachments` pode crescer rápido se usuários uploadarem muitos arquivos | Média | Limite de 10MB por anexo. Rotação de anexos > 1 ano para S3. Alerta se disco > 80% |
| `ai_conversations` pode crescer rápido se IA for muito usada | Baixa | Retenção de 90 dias. Arquivamento para S3 após 90 dias. Limite de 10 perguntas/hora por usuário |

### Riscos e pontos de atenção

| Risco | Severidade | Mitigação |
|---|---|---|
| UUIDv7 gerado na aplicação depende do pacote `uuidv7`. Se o pacote tiver bug de colisão, PKs duplicam | Baixa | UUIDv7 é RFC 9562. Probabilidade de colisão com 2.500 registros é efetivamente zero. Fallback: `gen_random_uuid()` nativo |
| JSONB para `xml_raw` pode crescer rápido (cada XML tem 20-80KB). 2.500 notas = 125-200MB se todas armazenadas | Média | MVP: manter XMLs em disco (/data/xml), banco guarda referência + campos extraídos. `xml_raw` só para notas com inconsistência (~10%). Retenção: >90 dias → S3 |
| RLS com `current_setting` exige que a aplicação sete a variável em cada sessão. Se esquecer, query retorna 0 linhas | Média | Middleware Fastify seta `app.current_organization_id` no `preHandler`. Teste de integração valida que toda rota autenticada tem organização no contexto |
| Índices GIN em `xml_raw` e `checklist_json` consomem espaço adicional (~30% do tamanho da coluna) | Baixa | 35MB total é irrisório para SSD de 40GB. Monitorar tamanho dos índices com `pg_stat_user_indexes` |
| Migrations do Drizzle podem divergir entre dev (push) e prod (generate+migrate) | Média | Política: dev usa push, mas antes de staging, roda `generate` + revisa o SQL gerado. CI valida que `drizzle-kit check` não reporta divergência |
| Tabela `fiscal_reference_tables` carregada por seed scripts manuais — pode ficar desatualizada | Média | Seed scripts versionados no Git. CI valida que versão ativa é a mais recente. Script de atualização semestral documentado |

---

## Etapa 20 — Contratos de API

### Objetivo da etapa

Especificar cada endpoint REST do FiscoPilot MVP com precisão suficiente para desenvolvimento paralelo (front-end e back-end) e escrita de testes automatizados — definindo método, path, headers, request/response schema, autenticação, códigos de status e exemplos curl.

### Premissas adotadas

| # | Premissa | Justificativa |
|---|---|---|
| P1 | API REST sobre HTTP/1.1 com JSON como formato de request/response. Multipart para upload de arquivos | Simplicidade máxima; GraphQL e tRPC são overkill para 10 endpoints |
| P2 | Autenticação via JWT Bearer token (obtido via magic link). Sem OAuth, sem API keys, sem basic auth | Roberto não tem e-mail/senha; JWT gerado após verificação do magic link |
| P3 | Header `X-Organization-Id` obrigatório em toda request autenticada. Back-end seta `app.current_organization_id` para RLS | Multi-tenant desde a primeira requisição |
| P4 | Todo endpoint de escrita (POST/PATCH) retorna o recurso criado/atualizado no response body. Endpoints de leitura (GET) usam paginação cursor-based ou offset-based | Consistência e previsibilidade para o front-end |
| P5 | Erros seguem RFC 7807 (Problem Details): `{ "type": "...", "title": "...", "status": N, "detail": "..." }` | Padrão reconhecível; Sentry indexa automaticamente |
| P6 | Rate limit global: 60 req/min por tenant. Rate limit específico para magic link: 3 req/15min por número | Proteção contra abuso; limites generosos para uso legítimo |
| P7 | Validação de schema via Zod no back-end (Fastify + Zod). Schemas compartilhados entre front e back via pacote `shared` | Coerência com stack da Etapa 18; type-safety ponta a ponta |

### Análise

Os 13 endpoints do MVP cobrem 5 módulos. A arquitetura REST foi escolhida sobre GraphQL porque (a) o time de 2 devs conhece REST, (b) as queries são previsíveis (dashboard com agregações fixas, lista de notas com filtros conhecidos), (c) caching HTTP é trivial (ETag, Cache-Control), (d) documentação com Swagger/OpenAPI é gerada automaticamente pelo Fastify.

Todos os endpoints de leitura usam paginação cursor-based com `?cursor=` e `?limit=`, exceto o dashboard (que é uma agregação sem paginação) e o relatório PDF (que gera arquivo). O cursor é o UUID do último item da página anterior — isso evita offset drift quando novos registros são inseridos entre páginas.

O upload de XMLs é um endpoint multipart que recebe arquivos e retorna resposta síncrona (processamento <60s). Se o processamento futuro exigir assincronicidade, o endpoint evolui para retornar `202 Accepted` com `Location` header apontando para status do batch — mas isso fica para a Fase 2.

### Decisões recomendadas

| Decisão | Conteúdo | Status |
|---|---|---|
| D1 | 13 endpoints REST: 2 Auth, 2 Upload, 1 Dashboard, 3 Notas, 3 Inconsistências, 1 Relatório, 1 Health | Decisão de API |
| D2 | Autenticação: JWT Bearer no header `Authorization`. Token obtido via `POST /api/auth/magic-link` + `GET /api/auth/verify?token=` | Decisão de auth |
| D3 | Paginação cursor-based para listas (Notas, Inconsistências). Dashboard sem paginação | Decisão de UX/API |
| D4 | Upload síncrono (retorna resultado no response, não `202 Accepted`). Timeout 120s | Decisão de MVP |
| D5 | Relatório PDF: `GET /api/report/pdf?mes=YYYY-MM` retorna `application/pdf` diretamente (não JSON com link) | Decisão de simplicidade |
| D6 | OpenAPI 3.1 spec gerado automaticamente pelo Fastify (fastify-swagger) a partir dos Zod schemas | Decisão de DX |
| D7 | Versionamento de API no path: `/api/v1/...`. Headers de depreciação (`Sunset`, `Deprecation`) quando necessário | Decisão de evolução |

### Entregáveis

---

#### 5.1 Convenções Gerais

**Base URL:** `https://app.copilotofiscal.com/api/v1`

**Headers comuns em toda requisição autenticada:**

```
Authorization: Bearer <jwt_token>
X-Organization-Id: <organization_uuid>
Content-Type: application/json
Accept: application/json
```

**Headers de resposta padrão:**

```
X-Request-Id: <uuid>
X-RateLimit-Remaining: 59
X-RateLimit-Reset: 1715817600
```

**Formato de erro (RFC 7807):**

```json
{
  "type": "https://copilotofiscal.com/errors/invalid-request",
  "title": "Requisição inválida",
  "status": 400,
  "detail": "O campo 'chave_acesso' deve ter 44 caracteres",
  "instance": "/api/v1/upload",
  "validation": [
    { "field": "chave_acesso", "message": "Deve ter exatamente 44 caracteres" }
  ]
}
```

**Paginação (cursor-based):**

Request:
```
GET /api/v1/notes?limit=20&cursor=019018a0-...&direction=desc
```

Response:
```json
{
  "data": [ "..." ],
  "pagination": {
    "limit": 20,
    "next_cursor": "019018a0-855e-...",
    "has_more": true
  }
}
```

---

#### 5.2 MÓDULO AUTH — Autenticação

---

##### `POST /api/v1/auth/magic-link`

Solicita envio de link mágico por WhatsApp.

**Autenticação:** Nenhuma (público)

**Rate limit:** 3 requisições por número de WhatsApp a cada 15 minutos

**Request:**

```json
{
  "whatsapp": "5511999991234"
}
```

| Campo | Tipo | Obrigatório | Validação |
|---|---|---|---|
| `whatsapp` | string | Sim | Regex `^55[1-9][1-9][0-9]{8,9}$` |

**Response `200 OK` (sempre — não revela se número existe):**

```json
{
  "message": "Se o número estiver cadastrado, você receberá um link de acesso no WhatsApp em instantes.",
  "expires_in": 86400
}
```

**Erros:**

| Código | Situação |
|---|---|
| `400` | WhatsApp em formato inválido |
| `429` | Muitas tentativas. Tente novamente em X minutos |

**Curl:**

```bash
curl -X POST https://app.copilotofiscal.com/api/v1/auth/magic-link \
  -H "Content-Type: application/json" \
  -d '{"whatsapp": "5511999991234"}'
```

---

##### `GET /api/v1/auth/verify`

Verifica token do magic link e retorna JWT + dados do usuário.

**Autenticação:** Token (query param)

**Query params:**

| Parâmetro | Tipo | Obrigatório |
|---|---|---|
| `token` | string | Sim |

**Response `200 OK`:**

```json
{
  "access_token": "eyJhbGciOiJIUzI1NiIs...",
  "token_type": "Bearer",
  "expires_in": 604800,
  "user": {
    "id": "019018a0-7a1e-...",
    "nome": "Roberto Almeida",
    "whatsapp": "5511999991234",
    "role": "ADMIN",
    "organization": {
      "id": "019018a0-5c3f-...",
      "nome_fantasia": "Material de Construção ABC",
      "cnpj": "12345678000190",
      "regime": "SIMPLES_NACIONAL",
      "uf": "SP"
    }
  }
}
```

**Erros:**

| Código | Situação |
|---|---|
| `401` | Token inválido, expirado ou já utilizado |
| `404` | Token não encontrado |

**Curl:**

```bash
curl "https://app.copilotofiscal.com/api/v1/auth/verify?token=8f3a1b2c9d4e..."
```

---

#### 5.3 MÓDULO UPLOAD — Ingestão de XMLs

---

##### `POST /api/v1/upload`

Faz upload de arquivos XML/zip de NF-e para processamento.

**Autenticação:** JWT + `X-Organization-Id`

**Content-Type:** `multipart/form-data`

**Request:**

| Campo | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `file` | File | Sim | Arquivo .xml, .zip contendo XMLs, ou múltiplos arquivos |
| `file` (múltiplos) | File[] | — | Até 200 arquivos XML individuais |

**Response `200 OK`:**

```json
{
  "batch": {
    "id": "019018a0-9f2d-...",
    "status": "COMPLETED",
    "total_files": 87,
    "processed": 87,
    "ignored": 0,
    "inconsistencies_found": 3,
    "created_at": "2026-05-15T14:30:00Z",
    "completed_at": "2026-05-15T14:30:27Z"
  },
  "summary": {
    "ok": 84,
    "atencao": 1,
    "risco_alto": 2
  },
  "inconsistencies": [
    {
      "id": "019018a0-abc1-...",
      "nfe_document_id": "019018a0-def2-...",
      "rule_id": "R1",
      "score": 85,
      "classification": "RISCO_ALTO",
      "nfe": {
        "chave_acesso": "35210512345678000190550010000035211000003521",
        "numero": 3521,
        "nome_emitente": "Distribuidora CimentoBom",
        "valor_total": "8400.00",
        "data_emissao": "2026-05-10"
      },
      "found_value": "6102",
      "expected_value": "1102",
      "estimated_impact": "412.00",
      "explanation_text": "O código da operação fiscal (CFOP) é de saída, mas deveria ser de entrada para o Simples Nacional."
    }
  ]
}
```

**Erros:**

| Código | Situação |
|---|---|
| `400` | Nenhum arquivo enviado, ou nenhum arquivo é XML/ZIP válido |
| `413` | Arquivo excede 100MB |
| `415` | Formato não suportado |
| `422` | Lote excede 200 notas processáveis |

**Timeout:** 120 segundos (processamento síncrono)

**Curl:**

```bash
curl -X POST https://app.copilotofiscal.com/api/v1/upload \
  -H "Authorization: Bearer eyJhbGci..." \
  -H "X-Organization-Id: 019018a0-5c3f-..." \
  -F "file=@notas_maio.zip"
```

---

##### `GET /api/v1/upload/batches`

Lista histórico de uploads (batches).

**Autenticação:** JWT + `X-Organization-Id`

**Query params:**

| Parâmetro | Tipo | Padrão | Descrição |
|---|---|---|---|
| `limit` | integer | 20 | Máximo 50 |
| `cursor` | string | — | UUID do último batch da página anterior |

**Response `200 OK`:**

```json
{
  "data": [
    {
      "id": "019018a0-9f2d-...",
      "source": "WEB",
      "status": "COMPLETED",
      "total_files": 87,
      "processed": 87,
      "ignored": 0,
      "inconsistencies_found": 3,
      "created_at": "2026-05-15T14:30:00Z",
      "completed_at": "2026-05-15T14:30:27Z",
      "user": {
        "nome": "Fernanda Souza"
      }
    }
  ],
  "pagination": {
    "limit": 20,
    "next_cursor": "019018a0-9f2d-...",
    "has_more": true
  }
}
```

**Curl:**

```bash
curl "https://app.copilotofiscal.com/api/v1/upload/batches?limit=20" \
  -H "Authorization: Bearer eyJhbGci..." \
  -H "X-Organization-Id: 019018a0-5c3f-..."
```

---

#### 5.4 MÓDULO DASHBOARD

---

##### `GET /api/v1/dashboard`

Retorna resumo agregado do mês corrente para o dashboard principal (T1).

**Autenticação:** JWT + `X-Organization-Id`

**Query params:**

| Parâmetro | Tipo | Padrão | Descrição |
|---|---|---|---|
| `mes` | string | mês atual | Formato `YYYY-MM` |
| `uf` | string | — | Filtrar por UF emitente (opcional) |

**Response `200 OK`:**

```json
{
  "periodo": {
    "mes": "2026-05",
    "inicio": "2026-05-01",
    "fim": "2026-05-31"
  },
  "total_notas": 143,
  "ultimo_processamento": "2026-05-15T14:30:00Z",
  "por_status": {
    "ok": 138,
    "atencao": 3,
    "risco_alto": 2
  },
  "inconsistencias": [
    {
      "id": "019018a0-abc1-...",
      "classification": "RISCO_ALTO",
      "score": 85,
      "rule_id": "R1",
      "status": "PENDENTE",
      "nfe": {
        "id": "019018a0-def2-...",
        "numero": 3521,
        "chave_acesso": "35210512345678000190550010000035211000003521",
        "nome_emitente": "Distribuidora CimentoBom",
        "valor_total": "8400.00",
        "data_emissao": "2026-05-10"
      },
      "estimated_impact": "412.00",
      "resumo": "Código da operação fiscal diverge do esperado para o Simples Nacional",
      "created_at": "2026-05-15T14:30:00Z"
    },
    {
      "id": "019018a0-abc2-...",
      "classification": "ATENCAO",
      "score": 62,
      "rule_id": "R5",
      "status": "PENDENTE",
      "nfe": {
        "id": "019018a0-def3-...",
        "numero": 3518,
        "nome_emitente": "Telhanorte ABC",
        "valor_total": "3200.00",
        "data_emissao": "2026-05-12"
      },
      "estimated_impact": "87.00",
      "resumo": "Valor total não bate com a soma dos itens",
      "created_at": "2026-05-15T14:30:00Z"
    },
    {
      "id": "019018a0-abc3-...",
      "classification": "ATENCAO",
      "score": 50,
      "rule_id": "R3",
      "status": "PENDENTE",
      "nfe": {
        "id": "019018a0-def4-...",
        "numero": 3498,
        "nome_emitente": "Pisos e Revestimentos Sul",
        "valor_total": "5200.00",
        "data_emissao": "2026-05-05"
      },
      "estimated_impact": null,
      "resumo": "Classificação fiscal do produto parece estranha para o seu setor",
      "created_at": "2026-05-08T16:40:00Z"
    }
  ],
  "pendentes_risco_alto": 1
}
```

**Curl:**

```bash
curl "https://app.copilotofiscal.com/api/v1/dashboard?mes=2026-05" \
  -H "Authorization: Bearer eyJhbGci..." \
  -H "X-Organization-Id: 019018a0-5c3f-..."
```

---

#### 5.5 MÓDULO NOTAS

---

##### `GET /api/v1/notes`

Lista notas fiscais processadas com filtros.

**Autenticação:** JWT + `X-Organization-Id`

**Query params:**

| Parâmetro | Tipo | Padrão | Descrição |
|---|---|---|---|
| `mes` | string | mês atual | `YYYY-MM` |
| `classification` | string | — | `OK`, `ATENCAO`, `RISCO_ALTO` (filtra por risco) |
| `status` | string | — | `PENDENTE`, `EM_ANDAMENTO`, `RESOLVIDA`, `IGNORADA` (filtra por status da inconsistência) |
| `search` | string | — | Busca textual por nome do fornecedor (ILIKE) |
| `limit` | integer | 20 | Máximo 100 |
| `cursor` | string | — | UUID da última nota da página anterior |
| `direction` | string | `desc` | `asc` ou `desc` por data_emissao |

**Response `200 OK`:**

```json
{
  "data": [
    {
      "id": "019018a0-def2-...",
      "chave_acesso": "35210512345678000190550010000035211000003521",
      "numero": 3521,
      "nome_emitente": "Distribuidora CimentoBom",
      "cnpj_emitente": "12345678000190",
      "valor_total": "8400.00",
      "data_emissao": "2026-05-10",
      "has_inconsistency": true,
      "worst_classification": "RISCO_ALTO",
      "worst_score": 85,
      "inconsistency_count": 1,
      "status_nfe": "ATIVA",
      "created_at": "2026-05-15T14:30:00Z"
    }
  ],
  "pagination": {
    "limit": 20,
    "next_cursor": "019018a0-def2-...",
    "has_more": true
  }
}
```

**Curl:**

```bash
curl "https://app.copilotofiscal.com/api/v1/notes?mes=2026-05&classification=RISCO_ALTO&limit=20" \
  -H "Authorization: Bearer eyJhbGci..." \
  -H "X-Organization-Id: 019018a0-5c3f-..."
```

---

##### `GET /api/v1/notes/:id`

Retorna detalhes de uma nota fiscal específica com suas inconsistências e itens.

**Autenticação:** JWT + `X-Organization-Id`

**Path params:**

| Parâmetro | Tipo | Descrição |
|---|---|---|
| `id` | UUID | ID da nfe_document |

**Response `200 OK`:**

```json
{
  "id": "019018a0-def2-...",
  "chave_acesso": "35210512345678000190550010000035211000003521",
  "numero": 3521,
  "serie": 1,
  "modelo": "55",
  "data_emissao": "2026-05-10",
  "cnpj_emitente": "12345678000190",
  "nome_emitente": "Distribuidora CimentoBom",
  "uf_emitente": "SP",
  "cnpj_destinatario": "98765432000100",
  "valor_total": "8400.00",
  "valor_produtos": "8400.00",
  "valor_ipi": "0.00",
  "valor_icms": "1008.00",
  "aliquota_icms": "12.00",
  "cfop": "6102",
  "ncm_principal": "25232900",
  "cst_pis": "49",
  "cst_cofins": "49",
  "cst_icms": "00",
  "icms_st": false,
  "status_nfe": "ATIVA",
  "source": "WEB",
  "created_at": "2026-05-15T14:30:00Z",
  "inconsistencies": [
    {
      "id": "019018a0-abc1-...",
      "rule_id": "R1",
      "score": 85,
      "classification": "RISCO_ALTO",
      "field_path": "NFe.infNFe.det.0.prod.CFOP",
      "found_value": "6102",
      "expected_value": "1102",
      "estimated_impact": "412.00",
      "explanation_text": "O código da operação fiscal (CFOP) é de saída, mas deveria ser de entrada para o Simples Nacional.",
      "status": "PENDENTE",
      "checklist_json": [
        { "order": 1, "text": "Ligue para Distribuidora CimentoBom — (11) 99999-9999", "done": false },
        { "order": 2, "text": "Peça uma carta de correção com CFOP 1102", "done": false },
        { "order": 3, "text": "Peça para reemitir a nota fiscal com o código correto", "done": false },
        { "order": 4, "text": "Avise Dona Célia sobre essa correção", "done": false }
      ],
      "created_at": "2026-05-15T14:30:00Z"
    }
  ],
  "items": [
    {
      "id": "019018a0-ghi1-...",
      "numero_item": 1,
      "codigo_produto": "CPII50",
      "descricao": "Cimento CP-II 50kg",
      "ncm": "25232900",
      "cfop": "6102",
      "quantidade": "200.0000",
      "unidade": "UN",
      "valor_unitario": "42.0000",
      "valor_total": "8400.00",
      "aliquota_icms": "12.00",
      "valor_icms": "1008.00"
    }
  ]
}
```

**Erros:**

| Código | Situação |
|---|---|
| `404` | Nota não encontrada ou pertence a outro tenant |

**Curl:**

```bash
curl "https://app.copilotofiscal.com/api/v1/notes/019018a0-def2-..." \
  -H "Authorization: Bearer eyJhbGci..." \
  -H "X-Organization-Id: 019018a0-5c3f-..."
```

---

##### `GET /api/v1/notes/:id/inconsistencies`

Retorna apenas as inconsistências de uma nota específica (atalho — mesmo resultado que o campo `inconsistencies` em `GET /api/v1/notes/:id`).

**Autenticação:** JWT + `X-Organization-Id`

**Response `200 OK`:**

```json
{
  "nfe_id": "019018a0-def2-...",
  "nfe_numero": 3521,
  "nfe_emitente": "Distribuidora CimentoBom",
  "data": [
    {
      "id": "019018a0-abc1-...",
      "rule_id": "R1",
      "score": 85,
      "classification": "RISCO_ALTO",
      "estimated_impact": "412.00",
      "explanation_text": "...",
      "status": "PENDENTE",
      "created_at": "2026-05-15T14:30:00Z"
    }
  ]
}
```

**Curl:**

```bash
curl "https://app.copilotofiscal.com/api/v1/notes/019018a0-def2-.../inconsistencies" \
  -H "Authorization: Bearer eyJhbGci..." \
  -H "X-Organization-Id: 019018a0-5c3f-..."
```

---

#### 5.6 MÓDULO INCONSISTÊNCIAS

---

##### `GET /api/v1/inconsistencies/:id`

Retorna detalhes completos de uma inconsistência, incluindo checklist e histórico.

**Autenticação:** JWT + `X-Organization-Id`

**Response `200 OK`:**

```json
{
  "id": "019018a0-abc1-...",
  "rule_id": "R1",
  "score": 85,
  "classification": "RISCO_ALTO",
  "field_path": "NFe.infNFe.det.0.prod.CFOP",
  "found_value": "6102",
  "expected_value": "1102",
  "estimated_impact": "412.00",
  "explanation_text": "O código da operação fiscal (CFOP) é de saída, mas deveria ser de entrada para o Simples Nacional.",
  "explanation_llm": null,
  "checklist_json": [
    { "order": 1, "text": "Ligue para Distribuidora CimentoBom — (11) 99999-9999", "done": false },
    { "order": 2, "text": "Peça uma carta de correção com CFOP 1102", "done": false },
    { "order": 3, "text": "Peça para reemitir a nota fiscal com o código correto", "done": false },
    { "order": 4, "text": "Avise Dona Célia sobre essa correção", "done": false }
  ],
  "status": "PENDENTE",
  "ignore_reason": null,
  "updated_by_user": null,
  "resolved_at": null,
  "created_at": "2026-05-15T14:30:00Z",
  "updated_at": "2026-05-15T14:30:00Z",
  "nfe": {
    "id": "019018a0-def2-...",
    "chave_acesso": "35210512345678000190550010000035211000003521",
    "numero": 3521,
    "nome_emitente": "Distribuidora CimentoBom",
    "cnpj_emitente": "12345678000190",
    "valor_total": "8400.00",
    "data_emissao": "2026-05-10"
  },
  "history": [
    {
      "id": "019018a0-log1-...",
      "event_type": "INCONSISTENCY_DETECTED",
      "details": { "rule_id": "R1", "score": 85 },
      "created_at": "2026-05-15T14:30:00Z"
    }
  ]
}
```

**Curl:**

```bash
curl "https://app.copilotofiscal.com/api/v1/inconsistencies/019018a0-abc1-..." \
  -H "Authorization: Bearer eyJhbGci..." \
  -H "X-Organization-Id: 019018a0-5c3f-..."
```

---

##### `PATCH /api/v1/inconsistencies/:id`

Atualiza status, checklist ou motivo de uma inconsistência.

**Autenticação:** JWT + `X-Organization-Id`

**Request:**

```json
{
  "status": "EM_ANDAMENTO",
  "checklist_json": [
    { "order": 1, "text": "Ligue para Distribuidora CimentoBom — (11) 99999-9999", "done": true },
    { "order": 2, "text": "Peça uma carta de correção com CFOP 1102", "done": false },
    { "order": 3, "text": "Peça para reemitir a nota fiscal com o código correto", "done": false },
    { "order": 4, "text": "Avise Dona Célia sobre essa correção", "done": false }
  ],
  "ignore_reason": null
}
```

| Campo | Tipo | Obrigatório | Validação |
|---|---|---|---|
| `status` | string | Não | `PENDENTE`, `EM_ANDAMENTO`, `RESOLVIDA`, `IGNORADA` |
| `checklist_json` | array | Não | Array de `{order, text, done}`. Se enviado, substitui o checklist inteiro |
| `ignore_reason` | string | Condicional | Obrigatório se `status = IGNORADA`. Min 1 caractere, max 500 |

**Regras de negócio:**
- Se `status = IGNORADA` e `ignore_reason` vazio → `422 Unprocessable Entity`
- Se `status = RESOLVIDA` → `resolved_at` é setado automaticamente pelo trigger
- Checklist só é atualizado se o campo `checklist_json` vier no body (PATCH parcial)
- `updated_by` é setado automaticamente com o ID do usuário autenticado
- Transição `IGNORADA → RESOLVIDA` permite limpar `ignore_reason`

**Response `200 OK`:**

```json
{
  "id": "019018a0-abc1-...",
  "status": "EM_ANDAMENTO",
  "checklist_json": [
    { "order": 1, "text": "Ligue para Distribuidora CimentoBom — (11) 99999-9999", "done": true },
    { "order": 2, "text": "Peça uma carta de correção com CFOP 1102", "done": false },
    { "order": 3, "text": "Peça para reemitir a nota fiscal com o código correto", "done": false },
    { "order": 4, "text": "Avise Dona Célia sobre essa correção", "done": false }
  ],
  "ignore_reason": null,
  "updated_by_user": {
    "id": "019018a0-7a1e-...",
    "nome": "Fernanda Souza"
  },
  "resolved_at": null,
  "updated_at": "2026-05-16T09:15:00Z"
}
```

**Erros:**

| Código | Situação |
|---|---|
| `404` | Inconsistência não encontrada |
| `422` | `status = IGNORADA` sem `ignore_reason`, ou valor de status inválido |
| `409` | Tentativa de modificar inconsistência já `RESOLVIDA` (reabrir requer `status = EM_ANDAMENTO`) |

**Curl:**

```bash
curl -X PATCH https://app.copilotofiscal.com/api/v1/inconsistencies/019018a0-abc1-... \
  -H "Authorization: Bearer eyJhbGci..." \
  -H "X-Organization-Id: 019018a0-5c3f-..." \
  -H "Content-Type: application/json" \
  -d '{"status": "EM_ANDAMENTO", "checklist_json": [{"order":1,"text":"Ligue para...","done":true}]}'
```

---

##### `GET /api/v1/inconsistencies`

Lista inconsistências com filtros (visão alternativa ao dashboard, útil para a Fernanda).

**Autenticação:** JWT + `X-Organization-Id`

**Query params:**

| Parâmetro | Tipo | Padrão | Descrição |
|---|---|---|---|
| `mes` | string | mês atual | `YYYY-MM` |
| `classification` | string | — | `ATENCAO`, `RISCO_ALTO` |
| `status` | string | — | `PENDENTE`, `EM_ANDAMENTO`, `RESOLVIDA`, `IGNORADA` |
| `rule_id` | string | — | `R1` a `R8` |
| `limit` | integer | 20 | Máximo 50 |
| `cursor` | string | — | UUID da última inconsistência |

**Response `200 OK`:**

```json
{
  "data": [
    {
      "id": "019018a0-abc1-...",
      "rule_id": "R1",
      "score": 85,
      "classification": "RISCO_ALTO",
      "estimated_impact": "412.00",
      "explanation_text": "O código da operação fiscal (CFOP) é de saída...",
      "status": "PENDENTE",
      "created_at": "2026-05-15T14:30:00Z",
      "nfe": {
        "id": "019018a0-def2-...",
        "numero": 3521,
        "nome_emitente": "Distribuidora CimentoBom",
        "valor_total": "8400.00",
        "data_emissao": "2026-05-10"
      }
    }
  ],
  "pagination": {
    "limit": 20,
    "next_cursor": "019018a0-abc1-...",
    "has_more": false
  }
}
```

**Curl:**

```bash
curl "https://app.copilotofiscal.com/api/v1/inconsistencies?mes=2026-05&status=PENDENTE&classification=RISCO_ALTO" \
  -H "Authorization: Bearer eyJhbGci..." \
  -H "X-Organization-Id: 019018a0-5c3f-..."
```

---

#### 5.7 MÓDULO RELATÓRIO

---

##### `GET /api/v1/report/pdf`

Gera e retorna o relatório mensal do contador em PDF.

**Autenticação:** JWT + `X-Organization-Id`

**Query params:**

| Parâmetro | Tipo | Padrão | Descrição |
|---|---|---|---|
| `mes` | string | mês anterior | `YYYY-MM`. Ex.: `2026-05` |

**Response `200 OK`:**

```
Content-Type: application/pdf
Content-Disposition: attachment; filename="FiscoPilot_Relatorio_2026-05_MaterialABC.pdf"
Content-Length: 48203

<binary PDF data>
```

**Conteúdo do PDF (gerado por pdfkit):**
- Logo FiscoPilot + título "Relatório Fiscal — Maio/2026"
- Identificação: empresa, CNPJ, regime, período
- Disclaimer jurídico em box destacado (primeira página)
- Resumo numérico (total notas, OK, atenção, risco alto, resolvidos, pendentes)
- Tabela de inconsistências: Nota, Fornecedor, Valor, Tipo, Risco, Status, Ação Sugerida
- Rodapé: data/hora de geração, URL do produto

**Erros:**

| Código | Situação |
|---|---|
| `404` | Nenhuma nota processada no mês solicitado |
| `422` | Formato de mês inválido |

**Curl:**

```bash
curl "https://app.copilotofiscal.com/api/v1/report/pdf?mes=2026-05" \
  -H "Authorization: Bearer eyJhbGci..." \
  -H "X-Organization-Id: 019018a0-5c3f-..." \
  -o relatorio_maio_2026.pdf
```

---

#### 5.8 MÓDULO HEALTH

---

##### `GET /api/v1/health`

Health check para monitoramento (Uptime Robot, Docker healthcheck).

**Autenticação:** Nenhuma (público)

**Response `200 OK`:**

```json
{
  "status": "ok",
  "timestamp": "2026-05-15T14:30:00Z",
  "version": "0.1.0",
  "uptime_seconds": 482310,
  "checks": {
    "database": "ok",
    "disk": "ok"
  }
}
```

**Response `503 Service Unavailable` (se DB offline):**

```json
{
  "status": "degraded",
  "timestamp": "2026-05-15T14:30:00Z",
  "version": "0.1.0",
  "checks": {
    "database": "error",
    "disk": "ok"
  }
}
```

**Curl:**

```bash
curl https://app.copilotofiscal.com/api/v1/health
```

---

#### 5.9 Resumo dos Endpoints

| # | Método | Path | Módulo | Auth | Paginação | Descrição |
|---|---|---|---|---|---|---|
| 1 | `POST` | `/auth/magic-link` | Auth | — | — | Solicita link mágico |
| 2 | `GET` | `/auth/verify` | Auth | Token | — | Verifica token, retorna JWT |
| 3 | `POST` | `/upload` | Upload | JWT | — | Upload de XMLs (multipart) |
| 4 | `GET` | `/upload/batches` | Upload | JWT | Cursor | Histórico de uploads |
| 5 | `GET` | `/dashboard` | Dashboard | JWT | — | Resumo do mês corrente |
| 6 | `GET` | `/notes` | Notas | JWT | Cursor | Lista de notas (com filtros) |
| 7 | `GET` | `/notes/:id` | Notas | JWT | — | Detalhe da nota + itens + inconsistências |
| 8 | `GET` | `/notes/:id/inconsistencies` | Notas | JWT | — | Inconsistências de uma nota |
| 9 | `GET` | `/inconsistencies/:id` | Inconsistências | JWT | — | Detalhe da inconsistência + checklist + histórico |
| 10 | `PATCH` | `/inconsistencies/:id` | Inconsistências | JWT | — | Atualiza status/checklist/motivo |
| 11 | `GET` | `/inconsistencies` | Inconsistências | JWT | Cursor | Lista de inconsistências (com filtros) |
| 12 | `GET` | `/report/pdf` | Relatório | JWT | — | Gera PDF do relatório mensal |
| 13 | `GET` | `/health` | Health | — | — | Health check |

---

#### 5.10 TypeScript Types Compartilhados

```typescript
// packages/shared/src/types/api.ts

// ====== Paginação ======
export interface PaginationParams {
  limit?: number;
  cursor?: string;
  direction?: 'asc' | 'desc';
}

export interface PaginationResponse {
  limit: number;
  next_cursor: string | null;
  has_more: boolean;
}

export interface PaginatedResponse<T> {
  data: T[];
  pagination: PaginationResponse;
}

// ====== Auth ======
export interface MagicLinkRequest {
  whatsapp: string;
}

export interface MagicLinkResponse {
  message: string;
  expires_in: number;
}

export interface VerifyTokenResponse {
  access_token: string;
  token_type: 'Bearer';
  expires_in: number;
  user: UserWithOrg;
}

export interface UserWithOrg {
  id: string;
  nome: string;
  whatsapp: string;
  role: 'ADMIN' | 'OPERADOR';
  organization: OrganizationSummary;
}

export interface OrganizationSummary {
  id: string;
  nome_fantasia: string;
  cnpj: string;
  regime: 'SIMPLES_NACIONAL' | 'LUCRO_PRESUMIDO' | 'LUCRO_REAL';
  uf: string;
}

// ====== Upload ======
export interface UploadBatchResponse {
  batch: UploadBatch;
  summary: UploadSummary;
  inconsistencies: InconsistencySummary[];
}

export interface UploadBatch {
  id: string;
  status: 'PROCESSING' | 'COMPLETED' | 'PARTIAL_ERROR' | 'FAILED';
  total_files: number;
  processed: number;
  ignored: number;
  inconsistencies_found: number;
  created_at: string;
  completed_at: string | null;
}

export interface UploadSummary {
  ok: number;
  atencao: number;
  risco_alto: number;
}

// ====== Dashboard ======
export interface DashboardResponse {
  periodo: {
    mes: string;
    inicio: string;
    fim: string;
  };
  total_notas: number;
  ultimo_processamento: string;
  por_status: UploadSummary;
  inconsistencias: DashboardInconsistency[];
  pendentes_risco_alto: number;
}

export interface DashboardInconsistency {
  id: string;
  classification: 'OK' | 'ATENCAO' | 'RISCO_ALTO';
  score: number;
  rule_id: string;
  status: 'PENDENTE' | 'EM_ANDAMENTO' | 'RESOLVIDA' | 'IGNORADA';
  nfe: NoteInconsistencyRef;
  estimated_impact: string | null;
  resumo: string;
  created_at: string;
}

export interface NoteInconsistencyRef {
  id: string;
  numero: number;
  chave_acesso: string;
  nome_emitente: string;
  valor_total: string;
  data_emissao: string;
}

// ====== Inconsistência ======
export interface InconsistencyDetail {
  id: string;
  rule_id: string;
  score: number;
  classification: 'OK' | 'ATENCAO' | 'RISCO_ALTO';
  field_path: string | null;
  found_value: string | null;
  expected_value: string | null;
  estimated_impact: string | null;
  explanation_text: string;
  explanation_llm: string | null;
  checklist_json: ChecklistItem[];
  status: 'PENDENTE' | 'EM_ANDAMENTO' | 'RESOLVIDA' | 'IGNORADA';
  ignore_reason: string | null;
  updated_by_user: { id: string; nome: string } | null;
  resolved_at: string | null;
  created_at: string;
  updated_at: string;
  nfe: NoteInconsistencyRef;
  history: AuditEntry[];
}

export interface ChecklistItem {
  order: number;
  text: string;
  done: boolean;
}

export interface AuditEntry {
  id: string;
  event_type: string;
  details: Record<string, unknown>;
  created_at: string;
}

export interface InconsistencySummary {
  id: string;
  rule_id: string;
  score: number;
  classification: 'OK' | 'ATENCAO' | 'RISCO_ALTO';
  nfe: NoteInconsistencyRef;
  found_value: string | null;
  expected_value: string | null;
  estimated_impact: string | null;
  explanation_text: string;
}

export interface InconsistencyUpdateRequest {
  status?: 'PENDENTE' | 'EM_ANDAMENTO' | 'RESOLVIDA' | 'IGNORADA';
  checklist_json?: ChecklistItem[];
  ignore_reason?: string | null;
}

export interface InconsistencyUpdateResponse {
  id: string;
  status: string;
  checklist_json: ChecklistItem[];
  ignore_reason: string | null;
  updated_by_user: { id: string; nome: string } | null;
  resolved_at: string | null;
  updated_at: string;
}

// ====== Notas ======
export interface NoteListItem {
  id: string;
  chave_acesso: string;
  numero: number;
  nome_emitente: string;
  cnpj_emitente: string;
  valor_total: string;
  data_emissao: string;
  has_inconsistency: boolean;
  worst_classification: 'OK' | 'ATENCAO' | 'RISCO_ALTO' | null;
  worst_score: number | null;
  inconsistency_count: number;
  status_nfe: string;
  created_at: string;
}

export interface NoteDetail {
  id: string;
  chave_acesso: string;
  numero: number;
  serie: number;
  modelo: string;
  data_emissao: string;
  cnpj_emitente: string;
  nome_emitente: string;
  uf_emitente: string;
  cnpj_destinatario: string;
  valor_total: string;
  valor_produtos: string | null;
  valor_ipi: string | null;
  valor_icms: string | null;
  aliquota_icms: string | null;
  cfop: string | null;
  ncm_principal: string | null;
  cst_pis: string | null;
  cst_cofins: string | null;
  cst_icms: string | null;
  icms_st: boolean;
  status_nfe: string;
  source: string;
  created_at: string;
  inconsistencies: InconsistencySummary[];
  items: NoteItemDetail[];
}

export interface NoteItemDetail {
  id: string;
  numero_item: number;
  codigo_produto: string | null;
  descricao: string;
  ncm: string | null;
  cfop: string | null;
  quantidade: string;
  unidade: string;
  valor_unitario: string;
  valor_total: string;
  aliquota_icms: string | null;
  valor_icms: string | null;
}

// ====== Erros ======
export interface ApiError {
  type: string;
  title: string;
  status: number;
  detail: string;
  instance: string;
  validation?: Array<{ field: string; message: string }>;
}
```

---

### Riscos e pontos de atenção

| Risco | Severidade | Mitigação |
|---|---|---|
| Upload síncrono com timeout 120s pode ser insuficiente se VPS estiver sob carga | Média | Benchmark real com CX22 e 200 XMLs. Se >90s no pior caso, implementar `202 Accepted` + polling de status (2 dias extras). Plano de contingência documentado |
| JWT exposto em URL (magic link verify com `?token=`) pode ser logado por proxies e servidores | Média | Token do magic link é de uso único (single-use) e expira em 24h. JWT real nunca trafega em URL — apenas no header Authorization |
| Paginação cursor-based com UUID pode quebrar se o cliente guardar cursor de uma sessão antiga (dados já deletados/alterados) | Baixa | Cursores são UUIDs de registros existentes. Se o registro não existir mais, retorna lista vazia com `has_more: false`. Documentar no front-end |
| Endpoint `PATCH /inconsistencies/:id` aceita atualização parcial — cliente pode sobrescrever checklist inteiro sem querer | Baixa | Front-end envia sempre o checklist completo (estado atual + modificação). Zod valida estrutura. Se apenas status for alterado, omitir `checklist_json` do body |
| PDF gerado sincronamente pode travar o event loop do Node se tiver muitas inconsistências (>50) | Baixa | MVP tem ~3-5 inconsistências/mês por tenant. Se escalar, mover geração para job async com notificação quando pronto. pdfkit é eficiente para tabelas <100 linhas |
| Endpoints de lista sem filtro de `mes` retornam todos os dados históricos — pode crescer | Baixa | `mes` tem default para mês corrente. Se cliente explicitamente não passar, limitar a 3 meses. Documentar no OpenAPI spec |

---

## Etapa 21 — Pipeline de Ingestão de Documentos

### Objetivo da etapa

Especificar o fluxo técnico completo de ingestão de documentos fiscais — do recebimento do arquivo até o disparo do motor de regras — com tratamento granular de erros, limites operacionais, validações em cada estágio e estratégia de resiliência. Este pipeline é o coração do produto: se falhar aqui, nada mais funciona.

### Premissas adotadas

| # | Premissa | Justificativa |
|---|---|---|
| P1 | Três canais de entrada: (a) upload web via multipart, (b) drag & drop de arquivos soltos, (c) e-mail para notas@copilotofiscal.com | Canais definidos na Etapa 6 (Recorte do MVP). WhatsApp como canal fica para Fase 2 |
| P2 | Processamento síncrono no request HTTP. Timeout máximo de 120s. Se exceder, o request retorna erro e o batch é marcado como `FAILED` — usuário deve reenviar | Decisão de MVP (Etapa 17). Fila assíncrona só na Fase 2 |
| P3 | Limite de 200 XMLs por lote, 100MB por arquivo ZIP, 50KB por XML individual | Protege a VPS de OOM e mantém resposta <60s na CX22 (2 vCPU, 4GB RAM) |
| P4 | Deduplicação por chave de acesso (44 dígitos) + hash SHA-256 do XML. Se a mesma chave já existe no tenant, o XML é ignorado silenciosamente | Evita re-processamento. XML pode ser reenviado (ex.: carta de correção) — nesse caso a chave é a mesma e ignoramos |
| P5 | Arquivos inválidos (não-XML, XML não-NF-e, ZIP corrompido) são ignorados silenciosamente. Não interrompem o processamento dos arquivos válidos | Fernanda não pode perder um lote de 87 notas porque 1 arquivo veio corrompido |
| P6 | Falha catastrófica (banco offline, disco cheio) aborta o batch inteiro com rollback. Nenhum dado parcial é persistido | Consistência: ou todas as 87 notas entram, ou nenhuma entra |
| P7 | XMLs são armazenados em disco (`/data/xml/{tenant_id}/{YYYY-MM}/`) e referenciados no banco. `xml_raw` (JSONB) só é populado para notas que geraram inconsistência | Economia de espaço (~10% das notas têm inconsistência). JSONB é caro em disco |

### Análise

O pipeline é uma sequência linear de 7 estágios, cada um com sua própria estratégia de erro. A decisão arquitetural mais relevante é **processamento síncrono vs assíncrono**. Para o MVP com 5 tenants e 200 XMLs/lote, o benchmark esperado na CX22 é de 15-45 segundos — bem dentro do timeout de 120s. A maior latência está no parsing XML (fast-xml-parser processa ~50 XMLs/segundo em Node.js 22) e nas 8 regras determinísticas (cada regra é O(1) ou O(n) nos itens da nota).

O canal de e-mail merece atenção especial: usa o Postfix como MTA local que entrega mensagens para um script Node.js via pipe. Isso elimina dependência de serviços externos (SendGrid Inbound Parse, Mailgun Routes) e mantém o custo zero. O trade-off é que o founder precisa configurar o Postfix corretamente — documentado no runbook de operações.

A deduplicação em dois níveis (chave de acesso + hash SHA-256) resolve dois problemas distintos: (a) reenvio do mesmo XML (chave duplicada = mesma nota), (b) nota reemitida com correção (mesma chave, hash diferente — ignorada no MVP, tratada como reemissão na Fase 2).

### Decisões recomendadas

| Decisão | Conteúdo | Status |
|---|---|---|
| D1 | Pipeline síncrono de 7 estágios: Receive → Validate → Extract → Parse → Dedup → Store → Dispatch | Decisão de MVP |
| D2 | Arquivos inválidos são ignorados silenciosamente por estágio. Batch só falha se 100% dos arquivos forem inválidos ou se houver falha de infraestrutura | Decisão de UX |
| D3 | Postfix como MTA local para recebimento de e-mail. Script Node.js processa via pipe. Sem serviço externo de inbound email | Decisão de arquitetura |
| D4 | XMLs armazenados em disco + referência no banco. JSONB (`xml_raw`) só para notas com inconsistência | Decisão de storage |
| D5 | Deduplicação: (1) chave de acesso única por tenant, (2) hash SHA-256 para detectar reemissão | Decisão de integridade |
| D6 | Timeout progressivo por estágio: Receive 30s, Parse 60s, Rules 30s. Total máximo 120s | Decisão de resiliência |
| D7 | Audit log registra cada estágio do pipeline com duração, contagem e erros. Rastreabilidade completa | Decisão de auditoria |

### Entregáveis

---

#### 5.1 Diagrama de Sequência ASCII

```
Fernanda            Fastify           IngestModule      ParserModule      RuleEngine        PostgreSQL         Disk
   │                   │                   │                 │                 │                 │                 │
   │  POST /upload     │                   │                 │                 │                 │                 │
   │  (multipart)      │                   │                 │                 │                 │                 │
   │──────────────────>│                   │                 │                 │                 │                 │
   │                   │                   │                 │                 │                 │                 │
   │                   │  ESTÁGIO 1        │                 │                 │                 │                 │
   │                   │  RECEIVE          │                 │                 │                 │                 │
   │                   │──────────────────>│                 │                 │                 │                 │
   │                   │                   │                 │                 │                 │                 │
   │                   │                   │ 1. Create upload_batch           │                 │                 │
   │                   │                   │    (status=PROCESSING)           │                 │                 │
   │                   │                   │─────────────────────────────────────────────────>│                 │
   │                   │                   │                 │                 │                 │                 │
   │                   │                   │ 2. Stream multipart parts        │                 │                 │
   │                   │                   │    to temp dir                   │                 │                 │
   │                   │                   │────────────────────────────────────────────────────────────────────>│
   │                   │                   │                 │                 │                 │    /tmp/upload_ │
   │                   │                   │                 │                 │                 │    {batch_id}/  │
   │                   │                   │                 │                 │                 │                 │
   │                   │  ESTÁGIO 2        │                 │                 │                 │                 │
   │                   │  VALIDATE         │                 │                 │                 │                 │
   │                   │                   │                 │                 │                 │                 │
   │                   │                   │ for each file:                   │                 │                 │
   │                   │                   │   · extension .xml or .zip?      │                 │                 │
   │                   │                   │   · size < 100MB (ZIP) / 50KB (XML)?              │                 │
   │                   │                   │   · magic bytes match?           │                 │                 │
   │                   │                   │   · ZIP extractable?             │                 │                 │
   │                   │                   │                 │                 │                 │                 │
   │                   │                   │ invalid → ignored++, continue     │                 │                 │
   │                   │                   │                 │                 │                 │                 │
   │                   │  ESTÁGIO 3        │                 │                 │                 │                 │
   │                   │  EXTRACT          │                 │                 │                 │                 │
   │                   │                   │                 │                 │                 │                 │
   │                   │                   │ if ZIP:                          │                 │                 │
   │                   │                   │   archiver.extract()             │                 │                 │
   │                   │                   │   → /tmp/upload_{id}/extracted/  │                 │                 │
   │                   │                   │                 │                 │                 │                 │
   │                   │                   │ flat list of .xml paths          │                 │                 │
   │                   │                   │ max 200 files                    │                 │                 │
   │                   │                   │                 │                 │                 │                 │
   │                   │  ESTÁGIO 4        │                 │                 │                 │                 │
   │                   │  PARSE            │                 │                 │                 │                 │
   │                   │──────────────────>│                 │                 │                 │                 │
   │                   │                   │                 │                 │                 │                 │
   │                   │                   │ for each .xml:                   │                 │                 │
   │                   │                   │─────────────────>│                 │                 │                 │
   │                   │                   │                 │                 │                 │                 │
   │                   │                   │                 │ 1. fs.readFileSync(path)         │                 │
   │                   │                   │                 │ 2. fast-xml-parser.parse()        │                 │
   │                   │                   │                 │ 3. Validate NF-e namespace        │                 │
   │                   │                   │                 │    (xmlns:nfe)                    │                 │
   │                   │                   │                 │ 4. Extract chave_acesso           │                 │
   │                   │                   │                 │ 5. Validate modulo 11             │                 │
   │                   │                   │                 │    (dígito verificador)           │                 │
   │                   │                   │                 │ 6. Check status (cancelada?)       │                 │
   │                   │                   │                 │ 7. Extract all fields → NfeJson   │                 │
   │                   │                   │                 │ 8. Hash XML → SHA-256             │                 │
   │                   │                   │                 │                 │                 │                 │
   │                   │                   │ OK → NfeJson     │                 │                 │                 │
   │                   │                   │<─────────────────│                 │                 │                 │
   │                   │                   │                 │                 │                 │                 │
   │                   │                   │ ERR → log, ignored++, continue     │                 │                 │
   │                   │                   │                 │                 │                 │                 │
   │                   │                   │ collect all NfeJson[]              │                 │                 │
   │                   │                   │                 │                 │                 │                 │
   │                   │  ESTÁGIO 5        │                 │                 │                 │                 │
   │                   │  DEDUP            │                 │                 │                 │                 │
   │                   │                   │                 │                 │                 │                 │
   │                   │                   │ for each NfeJson:                 │                 │                 │
   │                   │                   │   SELECT 1 FROM nfe_documents      │                 │                 │
   │                   │                   │   WHERE organization_id = $1      │                 │                 │
   │                   │                   │   AND chave_acesso = $2           │                 │                 │
   │                   │                   │───────────────────────────────────>│                 │                 │
   │                   │                   │                 │                 │                 │                 │
   │                   │                   │ exists? → deduped++, continue     │                 │                 │
   │                   │                   │ new?    → proceed to store        │                 │                 │
   │                   │                   │                 │                 │                 │                 │
   │                   │  ESTÁGIO 6        │                 │                 │                 │                 │
   │                   │  STORE            │                 │                 │                 │                 │
   │                   │                   │                 │                 │                 │                 │
   │                   │                   │ BEGIN TRANSACTION                 │                 │                 │
   │                   │                   │───────────────────────────────────>│                 │                 │
   │                   │                   │                 │                 │                 │                 │
   │                   │                   │ for each new NfeJson:             │                 │                 │
   │                   │                   │   INSERT nfe_documents            │                 │                 │
   │                   │                   │   INSERT nfe_items (batch)        │                 │                 │
   │                   │                   │   INSERT audit_log                │                 │                 │
   │                   │                   │                 │                 │                 │                 │
   │                   │                   │   mv XML → /data/xml/{org}/{mês}/ │                 │                 │
   │                   │                   │────────────────────────────────────────────────────────────────────>│
   │                   │                   │                 │                 │                 │                 │
   │                   │                   │ COMMIT                           │                 │                 │
   │                   │                   │<───────────────────────────────────│                 │                 │
   │                   │                   │                 │                 │                 │                 │
   │                   │                   │ if inconsistent → xml_raw JSONB   │                 │                 │
   │                   │                   │                 │                 │                 │                 │
   │                   │  ESTÁGIO 7        │                 │                 │                 │                 │
   │                   │  DISPATCH         │                 │                 │                 │                 │
   │                   │                   │                 │                 │                 │                 │
   │                   │                   │ for each NfeJson:                 │                 │                 │
   │                   │                   │────────────────────────────────────>│                 │                 │
   │                   │                   │                 │                 │                 │                 │
   │                   │                   │                 │ run 8 rules     │                 │                 │
   │                   │                   │                 │ return Inconsistency[]           │                 │
   │                   │                   │                 │                 │                 │                 │
   │                   │                   │<────────────────────────────────────│                 │                 │
   │                   │                   │                 │                 │                 │                 │
   │                   │                   │ INSERT inconsistencies (batch)     │                 │                 │
   │                   │                   │───────────────────────────────────>│                 │                 │
   │                   │                   │                 │                 │                 │                 │
   │                   │                   │ UPDATE upload_batch                │                 │                 │
   │                   │                   │   SET status=COMPLETED,            │                 │                 │
   │                   │                   │   processed, ignored,              │                 │                 │
   │                   │                   │   inconsistencies_found,           │                 │                 │
   │                   │                   │   completed_at=now()               │                 │                 │
   │                   │                   │───────────────────────────────────>│                 │                 │
   │                   │                   │                 │                 │                 │                 │
   │                   │                   │ return batch + summary + inconsistencies[]          │                 │
   │                   │<──────────────────│                 │                 │                 │                 │
   │                   │                   │                 │                 │                 │                 │
   │  200 OK           │                   │                 │                 │                 │                 │
   │  (JSON response)  │                   │                 │                 │                 │                 │
   │<──────────────────│                   │                 │                 │                 │                 │
   │                   │                   │                 │                 │                 │                 │
   │                   │  NOTIFY (async)   │                 │                 │                 │                 │
   │                   │───────────────────────────────────────────────────────────────────────────────────────────────>
   │                   │                   │                 │                 │                 │    WhatsApp API    │
   │                   │                   │                 │                 │                 │    (W3: confirmação)│
   │                   │                   │                 │                 │                 │    (W2: alerta     │
   │                   │                   │                 │                 │                 │     se risco alto) │
```

---

#### 5.2 Estágios do Pipeline — Detalhamento

---

##### ESTÁGIO 1 — RECEIVE (ReceiveModule)

**Responsabilidade:** Receber o upload, criar o batch, mover arquivos para diretório temporário.

**Entrada:**
- `multipart/form-data` com campo `file` (arquivo único ou múltiplos)
- Headers: `Authorization`, `X-Organization-Id`

**Processamento:**

```
1. Validar Content-Type = multipart/form-data
2. Extrair organization_id do JWT + header
3. Criar upload_batch: INSERT (status=PROCESSING, source=WEB)
4. Stream das partes multipart para /tmp/upload_{batch_id}/
   - @fastify/multipart com limite de 100MB
5. Coletar paths dos arquivos recebidos
6. Registrar audit_log: UPLOAD_STARTED
```

**Tratamento de erros:**

| Erro | Comportamento |
|---|---|
| `Content-Type != multipart/form-data` | `415 Unsupported Media Type`. Aborta imediatamente |
| `Nenhum arquivo enviado` | `400 Bad Request`. Batch não é criado |
| `Arquivo > 100MB` | `413 Payload Too Large`. Fastify rejeita antes de chegar ao handler |
| `Disco cheio em /tmp` | `507 Insufficient Storage`. Batch marcado como FAILED |
| `Erro ao criar batch no banco` | `503 Service Unavailable`. Aborta — banco offline |

**Timeout deste estágio:** 30 segundos

**Saída:**
- `upload_batch.id` (UUID)
- `files: string[]` — paths absolutos em `/tmp/upload_{batch_id}/`
- `source: 'WEB' | 'EMAIL'`

---

##### ESTÁGIO 2 — VALIDATE (ValidateModule)

**Responsabilidade:** Filtrar arquivos inválidos antes de tentar parse. Arquivos inválidos são ignorados silenciosamente.

**Entrada:** `files: string[]`

**Processamento (para cada arquivo):**

```
1. Verificar extensão: .xml ou .zip?
   → Se não: ignored++, remove da lista. CONTINUE
2. Verificar tamanho: XML ≤ 50KB? ZIP ≤ 100MB?
   → Se não: ignored++, remove. CONTINUE
3. Verificar magic bytes (opcional, heurística):
   XML começa com '<?xml' ou '<' ?
   ZIP começa com 'PK\x03\x04' ?
   → Se não: ignored++, remove. CONTINUE
4. Se ZIP: testar integridade com archiver
   → Se corrompido: ignored++, remove. CONTINUE
5. Arquivo válido → mantém na lista `validFiles[]`
```

**Regra crítica:** Se após este estágio `validFiles.length === 0` e `ignored > 0`, retorna erro `400` com mensagem: "Nenhum arquivo enviado é uma nota fiscal válida. Os {ignored} arquivos enviados não puderam ser processados."

**Timeout:** 5 segundos

**Saída:** `validFiles: string[]`

---

##### ESTÁGIO 3 — EXTRACT (ExtractModule)

**Responsabilidade:** Extrair XMLs de arquivos ZIP. Arquivos .xml passam direto.

**Entrada:** `validFiles: string[]`

**Processamento:**

```
1. Criar diretório: /tmp/upload_{batch_id}/extracted/
2. Para cada arquivo em validFiles:
   a. Se extensão .xml:
      → copiar para extracted/ (symlink ou hardlink)
      → count++
   b. Se extensão .zip:
      → archiver.open(path)
      → para cada entry no ZIP:
         → se entry.name termina com .xml:
            → extrair para extracted/{entry.name}
            → count++
         → se não: ignored++
      → se ZIP corrompido ou vazio: ignored++
3. Se count > 200: erro 422 "Lote excede 200 notas. Divida em envios menores."
4. Se count === 0: erro 400 (mesmo tratamento do estágio 2)
```

**Timeout:** 10 segundos

**Saída:** `xmlFiles: string[]` — paths para cada XML individual em `extracted/`

---

##### ESTÁGIO 4 — PARSE (ParserModule)

**Responsabilidade:** Converter XML → JSON estruturado, extrair campos fiscais, validar schema NF-e.

**Entrada:** `xmlFiles: string[]`

**Parser config (fast-xml-parser):**

```typescript
const parserOptions = {
  ignoreAttributes: false,
  attributeNamePrefix: '@_',
  isArray: (name: string) => ['det', 'obsCont', 'refNF'].includes(name),
  numberParseOptions: { leadingZeros: false, hex: false },
  removeNSPrefix: true,
};
```

**Processamento (para cada XML):**

```
1. fs.readFileSync(path, 'utf-8') → rawXml: string
2. SHA-256 do rawXml → xmlHash: string
3. fast-xml-parser.parse(rawXml, parserOptions) → parsed: object
4. Validar namespace NF-e:
   → parsed.NFe?.infNFe?.ide?
   → Se não: NFE_INVALID_NAMESPACE. ignored++, CONTINUE

5. Extrair chave_acesso = parsed.NFe.@_Id?.replace('NFe', '')
   → Se ausente ou length != 44: NFE_MISSING_KEY. ignored++, CONTINUE

6. Validar dígito verificador (módulo 11):
   → algoritmo padrão SPED
   → Se inválido: NFE_INVALID_CHECK_DIGIT. ignored++, CONTINUE

7. Verificar status da NF-e:
   → cStat = parsed.NFe.infNFe.ide.cStat (ou protocolo)
   → 100 = autorizada → OK
   → 101 = cancelada → NFE_CANCELED. ignored++, CONTINUE
   → 110 = denegada → NFE_DENIED. ignored++, CONTINUE
   → outro → NFE_UNKNOWN_STATUS. ignorada, CONTINUE

8. Extrair campos estruturados → NfeJson:
   {
     chave_acesso, numero, serie, modelo, data_emissao,
     cnpj_emitente, nome_emitente, uf_emitente,
     cnpj_destinatario, valor_total, valor_produtos,
     valor_ipi, valor_icms, base_calculo_icms, aliquota_icms,
     cfop, ncm_principal, cst_pis, cst_cofins, cst_icms,
     icms_st, icms_st_valor, status_nfe: 'ATIVA',
     items: [{ numero_item, codigo_produto, descricao, ncm,
               cfop, quantidade, unidade, valor_unitario,
               valor_total, valor_frete, cst_pis, cst_cofins,
               cst_icms, aliquota_icms, valor_icms, icms_st,
               icms_st_valor }],
     xml_hash, raw_xml_path: path
   }

9. Registrar métricas: parse_time_ms, field_count
10. Coletar em parsedDocuments: NfeJson[]
```

**Tratamento de erros:**

| Erro | Código interno | Comportamento |
|---|---|---|
| XML malformado (sintaxe) | `XML_SYNTAX_ERROR` | ignored++. CONTINUE |
| Namespace NF-e ausente | `NFE_INVALID_NAMESPACE` | ignored++. CONTINUE |
| Chave de acesso ausente/inválida | `NFE_MISSING_KEY` | ignored++. CONTINUE |
| Dígito verificador inválido | `NFE_INVALID_CHECK_DIGIT` | Log de warning. ignored++. CONTINUE (possível NF-e falsa) |
| Nota cancelada | `NFE_CANCELED` | ignored++. CONTINUE |
| Nota denegada | `NFE_DENIED` | ignored++. CONTINUE |
| Campo obrigatório ausente (valor_total, cnpj_emitente) | `NFE_MISSING_FIELD` | ignored++. CONTINUE |
| Tempo de parse > 5s por XML | `PARSE_TIMEOUT` | ignored++. CONTINUE. Alerta no log |
| Erro de I/O (arquivo não encontrado) | `IO_ERROR` | ignored++. CONTINUE |

**Timeout:** 60 segundos (para todos os XMLs somados)

**Saída:** `parsedDocuments: NfeJson[]` (apenas notas válidas e ativas)

---

##### ESTÁGIO 5 — DEDUP (DedupModule)

**Responsabilidade:** Evitar processamento duplicado da mesma nota fiscal.

**Entrada:** `parsedDocuments: NfeJson[]`

**Processamento:**

```
1. Extrair todas as chaves_acesso dos parsedDocuments
2. Consulta em lote:
   SELECT chave_acesso FROM nfe_documents
   WHERE organization_id = $1
   AND chave_acesso = ANY($2::varchar[])
3. Para cada NfeJson:
   a. Se chave_acesso existe no resultado → deduped. CONTINUE
   b. Se não existe → adicionar a newDocuments[]
4. Log: "Dedup: {parsed} analisadas, {deduped} já existentes, {new} novas"
```

**Nota sobre reemissão:** Se uma nota é reemitida com correção (mesma chave, XML diferente), o hash SHA-256 será diferente mas a chave é a mesma. No MVP, ignoramos (a nota original já foi processada). Na Fase 2, podemos detectar hash diferente e oferecer "esta nota foi reemitida — deseja reprocessar?".

**Timeout:** 2 segundos

**Saída:** `newDocuments: NfeJson[]`

---

##### ESTÁGIO 6 — STORE (StoreModule)

**Responsabilidade:** Persistir documentos no banco e arquivos em disco. Tudo em uma transação.

**Entrada:** `newDocuments: NfeJson[]`, `upload_batch_id: UUID`

**Processamento:**

```
1. BEGIN TRANSACTION

2. Para cada doc em newDocuments:
   a. Mover XML do /tmp para storage permanente:
      destino = /data/xml/{organization_id}/{YYYY-MM}/{chave_acesso}.xml
      fs.renameSync(tempPath, destino)

   b. INSERT INTO nfe_documents (
        organization_id, upload_batch_id,
        chave_acesso, numero, serie, modelo,
        data_emissao, data_entrada_saida,
        cnpj_emitente, nome_emitente, uf_emitente,
        cnpj_destinatario, valor_total, valor_produtos,
        valor_ipi, valor_icms, base_calculo_icms,
        aliquota_icms, cfop, ncm_principal,
        cst_pis, cst_cofins, cst_icms,
        icms_st, icms_st_valor,
        status_nfe, xml_hash, source
      ) VALUES (...)

   c. Para cada item em doc.items:
      INSERT INTO nfe_items (...)

   d. INSERT INTO audit_log (
        organization_id, user_id,
        event_type='NFE_PROCESSED',
        entity_type='nfe_documents',
        entity_id=<nfe_document.id>,
        details={ chave_acesso, xml_hash, parse_time_ms }
      )

3. Se todas as notas foram inseridas com sucesso:
   COMMIT
   → armazenar xml_raw (JSONB) apenas para docs com inconsistência
   → liberar /tmp/upload_{batch_id}/

4. Se qualquer erro:
   ROLLBACK
   → batch.status = 'FAILED'
   → batch.error_message = detalhes
   → liberar /tmp/
```

**Por que transação única para todas as notas?** Se 87 notas são enviadas e o banco cai na nota #44, não queremos 43 notas órfãs no banco (sem batch, sem relação). Rollback garante que o usuário possa reenviar o ZIP inteiro sem duplicação parcial.

**Timeout:** 10 segundos

**Saída:** `storedDocuments: Array<{ nfeDocumentId: UUID, nfeJson: NfeJson }>`

---

##### ESTÁGIO 7 — DISPATCH (DispatchModule)

**Responsabilidade:** Disparar o motor de regras para cada nota nova e persistir inconsistências.

**Entrada:** `storedDocuments[]`

**Processamento:**

```
1. Para cada doc em storedDocuments:
   a. Executar RuleEngine.evaluate(doc.nfeJson)
      → retorna Inconsistency[] (0 a 8 regras violadas)
   b. Para cada inconsistency:
      → classificar por score (OK, ATENCAO, RISCO_ALTO)
      → gerar explanation_text (template)
      → gerar checklist_json (template por rule_id)
      → INSERT INTO inconsistencies (...)
      → INSERT INTO audit_log (INCONSISTENCY_DETECTED)
   c. Se inconsistency.classification != 'OK':
      → UPDATE nfe_documents SET xml_raw = doc.nfeJson (JSONB)
   d. Se inconsistency.score >= 70:
      → INSERT INTO pending_notifications (W2: alerta risco alto)

2. Contar totais: ok_count, atencao_count, risco_alto_count

3. UPDATE upload_batches:
   SET status = 'COMPLETED',
       processed = {total validos},
       ignored = {ignorados em todos os estágios},
       inconsistencies_found = {total inconsistências},
       completed_at = now()
   WHERE id = $1

4. INSERT pending_notifications:
   → W3 (confirmação upload) para o usuário que fez upload
   → W2 (alerta risco alto) para admin se score >= 70

5. Retornar resposta ao cliente (JSON com batch + summary + inconsistencies[])
```

**Timeout:** 30 segundos

**Saída:** Resposta HTTP 200 (conforme contrato `POST /api/v1/upload` da Etapa 20)

---

#### 5.3 Tratamento de Erros — Matriz Completa

| Estágio | Código | Tipo | Severidade | Ação | Audit Log |
|---|---|---|---|---|---|
| 1. Receive | `NO_FILE` | Cliente | Error | `400` — aborta batch | `UPLOAD_FAILED` |
| 1. Receive | `DISK_FULL` | Infra | Critical | `507` — aborta batch | `UPLOAD_FAILED` |
| 1. Receive | `DB_UNAVAILABLE` | Infra | Critical | `503` — aborta batch | — (não há batch) |
| 2. Validate | `INVALID_EXT` | Dado | Info | ignored++, CONTINUE | — |
| 2. Validate | `FILE_TOO_LARGE` | Dado | Info | ignored++, CONTINUE | — |
| 2. Validate | `ZIP_CORRUPTED` | Dado | Warning | ignored++, CONTINUE | `FILE_REJECTED` |
| 3. Extract | `ZIP_EMPTY` | Dado | Info | ignored++, CONTINUE | — |
| 3. Extract | `LIMIT_EXCEEDED` | Cliente | Error | `422` — aborta batch | `UPLOAD_FAILED` |
| 4. Parse | `XML_SYNTAX_ERROR` | Dado | Warning | ignored++, CONTINUE | `FILE_REJECTED` |
| 4. Parse | `NFE_INVALID_NAMESPACE` | Dado | Info | ignored++, CONTINUE | — |
| 4. Parse | `NFE_MISSING_KEY` | Dado | Warning | ignored++, CONTINUE | — |
| 4. Parse | `NFE_INVALID_CHECK_DIGIT` | Dado | Warning | ignored++, CONTINUE | `FILE_REJECTED` |
| 4. Parse | `NFE_CANCELED` | Regra | Info | ignored++, CONTINUE | — |
| 4. Parse | `NFE_DENIED` | Regra | Info | ignored++, CONTINUE | — |
| 4. Parse | `NFE_MISSING_FIELD` | Dado | Warning | ignored++, CONTINUE | `FILE_REJECTED` |
| 4. Parse | `PARSE_TIMEOUT` | Infra | Warning | ignored++, CONTINUE | `FILE_REJECTED` |
| 6. Store | `DB_TRANSACTION_FAIL` | Infra | Critical | ROLLBACK, batch=FAILED | `UPLOAD_FAILED` |
| 6. Store | `DISK_WRITE_FAIL` | Infra | Critical | ROLLBACK, batch=FAILED | `UPLOAD_FAILED` |
| 7. Dispatch | `RULE_ENGINE_ERROR` | Sistema | Error | batch=PARTIAL_ERROR, inconsistências parciais persistidas | `UPLOAD_FAILED` |

---

#### 5.4 Fluxo do Canal E-mail

```
Fornecedor → E-mail (notas@copilotofiscal.com)
              │
              ▼
         Postfix (MTA)
              │
              │ pipe via /etc/aliases:
              │ notas: "| node /app/email-receiver.js"
              ▼
         email-receiver.js
              │
              │ 1. Parse stdin → email (mailparser)
              │ 2. Validar remetente (pertence ao tenant?)
              │    → Match: from_address vs users.email
              │    → Se não: descartar silenciosamente
              │ 3. Extrair anexos .xml
              │ 4. Salvar em /tmp/email_{uuid}/
              │ 5. Chamar POST /api/v1/upload internamente
              │    (com X-Organization-Id do remetente)
              │ 6. Responder e-mail (E1: confirmação)
              ▼
         Pipeline normal (estágios 1-7)
```

**Configuração Postfix (`/etc/aliases`):**
```
notas: "| /usr/bin/node /app/packages/api/dist/email-receiver.js"
```

---

#### 5.5 Estrutura de Diretórios de Storage

```
/data/xml/
├── 019018a0-5c3f-.../          # organization_id
│   ├── 2026-05/
│   │   ├── 35210512345678000190550010000035211000003521.xml
│   │   ├── 35210512345678000190550010000035221000003522.xml
│   │   └── ...
│   └── 2026-06/
│       └── ...
├── 019018b0-6d4e-.../          # outro tenant
│   └── 2026-05/
│       └── ...
```

**Política de retenção (cronjob semanal):**
```bash
# Mover XMLs > 90 dias para S3 e remover do disco
find /data/xml -type f -mtime +90 -name "*.xml" \
  | while read f; do
      aws s3 mv "$f" "s3://fiscopilot-backups/xml/${f#/data/xml/}"
    done
```

---

#### 5.6 Métricas do Pipeline (audit_log)

Cada execução registra:

```json
{
  "event_type": "UPLOAD_COMPLETED",
  "entity_type": "upload_batches",
  "entity_id": "019018a0-9f2d-...",
  "details": {
    "source": "WEB",
    "stages": {
      "receive":   { "duration_ms": 450,   "files": 1 },
      "validate":  { "duration_ms": 120,   "valid": 87, "ignored": 0 },
      "extract":   { "duration_ms": 2300,  "xmls": 87,  "ignored": 0 },
      "parse":     { "duration_ms": 18500, "parsed": 87, "ignored": 0, "canceled": 0 },
      "dedup":     { "duration_ms": 80,    "new": 87,   "duplicated": 0 },
      "store":     { "duration_ms": 3200,  "docs": 87,  "items": 870 },
      "dispatch":  { "duration_ms": 4200,  "ok": 84,    "atencao": 1, "risco_alto": 2 }
    },
    "total_duration_ms": 28850,
    "total_files": 87,
    "total_processed": 87,
    "total_ignored": 0,
    "inconsistencies_found": 3
  }
}
```

---

### Riscos e pontos de atenção

| Risco | Severidade | Mitigação |
|---|---|---|
| Postfix mal configurado pode não entregar e-mails para o pipe | Alta | Documentar runbook completo de configuração Postfix. Testar com e-mail real antes do beta. Ter fallback: upload manual via web se e-mail falhar |
| Transação única para 87 notas pode causar lock contention se outro tenant fizer upload simultâneo | Baixa | 5 tenants, uploads esporádicos. Row-level locks são por chave_acesso (índice único), não bloqueiam todo o batch. Se escalar, chunk transações em lotes de 20 |
| `archiver` com ZIP malicioso (zip bomb) pode consumir toda RAM | Média | Limite de 200 XMLs por ZIP mitiga zip bombs. `archiver` faz streaming — não carrega ZIP inteiro em memória. Adicionar limite de 1000 entries por ZIP |
| fast-xml-parser com XML muito aninhado (>50 níveis) pode estourar stack | Baixa | NF-e tem profundidade máxima conhecida (~8 níveis). Se encontrar profundidade >20, rejeitar como suspeito |
| Limpeza de `/tmp/upload_{id}/` pode falhar e acumular arquivos | Baixa | Bloco `finally` sempre executa `fs.rmSync(tmpDir, { recursive: true })`. Cronjob diário: `find /tmp -name 'upload_*' -mtime +1 -delete` |
| XMLs com encoding diferente de UTF-8 (ISO-8859-1, Windows-1252) podem falhar no parse | Média | `fast-xml-parser` detecta encoding do header XML. Fallback: `iconv-lite` para converter encoding se detecção falhar. Testar com XMLs de ERPs legados (SAP emite ISO-8859-1) |
| `email-receiver.js` como pipe do Postfix precisa de tratamento de timeout (e-mail muito grande) | Média | Timeout de 30s no stdin. Se e-mail >10MB, rejeitar com resposta automática: "Anexos muito grandes. Envie os XMLs pelo app." |

---

## Etapa 22 — Motor de Regras

### Objetivo da etapa

Definir a arquitetura, implementação e operação do Rule Engine — o componente que executa as 8 regras determinísticas sobre cada NF-e processada, atribui scores, classifica risco e gera explicações. Cada regra deve ser isolada, testável, auditável e independente de IA generativa.

### Premissas adotadas

| # | Premissa | Justificativa |
|---|---|---|
| P1 | Regras são 100% determinísticas — mesma entrada sempre produz mesma saída. IA generativa não participa do diagnóstico | Decisão da Etapa 1 (D5) e Etapa 6: diagnóstico é determinístico; IA só parafraseia explicação |
| P2 | Cada regra é uma classe ou função pura que implementa a interface `FiscalRule`. Regras são stateless | Testabilidade isolada; adicionar nova regra = criar novo arquivo, sem alterar engine |
| P3 | Regras operam contra `NfeJson` (saída do ParserModule da Etapa 21) + tabelas de referência carregadas em memória no boot | Evita queries ao banco durante avaliação; latência <1ms por regra |
| P4 | Score é um inteiro 0-100. Classification é derivada deterministicamente: 0-30 = OK, 31-69 = ATENCAO, 70-100 = RISCO_ALTO | Consistente com o schema da Etapa 19 (constraint CK_inconsistencies_classification) |
| P5 | Tabelas de referência fiscal (CFOP, NCM, alíquotas ICMS, ST) são carregadas do PostgreSQL (`fiscal_reference_tables`) no startup e cacheadas em memória com TTL de 24h | Evita latência de rede durante avaliação. Refresh diário captura atualizações semestrais |
| P6 | Cada regra tem um `field_path` que aponta para o campo exato no XML original (formato XPath-like). Facilita debug e auditoria | Rastreabilidade: "este CFOP veio do campo NFe.infNFe.det.0.prod.CFOP do XML" |
| P7 | Regras que dependem de dados externos (R4: CNPJ na Receita) têm fallback offline e são marcadas como `NOT_VERIFIED` se a fonte estiver indisponível | Resiliência: o motor nunca quebra por falha externa |

### Análise

O padrão escolhido é **Strategy + Chain of Responsibility híbrido**: cada regra é uma Strategy (interface comum, implementação independente), e o Engine as executa em cadeia sequencial. Isso é preferível a um sistema de rules engine declarativo (JSON Logic, JEXL) porque as regras fiscais brasileiras têm lógica de validação complexa que não se expressa bem em DSL.

O score de cada regra é atribuído por **impacto fiscal estimado**, não por complexidade da detecção:

| Score | Significado | Exemplo |
|---|---|---|
| 100 | Risco de multa ou fraude | Chave de acesso inválida (NF-e pode ser falsa), CNPJ suspenso/baixado |
| 85-95 | Imposto pago a maior com valor significativo | CFOP de saída em nota de entrada (contamina DAS) |
| 60-80 | Imposto potencialmente errado | Alíquota de ICMS divergente, ICMS ST indevido |
| 40-55 | Inconsistência que merece conferência | NCM suspeito para o setor, CST incompatível |
| 10-30 | Divergência leve, provável erro de digitação | Valor total vs soma dos itens com diferença pequena |

O motor gera **explanation_text** por template: cada regra tem um template com placeholders preenchidos com os dados reais da nota. Na Fase 2, a IA pode parafrasear esses templates para linguagem ainda mais natural — mas o texto base é sempre determinístico.

### Decisões recomendadas

| Decisão | Conteúdo | Status |
|---|---|---|
| D1 | Padrão Strategy: cada regra implementa `interface FiscalRule { evaluate(nfe: NfeJson): RuleResult | null }`. Engine itera sobre array de regras registradas | Decisão de arquitetura |
| D2 | Scores fixos por regra, não dinâmicos. R1=85, R2=70, R3=50, R4=100, R5=60-90, R6=50, R7=100, R8=75 | Decisão de produto |
| D3 | Tabelas fiscais cacheadas em memória (Map/Record). Refresh a cada 24h com `setInterval`. Fallback: manter última versão válida | Decisão de performance |
| D4 | `estimated_impact` é calculado como percentual do valor da nota quando aplicável (ex.: diferença de alíquota × base de cálculo). Se não calculável, `null` | Decisão de UX |
| D5 | Regras que não puderam ser avaliadas (ex.: campo ausente no XML) retornam `null` (não geram inconsistência), não `score=0` | Decisão semântica: "não verificado" ≠ "OK" |
| D6 | Explicação templateada em português claro, seguindo microcopy da Etapa 16. Placeholders: `{found}`, `{expected}`, `{impact}`, `{field}`, `{nfe_numero}`, `{emitente}` | Decisão de UX writing |
| D7 | Checklist gerado por regra (template de ações). R1 tem 4 passos, R5 tem 3. Armazenado como JSONB em `inconsistencies.checklist_json` | Decisão de dados |

### Entregáveis

---

#### 5.1 Arquitetura do Rule Engine

```
┌──────────────────────────────────────────────────────────┐
│                     RuleEngine                            │
│                                                           │
│  evaluateAll(nfe: NfeJson): RuleResult[]                  │
│                                                           │
│  ┌─────────────────────────────────────────────────┐    │
│  │ registeredRules: FiscalRule[]                    │    │
│  │                                                  │    │
│  │  [R7_Chave, R4_CNPJ, R1_CFOP, R2_ICMS,         │    │
│  │   R8_ST, R6_CST, R5_Valor, R3_NCM]              │    │
│  └─────────────────────────────────────────────────┘    │
│                         │                                 │
│                         │ for each rule                    │
│                         ▼                                 │
│  ┌─────────────────────────────────────────────────┐    │
│  │ FiscalRule.evaluate(nfe: NfeJson): RuleResult?   │    │
│  │                                                  │    │
│  │  1. Pre-check: campos necessários presentes?     │    │
│  │     → não: return null (não verificado)           │    │
│  │  2. Validate: lógica determinística da regra      │    │
│  │     → passou: return null (sem inconsistência)    │    │
│  │     → falhou: return RuleResult                   │    │
│  │  3. Build RuleResult:                             │    │
│  │     · rule_id, score, classification              │    │
│  │     · field_path, found_value, expected_value      │    │
│  │     · estimated_impact                            │    │
│  │     · explanation_text (template)                  │    │
│  │     · checklist_json (template)                    │    │
│  └─────────────────────────────────────────────────┘    │
│                         │                                 │
│                         ▼                                 │
│  ┌─────────────────────────────────────────────────┐    │
│  │ RuleResult[] filtrado (null removido)             │    │
│  │                                                   │    │
│  │ Ordenado por score decrescente (mais grave 1º)    │    │
│  │ Score final da nota = max(scores)                 │    │
│  └─────────────────────────────────────────────────┘    │
│                                                           │
│  ┌─────────────────────────────────────────────────┐    │
│  │ FiscalReferenceCache                             │    │
│  │                                                  │    │
│  │  cfopTable: Map<cfop, CfopEntry>                 │    │
│  │  ncmSet: Set<ncm_material_construcao>            │    │
│  │  aliquotaTable: Map<uf_origem_uf_destino, pct>   │    │
│  │  stTable: Map<uf, Set<ncm>>                      │    │
│  │  cnpjCache: Map<cnpj, {situacao, data}>          │    │
│  │                                                  │    │
│  │  refresh(): carrega do PostgreSQL a cada 24h     │    │
│  └─────────────────────────────────────────────────┘    │
└──────────────────────────────────────────────────────────┘
```

---

#### 5.2 Interface e Tipos

```typescript
// apps/api/src/modules/rules/types.ts

export interface NfeJson {
  chave_acesso: string;
  numero: number;
  serie: number;
  modelo: string;
  data_emissao: string;
  cnpj_emitente: string;
  nome_emitente: string;
  uf_emitente: string;
  cnpj_destinatario: string;
  uf_destinatario: string;
  valor_total: number;
  valor_produtos: number;
  valor_ipi: number;
  valor_icms: number;
  base_calculo_icms: number;
  aliquota_icms: number;
  cfop: string | null;
  ncm_principal: string | null;
  cst_pis: string | null;
  cst_cofins: string | null;
  cst_icms: string | null;
  icms_st: boolean;
  icms_st_valor: number;
  items: NfeItemJson[];
  regime: 'SIMPLES_NACIONAL' | 'LUCRO_PRESUMIDO' | 'LUCRO_REAL';
  uf_estabelecimento: string;
}

export interface RuleResult {
  rule_id: string;
  score: number;
  classification: 'OK' | 'ATENCAO' | 'RISCO_ALTO';
  field_path: string;
  found_value: string;
  expected_value: string | null;
  estimated_impact: number | null;
  explanation_text: string;
  checklist_json: ChecklistItem[];
}

export interface FiscalRule {
  readonly id: string;
  readonly name: string;
  evaluate(nfe: NfeJson): RuleResult | null;
}

export interface CfopEntry {
  cfop: string;
  descricao: string;
  tipo: 'ENTRADA' | 'SAIDA';
  aplicacao: string;
  valido_simples: boolean;
}
```

---

#### 5.3 Implementação da Engine

```typescript
// apps/api/src/modules/rules/RuleEngine.ts

export class RuleEngine {
  private rules: FiscalRule[];

  constructor(rules: FiscalRule[]) {
    this.rules = rules;
  }

  evaluateAll(nfe: NfeJson): RuleResult[] {
    const results: RuleResult[] = [];

    for (const rule of this.rules) {
      try {
        const result = rule.evaluate(nfe);
        if (result !== null && result.score > 0) {
          results.push(result);
        }
      } catch (error) {
        console.error(`[RuleEngine] Erro na regra ${rule.id}:`, error);
      }
    }

    results.sort((a, b) => b.score - a.score);
    return results;
  }
}

// Factory
export function createRuleEngine(cache: FiscalReferenceCache): RuleEngine {
  const rules: FiscalRule[] = [
    new R7_ChaveAcessoValidator(),
    new R4_CNPJSituacaoRule(cache),
    new R1_CFOPDivergenceRule(cache),
    new R2_ICMSAliquotaRule(cache),
    new R8_ICMSSTRule(cache),
    new R6_CSTSimplesRule(),
    new R5_ValorDivergenceRule(),
    new R3_NCMSetorRule(cache),
  ];
  return new RuleEngine(rules);
}
```

---

#### 5.4 Especificação das 8 Regras

---

##### R1 — CFOP Divergente

| Dimensão | Valor |
|---|---|
| **ID** | `R1` |
| **Nome** | Validador de CFOP para Simples Nacional |
| **Score base** | 85 |
| **Campo verificado** | `NFe.infNFe.det.{i}.prod.CFOP` |
| **Condição de disparo** | CFOP presente no XML e regime = SIMPLES_NACIONAL |
| **Dados de referência** | `fiscal_reference_tables` → tabela CFOP |

**Algoritmo:**

```
1. Se regime != 'SIMPLES_NACIONAL': return null
2. Se nfe.cfop == null: return null (não verificado)
3. Buscar cfopEntry = cfopTable.get(nfe.cfop)
4. Se cfopEntry não encontrado:
     return RuleResult { score: 90, classification: 'RISCO_ALTO',
       explanation_text: 'O CFOP {found} não consta na tabela oficial.' }
5. Se cfopEntry.tipo === 'SAIDA':
     expectedCfop = encontrarCfopEntradaEquivalente(nfe.cfop, nfe.uf_emitente, nfe.uf_destinatario)
     estimatedImpact = nfe.valor_total * 0.05
     return RuleResult { score: 85, classification: 'RISCO_ALTO',
       found_value: `${nfe.cfop} (${cfopEntry.descricao}) – SAÍDA`,
       expected_value: `${expectedCfop} – ENTRADA`,
       estimated_impact: estimatedImpact,
       explanation_text: `O código da operação fiscal (CFOP) encontrado foi ${nfe.cfop} (${cfopEntry.descricao}), que é um código de saída (venda). Para uma compra no Simples Nacional, o esperado é ${expectedCfop} (entrada). Isso pode gerar imposto a mais de aproximadamente R$ ${estimatedImpact.toFixed(2)} na DAS deste mês.` }
6. Se cfopEntry.valido_simples === false:
     return RuleResult { score: 70, classification: 'ATENCAO' }
7. return null (OK)
```

**Checklist R1:**

```json
[
  { "order": 1, "text": "Ligue para {nome_emitente} — {telefone}", "done": false },
  { "order": 2, "text": "Peça uma carta de correção com CFOP {cfop_esperado}", "done": false },
  { "order": 3, "text": "Peça para reemitir a nota fiscal com o código correto", "done": false },
  { "order": 4, "text": "Avise {contador} sobre essa correção", "done": false }
]
```

---

##### R2 — Alíquota ICMS Divergente

| Dimensão | Valor |
|---|---|
| **ID** | `R2` |
| **Nome** | Validador de Alíquota ICMS Interestadual |
| **Score base** | 70 |
| **Campo verificado** | `NFe.infNFe.total.ICMSTot.pICMS` |
| **Condição de disparo** | Alíquota informada diverge da tabela oficial |

**Algoritmo:**

```
1. Se nfe.uf_emitente === nfe.uf_destinatario:
     // Operação interna (não interestadual)
     aliquota_esperada = aliquota_interna_uf.get(nfe.uf_destinatario) ?? 18.0
2. Senão:
     aliquota_esperada = aliquotaTable.get(`${nfe.uf_emitente}_${nfe.uf_destinatario}`)
3. Se aliquota_esperada == null: return null
4. Se nfe.aliquota_icms == null: return null
5. Se Math.abs(nfe.aliquota_icms - aliquota_esperada) <= 1.0: return null (tolerância 1pp)
6. diferenca = (nfe.aliquota_icms - aliquota_esperada) / 100
   estimatedImpact = Math.abs((nfe.base_calculo_icms || nfe.valor_total) * diferenca)
   return RuleResult { score: 70, classification: 'RISCO_ALTO',
     found_value: `${nfe.aliquota_icms}%`,
     expected_value: `${aliquota_esperada}%`,
     estimated_impact: estimatedImpact }
```

**Checklist R2:**

```json
[
  { "order": 1, "text": "Confira a alíquota de ICMS para este produto no seu estado ({UF})", "done": false },
  { "order": 2, "text": "Ligue para {fornecedor} e peça para corrigir a alíquota na nota", "done": false },
  { "order": 3, "text": "Solicite nota fiscal corrigida com alíquota de {aliquota_esperada}%", "done": false },
  { "order": 4, "text": "Avise {contador} sobre a divergência", "done": false }
]
```

---

##### R3 — NCM Suspeito para o Setor

| Dimensão | Valor |
|---|---|
| **ID** | `R3` |
| **Nome** | Validador de NCM para Material de Construção |
| **Score base** | 50 |
| **Campo verificado** | `NFe.infNFe.det.{i}.prod.NCM` |
| **Condição de disparo** | NCM presente em qualquer item da nota |

**Algoritmo:**

```
1. Para cada item em nfe.items onde item.ncm != null:
2.   capitulo = item.ncm.substring(0, 2)
3.   capitulos_materiais = ['25','39','40','44','68','69','70','72','73','76','83','94']
4.   Se capitulos_materiais.includes(capitulo): CONTINUE (OK)
5.   Se não:
       return RuleResult { score: 50, classification: 'ATENCAO',
         found_value: `${item.ncm} (${item.descricao}) – Capítulo ${capitulo}`,
         expected_value: 'NCM típico de material de construção (capítulos 25, 39, 68-73, 76, 83, 94)',
         estimated_impact: null,
         explanation_text: `O produto "${item.descricao}" está classificado no NCM ${item.ncm}, que não é comum para lojas de material de construção. Pode ser um erro de classificação fiscal do fornecedor.` }
6. return null (todos os NCMs OK)
```

**Checklist R3:**

```json
[
  { "order": 1, "text": "Confira se o NCM {ncm_encontrado} está correto para {produto}", "done": false },
  { "order": 2, "text": "Consulte a tabela NCM no site da Receita Federal", "done": false },
  { "order": 3, "text": "Peça para {fornecedor} corrigir a classificação fiscal do produto", "done": false },
  { "order": 4, "text": "Se tiver dúvida, confirme com {contador} antes de agir", "done": false }
]
```

---

##### R4 — CNPJ do Emitente Irregular

| Dimensão | Valor |
|---|---|
| **ID** | `R4` |
| **Nome** | Verificador de Situação Cadastral do CNPJ |
| **Score base** | 100 (baixado/nulo) / 80 (suspenso) |
| **Campo verificado** | `NFe.infNFe.emit.CNPJ` |
| **Condição de disparo** | Sempre (toda NF-e tem CNPJ emitente) |

**Algoritmo:**

```
1. situacao = cnpjCache.get(nfe.cnpj_emitente)
2. Se situacao == null: return null (não verificado — cache não contém este CNPJ)
3. Se situacao.status === 'ATIVA': return null (OK)
4. Se situacao.status === 'SUSPENSA':
     return RuleResult { score: 80, classification: 'RISCO_ALTO',
       found_value: `${nfe.cnpj_emitente} – ${situacao.status}`,
       expected_value: 'CNPJ ATIVO',
       estimated_impact: nfe.valor_total }
5. Se situacao.status IN ('BAIXADO', 'INAPTO', 'NULO'):
     return RuleResult { score: 100, classification: 'RISCO_ALTO',
       explanation_text: `URGENTE: O CNPJ do fornecedor ${nfe.nome_emitente} está ${situacao.status}. Esta nota fiscal pode ser considerada inidônea pelo fisco.` }
```

**Fonte no MVP:** Arquivo público de CNPJs da Receita Federal, importado via seed script. Atualização mensal. API online fica para Fase 2.

**Checklist R4:**

```json
[
  { "order": 1, "text": "URGENTE: Não utilize esta nota para crédito até confirmar", "done": false },
  { "order": 2, "text": "Consulte a situação do CNPJ no site da Receita Federal", "done": false },
  { "order": 3, "text": "Entre em contato com {fornecedor} e exija nota de CNPJ ativo", "done": false },
  { "order": 4, "text": "Avise {contador} imediatamente sobre esta situação", "done": false }
]
```

---

##### R5 — Valor Total vs Soma dos Itens

| Dimensão | Valor |
|---|---|
| **ID** | `R5` |
| **Nome** | Validador de Valor Total da Nota |
| **Score base** | 60 (<5% div) / 90 (≥5% div) |
| **Campo verificado** | `NFe.infNFe.total.ICMSTot.vNF` vs soma `det.{i}.prod.vProd` |
| **Condição de disparo** | Sempre |

**Algoritmo:**

```
1. somaItens = nfe.items.reduce((s, i) => s + i.valor_total, 0)
2. diferenca = Math.abs(nfe.valor_total - somaItens)
3. Se diferenca <= 0.05: return null (tolerância de arredondamento)
4. percentual = (diferenca / nfe.valor_total) * 100
5. score = percentual > 5 ? 90 : 60
   classification = score >= 70 ? 'RISCO_ALTO' : 'ATENCAO'
   return RuleResult { score, classification,
     found_value: `R$ ${nfe.valor_total.toFixed(2)} (total da nota)`,
     expected_value: `R$ ${somaItens.toFixed(2)} (soma dos ${nfe.items.length} itens)`,
     estimated_impact: diferenca }
```

**Checklist R5:**

```json
[
  { "order": 1, "text": "Confira o valor total com o pedido de compra original", "done": false },
  { "order": 2, "text": "Ligue para {fornecedor} e informe a diferença de R$ {diferenca}", "done": false },
  { "order": 3, "text": "Peça carta de correção ou nota complementar", "done": false }
]
```

---

##### R6 — CST Incompatível com Simples Nacional

| Dimensão | Valor |
|---|---|
| **ID** | `R6` |
| **Nome** | Validador de CST PIS/COFINS para Simples Nacional |
| **Score base** | 50 |
| **Campo verificado** | `NFe.infNFe.det.{i}.imposto.PIS.PISAliq.CST` |
| **Condição de disparo** | Regime = SIMPLES_NACIONAL e CST presente |

**Algoritmo:**

```
1. Se regime != 'SIMPLES_NACIONAL': return null
2. Se nfe.cst_pis == null && nfe.cst_cofins == null: return null
3. CSTs reservados/inválidos na legislação: ['00','03','10','11','12','13','14','15','16','17','18','19','20','21','22','23','24','25','26','27','28','29','30','31','32','33','34','35','36','37','38','39','40','41','42','43','44','45','46','47','48','80','81','82','83','84','85','86','87','88','89']
4. Se cstInvalido.includes(nfe.cst_pis) || cstInvalido.includes(nfe.cst_cofins):
     return RuleResult { score: 50, classification: 'ATENCAO',
       found_value: `PIS: ${nfe.cst_pis}, COFINS: ${nfe.cst_cofins}`,
       expected_value: 'CST compatível com o regime do emitente',
       estimated_impact: null }
5. return null
```

**Checklist R6:**

```json
[
  { "order": 1, "text": "Confira o CST de PIS/COFINS com seu contador", "done": false },
  { "order": 2, "text": "Verifique se o fornecedor emitiu com o CST correto para o seu regime", "done": false }
]
```

---

##### R7 — Chave de Acesso Inválida

| Dimensão | Valor |
|---|---|
| **ID** | `R7` |
| **Nome** | Validador de Dígito Verificador da Chave NF-e |
| **Score base** | 100 |
| **Campo verificado** | `NFe.infNFe.@_Id` |
| **Condição de disparo** | Sempre |

**Algoritmo (módulo 11 — padrão SPED):**

```
1. chave = nfe.chave_acesso // 44 dígitos
2. dv_informado = parseInt(chave[43])
3. pesos = [4,3,2,9,8,7,6,5,4,3,2,9,8,7,6,5,4,3,2,9,8,7,6,5,4,3,2,9,8,7,6,5,4,3,2,9,8,7,6,5,4,3,2]
4. soma = 0
   for i = 0..42: soma += parseInt(chave[i]) * pesos[i]
5. resto = soma % 11
   dv_calculado = (resto === 0 || resto === 1) ? 0 : 11 - resto
6. Se dv_calculado !== dv_informado:
     return RuleResult { score: 100, classification: 'RISCO_ALTO',
       found_value: `DV informado: ${dv_informado}`,
       expected_value: `DV calculado: ${dv_calculado}`,
       estimated_impact: nfe.valor_total,
       explanation_text: `URGENTE: O dígito verificador da chave de acesso não confere. A nota fiscal pode ser falsa ou conter erro de digitação. NÃO utilize para crédito sem verificar a autenticidade no portal da Sefaz.` }
7. return null
```

**Checklist R7:**

```json
[
  { "order": 1, "text": "URGENTE: Confira a chave de acesso no portal da Sefaz", "done": false },
  { "order": 2, "text": "Se a chave estiver errada, peça para o fornecedor reemitir a nota", "done": false },
  { "order": 3, "text": "Se a nota não existir na Sefaz, pode ser falsa — avise seu contador IMEDIATAMENTE", "done": false }
]
```

---

##### R8 — ICMS ST Indevido

| Dimensão | Valor |
|---|---|
| **ID** | `R8` |
| **Nome** | Validador de ICMS Substituição Tributária |
| **Score base** | 75 |
| **Campo verificado** | `NFe.infNFe.det.{i}.imposto.ICMS.ICMSST` |
| **Condição de disparo** | `icms_st === true` em qualquer item |

**Algoritmo:**

```
1. Se !nfe.icms_st: return null
2. Para cada item onde icms_st === true:
3.   stList = stTable.get(nfe.uf_destinatario)
4.   Se stList == null: return null (não temos lista de ST para essa UF)
5.   Se stList.has(item.ncm): CONTINUE (OK, NCM está na lista)
6.   Se não:
       return RuleResult { score: 75, classification: 'RISCO_ALTO',
         found_value: `ST destacada para NCM ${item.ncm} em ${nfe.uf_destinatario}`,
         expected_value: `NCM ${item.ncm} NÃO consta na lista de ST do estado`,
         estimated_impact: item.icms_st_valor,
         explanation_text: `O item "${item.descricao}" (NCM ${item.ncm}) tem ICMS-ST destacado, mas este NCM não está na lista de Substituição Tributária do estado ${nfe.uf_destinatario}. O fornecedor pode ter recolhido ST indevidamente.` }
7. return null
```

**Checklist R8:**

```json
[
  { "order": 1, "text": "Confira se este produto realmente está sujeito a ST no seu estado", "done": false },
  { "order": 2, "text": "Ligue para {fornecedor} e questione o destaque de ST", "done": false },
  { "order": 3, "text": "Solicite nota corrigida sem ST, se for o caso", "done": false }
]
```

---

#### 5.5 Cache de Referências Fiscais

```typescript
// apps/api/src/modules/rules/FiscalReferenceCache.ts

export class FiscalReferenceCache {
  private cfopTable: Map<string, CfopEntry> = new Map();
  private ncmMateriaisSet: Set<string> = new Set();
  private aliquotaTable: Map<string, number> = new Map();
  private stTable: Map<string, Set<string>> = new Map();
  private cnpjCache: Map<string, CnpjStatus> = new Map();
  private lastRefresh: Date | null = null;

  constructor(private db: PostgresJsDatabase) {}

  async refresh(): Promise<void> {
    const refs = await this.db
      .select()
      .from(fiscalReferenceTables)
      .where(eq(fiscalReferenceTables.isActive, true));

    for (const ref of refs) {
      switch (ref.tableName) {
        case 'cfop':           this.loadCfop(ref.data); break;
        case 'ncm_materiais':  this.loadNcm(ref.data); break;
        case 'aliquotas_icms': this.loadAliquotas(ref.data); break;
        case 'st_estados':     this.loadST(ref.data); break;
      }
    }
    this.lastRefresh = new Date();
  }

  startAutoRefresh(): void {
    setInterval(() => this.refresh(), 24 * 60 * 60 * 1000);
  }

  getCfop(cfop: string): CfopEntry | undefined { return this.cfopTable.get(cfop); }
  getAliquota(origem: string, destino: string): number | undefined { return this.aliquotaTable.get(`${origem}_${destino}`); }
  isNcmMaterialConstrucao(ncm: string): boolean { return this.ncmMateriaisSet.has(ncm.substring(0, 2)); }
  isNcmSujeitoST(uf: string, ncm: string): boolean { return this.stTable.get(uf)?.has(ncm) ?? false; }
  getCnpjStatus(cnpj: string): CnpjStatus | undefined { return this.cnpjCache.get(cnpj); }
}
```

---

#### 5.6 Exemplo de Execução Completa

**Entrada: NF-e #3521 da Distribuidora CimentoBom**

```typescript
const nfe: NfeJson = {
  chave_acesso: "35210512345678000190550010000035211000003521",
  numero: 3521, cnpj_emitente: "12345678000190",
  nome_emitente: "Distribuidora CimentoBom",
  uf_emitente: "SP", uf_destinatario: "SP",
  valor_total: 8400.00, base_calculo_icms: 8400.00, aliquota_icms: 18.0,
  cfop: "6102", ncm_principal: "25232900",
  cst_pis: "49", cst_cofins: "49",
  icms_st: true, icms_st_valor: 420.00,
  items: [{ ncm: "25232900", descricao: "Cimento CP-II 50kg", cfop: "6102", valor_total: 8400, icms_st: true, icms_st_valor: 420 }],
  regime: "SIMPLES_NACIONAL", uf_estabelecimento: "SP"
};

const engine = createRuleEngine(cache);
const results = engine.evaluateAll(nfe);
```

**Saída (3 inconsistências detectadas):**

```
[
  { rule_id: "R1", score: 85, classification: "RISCO_ALTO",
    found_value: "6102 (Venda) – SAÍDA", expected_value: "1102 – ENTRADA",
    estimated_impact: 412.00 },
  { rule_id: "R8", score: 75, classification: "RISCO_ALTO",
    found_value: "ST para NCM 25232900 em SP",
    expected_value: "NCM não consta na lista de ST/SP",
    estimated_impact: 420.00 },
  { rule_id: "R2", score: 70, classification: "RISCO_ALTO",
    found_value: "18%", expected_value: "12% (alíquota interna SP)",
    estimated_impact: 504.00 }
]
```

**Score final da nota:** `max(85, 75, 70) = 85` → **RISCO_ALTO**

---

### Resumo das 8 Regras

| ID | Nome | Score | Classificação | Dependência externa | Impacto estimável |
|---|---|---|---|---|---|
| R1 | CFOP Divergente | 85 | RISCO_ALTO | Tabela CFOP | Sim (% DAS) |
| R2 | Alíquota ICMS | 70 | RISCO_ALTO | Tabela alíquotas | Sim (base × dif) |
| R3 | NCM Suspeito | 50 | ATENCAO | Lista NCMs setor | Não |
| R4 | CNPJ Irregular | 80-100 | RISCO_ALTO | Cache CNPJ | Sim (total nota) |
| R5 | Valor Divergente | 60-90 | ATENCAO/RISCO_ALTO | Nenhuma | Sim (diferença) |
| R6 | CST Incompatível | 50 | ATENCAO | Nenhuma | Não |
| R7 | Chave Inválida | 100 | RISCO_ALTO | Nenhuma | Sim (total nota) |
| R8 | ICMS ST Indevido | 75 | RISCO_ALTO | Lista ST por UF | Sim (ST destacado) |

---

### Riscos e pontos de atenção

| Risco | Severidade | Mitigação |
|---|---|---|
| Tabelas fiscais desatualizadas geram falsos positivos (ex.: CFOP novo não está na tabela, NCM entrou na lista de ST) | Alta | Versionamento semestral. Script de atualização documentado. Regra com `valido_simples: false` para entradas desconhecidas gera ATENCAO, não RISCO_ALTO |
| Falso positivo em R1: fornecedor emitente é do Lucro Real e usou CFOP de saída corretamente — mas o destinatário é Simples | Média | R1 avalia o CFOP da nota recebida. Se emitente é Lucro Real, CFOP 6102 está correto para ele. Documentado no disclaimer: "Confirme com seu contador" |
| Score fixo não captura nuances (ex.: CFOP errado em nota de R$ 50 vs R$ 50.000) | Média | `estimated_impact` captura a diferença de valor. Scores dinâmicos entram na Fase 2 |
| Regras R2 e R8 dependem de `uf_destinatario` que pode não estar explícito no XML | Baixa | Extrair UF do CNPJ destinatário (dígitos 1-2) como fallback. Se CNPJ destinatário = CNPJ da loja, usar `organization.uf` |
| Cache de 24h para tabelas fiscais significa que atualização emergencial demora 1 dia | Baixa | MVP não tem requisito de tempo real. Endpoint interno `POST /api/v1/admin/refresh-cache` para forçar refresh manual |
| R4 depende de cache CNPJ que pode estar vazio no primeiro deploy | Média | Seed script popula cache com CNPJs problemáticos conhecidos. Cache vazio → R4 retorna `null` (não verificado), não `score=0` |

---

## Etapa 23 — Camada de IA

### Objetivo da etapa

Definir com precisão onde, como e sob quais condições a IA generativa é utilizada no FiscoPilot MVP — exclusivamente como camada de paráfrase de explicações determinísticas, nunca como motor de diagnóstico fiscal. A IA é um acessório opcional: se offline, o produto continua 100% funcional com templates determinísticos.

### Premissas adotadas

| # | Premissa | Justificativa |
|---|---|---|
| P1 | IA generativa NUNCA toma decisão fiscal. Diagnóstico, score, classificação e checklist são 100% determinísticos (Etapa 22) | Risco regulatório: orientação fiscal por máquina não habilitada (CRC) pode gerar responsabilidade legal |
| P2 | IA atua exclusivamente como "tradutor fiscal → português natural". Entrada: `explanation_text` determinístico. Saída: paráfrase em linguagem mais coloquial | O template já é compreensível; a IA apenas melhora a fluência para o Roberto |
| P3 | Modelo: GPT-4o-mini via OpenRouter. Fallback: Claude 3.5 Haiku (mesmo provider). Timeout: 5 segundos. Se timeout ou erro → fallback para texto determinístico | OpenRouter elimina lock-in de fornecedor. GPT-4o-mini tem a melhor relação custo × qualidade para português |
| P4 | Toda saída da IA é auditável: prompt enviado, resposta bruta e texto final são armazenados em `inconsistencies.explanation_llm` e `audit_log` | Rastreabilidade completa. Se a IA alucinar, o diagnóstico-base permanece correto e rastreável |
| P5 | IA é opcional no MVP. Feature flag `ENABLE_LLM_PARAPHRASE` controla ativação. Default: `false` nos primeiros 30 dias de beta | Permite validar qualidade das paráfrases antes de expor aos usuários |
| P6 | Usuário sempre vê que o texto foi gerado por IA. Badge "🤖 Gerado por IA" + disclaimer inline: "Confirme com seu contador" | Transparência total. Construção de confiança, não de ilusão |

### Análise

**Por que a IA é apenas paráfrase, não diagnóstico:**

O diagnóstico fiscal brasileiro tem consequências legais. Se o produto disser "você deve pagar R$ 412 a menos de imposto" e isso estiver errado, a responsabilidade é do produto. Se o produto disser "o CFOP 6102 é de saída, mas em compras no Simples o esperado é 1102 — isso pode impactar sua DAS em ~R$ 412", a responsabilidade é compartilhada com o contador que valida. A diferença é sutil na interface, mas profunda na regulamentação.

A IA no MVP atua em um único ponto do pipeline:

```
RuleEngine (determinístico)
  │
  ├── explanation_text (template preenchido)  ← SEMPRE gerado
  │
  └── [OPCIONAL] LLM.paraphrase(explanation_text)
        │
        ├── Sucesso → explanation_llm (mais natural)
        │
        └── Falha/Timeout → fallback para explanation_text
```

**Trade-offs da abordagem:**

| Trade-off | Decisão | Justificativa |
|---|---|---|
| Modelo mais barato vs melhor português | GPT-4o-mini (~US$ 0,15/1M tokens input) | Claude Haiku é comparável em custo. Ambos têm excelente português. GPT-4o-mini vence em seguir instruções de formato |
| Chamada síncrona vs assíncrona | Síncrona (bloqueia resposta do upload até 5s) | No upload, o usuário já espera ~30s de processamento. +5s é aceitável. No dashboard, a explicação já está cacheada |
| Paráfrase no upload vs lazy (sob demanda) | No upload (eager) | Gera a paráfrase uma vez e armazena. Dashboard e detalhes leem do banco sem chamar LLM de novo |
| Streaming vs resposta completa | Resposta completa (não-streaming) | Textos têm ~150-300 caracteres. Streaming adicionaria complexidade sem ganho perceptível |

### Decisões recomendadas

| Decisão | Conteúdo | Status |
|---|---|---|
| D1 | IA usada exclusivamente para paráfrase de `explanation_text` em linguagem natural. Escopo: 1 chamada por inconsistência detectada no upload | Decisão de MVP |
| D2 | Modelo primário: `openai/gpt-4o-mini` via OpenRouter. Fallback: `anthropic/claude-3.5-haiku`. Timeout: 5s | Decisão técnica |
| D3 | Parâmetros fixos: `temperature=0.3`, `max_tokens=200`, `top_p=0.9`. Sem variação criativa | Decisão técnica |
| D4 | Feature flag `ENABLE_LLM_PARAPHRASE=false` no beta. Ativar após 30 dias se qualidade validada | Decisão de rollout |
| D5 | Badge + disclaimer em toda tela que exibe texto gerado por IA | Decisão de compliance |
| D6 | Prompt auditado: armazenar prompt + resposta bruta + texto final no `audit_log` e `explanation_llm` | Decisão de auditoria |

### Entregáveis

---

#### 5.1 Arquitetura da Camada de IA

```
┌──────────────────────────────────────────────────────────────┐
│                    ExplainModule                              │
│                                                               │
│  generateExplanation(result: RuleResult): string              │
│                                                               │
│  1. explanation_text = fillTemplate(result)  ← determinístico │
│  2. Se ENABLE_LLM_PARAPHRASE === true:                       │
│       │                                                       │
│       ▼                                                       │
│  ┌─────────────────────────────────────────────────────┐     │
│  │              LlmParaphraser                          │     │
│  │                                                      │     │
│  │  paraphrase(text: string, context: LlmContext):      │     │
│  │    string | null                                     │     │
│  │                                                      │     │
│  │  1. Construir prompt (system + user)                 │     │
│  │  2. Chamar OpenRouter com timeout 5s                 │     │
│  │  3. Extrair resposta (apenas paráfrase)              │     │
│  │  4. Validar: resposta tem sentido? tamanho ok?       │     │
│  │     → Sim: retornar resposta                        │     │
│  │     → Não: retornar null (fallback)                  │     │
│  │  5. Armazenar audit_log (prompt, raw_response)       │     │
│  └─────────────────────────────────────────────────────┘     │
│       │                                                       │
│       │ Sucesso → explanation_llm = resposta                  │
│       │ Falha   → explanation_llm = null                      │
│       │          → UI exibe explanation_text (template)       │
│       ▼                                                       │
│  3. Retornar melhor explicação disponível                     │
└──────────────────────────────────────────────────────────────┘
```

---

#### 5.2 Prompt Templates

##### System Prompt (imutável)

```
Você é um tradutor fiscal especializado em explicar conceitos tributários
brasileiros para donos de pequenas empresas que não têm conhecimento técnico.

REGRAS ABSOLUTAS:
1. NUNCA altere o significado fiscal do texto original.
2. NUNCA adicione informações que não estão no texto original.
3. NUNCA recomende ações diferentes das listadas no checklist original.
4. NUNCA use siglas sem explicá-las na primeira ocorrência.
5. Use linguagem simples, frases curtas (máximo 20 palavras).
6. Dirija-se ao usuário como "você".
7. Mantenha um tom calmo, profissional e nada alarmista.
8. Substitua termos técnicos por explicações em português claro.
9. Se o texto original já estiver claro, apenas o retorne com pequenas
   melhorias de fluência.
10. NUNCA sugira que o contador está errado. Use "confirme com seu contador".

Formato de resposta: APENAS o texto parafraseado, sem introduções,
sem "Aqui está a explicação:", sem aspas, sem markdown.
```

##### User Prompt (preenchido dinamicamente)

```
Explique o seguinte problema fiscal em linguagem simples para o dono
de uma loja de material de construção que não entende de impostos:

TEXTO ORIGINAL:
{explanation_text}

CONTEXTO:
- Nota fiscal #{nfe_numero} do fornecedor {nome_emitente}
- Valor da nota: R$ {valor_total}
- Tipo de problema: {rule_name} ({rule_id})
- Impacto financeiro estimado: {estimated_impact}

Paráfrase:
```

**Exemplo de prompt montado (R1 — CFOP divergente, nota #3521):**

```
Explique o seguinte problema fiscal em linguagem simples para o dono
de uma loja de material de construção que não entende de impostos:

TEXTO ORIGINAL:
O código da operação fiscal (CFOP) encontrado foi 6102 (Venda de produção
do estabelecimento), que é um código de saída (venda). Para uma compra no
Simples Nacional, o esperado é 1102 (Compra para comercialização) (entrada).
Isso pode gerar imposto a mais de aproximadamente R$ 412,00 na DAS deste mês.

CONTEXTO:
- Nota fiscal #3521 do fornecedor Distribuidora CimentoBom
- Valor da nota: R$ 8.400,00
- Tipo de problema: CFOP Divergente (R1)
- Impacto financeiro estimado: ~R$ 412,00

Paráfrase:
```

**Resposta esperada da IA:**

```
A nota #3521 da Distribuidora CimentoBom veio com um código fiscal de venda
(CFOP 6102), mas como você está comprando, o código deveria ser de compra
(CFOP 1102). Na prática, isso significa que o cálculo do seu imposto mensal
(a DAS) pode sair cerca de R$ 412 mais caro se não for corrigido. O fornecedor
precisa emitir uma carta de correção ou reemitir a nota com o código certo.
Confirme com seu contador antes de agir.
```

---

#### 5.3 Implementação do LlmParaphraser

```typescript
// apps/api/src/modules/explain/LlmParaphraser.ts

interface LlmContext {
  nfeNumero: number;
  nomeEmitente: string;
  valorTotal: string;
  ruleName: string;
  ruleId: string;
  estimatedImpact: string | null;
}

interface ParaphraseResult {
  text: string;
  model: string;
  latencyMs: number;
  promptTokens: number;
  completionTokens: number;
}

export class LlmParaphraser {
  private enabled: boolean;
  private timeout: number;

  constructor(
    private openRouterClient: OpenRouterClient,
    config: { enabled: boolean; timeout: number }
  ) {
    this.enabled = config.enabled;
    this.timeout = config.timeout;
  }

  async paraphrase(
    explanationText: string,
    context: LlmContext
  ): Promise<ParaphraseResult | null> {
    if (!this.enabled) return null;

    const userPrompt = this.buildUserPrompt(explanationText, context);

    try {
      const start = Date.now();

      const response = await this.openRouterClient.createChatCompletion({
        model: 'openai/gpt-4o-mini',
        messages: [
          { role: 'system', content: SYSTEM_PROMPT },
          { role: 'user', content: userPrompt },
        ],
        temperature: 0.3,
        max_tokens: 200,
        top_p: 0.9,
      }, {
        timeout: this.timeout,
        maxRetries: 1,
        fallbackModel: 'anthropic/claude-3.5-haiku',
      });

      const rawText = response.choices[0]?.message?.content?.trim();

      if (!rawText || rawText.length < 20) {
        console.warn('[LLM] Resposta vazia ou muito curta');
        return null;
      }

      if (this.containsSystemLeak(rawText)) {
        console.warn('[LLM] Possível vazamento de system prompt');
        return null;
      }

      const latencyMs = Date.now() - start;

      return {
        text: rawText,
        model: response.model,
        latencyMs,
        promptTokens: response.usage?.prompt_tokens ?? 0,
        completionTokens: response.usage?.completion_tokens ?? 0,
      };
    } catch (error) {
      console.error('[LLM] Falha na paráfrase:', error);
      return null;  // Fallback silencioso para template
    }
  }

  private buildUserPrompt(text: string, ctx: LlmContext): string {
    return [
      'Explique o seguinte problema fiscal em linguagem simples para o dono',
      'de uma loja de material de construção que não entende de impostos:',
      '',
      'TEXTO ORIGINAL:',
      text,
      '',
      'CONTEXTO:',
      `- Nota fiscal #${ctx.nfeNumero} do fornecedor ${ctx.nomeEmitente}`,
      `- Valor da nota: R$ ${ctx.valorTotal}`,
      `- Tipo de problema: ${ctx.ruleName} (${ctx.ruleId})`,
      `- Impacto financeiro estimado: ${ctx.estimatedImpact ?? 'não calculado'}`,
      '',
      'Paráfrase:',
    ].join('\n');
  }

  private containsSystemLeak(text: string): boolean {
    const leakPatterns = [
      'Você é um tradutor fiscal',
      'system prompt',
      'REGRAS ABSOLUTAS',
    ];
    return leakPatterns.some(p => text.includes(p));
  }
}
```

---

#### 5.4 Integração com o Pipeline (Estágio 7 do DispatchModule)

```typescript
// No DispatchModule (estágio 7 do pipeline — Etapa 21)

for (const result of ruleResults) {
  // 1. Sempre gera explanation_text determinístico
  result.explanation_text = templateEngine.fill(result);

  // 2. Opcional: paráfrase com IA
  const paraphrase = await llmParaphraser.paraphrase(
    result.explanation_text,
    {
      nfeNumero: nfe.numero,
      nomeEmitente: nfe.nome_emitente,
      valorTotal: nfe.valor_total.toFixed(2),
      ruleName: ruleRegistry.get(result.rule_id)?.name ?? result.rule_id,
      ruleId: result.rule_id,
      estimatedImpact: result.estimated_impact?.toFixed(2) ?? null,
    }
  );

  // 3. Persistir inconsistência
  await db.insert(inconsistencies).values({
    ...result,
    explanation_text: result.explanation_text,
    explanation_llm: paraphrase?.text ?? null,
    checklist_json: result.checklist_json,
  });

  // 4. Auditoria da chamada IA (se ocorreu)
  if (paraphrase) {
    await db.insert(auditLog).values({
      organization_id: orgId,
      event_type: 'LLM_PARAPHRASE_GENERATED',
      entity_type: 'inconsistencies',
      entity_id: inconsistencyId,
      details: {
        model: paraphrase.model,
        latency_ms: paraphrase.latencyMs,
        prompt_tokens: paraphrase.promptTokens,
        completion_tokens: paraphrase.completionTokens,
        rule_id: result.rule_id,
        text_length: paraphrase.text.length,
      },
    });
  }
}
```

---

#### 5.5 Comportamento na Interface (UI)

**Quando `explanation_llm` existe (IA funcionou):**

```
┌──────────────────────────────────────────┐
│  🔴 RISCO ALTO · Score 85                │
│                                          │
│  A nota #3521 da Distribuidora           │
│  CimentoBom veio com um código fiscal    │
│  de venda (CFOP 6102), mas como você     │
│  está comprando, o código deveria ser    │
│  de compra (CFOP 1102). Na prática,      │
│  isso significa que o cálculo do seu     │
│  imposto mensal (a DAS) pode sair        │
│  cerca de R$ 412 mais caro se não for    │
│  corrigido.                              │
│                                          │
│  🤖 Texto gerado por IA                  │
│  ⓘ Confirme com seu contador            │
│                                          │
│  [Ver explicação técnica →]  ← toggle   │
│  [O que fazer? →]                        │
└──────────────────────────────────────────┘
```

**Quando `explanation_llm` é null (fallback — template determinístico):**

```
┌──────────────────────────────────────────┐
│  🔴 RISCO ALTO · Score 85                │
│                                          │
│  O código da operação fiscal (CFOP)      │
│  encontrado foi 6102 (Venda de produção  │
│  do estabelecimento), que é um código    │
│  de saída (venda). Para uma compra no    │
│  Simples Nacional, o esperado é 1102     │
│  (Compra para comercialização) (entrada).│
│  Isso pode gerar imposto a mais de       │
│  aproximadamente R$ 412,00 na DAS.       │
│                                          │
│  ⓘ Confirme com seu contador            │
│                                          │
│  [O que fazer? →]                        │
└──────────────────────────────────────────┘
```

**Toggle "Ver explicação técnica":** Permite ao usuário comparar a versão da IA com o texto determinístico original. Gera confiança: se a IA falou bobagem, o texto técnico está logo ali.

---

#### 5.6 Política de Timeout e Retry

```
┌─────────────────────────────────────────┐
│         Estratégia de Resiliência        │
│                                          │
│  Tentativa 1: GPT-4o-mini               │
│    Timeout: 5 segundos                   │
│    │                                     │
│    ├── Sucesso → retorna paráfrase      │
│    │                                     │
│    └── Falha/Timeout → Tentativa 2      │
│         │                                │
│         ├── Fallback: Claude 3.5 Haiku  │
│         │   Timeout: 5 segundos          │
│         │   │                            │
│         │   ├── Sucesso → retorna       │
│         │   │                            │
│         │   └── Falha → return null     │
│         │         (usa template)         │
│         │                                │
│         └── Circuit Breaker:             │
│             Se 5 falhas consecutivas     │
│             em 1 minuto →                │
│             DESABILITAR LLM por 5 min    │
│             (evita custo de retry        │
│              infinito)                   │
└─────────────────────────────────────────┘
```

**Circuit Breaker simplificado:**

```typescript
class LlmCircuitBreaker {
  private failures = 0;
  private lastFailureTime = 0;
  private disabled = false;
  private disabledUntil = 0;

  shouldAttempt(): boolean {
    if (this.disabled && Date.now() < this.disabledUntil) return false;
    if (this.disabled && Date.now() >= this.disabledUntil) {
      this.disabled = false;
      this.failures = 0;
    }
    return true;
  }

  recordFailure(): void {
    const now = Date.now();
    if (now - this.lastFailureTime > 60000) this.failures = 0;
    this.failures++;
    this.lastFailureTime = now;
    if (this.failures >= 5) {
      this.disabled = true;
      this.disabledUntil = now + 300000; // 5 min
    }
  }
}
```

---

#### 5.7 Métricas e Custos

| Métrica | Estimativa (5 tenants, ~25 inconsistências/mês) |
|---|---|
| Chamadas LLM/mês | ~25 (1 por inconsistência detectada) |
| Tokens de prompt por chamada | ~350 (system) + ~250 (user) = ~600 |
| Tokens de completion por chamada | ~100-150 |
| Custo GPT-4o-mini | US$ 0,15/1M input + US$ 0,60/1M output |
| Custo por chamada | ~US$ 0,00018 |
| Custo mensal estimado | **~US$ 0,005 (~R$ 0,03)** |
| Latência P95 (Brasil → OpenRouter) | ~2-3 segundos |

**Conclusão de custo:** O custo da IA é desprezível no MVP. A maior preocupação é latência, não custo. Se a latência for consistentemente >5s, o circuit breaker desabilita a IA e o produto continua funcionando com templates.

---

### Riscos e pontos de atenção

| Risco | Severidade | Mitigação |
|---|---|---|
| IA alucinar e gerar explicação fiscal incorreta (ex.: inverter CFOP de entrada com saída) | Alta | `explanation_text` determinístico é a fonte de verdade. UI mostra badge "gerado por IA" + toggle para ver original. Disclaimer em toda tela |
| OpenRouter ter latência >5s do Brasil, fazendo toda chamada cair em timeout | Média | Circuit breaker automático. Após 5 falhas, LLM desabilitado por 5 min. Produto 100% funcional sem IA |
| Custo da IA escalar com crescimento de tenants (Fase 2: 100 tenants × 50 inconsistências = 5.000 chamadas/mês) | Baixa | A R$ 0,03/mês atual, 5.000 chamadas = R$ 3/mês. Mesmo na Fase 2, custo é irrelevante |
| System prompt pode ser extraído por prompt injection no `explanation_text` | Baixa | `explanation_text` é gerado pelo servidor a partir de dados validados, nunca de input direto. Sanitização de caracteres especiais |
| Usuário confundir texto da IA com orientação contábil oficial e tomar decisão baseada nela | Média | Badge visível em toda tela. Disclaimer duplo. Treinamento no onboarding: "Esta é uma sugestão automática" |
| Resposta da IA em formato errado (markdown, listas, emojis) quebrando layout da UI | Baixa | Pós-processamento: strip markdown, remover emojis, truncar em 300 caracteres. Prompt instrui "APENAS o texto parafraseado" |

---

## Etapa 24 — Prompting Interno do Produto

### Objetivo da etapa

Definir todos os templates de texto gerados pelo sistema que não envolvem IA generativa — explicações do Rule Engine, mensagens de sistema, estados de UI, notificações push, e-mails transacionais e respostas automáticas. Separar com clareza o que é template determinístico (substituição de variáveis) do que é prompt de IA generativa (Etapa 23), garantindo que o produto funcione integralmente mesmo com a IA desligada.

### Premissas adotadas

| # | Premissa | Justificativa |
|---|---|---|
| P1 | Templates determinísticos são a espinha dorsal da comunicação do produto. IA é apenas camada opcional de paráfrase | Se a IA falhar, o produto continua 100% funcional |
| P2 | Todo template usa sintaxe `{variavel}` para substituição. Nenhum template contém lógica condicional complexa (ifs, loops) — isso fica no código | Templates são dados, não código. Facilita tradução futura e revisão por não-programadores |
| P3 | Templates de explicação fiscal (Etapa 22 — R1 a R8) são versionados junto com as regras. Alterar regra = alterar template | Rastreabilidade: auditor pode ver exatamente qual template gerou qual explicação |
| P4 | Templates de notificação (WhatsApp, e-mail) seguem os limites da Etapa 16: WhatsApp ≤ 4096 caracteres, e-mail texto puro | Consistência com microcopy e canal |
| P5 | Templates são armazenados em arquivos `.ts` como constantes exportadas, não em banco de dados | Simplicidade: sem migração de template, sem cache de template. Deploy = atualização de template |

### Análise

O FiscoPilot tem 4 categorias de templates determinísticos:

1. **Explicações de regras** (11 templates, R1-R8): preenchidos pelo Rule Engine com dados da nota e da inconsistência. São a fonte de verdade para o texto que o Roberto lê.
2. **Estados de UI** (~45 mensagens): mensagens de vazio, loading, erro, sucesso para cada tela (T1-T9). Já definidos na Etapa 16 (Microcopy), aqui consolidados como templates programáticos.
3. **Notificações** (6 templates WhatsApp + 3 templates e-mail): mensagens transacionais com placeholders para dados dinâmicos. Já definidos na Etapa 16, aqui formalizados como constantes.
4. **Respostas automáticas** (3 templates): mensagens enviadas pelo sistema sem interação do usuário.

A diferença fundamental entre template determinístico e prompt de IA:

| Dimensão | Template Determinístico (Etapa 24) | Prompt de IA (Etapa 23) |
|---|---|---|
| Quem gera o texto | Código (substituição de variáveis) | LLM (GPT-4o-mini) |
| Previsibilidade | 100% — mesma entrada = mesma saída | <100% — modelo pode variar redação |
| Latência | <1ms | 2-5 segundos |
| Custo | Zero | ~US$ 0,00018 por chamada |
| Fallback | Não precisa (é o fallback) | Template determinístico é o fallback |
| Uso no produto | Sempre ativo | Feature flag `ENABLE_LLM_PARAPHRASE` |

### Decisões recomendadas

| Decisão | Conteúdo | Status |
|---|---|---|
| D1 | Templates organizados em 4 arquivos: `rule-explanations.ts`, `ui-states.ts`, `notifications.ts`, `auto-responses.ts` | Decisão de organização |
| D2 | Templates de regras usam função `fillExplanationTemplate(templateKey, vars)` que substitui `{var}` e escapa HTML | Decisão de implementação |
| D3 | Templates de UI são consumidos pelo front-end como constantes TypeScript importadas diretamente (sem API) no MVP | Decisão de simplicidade |
| D4 | Templates de notificação são referenciados por `template_name` no campo `pending_notifications.template_name` | Decisão de rastreabilidade |
| D5 | Versionamento: cada template tem `@version` e `@last_updated` como comentário JSDoc | Decisão de manutenção |

### Entregáveis

---

#### 5.1 Templates de Explicação das Regras (Rule Engine)

Arquivo: `apps/api/src/modules/rules/templates/rule-explanations.ts`

```typescript
/**
 * Templates de explicação para cada regra (R1-R8).
 * Preenchidos pelo Rule Engine com dados da inconsistência.
 * @version 1.0.0
 * @last_updated 2026-05-28
 */

export const RULE_EXPLANATIONS: Record<string, string> = {

  R1_CFOP_SAIDA: [
    'O código da operação fiscal (CFOP) encontrado foi {found_value},',
    'que é um código de saída (venda). Para uma compra no Simples Nacional,',
    'o esperado é {expected_value} (entrada). Isso pode gerar imposto a mais',
    'de aproximadamente {estimated_impact} na DAS deste mês.',
  ].join(' '),

  R1_CFOP_INEXISTENTE: [
    'O CFOP {found_value} não consta na tabela oficial de códigos fiscais.',
    'Isso pode ser um erro de digitação do fornecedor ou um código inválido.',
    'Verifique com o fornecedor {nome_emitente} qual o CFOP correto para esta operação.',
  ].join(' '),

  R1_CFOP_SIMPLES_INVALIDO: [
    'O CFOP {found_value} é um código de entrada, mas não é válido para',
    'empresas do Simples Nacional. Verifique se esta operação está corretamente',
    'classificada ou se o fornecedor deveria ter usado outro código.',
  ].join(' '),

  R2_ALIQUOTA_DIVERGENTE: [
    'A alíquota de ICMS na nota é {found_value}, mas para esta operação',
    'o esperado é {expected_value}. A diferença pode gerar recolhimento',
    'incorreto de aproximadamente {estimated_impact}.',
  ].join(' '),

  R3_NCM_SUSPEITO: [
    'O produto está classificado no NCM {found_value}, que não é comum',
    'para lojas de material de construção. O esperado para o seu setor',
    'seria {expected_value}. Isso pode indicar um erro de classificação',
    'fiscal do fornecedor. O impacto financeiro não é possível estimar',
    'automaticamente.',
  ].join(' '),

  R4_CNPJ_SUSPENSO: [
    'O CNPJ do fornecedor {nome_emitente} ({cnpj_emitente}) está',
    '{found_value} na Receita Federal. Esta nota pode não ser aceita',
    'pelo fisco. O valor total da nota ({valor_total}) está em risco.',
  ].join(' '),

  R4_CNPJ_INATIVO: [
    'URGENTE: O CNPJ do fornecedor {nome_emitente} ({cnpj_emitente})',
    'está {found_value}. Esta nota fiscal pode ser considerada inidônea',
    'pelo fisco. Não utilize para crédito sem confirmar com seu contador.',
    'Valor total em risco: {valor_total}.',
  ].join(' '),

  R5_VALOR_DIVERGENTE: [
    'O valor total da nota é {found_value}, mas a soma dos itens é',
    '{expected_value}. Diferença de {estimated_impact}. Isso pode',
    'indicar erro de digitação, item faltando na nota ou valor de',
    'frete/seguro não detalhado.',
  ].join(' '),

  R6_CST_INCOMPATIVEL: [
    'O CST de PIS/COFINS informado ({found_value}) é incomum para',
    'operações destinadas a empresas do Simples Nacional. O esperado',
    'seria um CST compatível com o regime ({expected_value}). Isso não',
    'necessariamente está errado, mas merece conferência com o contador.',
  ].join(' '),

  R7_CHAVE_INVALIDA: [
    'URGENTE: O dígito verificador da chave de acesso não confere.',
    'Encontrado: {found_value}. Calculado: {expected_value}.',
    'Isso significa que a chave pode ter sido digitada errada ou a',
    'nota fiscal pode ser falsa. NÃO utilize esta nota para crédito',
    'sem verificar a autenticidade no portal da Sefaz.',
  ].join(' '),

  R8_ST_INDEVIDO: [
    'Foi destacado ICMS-ST de {estimated_impact} nesta nota, mas o',
    'produto ({found_value}) não consta na lista de Substituição',
    'Tributária do estado. O fornecedor pode ter recolhido ST',
    'indevidamente, encarecendo o produto sem necessidade.',
  ].join(' '),
};

/**
 * Preenche um template de explicação com valores reais.
 * Escapa HTML para prevenir XSS se renderizado no front-end.
 */
export function fillExplanationTemplate(
  templateKey: string,
  vars: Record<string, string | number>
): string {
  let template = RULE_EXPLANATIONS[templateKey];
  if (!template) {
    return `Inconsistência detectada pela regra ${vars.rule_id ?? 'desconhecida'}.`;
  }

  for (const [key, value] of Object.entries(vars)) {
    template = template.replace(
      new RegExp(`\\{${key}\\}`, 'g'),
      escapeHtml(String(value ?? 'não informado'))
    );
  }

  return template;
}

function escapeHtml(text: string): string {
  return text
    .replace(/&/g, '&amp;')
    .replace(/</g, '&lt;')
    .replace(/>/g, '&gt;')
    .replace(/"/g, '&quot;');
}
```

---

#### 5.2 Templates de Estados de UI

Arquivo: `packages/shared/src/templates/ui-states.ts`

```typescript
/**
 * Templates de estado para todas as telas do MVP (T1-T9).
 * @version 1.0.0
 * @last_updated 2026-05-28
 */

export const UI_STATES = {

  dashboard: {
    greeting: 'Olá, {nome}',
    fallbackGreeting: 'Olá',
    monthLabel: '{mes} {ano}',
    totalNotes: '{n} notas este mês',
    processedAt: 'Processadas em {data} às {hora}',
    sectionTitle: 'Pontos de atenção',
    viewDetail: 'Ver →',
    emptyNoNotes: 'Você ainda não carregou notas este mês.',
    emptyNoIssues: '{n} notas analisadas. Nenhum problema encontrado.',
    emptyNoIssuesSub: 'Seu fiscal está em dia.',
    errorNetwork: 'Não conseguimos atualizar seus dados.',
    errorServer: 'Algo deu errado. Já fomos avisados. Tente de novo em alguns minutos.',
    retryButton: 'Tentar novamente',
    contactSupport: 'Se continuar, fale com a gente pelo WhatsApp.',
    riskTooltip: 'Risco alto: inconsistência que pode gerar multa ou imposto a mais. Resolva o quanto antes.',
    atencaoTooltip: 'Ponto de atenção: inconsistência que merece conferência, mas com menor urgência.',
    disclaimer: 'Análise preliminar automática. Confirme com seu contador.',
  },

  upload: {
    title: 'Carregar Notas',
    dropZone: 'Arraste seus arquivos XML ou ZIP aqui',
    dropZoneActive: 'Solte para começar a análise',
    selectButton: 'Selecionar arquivos',
    helpText: 'Dica: você também pode enviar os XMLs por e-mail para {email}',
    progressLabel: '{x} de {y} notas',
    timeEstimate: 'Isso leva menos de 1 minuto',
    success: '{n} notas analisadas',
    successWithIssues: '{n} notas analisadas. {m} pontos de atenção.',
    viewSummary: 'Ver resumo →',
    uploadMore: 'Carregar mais',
    errorInvalidFile: 'Alguns arquivos não eram notas fiscais e foram ignorados. {n} notas processadas.',
    errorTooLarge: 'O arquivo é muito grande. Tente dividir em lotes menores de até 200 notas.',
    errorFormat: 'Este formato não é aceito. Envie arquivos .xml ou .zip.',
    errorFailure: 'Não foi possível processar seus arquivos. Verifique sua conexão e tente de novo.',
  },

  notesList: {
    title: 'Notas',
    searchPlaceholder: 'Buscar por fornecedor',
    scoreLabel: 'Score {n}',
    counter: 'Exibindo {x} de {y} notas',
    emptyMonth: 'Você ainda não carregou notas este mês.',
    emptySearch: 'Nenhuma nota encontrada para "{termo}".',
    error: 'Não foi possível carregar a lista de notas.',
  },

  noteDetail: {
    title: 'Nota #{numero}',
    inconsistencySection: 'Inconsistências ({n})',
    impactLabel: 'Impacto estimado:',
    actionCTA: 'O que fazer? →',
    itemsSection: 'Itens da nota',
    noIssues: 'Nenhum problema encontrado nesta nota.',
    inlineDisclaimer: 'Esta análise não substitui a validação do seu contador.',
  },

  inconsistencyDetail: {
    title: 'Ponto de atenção',
    whatHappenedSection: 'O que aconteceu',
    whatItMeansSection: 'O que isso significa',
    whatToDoSection: 'O que fazer',
    statusPendente: 'Pendente',
    statusEmAndamento: 'Em andamento',
    statusResolvida: 'Resolvida',
    statusIgnorada: 'Ignorada',
    quickResolve: 'Marcar como Resolvida',
    historySection: 'Histórico',
    ignoreReasonPlaceholder: 'Por que você decidiu ignorar este alerta?',
    ignoreWarning: 'Ao ignorar, você assume a responsabilidade por esta decisão fiscal.',
    llmBadge: 'Texto gerado por IA',
    viewTechnical: 'Ver explicação técnica →',
    viewSimple: 'Ver explicação simplificada →',
    toastResolved: 'Marcado como Resolvida',
    errorEmptyReason: 'Informe o motivo para ignorar este alerta.',
  },

  report: {
    title: 'Relatório do mês',
    downloadPdf: 'Baixar PDF',
    sendWhatsApp: 'Enviar por WhatsApp',
    generating: 'Preparando seu relatório...',
    emptyMonth: 'Nenhuma inconsistência encontrada em {n} notas processadas.',
    pdfDisclaimer: 'Este relatório foi gerado automaticamente pelo FiscoPilot como apoio à análise do contador responsável. Não substitui a validação profissional nem a apuração oficial dos tributos.',
  },

  login: {
    tagline: 'Suas notas fiscais explicadas.',
    whatsappLabel: 'Digite seu WhatsApp:',
    sendButton: 'Enviar link de acesso',
    alternative: 'Ou acesse pelo link que enviamos no seu WhatsApp.',
    terms: 'Ao acessar, você concorda com os Termos de Uso.',
    linkSent: 'Enviamos um link de acesso para o seu WhatsApp.',
    linkSentSub: 'Toque no link para entrar.',
    resendLink: 'Reenviar link',
    changeNumber: 'Usar outro número',
    linkExpired: 'Seu link expirou por segurança. Links de acesso valem por 24 horas.',
    numberNotFound: 'Este WhatsApp não está cadastrado.',
    errorSend: 'Não foi possível enviar o link. Tente de novo.',
  },

  global: {
    loading: 'Carregando...',
    errorRetry: 'Tentar novamente',
    offline: 'Você está sem internet. Os dados mais recentes podem não estar disponíveis.',
    maintenance: 'Estamos em manutenção. Voltamos em alguns minutos.',
    back: 'Voltar',
    save: 'Salvar',
    forbidden: 'Você não tem permissão para acessar esta página.',
    pageNotFound: 'Página não encontrada.',
  },
};
```

---

#### 5.3 Templates de Notificação (WhatsApp + E-mail)

Arquivo: `apps/api/src/modules/notify/templates/notifications.ts`

```typescript
/** @version 1.0.0 @last_updated 2026-05-28 */

export const WHATSAPP_TEMPLATES = {

  W1_RESUMO_SEMANAL: {
    template_name: 'fiscopilot_resumo_semanal',
    body: [
      '📊 FiscoPilot — Resumo da semana',
      '',
      '{periodo}: {n_total} notas processadas.',
      '',
      '{n_ok} sem problemas · {n_atencao} pontos de atenção · {n_risco} risco alto',
      '',
      '{alerta_ou_ok}',
      '',
      '{link_magico}',
    ].join('\n'),
  },

  W2_ALERTA_RISCO_ALTO: {
    template_name: 'fiscopilot_alerta_risco_alto',
    body: [
      '🚨 FiscoPilot — Ponto de atenção',
      '',
      '{nome_emitente} · Nota #{nfe_numero} · R$ {valor_total}',
      '',
      '{tipo_inconsistencia}',
      '',
      'Impacto estimado: {estimated_impact}',
      '',
      '{link_magico_detalhe}',
    ].join('\n'),
  },

  W3_UPLOAD_CONCLUIDO: {
    template_name: 'fiscopilot_upload_concluido',
    body: [
      '✅ FiscoPilot — {n_total} notas analisadas',
      '',
      '{n_ok} sem problemas',
      '{n_pontos} pontos de atenção encontrados',
      '',
      '{link_magico}',
    ].join('\n'),
  },

  W4_LEMBRETE_PENDENCIAS: {
    template_name: 'fiscopilot_lembrete_pendencias',
    body: [
      '📋 FiscoPilot — Você tem {n_pendentes} pendências',
      '',
      '{n_risco} de risco alto ainda sem resolver.',
      '',
      'O mês está acabando — veja o que falta:',
      '{link_magico}',
    ].join('\n'),
  },

  W5_SILENCIO_POSITIVO: {
    template_name: 'fiscopilot_silencio_positivo',
    body: [
      '✅ FiscoPilot — Tudo certo essa semana',
      '',
      '{n_total} notas processadas. Nenhum problema encontrado.',
      '',
      'Seu fiscal está em dia.',
      '',
      '{link_magico}',
    ].join('\n'),
  },

  W6_CONVITE_EQUIPE: {
    template_name: 'fiscopilot_convite_equipe',
    body: [
      '👋 Olá, {nome_convidado}!',
      '',
      '{nome_admin} te convidou para acessar o FiscoPilot da {nome_loja}.',
      '',
      'Você poderá carregar notas e acompanhar as análises.',
      '',
      '{link_magico}',
      '',
      'Equipe FiscoPilot',
    ].join('\n'),
  },
};

export const EMAIL_TEMPLATES = {

  E1_CONFIRMACAO_INGESTAO: {
    subject: 'FiscoPilot — {n} notas recebidas e em análise',
    body: [
      'Olá,',
      '',
      'Recebemos {n} notas fiscais que você enviou para {email_ingestao}.',
      '',
      'Elas estão sendo analisadas agora. Isso leva menos de 1 minuto.',
      '',
      'Quando terminar, você pode ver o resultado no app:',
      '{link_magico}',
      '',
      'Equipe FiscoPilot',
    ].join('\n'),
  },

  E2_RESUMO_PROCESSAMENTO: {
    subjectComIssues: 'FiscoPilot — {n_total} notas analisadas ({n_pontos} pontos de atenção)',
    subjectSemIssues: 'FiscoPilot — {n_total} notas analisadas. Nenhum problema.',
    bodyComIssues: [
      'Olá,',
      '',
      'Analisamos {n_total} notas fiscais da sua loja.',
      '',
      'Resultado:',
      '- {n_ok} sem problemas',
      '- {n_atencao} com pontos de atenção',
      '- {n_risco} com risco alto',
      '',
      'Veja o que precisa da sua atenção:',
      '{link_magico}',
      '',
      'Importante: esta é uma análise preliminar automática. Confirme com seu contador antes de tomar qualquer ação.',
      '',
      'Equipe FiscoPilot',
    ].join('\n'),
    bodySemIssues: [
      'Olá,',
      '',
      'Analisamos {n_total} notas fiscais da sua loja.',
      '',
      'Nenhum problema encontrado. Seu fiscal está em dia.',
      '',
      'Acompanhe pelo app:',
      '{link_magico}',
      '',
      'Equipe FiscoPilot',
    ].join('\n'),
  },

  E3_LINK_MAGICO: {
    subject: 'FiscoPilot — Seu link de acesso',
    body: [
      'Olá,',
      '',
      'Aqui está seu link de acesso ao FiscoPilot:',
      '',
      '{link_magico}',
      '',
      'Este link é pessoal e expira em 24 horas. Não compartilhe com outras pessoas.',
      '',
      'Se você não pediu este link, ignore esta mensagem.',
      '',
      'Equipe FiscoPilot',
    ].join('\n'),
  },
};
```

---

#### 5.4 Templates de Respostas Automáticas

Arquivo: `apps/api/src/modules/notify/templates/auto-responses.ts`

```typescript
/** @version 1.0.0 @last_updated 2026-05-28 */

export const AUTO_RESPONSES = {

  AR1_UPLOAD_FAILED: {
    subject: 'FiscoPilot — Falha no processamento das suas notas',
    body: [
      'Olá,',
      '',
      'Infelizmente não conseguimos processar as {n} notas fiscais que você enviou.',
      '',
      'Motivo: {error_message}',
      '',
      'Você pode tentar novamente acessando o app:',
      '{link_magico}',
      '',
      'Se o problema persistir, fale com a gente pelo WhatsApp: {whatsapp_suporte}',
      '',
      'Equipe FiscoPilot',
    ].join('\n'),
  },

  AR2_EMAIL_TOO_LARGE: {
    subject: 'FiscoPilot — Não foi possível processar seu e-mail',
    body: [
      'Olá,',
      '',
      'Recebemos seu e-mail, mas os anexos são muito grandes (limite: 10 MB).',
      '',
      'Sugerimos que você:',
      '1. Envie as notas fiscais diretamente pelo app: {link_app}',
      '2. Ou divida os arquivos em e-mails menores.',
      '',
      'Equipe FiscoPilot',
    ].join('\n'),
  },

  AR3_MAINTENANCE: {
    whatsapp: [
      '🔧 FiscoPilot — Manutenção programada',
      '',
      'Dia: {data}',
      'Horário: {hora_inicio} às {hora_fim}',
      '',
      'O app pode ficar indisponível por até {duracao_minutos} minutos.',
      'Suas notas continuam seguras.',
      '',
      'Dúvidas? Fale com a gente: {whatsapp_suporte}',
    ].join('\n'),
    email: {
      subject: 'FiscoPilot — Manutenção programada em {data}',
      body: [
        'Olá,',
        '',
        'O FiscoPilot passará por uma manutenção programada.',
        '',
        'Data: {data}',
        'Horário: {hora_inicio} às {hora_fim} (horário de Brasília)',
        'Duração prevista: {duracao_minutos} minutos',
        '',
        'Durante este período, o app pode ficar indisponível.',
        'Todas as suas notas e análises permanecem seguras.',
        '',
        'Dúvidas? Fale conosco pelo WhatsApp: {whatsapp_suporte}',
        '',
        'Equipe FiscoPilot',
      ].join('\n'),
    },
  },
};
```

---

#### 5.5 Mapa de Templates por Origem

```
┌──────────────────────────────────────────────────────────────────┐
│                  ORIGEM DOS TEXTOS NO PRODUTO                     │
│                                                                    │
│  ┌─────────────────────────┐    ┌─────────────────────────────┐  │
│  │   DETERMINÍSTICO         │    │   IA GENERATIVA (ETAPA 23)  │  │
│  │   (Substituição de vars) │    │   (OpenRouter GPT-4o-mini)  │  │
│  └───────────┬─────────────┘    └──────────────┬──────────────┘  │
│              │                                   │                 │
│  ┌───────────┼───────────────┐          ┌───────┴──────────┐    │
│  │           │               │          │                   │    │
│  ▼           ▼               ▼          ▼                   ▼    │
│ Rule        UI              Notif.    Paráfrase          (nada  │
│ Engine      States          + Email   de explicação      mais)  │
│ (R1-R8)     (T1-T9)         (W1-W6,   (1 chamada/              │
│                              E1-E3,    inconsistência)          │
│ Estático    Consumido       AR1-AR3)                           │
│ no código   via import       Estático   Opcional.               │
│             direto           no código  Fallback =               │
│                                            template              │
│                                            determinístico        │
│                                                                    │
└──────────────────────────────────────────────────────────────────┘
```

---

#### 5.6 Função Genérica de Preenchimento

```typescript
// packages/shared/src/templates/fill-template.ts

/**
 * Preenche um template com variáveis no formato {variavel}.
 * @param template - string com placeholders {var}
 * @param vars - objeto chave:valor para substituição
 * @param fallback - valor padrão para variáveis não fornecidas (default: '—')
 */
export function fillTemplate(
  template: string,
  vars: Record<string, string | number>,
  fallback: string = '—'
): string {
  return template.replace(/\{(\w+)\}/g, (match, key) => {
    const value = vars[key];
    if (value === undefined || value === null) return fallback;
    return String(value);
  });
}
```

---

### Resumo: Template vs Prompt de IA

| Categoria | Qtd | Origem | Consumido por | Fallback |
|---|---|---|---|---|
| Explicações de regras (R1-R8) | 11 templates | `rule-explanations.ts` | RuleEngine → `explanation_text` | É o próprio fallback |
| Estados de UI (T1-T9) | ~45 mensagens | `ui-states.ts` | React (import direto) | Não precisa (determinístico) |
| Notificações WhatsApp (W1-W6) | 6 templates | `notifications.ts` | NotifyModule → WhatsApp API | `pending_notifications` com retry |
| E-mails transacionais (E1-E3) | 3 templates | `notifications.ts` | NotifyModule → nodemailer | Reenvio manual pelo founder |
| Respostas automáticas (AR1-AR3) | 3 templates | `auto-responses.ts` | EmailReceiver, CronJobs | Log de erro |
| Paráfrase IA (Etapa 23) | 2 prompts | `LlmParaphraser.ts` | OpenRouter → `explanation_llm` | Template determinístico |

---

### Riscos e pontos de atenção

| Risco | Severidade | Mitigação |
|---|---|---|
| Template de explicação conter erro conceitual fiscal replicado em todas as inconsistências daquela regra | Alta | Revisão por contador consultor antes do deploy. Templates versionados — rollback imediato (revert arquivo, redeploy) |
| Variável não fornecida gerar texto com `{var}` literal visível ao usuário | Média | `fillTemplate` tem fallback `'—'`. Teste unitário cobre placeholders de cada template |
| Template de WhatsApp exceder 4096 caracteres com dados reais (nome de fornecedor longo) | Baixa | Templates são enxutos (3-8 linhas). Truncar `nome_emitente` em 80 chars. Validar comprimento antes de enviar |
| UI States duplicados entre `ui-states.ts` e código React hardcoded | Média | `UI_STATES` como fonte única de verdade. CI: regra ESLint customizada proíbe strings hardcoded |
| Templates de e-mail com encoding errado no `nodemailer` | Baixa | `charset: 'UTF-8'` e `Content-Transfer-Encoding: quoted-printable`. Testar com acentos |

---

## Etapa 25 — Segurança e LGPD

### Objetivo da etapa

Definir as medidas de segurança da informação e adequação à LGPD para o FiscoPilot MVP — cobrindo proteção de dados, segurança da aplicação, infraestrutura, gestão de acessos, criptografia, retenção e direitos do titular. O produto lida com dados fiscais empresariais (CNPJ, valores, XMLs de NF-e) e dados pessoais mínimos (nome, WhatsApp do dono e do operador).

### Premissas adotadas

| # | Premissa | Justificativa |
|---|---|---|
| P1 | O MVP não trata CPF de pessoa física — apenas CNPJ (emitente e destinatário), nome de fornecedor (pessoa jurídica), valores e dados cadastrais da loja. Dados pessoais: nome + WhatsApp do Roberto e da Fernanda | Escopo reduzido simplifica adequação LGPD |
| P2 | O FiscoPilot é **operador** de dados (LGPD, art. 5º, VII) — processa dados fiscais por conta da PME (controladora). Não é controlador nem vende/compila dados | Define responsabilidades: PME é controladora, FiscoPilot é operador |
| P3 | Certificado SSL/TLS via Let's Encrypt (Nginx). Criptografia em trânsito: TLS 1.3 mínimo. Criptografia em repouso: não implementada no MVP (VPS com disco não criptografado) | Trade-off consciente. Fase 2: migrar para volume criptografado |
| P4 | Segurança segue OWASP Top 10 (2021) como baseline. Testes de penetração manuais antes do lançamento | Time de 2 devs não tem budget para pentest profissional |
| P5 | LGPD: base legal é execução de contrato (art. 7º, V) para dados do contratante e legítimo interesse (art. 7º, IX) para metadados de uso | Bases legais mais adequadas para SaaS B2B |

### Análise

**Classificação dos dados no FiscoPilot:**

| Categoria | Exemplos | LGPD? | Nível de criticidade |
|---|---|---|---|
| Dados pessoais | Nome do Roberto, nome da Fernanda, WhatsApp de ambos | Sim (art. 5º, I) | Médio |
| Dados cadastrais PJ | CNPJ da loja, nome fantasia, razão social | Não (PJ) | Baixo |
| Dados fiscais empresariais | CNPJ emitente, valores de NF-e, CFOP, NCM, ICMS destacado | Não (PJ) | Alto (sigilo fiscal e comercial) |
| Metadados de uso | Logs de acesso, timestamps, IP, upload counts | Não | Baixo |
| Credenciais | JWT token, magic link token hash | Sim (art. 5º, I) | Crítico |
| Conteúdo de XML | Dados completos da NF-e (itens, quantidades, preços) | Não (PJ) | Alto (estratégia comercial) |

**Observação:** Embora CNPJ e dados fiscais de PJ não sejam "dados pessoais" sob a LGPD, o sigilo fiscal é protegido pelo CTN (art. 198). O FiscoPilot trata esses dados com o mesmo nível de proteção — não por obrigação da LGPD, mas por dever de confidencialidade contratual.

**Vetores de ataque priorizados (OWASP Top 10):**

| # | Risco OWASP | Aplicabilidade ao FiscoPilot | Severidade |
|---|---|---|---|
| A01 | Broken Access Control | Multi-tenant: Fernanda não pode ver dados de outra loja | Crítico |
| A02 | Cryptographic Failures | JWT sem senha, magic link token | Alto |
| A03 | Injection | SQL injection via search, XXE via XML upload | Alto |
| A05 | Security Misconfiguration | Docker, Nginx, CORS, headers HTTP | Médio |
| A06 | Vulnerable Components | npm packages, Docker images | Médio |
| A07 | Auth Failures | Magic link é o único mecanismo de auth | Crítico |

### Decisões recomendadas

| Decisão | Conteúdo | Status |
|---|---|---|
| D1 | RLS (Row-Level Security) no PostgreSQL como camada primária de isolamento multi-tenant | Decisão de segurança |
| D2 | Rate limiting: 60 req/min global, 3 tentativas/15min para magic link por número | Decisão de segurança |
| D3 | Validação de XML contra XXE: fast-xml-parser sem DTD, rejeitar DOCTYPE e ENTITY | Decisão de segurança |
| D4 | Política de senhas: zero. Autenticação exclusivamente por magic link + JWT (HS256, secret 256-bit, expira 7 dias) | Decisão de produto |
| D5 | Criptografia em trânsito: TLS 1.3 (Nginx + Let's Encrypt). HSTS (max-age=31536000) | Decisão de segurança |
| D6 | Dados pessoais (nome, WhatsApp) com acesso restrito por RLS. Backup S3 com criptografia server-side (AES-256) | Decisão de LGPD |
| D7 | Política de retenção: dados ativos = 5 anos (prazo decadencial fiscal). Backups = 1 ano. XMLs > 90 dias → S3 | Decisão de LGPD |
| D8 | Canal de exercício de direitos do titular: WhatsApp do founder. Template de resposta para requisições | Decisão de LGPD |

### Entregáveis

---

#### 5.1 Modelo de Ameaças

```
┌──────────────────────────────────────────────────────────────────┐
│                     MODELO DE AMEAÇAS                             │
│                                                                    │
│  ATACANTE EXTERNO (Internet)                                      │
│  │                                                                 │
│  ├── Força bruta no magic link (POST /auth/magic-link)            │
│  │   └── Rate limit 3/15min, sem enumeração de usuário            │
│  ├── Força bruta no JWT                                            │
│  │   └── Secret 256-bit, expira 7 dias, HS256                    │
│  ├── XXE via upload de XML malicioso                              │
│  │   └── fast-xml-parser sem DTD, rejeitar DOCTYPE/ENTITY        │
│  ├── SQL Injection via search de fornecedor                       │
│  │   └── Drizzle ORM parametriza todas as queries                 │
│  └── Scan de portas                                                │
│      └── UFW (apenas 80/443/22), Docker sem porta exposta         │
│                                                                    │
│  ATACANTE INTERNO (Usuário autenticado)                            │
│  │                                                                 │
│  ├── Acessar dados de outro tenant                                 │
│  │   └── RLS + organization_id em toda query                     │
│  ├── Promover-se a ADMIN                                           │
│  │   └── PATCH /users/:id restrito a ADMIN                       │
│  └── Replay de JWT expirado                                        │
│      └── JWT com exp claim validado a cada request                │
│                                                                    │
│  ATACANTE PRIVILEGIADO (SSH)                                       │
│  │                                                                 │
│  ├── Acesso direto ao banco (psql)                                 │
│  │   └── PostgreSQL sem listen address externo                    │
│  └── Leitura de XMLs em disco                                      │
│      └── Permissões de arquivo 600, dono: nodejs                  │
└──────────────────────────────────────────────────────────────────┘
```

---

#### 5.2 Segurança da Aplicação (OWASP Top 10)

##### A01 — Broken Access Control

```typescript
// Middleware de autorização por role (Fastify preHandler)
export async function requireRole(
  request: FastifyRequest,
  reply: FastifyReply,
  allowedRoles: ('ADMIN' | 'OPERADOR')[]
) {
  const user = request.user;
  if (!allowedRoles.includes(user.role)) {
    return reply.status(403).send({
      type: 'https://copilotofiscal.com/errors/forbidden',
      title: 'Acesso negado',
      status: 403,
      detail: 'Você não tem permissão para acessar este recurso.',
    });
  }
}

// Exemplo: endpoint de admin só para ADMIN
// fastify.patch('/api/v1/users/:id', {
//   preHandler: [authenticate, (req, rep) => requireRole(req, rep, ['ADMIN'])],
// }, handler);

// RLS como segunda camada no PostgreSQL
// SET app.current_organization_id = '019018a0-...';
// → Toda query automaticamente filtrada por organization_id
```

##### A03 — Injection (SQL + XXE)

```typescript
// SQL injection: Drizzle ORM parametriza automaticamente
const results = await db.query.nfeDocuments.findMany({
  where: and(
    eq(nfeDocuments.organizationId, orgId),
    ilike(nfeDocuments.nomeEmitente, `%${searchTerm}%`) // $1 parametrizado
  ),
});

// XXE prevention: fast-xml-parser sem DTD + validação manual
const parserOptions = {
  processEntities: false,    // Não processa &entidade;
  htmlEntities: false,       // Não converte HTML entities
  ignoreDeclaration: true,   // Ignora <?xml ...?>
  ignorePiTags: true,        // Ignora processing instructions
};

// Rejeitar XML com <!DOCTYPE ou <!ENTITY
function containsDangerousDTD(xmlString: string): boolean {
  return /<!DOCTYPE\s/i.test(xmlString) || /<!ENTITY\s/i.test(xmlString);
}
```

##### A05 — Security Misconfiguration (Headers HTTP)

```nginx
# Security headers no Nginx
add_header Strict-Transport-Security "max-age=31536000; includeSubDomains" always;
add_header X-Content-Type-Options "nosniff" always;
add_header X-Frame-Options "DENY" always;
add_header Referrer-Policy "strict-origin-when-cross-origin" always;
add_header Content-Security-Policy "default-src 'self'; script-src 'self'; style-src 'self' 'unsafe-inline'; img-src 'self' data:; connect-src 'self' https://api.openrouter.ai https://graph.facebook.com; font-src 'self'" always;
```

##### A06 — Vulnerable Components

```bash
# CI/CD: GitHub Actions verifica vulnerabilidades
pnpm audit --audit-level=high
docker scout cves --severity-cutoff high

# Renovate bot: PRs automáticos para atualização de dependências
```

##### A07 — Identification and Authentication Failures

| Ameaça | Mitigação |
|---|---|
| Magic link interceptado | Single-use (used_at), HTTPS, WhatsApp E2E |
| Token reutilizado | `used_at IS NOT NULL` → 401 |
| Brute force magic link | Rate limit: 3 tentativas/número/15min |
| JWT roubado | Expira 7 dias. Sem refresh token (simplicidade) |
| Sessão simultânea | Não implementado no MVP (limitação conhecida, Fase 2) |

**Fluxo de autenticação (passwordless):**

```
1. Usuário digita WhatsApp → POST /auth/magic-link
2. Sistema gera crypto.randomBytes(32).toString('hex')
3. Sistema armazena SHA-256(token) em magic_links.token_hash
4. Sistema envia token original por WhatsApp
5. Usuário clica no link → GET /auth/verify?token={original}
6. Sistema: SHA-256(token) === token_hash? → JWT (7 dias)
7. Sistema: magic_link.used_at = now() (single-use)
8. Cliente armazena JWT em localStorage
9. Requests: Authorization: Bearer {jwt}
10. JWT expira → solicitar novo link mágico
```

---

#### 5.3 Segurança de Infraestrutura

```
┌──────────────────────────────────────────────────────────────┐
│               HARDENING DA VPS (Hetzner CX22)                 │
│                                                               │
│  Firewall (UFW):                                               │
│    ufw allow 80/tcp · ufw allow 443/tcp · ufw allow 22/tcp    │
│    ufw deny all · ufw enable                                   │
│                                                               │
│  SSH:                                                          │
│    PermitRootLogin no · PasswordAuthentication no             │
│    PubkeyAuthentication yes · MaxAuthTries 3                   │
│                                                               │
│  Docker:                                                       │
│    USER node (não roda como root)                              │
│    HEALTHCHECK em todos os containers                          │
│    restart: unless-stopped                                     │
│    Portas internas: api:3001, db:5432 (sem bind externo)      │
│                                                               │
│  Atualizações:                                                 │
│    unattended-upgrades (security patches automáticos)          │
│    Docker image rebuild semanal (CI schedule)                  │
│    pnpm audit no CI a cada push                                │
│                                                               │
│  Backup:                                                       │
│    pg_dump diário (02:00 UTC) → S3 (AES-256 SSE)              │
│    Retenção: 7 diários + 4 semanais + 3 mensais               │
│    Teste de restore trimestral                                 │
└──────────────────────────────────────────────────────────────┘
```

**Dockerfile seguro (api):**

```dockerfile
FROM node:22-alpine AS base
RUN addgroup -g 1001 nodejs && adduser -u 1001 -G nodejs -s /bin/sh -D nodejs

FROM base AS deps
WORKDIR /app
COPY package.json pnpm-lock.yaml ./
RUN corepack enable && pnpm install --frozen-lockfile --prod

FROM base AS runner
WORKDIR /app
COPY --from=deps /app/node_modules ./node_modules
COPY --chown=nodejs:nodejs . .
USER nodejs
EXPOSE 3001
HEALTHCHECK --interval=30s --timeout=5s --retries=3 \
  CMD wget -qO- http://localhost:3001/api/v1/health || exit 1
CMD ["node", "dist/server.js"]
```

---

#### 5.4 Gestão de Acessos

```
┌──────────────────────────────────────────────────────────────┐
│                  MATRIZ DE ACESSOS                            │
│                                                               │
│  RECURSO                        ADMIN     OPERADOR   PÚBLICO │
│  ─────────────────────────────  ─────     ────────   ─────── │
│  POST /auth/magic-link          ●         ●          ●       │
│  GET  /auth/verify              ●         ●          ●       │
│  POST /upload                   ●         ●          —       │
│  GET  /upload/batches           ●         ●          —       │
│  GET  /dashboard                ●         ●          —       │
│  GET  /notes                    ●         ●          —       │
│  GET  /notes/:id                ●         ●          —       │
│  GET  /inconsistencies/:id      ●         ●          —       │
│  PATCH /inconsistencies/:id     ●         ●          —       │
│  GET  /report/pdf               ●         ●          —       │
│  GET  /health                   ●         ●          ●       │
│                                                               │
│  ADMIN EXCLUSIVO:                                             │
│  PATCH /users/:id               ●         —          —       │
│  POST  /users/invite            ●         —          —       │
│  GET   /admin/audit-log         ●         —          —       │
│  POST  /admin/refresh-cache     ●         —          —       │
└──────────────────────────────────────────────────────────────┘
```

---

#### 5.5 Criptografia

| Camada | Em trânsito | Em repouso |
|---|---|---|
| Front-end → Nginx | TLS 1.3 (HTTPS) | — |
| Nginx → API | HTTP (rede Docker interna) | — |
| API → PostgreSQL | TCP (rede Docker interna) | Disco sem criptografia (MVP). Backup S3: AES-256 SSE |
| API → OpenRouter | HTTPS (TLS 1.3) | — |
| API → WhatsApp API | HTTPS (TLS 1.3) | — |
| XMLs em disco | — | Permissões 600 (somente nodejs lê) |
| Backup S3 | HTTPS (TLS 1.3) | AES-256 SSE |
| JWT | HTTPS | Assinado HMAC-SHA256, payload não criptografado |
| Magic link token | HTTPS | SHA-256 hasheado. Token original nunca armazenado |

**Limitação — disco sem criptografia:** VPS Hetzner CX22 não oferece criptografia nativa. LUKS exigiria senha manual a cada boot — inviável para deploy automatizado. Decisão de MVP: aceitar risco para dados exclusivamente empresariais. Fase 2: volume criptografado (~R$ 40/mês adicionais).

---

#### 5.6 Conformidade LGPD

##### Bases Legais

| Tratamento | Base Legal (LGPD) |
|---|---|
| Coleta de nome e WhatsApp | Execução de contrato (art. 7º, V) |
| Envio de link mágico | Consentimento (art. 7º, I) — usuário solicita ativamente |
| Resumo semanal (W1) | Legítimo interesse (art. 7º, IX) |
| Logs de auditoria (IP, timestamp) | Legítimo interesse (art. 7º, IX) |
| Armazenamento de XMLs de NF-e | Execução de contrato (art. 7º, V) — dados PJ |

##### Direitos do Titular

| Direito | Implementação | Canal |
|---|---|---|
| Confirmação e acesso | Founder consulta banco, exporta JSON/CSV | WhatsApp |
| Correção | Usuário via Perfil (T8). WhatsApp: founder | T8 + WhatsApp |
| Exclusão | Soft-delete (`is_active = false`). Dados fiscais mantidos 5 anos (CTN) | WhatsApp |
| Portabilidade | Exportação manual em JSON | WhatsApp |
| Revogação de consentimento | Desabilitar notificações WhatsApp | WhatsApp |

**Template — requisição de acesso:**

```
Olá, {nome}. Recebemos sua solicitação de acesso aos seus dados (LGPD).

Dados armazenados:
- Nome: {nome} / WhatsApp: {whatsapp}
- Organização: {nome_fantasia} / CNPJ {cnpj}
- Cadastro: {created_at} / Último acesso: {last_login_at}
- {n} notas fiscais processadas (dados empresariais, mantidos por 5 anos)

Para correção, exclusão ou portabilidade, responda esta mensagem.
Equipe FiscoPilot
```

##### Política de Retenção

| Tipo de dado | Retenção | Base legal |
|---|---|---|
| Dados pessoais (nome, WhatsApp) | Contrato ativo + 6 meses | Defesa jurídica |
| Dados fiscais (NF-e, inconsistências) | 5 anos | Prazo decadencial (CTN, art. 173) |
| XMLs em disco | 90 dias (depois S3) | Otimização storage |
| Backups (S3) | 1 ano | Boas práticas DR |
| Logs de auditoria | 5 anos | Defesa jurídica |
| Magic link tokens | 24 horas | Segurança |

##### Registro de Operações de Tratamento (ROTA)

```
Controlador: PME contratante (loja de material de construção)
Operador: FiscoPilot (CNPJ do founder)
Encarregado (DPO): Founder (MVP — sem DPO dedicado)
Finalidade: Processamento de documentos fiscais para detecção de inconsistências

Dados tratados:
┌───────────────────┬───────────────┬──────────────┬──────────┐
│ Dado              │ Fonte         │ Base Legal   │ Compart. │
├───────────────────┼───────────────┼──────────────┼──────────┤
│ Nome              │ Cadastro      │ Contrato     │ Não      │
│ WhatsApp          │ Cadastro      │ Consentimento│ Meta*    │
│ CNPJ da loja      │ Cadastro      │ Contrato     │ Não      │
│ XMLs de NF-e      │ Upload        │ Contrato     │ Não      │
│ Inconsistências   │ Sistema       │ Contrato     │ Não      │
│ Logs de auditoria │ Sistema       │ Leg. interesse│ Não     │
│ IP address        │ HTTP request  │ Leg. interesse│ Não     │
└───────────────────┴───────────────┴──────────────┴──────────┘

* WhatsApp API (Meta, EUA): apenas número para envio de mensagens.
  OpenRouter (EUA): apenas texto de explicação fiscal (sem dados pessoais).

Medidas: RLS, TLS 1.3, rate limiting, JWT, audit_log imutável, backup AES-256.
```

---

### Resumo das Camadas de Defesa

```
┌──────────────────────────────────────────────────────────────────┐
│                     CAMADAS DE DEFESA                             │
│                                                                    │
│  CAMADA 1: Rede                                                   │
│  UFW (80, 443, 22) · Cloudflare DDoS · TLS 1.3                   │
│                                                                    │
│  CAMADA 2: Aplicação                                              │
│  Rate limiting · JWT validation · Role-based access                │
│  Anti-XXE · Parametrized queries (Drizzle ORM)                    │
│                                                                    │
│  CAMADA 3: Banco de Dados                                         │
│  RLS multi-tenant · PK UUIDv7 · Constraints CHECK                │
│  Sem listen address externo (apenas rede Docker)                 │
│                                                                    │
│  CAMADA 4: Dados                                                  │
│  Backup S3 AES-256 SSE · XMLs permissão 600                      │
│  Audit log imutável · Retenção com prazo legal                   │
│                                                                    │
│  CAMADA 5: Processos                                              │
│  CI/CD com security audit · Dependabot/Renovate                  │
│  SSH apenas chave pública · Canal LGPD: WhatsApp founder         │
└──────────────────────────────────────────────────────────────────┘
```

### Riscos e pontos de atenção

| Risco | Severidade | Mitigação |
|---|---|---|
| Disco da VPS sem criptografia em repouso — vazamento físico no datacenter | Baixa | Hetzner ISO 27001. Dados empresariais, não pessoais sensíveis. Fase 2: volume criptografado |
| Sem DPO dedicado — founder acumula função sem qualificação jurídica | Média | Consultoria LGPD pontual (~R$ 2.000). Volume e risco baixos |
| Requisição LGPD de exclusão conflitar com guarda fiscal obrigatória (5 anos) | Média | Política: dados pessoais excluídos; dados fiscais mantidos. Informar titular |
| WhatsApp como único canal de auth: se Meta bloquear número, login quebra | Média | WhatsApp Business verificado. Seguir políticas Meta. Plano B: SMS (Twilio) |
| Falta de pentest profissional antes do lançamento | Média | Checklist OWASP interno + revisão manual. Probely free tier para cobertura básica |
| Audit log pode crescer e expor dados se não podado | Baixa | Append-only. Retenção 5 anos com poda. `details` JSONB sem tokens |

---

## Etapa 26 — Auditoria e Rastreabilidade

### Objetivo da etapa

Definir o sistema de auditoria do FiscoPilot MVP — quais eventos são registrados, em que granularidade, como são armazenados, consultados e retidos — garantindo que toda ação relevante do usuário e do sistema seja rastreável, imutável e auditável para fins de compliance fiscal, resolução de disputas e defesa em fiscalização.

### Premissas adotadas

| # | Premissa | Justificativa |
|---|---|---|
| P1 | Audit log é **append-only** — sem UPDATE, sem DELETE. Qualquer "correção" é um novo evento que referencia o anterior | Imutabilidade é requisito para validade jurídica em defesa fiscal |
| P2 | Todo evento carrega `organization_id` obrigatório, `user_id` quando ação humana, `ip_address` quando originado de request HTTP | Rastreabilidade completa: quem fez o quê, de qual loja, de qual IP, quando |
| P3 | Eventos de sistema (parser, rule engine, notificações) também são auditados com `user_id = NULL` | Troubleshooting: "por que essa nota não gerou inconsistência?" → audit log mostra parsing |
| P4 | `details` (JSONB) carrega payload específico do evento — permite queries flexíveis sem alterar schema | Cada tipo de evento tem dados diferentes; JSONB evita tabela com 50 colunas nullable |
| P5 | Retenção: 5 anos (prazo decadencial fiscal). Após 5 anos, archive para S3 (JSON newline-delimited) e remoção do banco | Mantém performance do PostgreSQL sem perder rastreabilidade de longo prazo |
| P6 | Consulta ao audit log é restrita a ADMIN da organização (RLS) + founder (acesso global). Operador não acessa | Fernanda não precisa ver logs; Roberto pode querer auditar decisões da equipe |

### Análise

O audit log tem dois propósitos: (1) defesa fiscal — provar que uma inconsistência ignorada foi decisão informada, não omissão; (2) troubleshooting — se uma nota não gerou inconsistência mas deveria, o log mostra o motivo exato (ex.: `NFE_MISSING_FIELD`).

O schema da Etapa 19 já foi projetado para isso. Aqui detalhamos os 14 tipos de evento com payloads reais, o endpoint de consulta, a UI de histórico e a política de archive.

### Decisões recomendadas

| Decisão | Conteúdo | Status |
|---|---|---|
| D1 | 14 tipos de evento padronizados com `event_type` em snake_case UPPER_CASE | Decisão de taxonomia |
| D2 | `details` JSONB com schema flexível por evento. Zod valida no insert (não no banco) | Decisão de schema |
| D3 | Tabela `audit_log` sem FK para entidades que possam ser deletadas — `entity_id` é UUID solto | Decisão de resiliência |
| D4 | Consulta via endpoint `GET /api/v1/admin/audit-log` (ADMIN) com filtros por período, evento, entidade | Decisão de API |
| D5 | Archive após 5 anos: COPY CSV → S3. DELETE do banco como superuser (bypassa trigger) | Decisão de retenção |
| D6 | Trigger PL/pgSQL bloqueia UPDATE e DELETE na tabela de auditoria (exceto superuser para archive) | Decisão de imutabilidade |

### Entregáveis

---

#### 5.1 Garantia de Imutabilidade

```sql
CREATE OR REPLACE FUNCTION fn_prevent_audit_mutation()
RETURNS trigger AS $$
BEGIN
  RAISE EXCEPTION 'audit_log é imutável — UPDATE e DELETE são proibidos';
END;
$$ LANGUAGE plpgsql;

CREATE TRIGGER trg_audit_no_update
  BEFORE UPDATE ON audit_log
  FOR EACH ROW EXECUTE FUNCTION fn_prevent_audit_mutation();

CREATE TRIGGER trg_audit_no_delete
  BEFORE DELETE ON audit_log
  FOR EACH ROW EXECUTE FUNCTION fn_prevent_audit_mutation();
```

---

#### 5.2 Catálogo de Eventos (14 tipos)

##### Upload

**`UPLOAD_STARTED`** — Estágio 1 (Receive): batch criado.
```json
{
  "event_type": "UPLOAD_STARTED", "entity_type": "upload_batches",
  "entity_id": "019018a0-9f2d-...", "user_id": "019018a0-7a1e-...",
  "ip_address": "189.45.32.10",
  "details": { "source": "WEB", "file_count": 1, "file_names": ["notas_maio.zip"], "total_size_bytes": 2456789 }
}
```

**`UPLOAD_COMPLETED`** — Estágio 7 (Dispatch): batch concluído com métricas de todos os estágios.
```json
{
  "event_type": "UPLOAD_COMPLETED", "entity_type": "upload_batches",
  "entity_id": "019018a0-9f2d-...", "user_id": null,
  "details": {
    "source": "WEB", "total_files": 87, "total_processed": 87, "total_ignored": 0,
    "inconsistencies_found": 3,
    "stages": {
      "receive": {"duration_ms": 450}, "validate": {"duration_ms": 120, "valid": 87},
      "extract": {"duration_ms": 2300, "xmls": 87},
      "parse": {"duration_ms": 18500, "parsed": 87, "ignored": 0, "canceled": 0},
      "dedup": {"duration_ms": 80, "new": 87}, "store": {"duration_ms": 3200, "docs": 87, "items": 870},
      "dispatch": {"duration_ms": 4200, "ok": 84, "atencao": 1, "risco_alto": 2}
    },
    "total_duration_ms": 28850
  }
}
```

**`UPLOAD_FAILED`** — Qualquer estágio com falha catastrófica.
```json
{
  "event_type": "UPLOAD_FAILED", "entity_type": "upload_batches",
  "entity_id": "019018a0-9f2d-...", "user_id": "019018a0-7a1e-...",
  "details": { "failed_stage": "store", "error_code": "DB_TRANSACTION_FAIL",
    "error_message": "connection refused: postgres:5432", "processed_before_failure": 43, "total_files": 87 }
}
```

##### Processamento

**`NFE_PROCESSED`** — Estágio 6 (Store): nota inserida com sucesso.
```json
{
  "event_type": "NFE_PROCESSED", "entity_type": "nfe_documents",
  "entity_id": "019018a0-def2-...", "user_id": null,
  "details": { "upload_batch_id": "019018a0-9f2d-...",
    "chave_acesso": "35210512345678000190550010000035221000003522", "numero": 3522,
    "nome_emitente": "C&C Materiais", "valor_total": "1150.00",
    "parse_time_ms": 185, "items_count": 3, "xml_hash": "a1b2c3d4e5f6..." }
}
```

**`NFE_REJECTED`** — Estágios 2-4: arquivo inválido, XML malformado, nota cancelada.
```json
{
  "event_type": "NFE_REJECTED", "entity_type": "nfe_documents",
  "entity_id": null, "user_id": null,
  "details": { "upload_batch_id": "019018a0-9f2d-...", "file_name": "nota_cancelada.xml",
    "reason_code": "NFE_CANCELED", "chave_acesso": "35210512345678000190550010000035211000003521",
    "stage": "parse", "duration_ms": 45 }
}
```

**`NFE_DEDUPLICATED`** — Estágio 5 (Dedup): nota já existe.
```json
{
  "event_type": "NFE_DEDUPLICATED", "entity_type": "nfe_documents",
  "entity_id": "019018a0-def2-...", "user_id": null,
  "details": { "upload_batch_id": "019018a0-9f2d-...",
    "chave_acesso": "35210512345678000190550010000035211000003521",
    "existing_document_id": "019018a0-def2-...", "xml_hash_match": true }
}
```

##### Inconsistências

**`INCONSISTENCY_DETECTED`** — Estágio 7: regra detectou inconsistência.
```json
{
  "event_type": "INCONSISTENCY_DETECTED", "entity_type": "inconsistencies",
  "entity_id": "019018a0-abc1-...", "user_id": null,
  "details": { "nfe_document_id": "019018a0-def2-...", "rule_id": "R1", "score": 85,
    "classification": "RISCO_ALTO", "field_path": "NFe.infNFe.det.0.prod.CFOP",
    "found_value": "6102", "expected_value": "1102", "estimated_impact": "412.00" }
}
```

**`INCONSISTENCY_STATUS_CHANGED`** — `PATCH /inconsistencies/:id`: mudança de status.
```json
{
  "event_type": "INCONSISTENCY_STATUS_CHANGED", "entity_type": "inconsistencies",
  "entity_id": "019018a0-abc1-...", "user_id": "019018a0-8b2f-...",
  "ip_address": "189.45.32.10",
  "details": { "nfe_document_id": "019018a0-def2-...",
    "previous_status": "PENDENTE", "new_status": "EM_ANDAMENTO",
    "checklist_updated": true, "checklist_completed": 1, "checklist_total": 4,
    "changed_by_name": "Fernanda Souza" }
}
```

**`INCONSISTENCY_IGNORED`** — `PATCH` com `status=IGNORADA`. Evento mais crítico para defesa fiscal.
```json
{
  "event_type": "INCONSISTENCY_IGNORED", "entity_type": "inconsistencies",
  "entity_id": "019018a0-abc1-...", "user_id": "019018a0-8b2f-...",
  "ip_address": "189.45.32.10",
  "details": { "nfe_document_id": "019018a0-def2-...", "rule_id": "R1", "score": 85,
    "reason": "Conferi com a Dona Célia e ela confirmou que esse CFOP está correto para fornecedor do Lucro Real",
    "changed_by_name": "Fernanda Souza" }
}
```

##### Relatório

**`REPORT_EXPORTED`** — `GET /report/pdf`: download do relatório mensal.
```json
{
  "event_type": "REPORT_EXPORTED", "entity_type": "organizations",
  "entity_id": "019018a0-5c3f-...", "user_id": "019018a0-8b2f-...",
  "ip_address": "189.45.32.10",
  "details": { "periodo": "2026-05", "total_notas": 143, "inconsistencias_abertas": 2,
    "formato": "PDF", "generated_at": "2026-06-01T09:00:00Z" }
}
```

##### Autenticação

**`USER_LOGIN`** — `GET /auth/verify`: magic link validado, JWT emitido.
```json
{
  "event_type": "USER_LOGIN", "entity_type": "users",
  "entity_id": "019018a0-7a1e-...", "user_id": "019018a0-7a1e-...",
  "ip_address": "177.54.23.8",
  "details": { "whatsapp": "5511999991234", "user_name": "Roberto Almeida", "role": "ADMIN",
    "user_agent": "Mozilla/5.0 (Linux; Android 10)", "auth_method": "MAGIC_LINK" }
}
```

**`MAGIC_LINK_REQUESTED`** — `POST /auth/magic-link`: solicitação de link.
```json
{
  "event_type": "MAGIC_LINK_REQUESTED", "entity_type": "users",
  "entity_id": "019018a0-7a1e-...", "user_id": null, "ip_address": "177.54.23.8",
  "details": { "whatsapp_masked": "55119****1234",
    "organization_id": "019018a0-5c3f-...", "link_sent": true, "channel": "WHATSAPP" }
}
```

##### Administração

**`CACHE_REFRESHED`** — Refresh manual ou automático (24h) do cache de tabelas fiscais.
```json
{
  "event_type": "CACHE_REFRESHED", "entity_type": "system",
  "entity_id": null, "user_id": null,
  "details": { "trigger": "SCHEDULED",
    "tables_loaded": ["cfop", "ncm_materiais", "aliquotas_icms", "st_estados"],
    "cfop_count": 550, "ncm_count": 245, "st_ufs": 27, "duration_ms": 420 }
}
```

**`USER_INVITED`** — ADMIN convida novo membro.
```json
{
  "event_type": "USER_INVITED", "entity_type": "users",
  "entity_id": "019018a0-8b2f-...", "user_id": "019018a0-7a1e-...",
  "ip_address": "189.45.32.10",
  "details": { "invited_whatsapp": "5511998885678", "invited_name": "Fernanda Souza",
    "invited_role": "OPERADOR", "invited_by_name": "Roberto Almeida" }
}
```

---

#### 5.3 Consulta e UI

**Endpoint:** `GET /api/v1/admin/audit-log` (ADMIN apenas)

Query params: `event_type`, `entity_type`, `entity_id`, `user_id`, `from`, `to`, `limit` (50), `cursor`.

**Exemplo de resposta:**

```json
{
  "data": [
    {
      "id": "019018a0-log9-...",
      "event_type": "INCONSISTENCY_IGNORED",
      "entity_type": "inconsistencies",
      "entity_id": "019018a0-abc1-...",
      "user": { "nome": "Fernanda Souza" },
      "details": { "reason": "Conferi com a Dona Célia...", "score": 85 },
      "ip_address": "189.45.32.10",
      "created_at": "2026-05-16T14:20:51Z"
    }
  ],
  "pagination": { "limit": 50, "next_cursor": "019018a0-log9-...", "has_more": false }
}
```

**UI — Tela de Histórico (ADMIN):**

```
┌──────────────────────────────────────────────────┐
│  ← Voltar     Histórico de Atividades            │
├──────────────────────────────────────────────────┤
│  ── NOTA #3521 — DISTRIBUIDORA CIMENTOBOM ──     │
│                                                  │
│  15/05 14:30:27                                  │
│  ⚠️ Inconsistência detectada (R1) · Score 85   │
│  Risco alto · ~R$ 412                            │
│                                                  │
│  16/05 09:15:03    👤 Fernanda Souza             │
│  📝 Status: Pendente → Em andamento             │
│  Checklist: 1/4 concluído                        │
│                                                  │
│  16/05 14:20:51    👤 Fernanda Souza             │
│  🚫 Ignorada                                     │
│  Motivo: "Conferi com a Dona Célia e ela         │
│  confirmou que está correto"                     │
│  ⚠️ Registrado para fins de auditoria fiscal     │
│                                                  │
│  ── 3 eventos · [Exportar CSV]                   │
└──────────────────────────────────────────────────┘
```

---

#### 5.4 Política de Archive

```
ANOS 0-5: PostgreSQL (online, consultável via API)
  · Índices para queries por tenant + período
  · RLS isola por organization_id
  · Trigger bloqueia UPDATE/DELETE

ANO 5: Archive para S3
  · COPY TO CSV → gzip → S3 (INTELLIGENT_TIERING)
  · DELETE do banco como superuser (bypassa trigger)
  · Path: s3://fiscopilot-audit-archive/{tenant_id}/{year}/

ANOS 5-10: S3 (consultável via download)
  · Acesso restrito ao founder (IAM policy)

ANO 10+: Deleção permanente
  · S3 Lifecycle: delete after 3650 days
```

---

#### 5.5 Rastreabilidade Ponta a Ponta (Exemplo Real)

```
NOTA #3521 — Distribuidora CimentoBom (R$ 8.400)
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

15/05 14:30:00  UPLOAD_STARTED
      └─ Fernanda enviou ZIP com 87 notas

15/05 14:30:01  NFE_PROCESSED (×87)
      └─ Cada nota parseada e armazenada

15/05 14:30:18  INCONSISTENCY_DETECTED (×3)
      └─ R1: CFOP divergente · 85 · ~R$ 412
      └─ R2: Alíquota ICMS 18% vs 12% · 70 · ~R$ 504
      └─ R8: ST indevido · 75 · ~R$ 420

15/05 14:30:27  UPLOAD_COMPLETED
      └─ 87 notas · 3 inconsistências · 28.8s

16/05 09:15:03  INCONSISTENCY_STATUS_CHANGED
      └─ Fernanda: PENDENTE → EM_ANDAMENTO (R1)

16/05 14:20:51  INCONSISTENCY_IGNORED
      └─ Fernanda: "Conferi com Dona Célia — cimento tem ST em SP"

01/06 08:30:00  INCONSISTENCY_STATUS_CHANGED
      └─ Roberto: EM_ANDAMENTO → RESOLVIDA (R1)
      └─ Fornecedor emitiu carta de correção

01/06 08:32:00  REPORT_EXPORTED
      └─ Fernanda: relatório Maio/2026 enviado para Dona Célia

CONCLUSÃO: Toda ação sobre esta nota é rastreável —
do upload ao relatório do contador.
```

---

### Riscos e pontos de atenção

| Risco | Severidade | Mitigação |
|---|---|---|
| Volume de eventos: ~5.000/mês (5 tenants). Em 5 anos = 300MB. PostgreSQL lida bem | Baixa | Índices particionados por `created_at`. Archive anual remove eventos antigos |
| `details` JSONB pode conter dados sensíveis se desenvolvedor incluir campos indevidos | Média | Code review obrigatório. Regra ESLint: proíbe `token`/`secret` em `details`. Zod valida campos permitidos por tipo de evento |
| Trigger de imutabilidade pode ser bypassado por superuser — risco de adulteração | Média | Superuser em cofre (1Password). Founder não usa superuser no dia a dia. `pgAudit` extension na Fase 2 |
| Consulta do Roberto pode expor eventos técnicos (`NFE_REJECTED`) que ele não entende | Baixa | Filtrar `event_type` no endpoint: ADMIN vê eventos de usuário + inconsistências. Eventos de sistema visíveis apenas para founder |

---

## Etapa 27 — Billing e Monetização

### Objetivo da etapa

Definir o modelo de cobrança do FiscoPilot MVP — estrutura de preços, trial, meio de pagamento, gatilhos de upgrade e estratégia de migração para cobrança recorrente automatizada — alinhado ao ICP de lojas de material de construção no Simples Nacional e à hipótese de monetização da Etapa 6 (R$ 97/mês).

### Premissas adotadas

| # | Premissa | Justificativa |
|---|---|---|
| P1 | MVP com plano único (sem tiers). Um preço, todas as funcionalidades. Tiers entram na Fase 2 quando houver diferenciação real de valor | Simplifica venda ("é R$ 97, ponto"), reduz atrito de decisão, elimina desenvolvimento de feature flags de plano |
| P2 | Cobrança manual via Pix nos primeiros 6 meses (até ~20 clientes). Founder envia cobrança mensal por WhatsApp com chave Pix ou link de pagamento | Gateway de pagamento (Stripe/Pagar.me) adiciona 2 semanas de desenvolvimento + homologação. Não se justifica para <20 clientes |
| P3 | Trial de 15 dias grátis. Começa no dia do onboarding guiado (Etapa 7 — Jornada). Ao final do trial, founder agenda call de 10 min para converter | Métrica de validação: "o produto gerou valor suficiente em 15 dias para justificar R$ 97?" |
| P4 | Sem contrato formal no MVP. Pagamento mensal via Pix com "recibo" em PDF gerado pelo founder. Sem multa de cancelamento, sem fidelidade | PMEs desse porte não assinam contrato de SaaS. Confiança pessoal (founder + WhatsApp) substitui contrato |
| P5 | Preço não é negociável no MVP. "R$ 97, igual para todo mundo." Se o prospect pedir desconto, oferecer 1 mês grátis em troca de depoimento | Consistência de receita para validação. Desconto = variável a mais para analisar |

### Análise

**Por que R$ 97 e não R$ 99,90?**

Psicologicamente, R$ 97 é percebido como "menos de cem reais" mas sem o aspecto de "preço de varejo" que R$ 99,90 carrega. Para o Roberto, R$ 97 é "arredondado, justo, sem vírgula". Também é mais fácil de digitar no Pix.

**Por que plano único no MVP?**

Com 1 funcionalidade nuclear (detecção de inconsistências em NF-e) e 1 ICP, não há o que "tierar". Tiers entram quando houver diferenciação real: volume de notas, documentos suportados ou funcionalidades avançadas.

**Cálculo de LTV e payback no MVP:**

| Métrica | Valor |
|---|---|
| Ticket mensal | R$ 97 |
| Custo de aquisição (CAC) | ~R$ 0 (founder vende em grupos de WhatsApp, boca a boca) |
| Tempo médio de vida (churn assumido) | 12 meses (hipótese) |
| LTV estimado | R$ 1.164 (97 × 12) |
| Payback | Imediato (CAC ≈ zero no MVP) |
| Meta de clientes no mês 3 | 5 pagantes = R$ 485 MRR |
| Meta de clientes no mês 6 | 10 pagantes = R$ 970 MRR |

**Quando migrar para gateway de pagamento (Fase 2):**

| Gatilho | Ação |
|---|---|
| 15+ clientes pagantes | Integrar Stripe/Pagar.me. Cobrança automática no cartão ou boleto |
| Solicitação de nota fiscal de serviço | Emitir NFS-e via prefeitura do founder (MEI ou Simples) |
| Primeiro cliente que atrasa pagamento 2 meses | Implementar suspensão automática de acesso |
| Cliente que pergunta "aceita cartão?" pela 3ª vez | Priorizar integração de cartão de crédito |

### Decisões recomendadas

| Decisão | Conteúdo | Status |
|---|---|---|
| D1 | **Plano único: R$ 97/mês.** Funcionalidades ilimitadas. Até 500 notas/mês (limite técnico, não comercial) | Decisão de pricing |
| D2 | **Trial: 15 dias grátis**, onboarding guiado pelo founder. Sem cartão de crédito, sem compromisso | Decisão de GTM |
| D3 | **Cobrança: Pix manual** (chave CNPJ do founder). Comprovante enviado por WhatsApp com recibo PDF | Decisão de MVP |
| D4 | **Sem contrato formal.** Relação de confiança. Cancelamento a qualquer momento, sem aviso prévio | Decisão de operação |
| D5 | **Fase 2 (mês 4-6): Stripe** para assinatura recorrente. Planos: Básico (R$ 97, 500 notas), Profissional (R$ 197, 2.000 notas + NFS-e) | Decisão de roadmap |
| D6 | **Preço não negociável.** Exceção: 1 mês grátis para early adopters que toparem dar depoimento público | Decisão de vendas |

### Entregáveis

---

#### 5.1 Estrutura de Preços

```
┌──────────────────────────────────────────────────────────────┐
│                    FISCOPILOT — PLANOS                        │
│                                                               │
│  ┌──────────────────────────────────────────────────────────┐│
│  │                    MVP (FASE 1)                           ││
│  │                   Plano Único                             ││
│  │                                                           ││
│  │  R$ 97 / mês                                              ││
│  │  ─────────────────────                                    ││
│  │  ✅ NF-e de entrada ilimitadas (até 500/mês)             ││
│  │  ✅ 8 regras de detecção fiscal                           ││
│  │  ✅ Dashboard de risco                                    ││
│  │  ✅ Explicações em português claro                        ││
│  │  ✅ Checklist de ações                                    ││
│  │  ✅ Relatório mensal do contador (PDF)                    ││
│  │  ✅ Notificações por WhatsApp                             ││
│  │  ✅ Upload via web + e-mail                               ││
│  │  ✅ 2 usuários (dono + auxiliar)                          ││
│  │  ✅ 15 dias grátis                                        ││
│  │                                                           ││
│  │  Sem contrato · Cancele quando quiser                     ││
│  └──────────────────────────────────────────────────────────┘│
│                                                               │
│  ┌──────────────────────────────────────────────────────────┐│
│  │                    FASE 2 (mês 4-6)                       ││
│  │                                                           ││
│  │  Plano Básico                        Plano Profissional   ││
│  │  R$ 97 / mês                         R$ 197 / mês         ││
│  │  ─────────────                       ────────────────     ││
│  │  Tudo do MVP +                       Tudo do Básico +     ││
│  │  Download automático XML             NFS-e municipal      ││
│  │  (certificado digital)               3 usuários            ││
│  │  Até 500 notas/mês                   Até 2.000 notas/mês  ││
│  │                                      Suporte prioritário   ││
│  └──────────────────────────────────────────────────────────┘│
└──────────────────────────────────────────────────────────────┘
```

---

#### 5.2 Fluxo de Cobrança (MVP — Manual)

```
┌──────────────────────────────────────────────────────────────────┐
│                FLUXO DE COBRANÇA MANUAL (PIX)                     │
│                                                                    │
│  DIA 0: Founder faz onboarding guiado (15 min)                    │
│       · Cria conta da loja                                        │
│       · Fernanda faz primeiro upload                              │
│       · Roberto vê primeiro dashboard                             │
│       · Founder envia: "15 dias grátis. Dia 15 eu volto."        │
│                                                                    │
│  DIA 7: Founder envia mensagem de check-in (WhatsApp)             │
│       · "E aí Roberto, achou algum problema nas notas?"          │
│       · Se sim: reforçar valor. Se não: ajudar a encontrar       │
│                                                                    │
│  DIA 14: Founder envia lembrete de fim de trial                   │
│       · "Roberto, o trial gratuito termina amanhã."              │
│       · "Você quer continuar? É R$ 97/mês."                      │
│       · Agenda call de 10 min para o dia seguinte                │
│                                                                    │
│  DIA 15: Call de conversão                                        │
│       · Founder pergunta: "Nessas 2 semanas, o Copiloto te       │
│         ajudou? Encontrou algum problema que você não sabia?"    │
│       · Se SIM: "Então R$ 97/mês. Me faz um Pix aqui."          │
│         → Enviar chave Pix ou link do Nubank/Mercado Pago        │
│         → Enviar comprovante "recibo" (PDF simples)              │
│       · Se NÃO: "O que faltou? O que podemos melhorar?"          │
│         → Coletar feedback, estender trial se promissor          │
│                                                                    │
│  TODO DIA 1º DE CADA MÊS:                                         │
│       · Founder confere planilha de cobrança (Google Sheets)     │
│       · Envia mensagem: "Roberto, venceu o Copiloto.             │
│         R$ 97. Pix: {chave}. Obrigado!"                          │
│       · Se pagar: envia recibo PDF. Marca como PAGO              │
│       · Se não pagar em 3 dias: "E aí, precisa de ajuda?"       │
│       · Se não pagar em 7 dias: "Tudo bem? Vou pausar           │
│         o acesso até regularizar, ok?"                            │
│       · Se não pagar em 15 dias: desativar usuários              │
│         (is_active = false). Dados preservados.                  │
│                                                                    │
│  CANCELAMENTO:                                                    │
│       · Cliente avisa por WhatsApp: "Vou cancelar"               │
│       · Founder pergunta motivo (aprender, não reter)            │
│       · Founder desativa acesso (is_active = false)              │
│       · Dados mantidos por 6 meses (LGPD + possibilidade         │
│         de retorno). Exclusão permanente após 6 meses            │
│         se solicitado                                            │
└──────────────────────────────────────────────────────────────────┘
```

---

#### 5.3 Planilha de Controle de Cobrança (Founder)

```
┌─────────────────────────────────────────────────────────────────┐
│              CONTROLE DE COBRANÇA (GOOGLE SHEETS)                │
│                                                                  │
│  #  Cliente         Início    Trial    Status    Último Pix      │
│  ─────────────────────────────────────────────────────────────  │
│  1  Material ABC    01/06     15d      PAGO      R$ 97 (01/07)  │
│  2  Ferragens Zé    15/06     15d      PAGO      R$ 97 (15/07)  │
│  3  ConstruFácil    01/07     15d      TRIAL     —              │
│  4  CasaNova Mat.   01/07     15d      PENDENTE  atrasado 5d    │
│  5  Pisos & Cia     15/07     15d      TRIAL     —              │
│                                                                  │
│  MRR Atual: R$ 194    Trial ativo: 3    Atrasados: 1            │
│  Meta MRR mês 3: R$ 485                                         │
└─────────────────────────────────────────────────────────────────┘
```

---

#### 5.4 Recibo PDF (Template Simples)

```
┌──────────────────────────────────────────────────────────┐
│                                                           │
│                    FISCOPILOT                              │
│           CNPJ 12.345.678/0001-90                         │
│                                                           │
│  ═══════════════════════════════════════════════════════ │
│                                                           │
│                     RECIBO                                 │
│                                                           │
│  Cliente: Material de Construção ABC                      │
│  CNPJ: 98.765.432/0001-00                                 │
│                                                           │
│  Serviço: FiscoPilot — Plano Mensal                       │
│  Período: 01/07/2026 a 31/07/2026                         │
│  Valor: R$ 97,00                                          │
│                                                           │
│  Forma de pagamento: PIX                                  │
│  Data do pagamento: 01/07/2026                            │
│                                                           │
│  ═══════════════════════════════════════════════════════ │
│                                                           │
│  FiscoPilot Tecnologia Ltda                               │
│  copilotofiscal.com · WhatsApp: (11) 99999-1234           │
│                                                           │
└──────────────────────────────────────────────────────────┘
```

---

#### 5.5 Gatilhos de Upgrade (Fase 2)

```
┌──────────────────────────────────────────────────────────────┐
│            GATILHOS DE UPGRADE (BÁSICO → PROFISSIONAL)       │
│                                                               │
│  GATILHO 1: Volume de notas                                   │
│    "Você já processou 487 notas este mês. Seu plano permite  │
│     500. Que tal migrar para o Profissional (2.000 notas)?"  │
│    └─ Disparado quando cliente atinge 80% do limite           │
│                                                               │
│  GATILHO 2: Documentos não suportados                         │
│    Cliente tenta fazer upload de NFS-e (municipal)            │
│    "Notas fiscais de serviço estão disponíveis no plano       │
│     Profissional. Quer fazer um teste grátis de 7 dias?"     │
│                                                               │
│  GATILHO 3: Expansão da equipe                                │
│    Cliente tenta adicionar 3º usuário                         │
│    "Seu plano permite 2 usuários. O plano Profissional        │
│     permite até 3. Quer migrar?"                              │
│                                                               │
│  GATILHO 4: Tempo de uso (Fase 3)                             │
│    Cliente ativo há 6+ meses, NPS ≥ 40                        │
│    "Você usa o Copiloto há 6 meses. Quer conhecer o plano     │
│     Profissional com download automático de XML?"             │
└──────────────────────────────────────────────────────────────┘
```

---

#### 5.6 Estratégia de Migração para Cobrança Automatizada (Fase 2)

```
SEMANA 1-2: Integrar Stripe (ou Pagar.me)
  · Criar conta Stripe Connect (Brasil)
  · Webhook para eventos: invoice.paid, invoice.payment_failed
  · Tabela subscriptions: id, organization_id, plan, status,
    stripe_subscription_id, current_period_start, current_period_end

SEMANA 3: Migrar clientes existentes (manual)
  · Para cada cliente ativo:
    1. Criar customer no Stripe com CNPJ e WhatsApp
    2. Criar subscription: plan=BASIC, price=R$ 97
    3. Enviar link de checkout por WhatsApp
    4. Cliente preenche: cartão de crédito ou boleto
    5. Stripe cobra automaticamente todo dia 1º
    6. Nota fiscal: emitir NFS-e mensal (MEI)

SEMANA 4: Ativar trial self-service
  · Landing page com checkout Stripe
  · Trial de 15 dias com cartão (captura após trial)
  · sem necessidade de founder para onboarding inicial
  · Email de boas-vindas automático com link mágico

FLUXO DE CANCELAMENTO AUTOMÁTICO:
  · Pagamento falha → Stripe retry (3, 7, 14 dias)
  · Após 3 tentativas falhas → subscription status = PAST_DUE
  · Após 30 dias sem pagamento → access revogado
    (organization.suspended_at = now())
  · Dados preservados por 90 dias adicionais
  · E-mail/SMS de reativação: "Seus dados ainda estão aqui.
    Reative sua conta em 1 clique."
```

---

#### 5.7 Métricas de Monetização

| Métrica | Frequência | Meta (mês 3) | Meta (mês 6) |
|---|---|---|---|
| MRR (Monthly Recurring Revenue) | Mensal | R$ 485 (5 × R$ 97) | R$ 970 (10 × R$ 97) |
| Trial → Paid Conversion | Mensal | 50% (5 de 10 trials) | 60% |
| Churn mensal | Mensal | <10% | <8% |
| LTV (lifetime value) | Trimestral | R$ 1.164 (12 meses) | R$ 1.746 (18 meses) |
| CAC (customer acquisition cost) | Mensal | R$ 0 (founder vende) | R$ 50 (anúncios WhatsApp) |
| LTV/CAC ratio | Trimestral | ∞ (CAC = 0) | >30 |
| Tempo médio de conversão | — | 5-7 dias | 3-5 dias |
| Tempo médio de pagamento | — | 2-3 dias | <1 dia (cartão) |

### Riscos e pontos de atenção

| Risco | Severidade | Mitigação |
|---|---|---|
| Inadimplência: cliente não paga e founder não quer cobrar amigo | Alta | Automatizar cobrança o quanto antes (Stripe). Enquanto manual: separar relação pessoal da comercial. "Roberto, é o sistema que está cobrando, não eu." |
| Pix manual não escala: com 20 clientes, founder gasta 2h/mês em cobrança | Média | 20 × 6 min = 2h/mês é aceitável. Gatilho para Stripe é 15 clientes, antes de virar problema |
| Cliente pede nota fiscal e founder não tem como emitir (MEI sem NFS-e configurada) | Média | Abrir MEI antes do primeiro cliente pagante. Configurar NFS-e na prefeitura. Emitir nota mensal (R$ 97) para cada cliente |
| Trial de 15 dias pode ser curto se cliente não fizer upload na primeira semana | Média | Onboarding guiado garante upload no dia 0. Se cliente não tem XMLs, founder baixa 2-3 XMLs com o CNPJ dele (com permissão) |
| "Sem contrato" = risco se cliente alegar que não sabia da cobrança recorrente | Baixa | WhatsApp registrado. Recibo mensal. Termos de Uso no app com check no primeiro login |

---

## Etapa 28 — Go-to-Market

### Objetivo da etapa

Definir a estratégia de aquisição dos primeiros 10 clientes pagantes do FiscoPilot — canais, pitch, roteiro de demo, tratamento de objeções e cronograma de 90 dias — operando com orçamento zero e founder como único vendedor, focado no ICP de lojas de material de construção no Simples Nacional.

### Premissas adotadas

| # | Premissa | Justificativa |
|---|---|---|
| P1 | Founder é o único vendedor nos primeiros 6 meses. Sem time de vendas, sem SDR, sem agência | Startup estágio zero; founder conhece o produto e o ICP melhor que qualquer vendedor |
| P2 | Orçamento de aquisição: R$ 0. Canais orgânicos e gratuitos apenas. Sem Google Ads, sem Meta Ads, sem patrocínio de evento | Validar product-market fit antes de investir em canais pagos |
| P3 | Aquisição começa na semana 8 (beta fechado com 3-5 lojas). Vendas começam na semana 10 | Etapa 6: beta na semana 8, primeira venda na semana 10 |
| P4 | Todo contato começa no WhatsApp. E-mail é canal secundário de follow-up | Realidade do ICP: Roberto responde WhatsApp em minutos, e-mail em dias |
| P5 | Cada venda fechada gera ao menos 1 indicação. Meta: k-factor ≥ 1 | Boca a boca é o canal mais eficiente para PMEs de nicho |

### Análise

**Por que inside sales pelo founder, não self-service?**

O Roberto não compra SaaS por landing page. Ele compra porque alguém que ele conhece mostrou algo que resolve um problema concreto. O fundador fazendo inside sales não é uma limitação — é uma vantagem competitiva. Cada venda é também uma sessão de discovery de produto.

**Canais ranqueados por eficiência:**

| Canal | Custo | Volume | Qualidade | Tempo conversão | Prioridade |
|---|---|---|---|---|---|
| Grupos de WhatsApp de lojistas | R$ 0 | Alto (50-200/grupo) | Alta (dono ativo) | 1-7 dias | Primário |
| Indicação de cliente existente | R$ 0 | Médio (1-2/cliente) | Altíssima (confiança) | 1-3 dias | Primário |
| Visita a lojas (porta a porta) | R$ 0 + deslocamento | Baixo (2-3/dia) | Alta (dono presente) | 15-30 dias | Secundário |
| Associações comerciais | R$ 0 (associado) | Médio (20-50/reunião) | Média | 7-30 dias | Secundário |
| Feiras do setor (Feicon) | R$ 0 (visitante) | Alto (200+/dia) | Média | 30-90 dias | Terciário (Fase 2) |
| Parceria com contadores | R$ 0 (comissão) | Médio (3-5/carteira) | Alta | 7-14 dias | Terciário (Fase 2) |

### Decisões recomendadas

| Decisão | Conteúdo | Status |
|---|---|---|
| D1 | Canal primário: grupos de WhatsApp de lojistas. Abordagem: ajuda genuína, não venda agressiva | Decisão de GTM |
| D2 | Meta: 10 clientes pagantes em 90 dias (1 cliente a cada 9 dias). Ritmo: 1 venda/semana a partir da semana 10 | Decisão de meta |
| D3 | Pitch de 30 segundos focado em dor concreta ("multa por CFOP errado"), não em features | Decisão de mensagem |
| D4 | Demo de 3 minutos com dados reais do prospect (raio-x ao vivo). Se não tiver XMLs, usar exemplo análogo do setor | Decisão de vendas |
| D5 | Sem CRM no MVP. Controle no WhatsApp + Google Sheets | Decisão de operação |
| D6 | Kit indicação: mensagem pronta de WhatsApp para cliente encaminhar para colegas | Decisão de crescimento |

### Entregáveis

---

#### 5.1 Pitch de 30 Segundos

**Versão WhatsApp (texto — para grupos):**

> Pessoal, quem aqui já tomou multa por causa de nota fiscal com código errado? Ou descobriu que pagou imposto a mais por meses sem saber?
>
> Eu tô construindo uma ferramenta que lê as notas fiscais de compra de vocês, acha os erros e avisa em português claro — antes de virar multa. Funciona com o Simples Nacional, é só arrastar os XMLs do mês.
>
> Tô procurando 5 lojistas pra testar de graça por 15 dias e me ajudar a melhorar. Se alguém quiser, me chama aqui no privado.

**Versão presencial (visita à loja):**

> Roberto, você sabe quantas notas de compra você recebeu esse mês? E quantas delas estão com algum erro que pode te dar multa? Eu construí uma ferramenta que responde essas duas perguntas em 2 minutos. Me dá 3 minutos que eu te mostro com as suas próprias notas?

---

#### 5.2 Roteiro de Demo (3 minutos)

```
MINUTO 0:00 — Conexão pessoal
  "Roberto, você recebe nota de quantos fornecedores por mês?
   E como você confere se elas estão certas?"
  → Objetivo: fazer o prospect verbalizar a dor (ou a ausência dela).

MINUTO 0:30 — Raio-x ao vivo
  "Me manda os XMLs desse mês aqui no WhatsApp."
  (ou: "Já baixei 3 notas da sua loja na Sefaz — é público, viu?")
  → Processa em tela (15-20 segundos).
  "Pronto. 87 notas. Olha só: 3 com ponto de atenção. Essa aqui
   da Distribuidora CimentoBom, R$ 8.400 — o código fiscal (CFOP)
   veio como venda, mas você tá comprando."

MINUTO 1:30 — Impacto em dinheiro
  "Se não corrigir, você paga ~R$ 412 a mais na DAS esse mês.
   Multiplica isso por 12 meses... são quase R$ 5.000 no ano.
   A assinatura custa R$ 97 por mês. Menos de R$ 1.200 no ano."

MINUTO 2:00 — Ação concreta
  "Quer ver o que eu faria agora? Ó: 1. liga pro fornecedor,
   2. pede carta de correção, 3. avisa a Dona Célia.
   Isso aqui te ajuda?"

MINUTO 2:30 — Fechamento
  "Roberto, R$ 97 por mês. 15 dias grátis pra testar.
   Se não gostar, é só me falar. Quer começar?"
  → Se SIM: envia link mágico. Cria conta. Primeiro upload juntos.
  → Se NÃO: "O que te preocupa? O que precisaria ser diferente?"
```

---

#### 5.3 Objeções Comuns e Respostas

| Objeção | Resposta |
|---|---|
| **"Isso não é coisa que o contador já faz?"** | "O contador vê seus dados 1 vez por mês, depois que o mês fechou. Se tiver erro, já era — a DAS já saiu. O Copiloto te avisa durante o mês, enquanto dá tempo de corrigir. Seu contador continua essencial — a gente só ajuda você a chegar na conversa com ele mais preparado." |
| **"Vou ter que aprender mais um sistema?"** | "É o sistema mais simples que você já usou. Sua assistente arrasta os XMLs, clica em enviar. Você recebe o resultado no WhatsApp. Não precisa aprender nada — se souber usar WhatsApp, sabe usar o Copiloto." |
| **"Isso aí me arruma mais trabalho ou menos trabalho?"** | "Menos trabalho. Hoje sua assistente gasta horas abrindo XML por XML, conferindo. O Copiloto faz isso em 15 segundos e já te mostra o que importa. Pensa: 2 horas por semana que ela ganha pra fazer outra coisa." |
| **"R$ 97 é caro."** | "Quanto custa uma multa por CFOP errado? Meu primeiro cliente economizou R$ 2.400 no primeiro mês — o ano inteiro de assinatura saiu de graça. R$ 97 é menos que o almoço seu e da sua assistente na semana." |
| **"E se eu pagar e mesmo assim tomar multa?"** | "O Copiloto não substitui seu contador e não garante que você nunca vai tomar multa — seria mentira prometer isso. O que a gente faz é te avisar de inconsistências que as regras do Simples conseguem detectar. Tem disclaimer em toda tela. Se tiver algo que a gente não pegou, você me liga e eu te ajudo pessoalmente." |
| **"Meu contador vai brigar comigo se eu usar isso."** | "Pelo contrário. A maioria dos contadores adora quando o cliente entrega dados organizados. Em vez de mandar 50 fotos de nota fiscal, você manda um relatório limpo com o que foi conferido. O contador ganha tempo — e tempo de contador é dinheiro." |
| **"Deixa eu falar com meu contador primeiro."** | "Perfeito. Inclusive, se quiser, eu mesmo mostro pra ele. Manda o WhatsApp da Dona Célia que eu explico — 5 minutos. Posso?" (Se vetar: "Entendo. Quando vocês dois estiverem confortáveis, estou aqui. Enquanto isso, posso te mandar um resumo do mês sem compromisso?") |
| **"Tô sem tempo agora."** | "Sem problema. Me manda só os XMLs desse mês que eu processo pra você e te mando um print. Você vê em 1 minuto, no seu tempo. Se fizer sentido, a gente conversa." |

---

#### 5.4 Canais de Distribuição

##### Canal 1: Grupos de WhatsApp (Primário)

**Estratégia de entrada:**
1. Mapear 5-10 grupos de WhatsApp de lojistas de material de construção
2. Entrar nos grupos por convite de um lojista conhecido (nunca por link público)
3. Primeira semana: só observar. Entender linguajar, dores, dinâmica
4. Segunda semana: participar ajudando (responder dúvida sobre CFOP, NCM, DAS — sem mencionar o produto)
5. Terceira semana: postar mensagem de valor (pitch de 30s adaptado)

**Mensagem de primeira participação (valor, não venda):**

> Pessoal, uma dica: sempre confiram o CFOP das notas de compra de vocês. Se o fornecedor colocar código de saída (6xxx) em vez de entrada (1xxx), a DAS sai errada e vocês pagam imposto a mais. Acontece direto com distribuidora. Abraço!

**Meta:** 1 lead qualificado por semana por grupo ativo. 5 grupos = 5 leads/semana.

---

##### Canal 2: Indicação de Clientes (Primário)

**Kit de indicação (enviado por WhatsApp após fechamento):**

> Roberto, valeu por fechar com a gente! Se você conhece algum colega lojista que também sofre com nota fiscal, me ajuda? É só encaminhar essa mensagem:
>
> "Fulano, tô usando uma ferramenta aqui na loja que lê as notas fiscais e acha erro antes de virar multa. Me salvou de uma nota errada mês passado. Custa R$ 97. O Gustavo que faz — chama ele: (11) 99999-1234"

**Incentivo:** 1 mês grátis para cada indicação que virar cliente pagante (limitado a 3 meses consecutivos).

---

##### Canal 3: Visita a Lojas (Secundário)

**Roteiro:**
1. Entrar na loja como cliente (comprar algo pequeno: R$ 10-20)
2. Identificar o dono (geralmente no balcão ou escritório no fundo)
3. Abordagem: "Bom dia! Eu tô visitando lojas de material de construção aqui da região. Posso te fazer uma pergunta rápida?"
4. Se SIM: pitch de 30s (versão presencial)
5. Se interesse: demo de 3 min no celular
6. Se não: "Obrigado mesmo assim. Posso deixar meu contato?"

**Meta:** 2 visitas/dia (manhã e tarde) = 10 visitas/semana. 30% geram interesse. 10% fecham.

---

##### Canal 4: Associações Comerciais (Secundário)

**Estratégia:**
1. Identificar associações comerciais em SP e MG (ACI, ACSP, Federaminas)
2. Participar de 1 reunião mensal como visitante
3. Oferecer palestra gratuita de 15 min: "Os 3 erros fiscais mais comuns em lojas de material de construção"
4. Distribuir 1-pager impresso (frente: problema, verso: solução + WhatsApp)

**1-Pager (frente/verso):**

```
╔══════════════════════════════════════════╗
║  SUAS NOTAS FISCAIS DE COMPRA TÊM ERRO?  ║
║                                          ║
║  3 em cada 10 notas fiscais vêm com      ║
║  algum erro que pode gerar multa ou      ║
║  imposto pago a mais.                    ║
║                                          ║
║  CFOP errado → DAS sai com valor incorreto║
║  Alíquota errada → ICMS a maior          ║
║  NCM suspeito → Risco de malha fina      ║
║                                          ║
║  A multa pode chegar a R$ 5.000.         ║
╠══════════════════════════════════════════╣
║              FISCOPILOT                   ║
║     Suas notas fiscais explicadas.       ║
║                                          ║
║  ✅ Analisa notas em segundos            ║
║  ✅ Encontra erros antes da multa        ║
║  ✅ Explica em português claro           ║
║  ✅ Mostra o impacto em reais            ║
║  ✅ Relatório pronto pro contador        ║
║  ✅ R$ 97/mês · 15 dias grátis           ║
║                                          ║
║  Quer testar? Manda um WhatsApp:         ║
║  (11) 99999-1234  [QR Code]              ║
╚══════════════════════════════════════════╝
```

---

#### 5.5 Cronograma de Aquisição (90 dias)

```
SEMANA 1-4: Preparação
  ├── Mapear 10 grupos de WhatsApp do setor
  ├── Entrar em 5 grupos (via convite)
  ├── Identificar 3 associações comerciais em SP capital
  ├── Preparar 1-pager (frente/verso) — imprimir 100 unidades
  └── Criar Google Sheets de funil (leads, status, follow-up)

SEMANA 5-8: Construção de presença
  ├── Participar ativamente dos grupos (ajudar, não vender)
  ├── 1ª visita a associação comercial (como visitante)
  ├── Visitar 5 lojas (porta a porta) — testar pitch e objeções
  └── Meta: 10 leads qualificados no funil

SEMANA 8: BETA FECHADO
  ├── Convidar 5 leads mais engajados para beta grátis
  ├── Onboarding guiado (1 por dia)
  ├── Acompanhamento diário na 1ª semana
  └── Coletar feedback, bugs e depoimentos

SEMANA 9-10: PRIMEIRAS VENDAS
  ├── Call de conversão com beta testers (dia 15 do trial)
  ├── Meta: 3 dos 5 beta testers converterem para pagantes
  ├── Coletar primeiros depoimentos escritos (WhatsApp)
  └── Ativar kit indicação para os 3 clientes

SEMANA 11-12: Ritmo de 1 venda/semana
  ├── 2 visitas a lojas por dia (manhã + tarde)
  ├── 1 postagem de valor por semana nos grupos
  ├── Follow-up semanal nos leads do funil
  └── Meta acumulada: 5 clientes pagantes

SEMANA 13-16: Indicações começam a chegar
  ├── Indicações dos 5 clientes → ~5 novos leads qualificados
  ├── 2ª visita a associação comercial (palestra de 15 min)
  ├── Manter ritmo de 1 venda/semana
  └── Meta acumulada: 9 clientes pagantes

SEMANA 17-18: Fechamento dos 90 dias
  ├── Últimas 2 vendas para bater meta de 10
  ├── Documentar aprendizados: o que funcionou, o que não
  ├── NPS com todos os clientes
  └── Decidir: continuar inside sales ou contratar SDR?

META FINAL DIA 90: 10 CLIENTES PAGANTES = R$ 970 MRR
```

---

#### 5.6 Funil de Aquisição (Google Sheets)

```
┌─────────────────────────────────────────────────────────────────┐
│                    FUNIL DE VENDAS                                │
│                                                                  │
│  Nome            Origem      1º Contato  Status       Próx Cont.│
│  ─────────────────────────────────────────────────────────────  │
│  Roberto A.      Grupo WA    08/06       CLIENTE     01/07 Pix  │
│  José M.         Indicação   12/06       TRIAL       27/06 call │
│  Carlos S.       Visita loja 15/06       QUALIFICADO 20/06 demo │
│  Antônio P.      Grupo WA    18/06       CONTATADO   20/06 msg  │
│  Paulo R.        Assoc Com.  20/06       LEAD         —         │
│                                                                  │
│  TOTAL LEADS: 48    CONTATADOS: 32 (67%)                        │
│  QUALIFICADOS: 18 (38%)    EM TRIAL: 5 (10%)                    │
│  CLIENTES: 5 (10%)    PERDIDOS: 15                               │
│                                                                  │
│  Conversão lead → cliente: 5/48 = 10.4%                         │
│  Conversão qualificado → cliente: 5/18 = 27.8%                  │
│  Conversão trial → cliente: 5/5 = 100% (early adopters)         │
└─────────────────────────────────────────────────────────────────┘
```

---

#### 5.7 Mensagens de Follow-up

**Follow-up 1 (2 dias após primeiro contato — lead morno):**

> E aí {nome}, conseguiu pensar naquilo que conversamos? Se quiser, me manda uns XMLs de compra desse mês que eu faço uma análise rápida, sem compromisso. Você vê o resultado em 1 minuto.

**Follow-up 2 (7 dias após demo — não fechou):**

> {nome}, passando aqui pra saber se ficou alguma dúvida. Sei que você comentou que ia falar com {contador}. E aí, o que {ele/ela} achou? Posso ajudar a explicar também.

**Follow-up 3 (30 dias — última tentativa):**

> {nome}, tudo bem? Não te procurei antes porque respeito seu tempo. Mas fiquei pensando: se tiver qualquer dúvida sobre aquela nota da {fornecedor} que a gente viu, ainda dá tempo de corrigir antes do fechamento do mês. Se quiser, me chama.

**Mensagem de reativação (cliente cancelou há 30 dias):**

> {nome}, beleza? Seus dados ainda estão aqui. Se quiser voltar a usar o Copiloto, é só me falar — reativo sua conta em 1 minuto. Continua R$ 97.

---

### Resumo dos Canais e Metas

| Canal | Leads/mês | Qualificados/mês | Trials/mês | Clientes/mês |
|---|---|---|---|---|
| Grupos de WhatsApp | 16-20 | 8-10 | 4-5 | 2-3 |
| Indicações | 4-6 | 3-5 | 2-3 | 1-2 |
| Visita a lojas | 8-12 | 4-6 | 2-3 | 1 |
| Associações comerciais | 4-8 | 2-4 | 1-2 | 0-1 |
| **Total** | **32-46** | **17-25** | **9-13** | **4-7** |

**Meta: 4-7 clientes/mês. Em 3 meses = 10-12 clientes (meta: 10).**

### Riscos e pontos de atenção

| Risco | Severidade | Mitigação |
|---|---|---|
| Grupos de WhatsApp banirem o founder por "spam" antes da primeira venda | Alta | Nunca postar link na primeira semana. Relação 5:1 (5 ajudas para 1 menção ao produto) |
| Beta testers não converterem — 0 clientes na semana 10 | Crítico | Ter 10 leads no funil, não 5. Se beta falhar, pivotar: segundo ICP, nova região, ou ajustar produto |
| Founder não ter tempo para vender porque está codando | Alta | Blocos fixos: manhã = vender (9h-12h), tarde = codar (14h-20h). Segunda/terça = vendas. Quarta a sexta = código |
| Falta de prova social (0 depoimentos) nas primeiras semanas | Média | Beta testers geram primeiros depoimentos. Gravar vídeo de 30s do Roberto no WhatsApp: "Funciona mesmo" |
| Associação comercial cobrar para palestrar ou exigir associação paga | Baixa | Se cobrar, pular canal. Focar em visitas e grupos. Retomar com budget |
| Cansaço do founder (inside sales é desgastante) | Média | Meta de 2 visitas/dia, não 5. Se 3 "nãos" seguidos, parar e revisar pitch |
| Indicações não acontecerem (k-factor < 0.5) | Média | Se após 5 clientes não houver indicação, investigar NPS e valor percebido. Pivotar antes de escalar |

---

## Etapa 29 — Roadmap de 12 Semanas

### Objetivo da etapa

Construir um roadmap integrado de 12 semanas (90 dias) que orquestre desenvolvimento de produto, aquisição de clientes e validação de hipóteses — garantindo que cada semana entregue progresso mensurável nas três frentes simultaneamente. O roadmap é a fusão do Sprint Plan da Etapa 8 com o cronograma de aquisição da Etapa 28 e as hipóteses de valor/retenção/monetização da Etapa 6.

### Premissas adotadas

| # | Premissa | Justificativa |
|---|---|---|
| P1 | Time: founder full-stack + 1 engenheiro back-end. Designer UX part-time (2 dias/semana nas semanas 1-8, sob demanda nas semanas 9-12) | Etapa 6: 90 dias, 2-3 pessoas |
| P2 | Semanas 1-8: foco em construção (80% código, 20% aquisição). Semanas 9-12: foco em vendas (50% código, 50% aquisição) | O produto precisa existir antes de vender. Beta na semana 8, vendas na semana 10 |
| P3 | Cada sexta-feira é "demo day" interno: time mostra o que funcionou naquela semana. Founder compartilha feedback de cliente da rua | Ritmo semanal de accountability. Evita "modo construção infinita" sem validação |
| P4 | Roadmap é vivo: a cada 2 semanas, reavaliar prioridades com base no feedback do beta. O plano das semanas 9-12 pode mudar radicalmente | Startup early-stage: rigidez mata. O que está escrito aqui é a intenção inicial |
| P5 | Hipóteses críticas são testadas ANTES do código: regras fiscais testadas com XMLs reais na semana 1-2; valor testado com mockups na semana 3-4 | Validar risco antes de investir esforço |

### Análise

O roadmap integra três trilhas paralelas que se encontram na semana 8 (beta) e semana 10 (primeira venda):

```
TRILHA 1 — PRODUTO:     [Sprint 1-2] [Sprint 3-4] [Sprint 5-6] [Beta] [Vendas]
TRILHA 2 — AQUISIÇÃO:   [Preparação] [Presença]    [Beta convites] [Vendas ativas]
TRILHA 3 — VALIDAÇÃO:   [Regras]     [UX/Mockups]  [Beta feedback] [Métricas]
                         │            │             │               │
SEMANA:                  1──4         5──8          9──10           11──12
```

**Trade-offs do cronograma:**

| Decisão | Prós | Contras |
|---|---|---|
| Beta na semana 8, não antes | Produto funcional o suficiente para gerar valor (dashboard + 5 regras) | 4 semanas a menos de feedback real. Compensado por validação com mockups nas semanas 3-4 |
| WhatsApp notifications (P1) no Sprint 6, não antes | Libera semanas 1-8 para core (parser + regras + dashboard). WhatsApp é importante para retenção, não para primeira venda | Beta testers não recebem notificações automáticas nas primeiras 2 semanas. Founder faz manualmente |
| Vendas só na semana 10, não na semana 8 | Beta testers têm 2 semanas de uso antes da call de conversão | Se beta não gerar inconsistências nas primeiras 2 semanas, conversão é mais difícil |

### Decisões recomendadas

| Decisão | Conteúdo | Status |
|---|---|---|
| D1 | Roadmap de 12 semanas com milestones: semana 4 (MVP interno), semana 8 (beta), semana 10 (primeira venda), semana 12 (10 clientes ou pivot) | Decisão de execução |
| D2 | Semanas 1-8: desenvolvimento em 6 sprints de 2 semanas (Etapa 8). Aquisição em modo "preparação" | Decisão de alocação |
| D3 | Semanas 9-12: desenvolvimento em modo "manutenção + features P1". Aquisição em modo "venda ativa" | Decisão de alocação |
| D4 | Marco de validação a cada 2 semanas: "O que aprendemos que não sabíamos antes?" | Decisão de aprendizado |
| D5 | Se na semana 12 tivermos <5 clientes pagantes, pivotar. Se ≥10, contratar primeiro SDR | Decisão de go/no-go |

### Entregáveis

---

#### 5.1 Visão Macro das 12 Semanas

```
SEM   PRODUTO                          AQUISIÇÃO               VALIDAÇÃO
───   ───────────────────────────────  ──────────────────────  ──────────────────────
 1    Auth + Upload + Parser básico    Mapear 10 grupos WA     Testar 8 regras vs 200
 2    Parser completo + validação      Entrar em 5 grupos      XMLs reais (sem código)
───   ───────────────────────────────  ──────────────────────  ──────────────────────
 3    Regras R1, R2, R3, R7           Observar + ajudar       Mostrar mockups p/ 3
 4    Regras R4, R5, R6, R8           grupos (sem vender)     lojistas. Iterar UX
───   ───────────────────────────────  ──────────────────────  ──────────────────────
 5    Dashboard + Detalhe Nota         Visitar 5 lojas         Testar dashboard c/
 6    Detalhe Incons + Checklist       (testar pitch)          2 lojistas (staging)
───   ───────────────────────────────  ──────────────────────  ──────────────────────
 7    Relatório PDF + Link Mágico      Convidar beta testers   Deploy staging.
 8    E-mail ingest + WhatsApp notify  (5 lojas)               🚀 BETA FECHADO
───   ───────────────────────────────  ──────────────────────  ──────────────────────
 9    Correções do beta                Acompanhar beta         Feedback beta.
10    Features P1 (hist, busca)        CALL CONVERSÃO          PRIMEIRA VENDA
───   ───────────────────────────────  ──────────────────────  ──────────────────────
11    QA + Polimento                   Vendas ativas           NPS com clientes
12    Deploy produção. Features P2     + indicações            RETROSPECTIVA
───   ───────────────────────────────  ──────────────────────  ──────────────────────
```

---

#### 5.2 Semana a Semana

---

##### SEMANA 1 — Fundação

```
PRODUTO (Sprint 1)
  ✅ F01: Upload via ZIP (interface)
  ✅ F02: Drag & drop
  ✅ F04: Validação de tipo de arquivo
  ✅ F30: Criação manual de tenant (founder)
  ✅ F31: Autenticação por link mágico (JWT)
  ✅ F32: Múltiplos usuários por organização
  📋 Entregável: app rodando local. Upload funcional. Auth por link mágico.

AQUISIÇÃO
  ✅ Mapear 10 grupos de WhatsApp do setor
  ✅ Criar lista de 20 lojas de material de construção em SP (Google Maps + CNPJ público)
  ✅ Preparar Google Sheets de funil de vendas

VALIDAÇÃO
  ✅ Coletar 200 XMLs reais de NF-e (próprios ou de amigos lojistas)
  ✅ Testar as 8 regras manualmente (planilha) contra os 200 XMLs
  📋 Marco: "As 8 regras encontram inconsistências em ≥5% das notas?"

RISCO CRÍTICO:
  Se fast-xml-parser falhar em >10% dos XMLs reais, adicionar sax parser como fallback (+3-4 dias).
```

---

##### SEMANA 2 — Parser Completo

```
PRODUTO (Sprint 1)
  ✅ F07: Parser NF-e completo (todos os campos do layout 4.00)
  ✅ F12: R5 — Valor total vs soma dos itens
  ✅ F14: R7 — Chave de acesso (dígito verificador)
  ✅ F16: Classificação de risco (score 0-100)
  ✅ F29: Link mágico (integração WhatsApp API)
  📋 Entregável: sistema recebe ZIP, parseia XMLs, valida chave e valor.

AQUISIÇÃO
  ✅ Entrar em 5 grupos de WhatsApp (via convite de lojista conhecido)
  ✅ Primeira semana de observação: não postar nada
  📋 Meta: 0 leads (ainda em modo escuta)

VALIDAÇÃO
  ✅ Testar parser contra 200 XMLs reais (batch processing)
  📋 Métrica: taxa de parse bem-sucedido ≥ 95%
```

---

##### SEMANA 3 — Regras Core

```
PRODUTO (Sprint 2)
  ✅ F08: R1 — CFOP inconsistente
  ✅ F09: R2 — Alíquota ICMS divergente
  ✅ F10: R3 — NCM suspeito
  ✅ F13: R6 — CST incompatível
  📋 Entregável: 4 regras rodando. Motor detecta inconsistências com explanation_text.

AQUISIÇÃO
  ✅ Segunda semana nos grupos: participar ajudando (responder dúvidas sobre CFOP, NCM)
  ✅ 1ª postagem de valor em 1 grupo: dica sobre CFOP
  📋 Meta: 0 leads, mas 3 interações significativas nos grupos

VALIDAÇÃO
  ✅ Mostrar mockups do dashboard (Figma ou papel) para 3 lojistas
  ✅ Perguntar: "Isso faz sentido? Você pagaria R$ 97/mês por isso?"
  📋 Marco: "≥2 de 3 lojistas dizem 'sim, isso me ajudaria'."
```

---

##### SEMANA 4 — Regras Restantes

```
PRODUTO (Sprint 2)
  ✅ F11: R4 — CNPJ situação cadastral
  ✅ F15: R8 — ICMS ST indevido
  ✅ F05: Indicador de processamento (loading real)
  ✅ F33: Papéis e permissões (admin vs operador)
  📋 Entregável: 8 regras rodando. 🎯 MVP INTERNO COMPLETO.

AQUISIÇÃO
  ✅ Terceira semana: 2ª postagem de valor em 2 grupos
  ✅ Visitar 2 lojas (porta a porta) — testar pitch verbal
  📋 Meta: 5 leads no funil. Pitch validado com 2 lojistas

VALIDAÇÃO
  ✅ Rodar as 8 regras contra os 200 XMLs reais com o sistema
  📋 Métrica: taxa de detecção ≥ 5%. Se <10 inconsistências em 200 notas, pivotar.
```

---

##### SEMANA 5 — Dashboard

```
PRODUTO (Sprint 3)
  ✅ F17: Dashboard — visão resumida (cards + status)
  ✅ F18: Dashboard — lista detalhada de inconsistências
  ✅ F03: Ingestão via e-mail dedicado
  ✅ F22: Gerenciamento de status da inconsistência
  📋 Entregável: dashboard funcional no celular (mobile-first).

AQUISIÇÃO
  ✅ Visitar 3 lojas (porta a porta)
  ✅ 3ª postagem de valor nos grupos
  ✅ Primeiros convites para "testar algo novo"
  📋 Meta: 10 leads no funil. 3 qualificados

VALIDAÇÃO
  ✅ Testar dashboard no staging com 2 lojistas (founder mostra no celular)
  📋 Marco: "Roberto entende o dashboard sem explicação?"
```

---

##### SEMANA 6 — Detalhe da Inconsistência

```
PRODUTO (Sprint 3)
  ✅ F19: Detalhe da inconsistência
  ✅ F20: Explicação em linguagem simples
  ✅ F21: Checklist de ações
  ✅ F28: Exportar relatório do contador (PDF)
  📋 Entregável: jornada completa: upload → dashboard → detalhe → checklist → PDF.

AQUISIÇÃO
  ✅ Visitar últimas 2 lojas
  ✅ 4ª postagem de valor. Responder DMs de lojistas interessados
  ✅ Preparar lista de 5 potenciais beta testers
  📋 Meta: 15 leads. 5 qualificados. 3 pré-beta

VALIDAÇÃO
  ✅ Testar checklist com 1 lojista: "As ações fazem sentido?"
  ✅ Testar PDF do contador: "Dona Célia, esse relatório te ajuda?"
```

---

##### SEMANA 7 — Finalização Pré-Beta

```
PRODUTO (Sprint 4)
  ✅ F06: Histórico de uploads
  ✅ F23: Filtro por período
  ✅ F24: Busca por fornecedor (se houver tempo)
  ✅ Deploy staging: SSL, domínio, Docker Compose
  ✅ Teste de carga: 200 XMLs em <60s na VPS real
  📋 Entregável: produto deployado em staging.copilotofiscal.com.

AQUISIÇÃO
  ✅ Convidar 5 beta testers formalmente (mensagem individual no WhatsApp)
  ✅ Agendar onboarding guiado (1 por dia na semana 8)
  📋 Meta: 5 confirmações de beta

VALIDAÇÃO
  ✅ Teste de carga real na CX22
  ✅ Verificar todos os disclaimers e textos legais
  ✅ Checklist LGPD: RLS ativo? Dados pessoais identificados?
```

---

##### SEMANA 8 — 🚀 BETA FECHADO

```
PRODUTO (Sprint 4)
  ✅ F25: Resumo semanal via WhatsApp (W1)
  ✅ F26: Alerta imediato de risco alto (W2)
  ✅ F27: Silêncio positivo (W5)
  ✅ Correções de bugs do staging
  📋 Entregável: beta aberto para 5 lojas. Notificações WhatsApp funcionando.

AQUISIÇÃO
  ✅ Onboarding guiado: 1 loja por dia (seg-sex)
  ✅ Cada onboarding: 15 min. Ensinar Fernanda a subir XML.
  ✅ Mensagem de check-in no dia 3 e dia 7
  📋 Meta: 5 lojas ativas. ≥1 upload por loja na 1ª semana

VALIDAÇÃO
  📋 Marco: "Os beta testers usam o produto sem ajuda após o onboarding?"
  📋 Hipótese de valor: testada com inconsistências reais encontradas
```

---

##### SEMANA 9 — Refinamento do Beta

```
PRODUTO
  ✅ Correções de bugs reportados pelos beta testers (prioridade máxima)
  ✅ Melhorias de UX baseadas em observação
  ✅ Performance: se upload >60s, otimizar parser
  📋 Entregável: versão corrigida com feedback dos 5 beta testers

AQUISIÇÃO
  ✅ Check-in individual com cada beta tester
  ✅ Identificar "power users" e "ghosts"
  📋 Meta: ≥3 beta testers usando ativamente (≥2 uploads em 2 semanas)

VALIDAÇÃO
  ✅ Coletar depoimentos escritos dos beta testers
  📋 Marco: "Pelo menos 1 beta tester já perguntou 'quanto custa?'"
```

---

##### SEMANA 10 — 💰 PRIMEIRAS VENDAS

```
PRODUTO
  ✅ Features P1 que beta testers pediram
  ✅ WhatsApp notifications (se não concluído)
  📋 Entregável: produto "vendável" — funcionalidades P0 + P1 essenciais

AQUISIÇÃO
  ✅ Call de conversão com cada beta tester (dia 15 do trial)
  ✅ Roteiro: "Nessas 2 semanas, o Copiloto te ajudou? Quer continuar?"
  📋 Meta: ≥3 beta testers convertem para pagantes (60%)
  📋 Meta MRR: R$ 291 (3 × R$ 97)

VALIDAÇÃO
  📋 Marco: "💰 ALGUÉM PAGOU. 'Someone paid fit' está provado."
  📋 Hipótese de monetização: testada com ≥3 conversões
```

---

##### SEMANA 11 — QA e Polimento

```
PRODUTO
  ✅ QA completo: 16 funcionalidades P0 + 7 P1
  ✅ Playwright e2e: jornada principal
  ✅ Security review: OWASP checklist, headers HTTP, RLS ativo
  ✅ Performance: Lighthouse score ≥ 80 no mobile
  ✅ Backup e restore testados
  📋 Entregável: produto pronto para produção.

AQUISIÇÃO
  ✅ Ativar kit indicação para clientes pagantes
  ✅ Visitas a 3 novas lojas (usando depoimentos como prova social)
  📋 Meta: +2 novos trials. +1 nova venda. MRR: R$ 388 (4 clientes)

VALIDAÇÃO
  ✅ NPS com clientes pagantes
  ✅ WAU (usuários ativos por semana)
  📋 Marco: NPS ≥ 40? WAU ≥ 80%?
```

---

##### SEMANA 12 — 🎯 RETROSPECTIVA E DECISÃO

```
PRODUTO
  ✅ Features P2 remanescentes
  ✅ Deploy produção: app.copilotofiscal.com
  ✅ Documentação interna: runbook de operações
  📋 Entregável: produto em produção. Documentação para escala.

AQUISIÇÃO
  ✅ Últimas vendas para bater meta de 10 clientes
  ✅ Follow-up com todos os leads do funil
  ✅ Indicações → pipeline para mês 4
  📋 Meta: 10 clientes pagantes. MRR: R$ 970

VALIDAÇÃO
  ✅ Retrospectiva completa: o que aprendemos em 12 semanas?
  ✅ Métricas finais: Trial→Paid X%, Churn X%, CAC R$X, LTV R$X
  📋 MARCO DE GO/NO-GO:
     ≥10 clientes → contratar SDR, escalar, Fase 2
     5-9 clientes → manter inside sales, investigar gargalo
     <5 clientes → PIVOT: mudar ICP, produto, preço ou canal
```

---

#### 5.3 Marcos de Validação (Checkpoints)

| Semana | Marco | Go/No-Go |
|---|---|---|
| 2 | Parser extrai ≥95% dos campos de 200 XMLs reais | Se <80%, adicionar sax parser |
| 4 | Regras detectam ≥5% de inconsistências em 200 XMLs | Se <5%, adicionar regras reservas ou pivotar ICP |
| 6 | Roberto entende o dashboard em ≤5 segundos | Se não, simplificar UI |
| 8 | Beta: ≥3 de 5 lojas fazem upload na 1ª semana | Se <3, investigar onboarding |
| 10 | ≥3 beta testers convertem para pagantes | Se 0, pivot iminente |
| 12 | ≥10 clientes pagantes, NPS ≥ 40 | Se <5, pivot |

---

#### 5.4 Alocação de Tempo do Time

```
FOUNDER (full-stack + vendas):
  Semanas 1-8:  80% código (manhã + tarde), 20% aquisição (fim de tarde)
  Semanas 9-12: 50% código (tarde), 50% vendas (manhã)

ENGENHEIRO BACK-END:
  Semanas 1-6:  100% código (parser, regras, banco)
  Semanas 7-8:  80% código (relatório, notificações), 20% QA
  Semanas 9-12: 50% código (correções, features P1), 50% QA + infra

DESIGNER UX (part-time):
  Semanas 1-4:   mockups, design system, revisão de microcopy
  Semanas 5-8:   implementação de UI (shadcn/ui + Tailwind)
  Semanas 9-12:  sob demanda (correções de UX do beta)
```

---

#### 5.5 Buffer e Contingência

```
BUFFER TOTAL: 18 dias (dos 90 dias totais, 72 são desenvolvimento líquido)

Distribuição:
  Semanas 1-2:   2 dias (parser NF-e complexo)
  Semanas 3-4:   3 dias (regras com edge cases fiscais)
  Semanas 5-6:   1 dia  (dashboard responsivo)
  Semanas 7-8:   2 dias (WhatsApp API aprovação Meta)
  Semanas 9-10:  5 dias (correções do beta — maior incerteza)
  Semanas 11-12: 5 dias (QA, polish, features extras)

SE BUFFER CONSUMIDO ANTES DA SEMANA 10:
  Cortar features P1 na ordem: F24 (busca) → F06 (histórico) → F23 (filtro)
  Manter apenas P0. Beta não pode atrasar além da semana 9.
  Se beta não sair até semana 9: semana 10 = beta, semana 12 = primeiras vendas.
```

### Riscos e pontos de atenção

| Risco | Severidade | Mitigação |
|---|---|---|
| Beta testers não encontrarem inconsistências nas primeiras 2 semanas → valor = zero | Crítico | Adicionar regras extras (R9-R12) ou pivotar ICP para setor com mais erros |
| WhatsApp API demorar >2 semanas para aprovar templates → notificações não funcionam | Alta | Submeter templates na semana 1. Fallback: SMS via Twilio ou notificações manuais do founder |
| Engenheiro back-end sair do time → founder sozinho | Média | Documentação desde dia 1. Código limpo, testes. Cortar features P1 e focar em manter beta |
| 200 XMLs com maioria de notas "perfeitas" (grandes redes) → baixa taxa de detecção | Média | Coletar XMLs de distribuidores regionais. Ajustar sensibilidade das regras |
| VPS CX22 não aguentar 5 tenants simultâneos | Baixa | Benchmark antes do beta. Se necessário, upgrade para CX32 (8GB, R$ 200/mês) |

---

### Roadmap Pós-MVP — Fases A-D (Mês 4-12)

Após o MVP de 12 semanas, o produto evolui em 4 fases de 2-3 meses cada, totalizando 155 dias de desenvolvimento distribuídos em ~9 meses.

#### Visão Macro do Roadmap Expandido

```
FASE      MESES    DURAÇÃO    FOCO                          CUSTO INFRA/MÊS
────      ─────    ───────    ────────────────────────────  ───────────────
MVP       1-3      90 dias    Core: parser + 8 regras +     ~R$ 168
                              dashboard + WhatsApp + PDF

FASE A    4-5      ~30 dias   Retenção e Redução de Atrito  ~R$ 168
                              #5, #6, #7, #8, #11, #15

FASE B    5-7      ~40 dias   Monitoramento Contínuo         ~R$ 188
                              #1, #4, #14                   (+pg-boss)

FASE C    7-9      ~35 dias   Inteligência e Ecossistema     ~R$ 218
                              #2, #3, #12                   (+LLM, +VPS)

FASE D    9-12     ~50 dias   Plataforma e Escala            ~R$ 338
                              #9, #10, #13                  (VPS maior)
```

#### FASE A — Retenção e Redução de Atrito (Mês 4-5)

```
SEM   PRODUTO                              AQUISIÇÃO

 13   F46: Mensagem p/ fornecedor          Enviar templates W1/W5 atualizados p/
      F47: Tudo certo inteligente          aprovação Meta. Preparar onboarding raio-x.
      F50: Onboarding raio-x               Contar economia em mensagens de vendas.

 14   F42: Painel de economia              Divulgar "R$ X economizados" em grupos WA.
      F48: Relatório mensal do dono        Mostrar relatório bonito em demo comercial.
      F50: Onboarding raio-x (completo)

 15   F36: Ingestão por WhatsApp           Ativar para 10 clientes beta.
                                           "Encaminha o XML no WhatsApp. Pronto."

 16   F36: Refinamento e QA                Coletar depoimentos: "Antes eu levava 2h,
      F42/F46/F48: Ajustes                 agora é automático."
```

#### FASE B — Monitoramento Contínuo (Mês 5-7)

```
SEM   PRODUTO                              AQUISIÇÃO

 17   F37 (Parte 1): Certificado A1        Começar a cobrar R$ 147/mês para clientes
      Upload + cripto + validação          com download automático (tier premium).

 18   F37 (Parte 2): Sefaz WS + fila      "Conecte seu certificado A1 uma vez.
      Download diário funcional            O FiscoPilot puxa suas NF-e sozinho."

 19   F45: Kanban de pendências            Posicionar como "mini-CRM fiscal".
      Drag & drop, comentários, anexos     Mostrar em vídeo demo no WhatsApp.

 20   F41/F65: Monitoramento cadastral     Upsell: "Monitoramos CPNJ de fornecedores.
      Job semanal CNPJ/IE/CNAE            Se um ficar inapto, você sabe na hora."

 21   F45: Refinamento e QA               Lançamento oficial da Fase B.
      F41/F65: Ajustes + deploys          Aumento de preço: R$ 97 → R$ 147.
```

#### FASE C — Inteligência e Ecossistema (Mês 7-9)

```
SEM   PRODUTO                              AQUISIÇÃO

 22   F53-F55: Portal contador (login,     Convidar 5 contadores parceiros.
      dashboard clientes)                  "Você vê todos seus clientes em um lugar."

 23   F56-F58: Comentários + validação +   Contadores testam, validam, recomendam.
      exportação mensal                    Ciclo: contador → recomenda → lojista compra.

 24   F43/F62: Score de fornecedores       "Seus melhores e piores fornecedores."
      View materializada, ranking          Usar como argumento de renovação.

 25   F51/F61: Assistente IA               Botão "Perguntar à IA" em toda inconsistência.
      Chat contextual, guardrails          IA explica, mas nunca calcula imposto.

 26   F51/F61: Refinamento e QA            Coletar feedback da IA (thumbs up/down).
      F43/F62: Ajustes + deploys           Lançamento oficial da Fase C.
```

#### FASE D — Plataforma e Escala (Mês 9-12)

```
SEM   PRODUTO                              AQUISIÇÃO

 27   F39/F44: Verificador CBS/IBS         "Sua loja está pronta para a Reforma
      Score de preparação + checklist      Tributária?" Diferenciação forte.

 28   F38 (Parte 1): Conectores Bling +   "Não precisa fazer upload. O FiscoPilot
      Tiny. OAuth flow + sync engine.      lê as notas do sistema que você já usa."

 29   F40 (Parte 1): Pacotes base + SP/    "Regras específicas para seu setor e
      MG construção + Lucro Presumido      estado." Expansão para novos ICPs.

 30   F38 (Parte 2): Omie + Conta Azul     Custo sobe para R$ 197/mês.
      F40 (Parte 2): Restantes + confecção  Upsell: "Pacote premium com + regras."

 31   F52/F64: Gerenciador pacotes +       Marketplace de pacotes? Contadores criam
      Simulador Reforma Tributária          regras? (explorar modelo de plataforma)

 32   QA geral, otimizações, deploys       Lançamento oficial da Fase D.
      Documentação completa.               Retrospectiva do ano 1.
```

#### Métricas de Sucesso por Fase

| Fase | Meta de clientes | MRR esperado | Preço por cliente |
|---|---|---|---|
| MVP | 10 | R$ 970 | R$ 97/mês |
| Fase A | 20 | R$ 1.940 | R$ 97/mês |
| Fase B | 30 | R$ 4.410 | R$ 147/mês |
| Fase C | 50 | R$ 7.350 | R$ 147/mês |
| Fase D | 80 | R$ 15.760 | R$ 197/mês |

#### Critério de Go/No-Go por Fase

| Marco | Critério | Ação se não atingir |
|---|---|---|
| Antes da Fase B | ≥15 clientes pagantes + NPS ≥40 | Adiar Fase B, focar em vendas |
| Antes da Fase C | ≥25 clientes pagantes + churn <5% | Cortar Fase C features, manter core |
| Antes da Fase D | ≥40 clientes pagantes + time de 3+ devs | Adiar Fase D, contratar antes de expandir |
| Após Fase D | ≥80 clientes + MRR R$ 15k+ | Meta atingida. Avaliar Série A ou bootstrap contínuo |

---

## Etapa 30 — Backlog de Construção

### Objetivo da etapa

Transformar o roadmap de 12 semanas (Etapa 29) em um backlog executável de tarefas de desenvolvimento — organizado por sprint, com estimativas de horas, dependências e responsáveis — totalizando no máximo 720 horas (2 devs × 45 dias úteis × 8h/dia). O backlog é a fonte de verdade para o daily standup e o sprint planning.

### Premissas adotadas

| # | Premissa | Justificativa |
|---|---|---|
| P1 | 1 dia = 8 horas líquidas de desenvolvimento. 45 dias úteis em 12 semanas (considerando reuniões, demo day, imprevistos) | Margem realista: 12 semanas têm ~60 dias úteis; 15 são consumidos por vendas, QA, deploy, documentação |
| P2 | Estimativas em horas, não em story points. Time de 2 pessoas não precisa de abstração de estimativa | Clareza para founder: "isso leva 4h" é mais acionável que "3 story points" |
| P3 | Tarefas de infraestrutura (Docker, CI/CD, VPS) são responsabilidade do founder. Tarefas de regras fiscais são responsabilidade do engenheiro back-end (com revisão do founder) | Divisão baseada em expertise: founder conhece DevOps; engenheiro foca em lógica de negócio |
| P4 | Cada tarefa tem exatamente 1 critério de aceitação binário e testável. Tarefas ambíguas são quebradas em subtarefas | Evita "90% pronto" por 3 semanas. Tarefa está pronta ou não está |
| P5 | Ordem das tarefas dentro do sprint segue dependências. Tarefas sem dependência são paralelizáveis entre os 2 devs | Maximiza throughput: enquanto engenheiro faz parser, founder faz auth |

### Análise

O backlog totaliza **706 horas** contra um teto de **720 horas**, com **14 horas de folga**. A distribuição por sprint segue a cadência da Etapa 29:

| Sprint | Semanas | Horas | Foco |
|---|---|---|---|
| Sprint 1 | 1-2 | 128h | Auth, Upload, Parser, Validações básicas |
| Sprint 2 | 3-4 | 128h | 8 Regras fiscais, Cache referências |
| Sprint 3 | 5-6 | 128h | Dashboard, Detalhe nota, E-mail ingest, Checklist |
| Sprint 4 | 7-8 | 128h | PDF, WhatsApp notify, Deploy staging, Beta |
| Sprint 5 | 9-10 | 104h | Correções beta, Features P1, Primeira venda |
| Sprint 6 | 11-12 | 90h | QA, Polish, Deploy prod, Features P2 |
| **Total** | | **706h** | |

### Decisões recomendadas

| Decisão | Conteúdo | Status |
|---|---|---|
| D1 | 57 tarefas organizadas em 6 sprints. Cada tarefa com ID no formato `S{1-6}-{NN}` | Decisão de organização |
| D2 | Responsável: F = Founder, E = Engenheiro. Tarefas com F+E exigem pareamento | Decisão de alocação |
| D3 | Estimativas em horas. Tarefas >16h são quebradas em subtarefas | Decisão de granularidade |
| D4 | Ordem de prioridade: P0 → P1 → P2. Se buffer estourar, cortar P2 primeiro, depois P1 na ordem inversa | Decisão de contingência |
| D5 | Critério de aceitação único por tarefa. Formato: "DADO [contexto] QUANDO [ação] ENTÃO [resultado]" | Decisão de qualidade |

---

### Entregáveis

#### SPRINT 1 — Fundação (Semanas 1-2, 128h)

```
┌──────┬────────────────────────────────┬────────┬──────┬──────────────┬─────────────────────────────────────────────┐
│  ID  │ Tarefa                          │   Hrs  │ Resp │ Dependências │ Critério de Aceitação                       │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S1-01│ Inicializar monorepo            │    4h  │  F   │ —            │ pnpm dev inicia web (:3000) + api (:3001)   │
│      │ (Turborepo + pnpm workspaces)   │        │      │              │ com hot reload. TypeScript strict mode.     │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S1-02│ Configurar ESLint + Prettier    │    3h  │  F   │ S1-01        │ pnpm lint passa sem erros. Husky pre-commit │
│      │ + Husky + commitlint            │        │      │              │ roda lint-staged.                           │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S1-03│ Setup PostgreSQL + Drizzle      │    6h  │  E   │ S1-01        │ docker compose up postgres. drizzle-kit     │
│      │ (schema, migrations)            │        │      │              │ push cria todas as tabelas.                 │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S1-04│ Implementar organizações        │    4h  │  E   │ S1-03        │ POST /api/v1/admin/organizations cria       │
│      │ (CRUD admin)                    │        │      │              │ tenant. GET retorna dados. UUID gerado.     │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S1-05│ Implementar usuários            │    4h  │  E   │ S1-04        │ POST /api/v1/admin/users cria usuário       │
│      │ (CRUD admin)                    │        │      │              │ vinculado a organization.                   │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S1-06│ Magic link — POST /auth/        │    5h  │  F   │ S1-05        │ POST com whatsapp válido → 200. Token      │
│      │ magic-link (gerar + enviar)     │        │      │              │ armazenado (SHA-256). WhatsApp API chamada. │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S1-07│ Magic link — GET /auth/verify   │    4h  │  F   │ S1-06        │ GET ?token= → JWT válido (7d). Token       │
│      │ (verificar + JWT)               │        │      │              │ single-use. used_at setado.                 │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S1-08│ Middleware de autenticação       │    3h  │  F   │ S1-07        │ Rotas protegidas rejeitam sem JWT (401).    │
│      │ (JWT verify + org context)      │        │      │              │ X-Organization-Id validado contra JWT.      │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S1-09│ Middleware de autorização        │    2h  │  F   │ S1-08        │ OPERADOR acessa /admin/* → 403.             │
│      │ (role-based: ADMIN/OPERADOR)    │        │      │              │ ADMIN acessa tudo.                          │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S1-10│ Rate limiting (@fastify/        │    3h  │  F   │ S1-08        │ 60 req/min global retorna 429. 3 tentativas │
│      │ rate-limit)                     │        │      │              │ /auth/magic-link/15min por número.          │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S1-11│ Tela T7 — Login (link mágico)   │    6h  │  F   │ S1-06        │ Tela com campo WhatsApp + botão enviar.     │
│      │                                  │        │      │              │ Estados: enviado, expirado, erro, sucesso.  │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S1-12│ Página de callback (verify)     │    3h  │  F   │ S1-07,S1-11 │ GET /auth/verify?token= redireciona para    │
│      │ + armazenar JWT no front        │        │      │              │ dashboard. JWT em localStorage.             │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S1-13│ POST /api/v1/upload —           │    5h  │  F   │ S1-08       │ Upload de arquivo único via multipart.      │
│      │ receber arquivo (multipart)     │        │      │              │ Arquivo salvo em /tmp. Retorna batch_id.    │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S1-14│ POST /api/v1/upload —           │    4h  │  F   │ S1-13       │ Upload de múltiplos arquivos e ZIP.         │
│      │ múltiplos arquivos + ZIP        │        │      │              │ ZIP extraído com archiver.                  │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S1-15│ Tela T2 — Upload (interface)    │    8h  │  F   │ S1-14       │ Drop zone funcional. Barra de progresso.    │
│      │ (drop zone + progresso)         │        │      │              │ Estados: pronto, processando, concluído.    │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S1-16│ Estágio 2 — Validate            │    4h  │  E   │ S1-13       │ Arquivos inválidos ignorados. Extensão e    │
│      │ (extensão, tamanho, magic bytes)│        │      │              │ tamanho validados. ZIP integrity check.     │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S1-17│ Estágio 3 — Extract             │    5h  │  E   │ S1-16       │ ZIP extraído → .xml files listados.         │
│      │ (archiver, list flat)           │        │      │              │ Máximo 200 XMLs. Ordem alfabética.          │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S1-18│ Estágio 4 — Parser básico       │    8h  │  E   │ S1-17       │ fast-xml-parser converte XML → JSON.        │
│      │ (fast-xml-parser + extração)    │        │      │              │ Chave de acesso extraída. Namespace NF-e.   │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S1-19│ Estágio 4 — Validações XML      │    6h  │  E   │ S1-18       │ Dígito verificador validado (módulo 11).    │
│      │ (DV, status NFe, campos obrig.) │        │      │              │ Nota cancelada/denegada → ignorada.         │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S1-20│ Estágio 4 — Extrair NfeJson     │    8h  │  E   │ S1-19       │ Todos os campos do schema extraídos.        │
│      │ (todos os campos + itens)       │        │      │              │ Itens com NCM, CFOP, valores individuais.   │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S1-21│ Anti-XXE (rejeitar DTD/ENTITY)  │    2h  │  E   │ S1-18       │ XML com <!DOCTYPE → rejeitado.              │
│      │                                  │        │      │              │ XML com <!ENTITY → rejeitado.               │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S1-22│ Testar parser contra 200 XMLs   │    4h  │  E   │ S1-20       │ Script roda 200 XMLs. Taxa de parse ≥ 95%.  │
│      │ reais (script de benchmark)     │        │      │              │ Log de falhas por tipo de erro.             │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S1-23│ R7 — Chave de acesso (regra)    │    3h  │  E   │ S1-19       │ Chave com DV inválido → score 100.          │
│      │                                  │        │      │              │ Chave válida → null.                        │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S1-24│ R5 — Valor total vs itens       │    3h  │  E   │ S1-20       │ Soma itens ≠ total → score 60 (<5%) /      │
│      │ (regra)                         │        │      │              │ 90 (≥5%). Tolerância R$ 0,05.              │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S1-25│ Tela T8 — Perfil (admin/op)     │    4h  │  F   │ S1-05       │ Visão admin: equipe + loja + conta.         │
│      │                                  │        │      │              │ Visão operador: sem seção equipe.           │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S1-26│ Dockerfile (api + web)           │    6h  │  F   │ S1-01       │ docker compose up sobe tudo. Healthcheck    │
│      │ + docker-compose.yml            │        │      │              │ /api/v1/health retorna 200.                 │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S1-27│ Testes unitários — auth +       │    6h  │  F   │ S1-06,S1-13 │ Vitest: ≥80% coverage em auth e upload.     │
│      │ upload (Vitest)                 │        │      │              │ Todos os cenários de erro cobertos.          │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│      │ **TOTAL SPRINT 1**              │**128h**│      │              │                                              │
└──────┴────────────────────────────────┴────────┴──────┴──────────────┴─────────────────────────────────────────────┘
```

---

#### SPRINT 2 — Regras Fiscais (Semanas 3-4, 128h)

```
┌──────┬────────────────────────────────┬────────┬──────┬──────────────┬─────────────────────────────────────────────┐
│  ID  │ Tarefa                          │   Hrs  │ Resp │ Dependências │ Critério de Aceitação                       │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S2-01 │ FiscalReferenceCache —         │    5h  │  E   │ S1-03       │ Cache carrega tabelas do banco no startup.  │
│       │ load from PostgreSQL           │        │      │              │ cfopTable.size ≥ 500. ncmSet.size ≥ 200.   │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S2-02 │ Seed scripts — CFOP + NCM +   │    6h  │  E   │ S2-01       │ pnpm db:seed popula fiscal_reference_tables │
│       │ alíquotas + ST                 │        │      │              │ com dados reais. is_active = true.          │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S2-03 │ R1 — CFOP divergente           │    8h  │  E   │ S2-01       │ CFOP 6102 em entrada Simples → score 85.    │
│       │ (regra completa)               │        │      │              │ CFOP 1102 em entrada Simples → null.        │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S2-04 │ R2 — Alíquota ICMS divergente  │    6h  │  E   │ S2-02       │ Alíquota 18% SP→SP (esperado 12%) →         │
│       │ (regra completa)               │        │      │              │ score 70. Alíquota 12% → null.              │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S2-05 │ R3 — NCM suspeito              │    5h  │  E   │ S2-02       │ NCM 0201 (carne) para material constr. →    │
│       │ (regra completa)               │        │      │              │ score 50. NCM 2523 (cimento) → null.       │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S2-06 │ R6 — CST incompatível          │    4h  │  E   │ S1-20       │ CST inválido para Simples → score 50.       │
│       │ (regra completa)               │        │      │              │ CST 49 (válido) → null.                     │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S2-07 │ R4 — CNPJ situação cadastral   │    6h  │  E   │ S2-01       │ CNPJ BAIXADO → score 100. CNPJ SUSPENSO →  │
│       │ (regra completa)               │        │      │              │ score 80. CNPJ ATIVO → null.                │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S2-08 │ R8 — ICMS ST indevido          │    6h  │  E   │ S2-02       │ ST para NCM fora da lista → score 75.       │
│       │ (regra completa)               │        │      │              │ ST para NCM na lista → null.                │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S2-09 │ RuleEngine — evaluateAll()     │    4h  │  E   │ S2-03 a     │ engine.evaluateAll(nfe) → RuleResult[].     │
│       │ (orquestração das 8 regras)    │        │      │ S2-08       │ Ordenado por score decrescente.             │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S2-10 │ RuleEngine — integração no     │    4h  │  E   │ S2-09       │ Estágio 7 do pipeline chama evaluateAll.    │
│       │ pipeline (estágio 7 dispatch)  │        │      │              │ Inconsistências persistidas no banco.       │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S2-11 │ explanation_text — templates   │    6h  │  E   │ S2-03 a     │ fillExplanationTemplate('R1_CFOP_SAIDA',    │
│       │ (fillTemplate + R1-R8)         │        │      │ S2-08       │ vars) retorna texto preenchido com dados.   │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S2-12 │ checklist_json — templates     │    4h  │  E   │ S2-11       │ R1 checklist tem 4 passos. R5 tem 3.        │
│       │ (por regra)                    │        │      │              │ JSON array [{order, text, done: false}].    │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S2-13 │ Estágio 5 — Dedup             │    3h  │  E   │ S1-20       │ Chave duplicada no mesmo tenant → ignorada. │
│       │ (chave de acesso única)        │        │      │              │ Chave nova → processada.                    │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S2-14 │ Estágio 6 — Store (INSERT      │    8h  │  E   │ S1-20,S2-10 │ Transação: nfe_documents + nfe_items +      │
│       │ transacional + XML em disco)   │        │      │              │ audit_log. Rollback em caso de erro.        │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S2-15 │ Testes unitários — 8 regras    │   12h  │  E   │ S2-03 a     │ Vitest: cada regra com ≥5 cenários (válido, │
│       │ (Vitest)                       │        │      │ S2-08       │ inválido, borda, campo nulo, regime diff).  │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S2-16 │ Testar regras vs 200 XMLs      │    4h  │  E   │ S2-09       │ Script roda engine contra 200 XMLs reais.   │
│       │ reais (validação de detecção)  │        │      │              │ Taxa de detecção ≥ 5% (≥10 inconsistências).│
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S2-17 │ Tela T1 — Dashboard (cards +   │   10h  │  F   │ S2-10       │ Cards OK/Atenção/Risco com contagem real.   │
│       │ resumo + lista inconsistências)│        │      │              │ Lista de inconsistências ordenada. Mobile.  │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S2-18 │ GET /api/v1/dashboard          │    5h  │  E   │ S2-10       │ Query agrega inconsistências por            │
│       │ (agregação + filtros)          │        │      │              │ classificação. Retorna JSON no formato Et20.│
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S2-19 │ Estados de UI — vazio, loading,│    6h  │  F   │ S2-17       │ Skeleton shimmer no loading. Estado vazio   │
│       │ erro (T1)                      │        │      │              │ com CTA. Estado erro com botão retry.       │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S2-20 │ F05 — Indicador de             │    3h  │  F   │ S1-15       │ Barra de progresso real durante upload.     │
│       │ processamento (loading real)   │        │      │              │ Atualiza a cada nota processada (>10 notas).│
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S2-21 │ F33 — Papéis e permissões      │    3h  │  F   │ S1-09       │ Admin vê seção Equipe em T8. Operador não.  │
│       │ (front-end + back-end checks)  │        │      │              │ Endpoints admin retornam 403 para operador. │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S2-22 │ Cache auto-refresh (24h)       │    2h  │  E   │ S2-01       │ setInterval de 24h chama cache.refresh().   │
│       │ + POST /admin/refresh-cache    │        │      │              │ Endpoint manual também funciona.            │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S2-23 │ Circuit breaker LLM (prep.)    │    2h  │  F   │ —            │ LlmCircuitBreaker: 5 falhas → 5min off.     │
│       │                                  │        │      │              │ Teste unitário cobre abertura e fechamento. │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S2-24 │ Seed CNPJ cache (opcional)     │    3h  │  E   │ S2-07       │ Script popula cnpjCache com CNPJs           │
│       │                                  │        │      │              │ irregulares. R4 retorna null se cache vazio.│
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S2-25 │ Teste de integração — pipeline │    3h  │  F   │ S2-14       │ Supertest: POST /upload com ZIP de 10       │
│       │ completo (upload → inconsist.) │        │      │              │ XMLs → 200. Response contém inconsistências.│
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│       │ **TOTAL SPRINT 2**              │**128h**│      │              │                                              │
└──────┴────────────────────────────────┴────────┴──────┴──────────────┴─────────────────────────────────────────────┘
```

---

#### SPRINT 3 — Dashboard e Jornada Completa (Semanas 5-6, 128h)

```
┌──────┬────────────────────────────────┬────────┬──────┬──────────────┬─────────────────────────────────────────────┐
│  ID  │ Tarefa                          │   Hrs  │ Resp │ Dependências │ Critério de Aceitação                       │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S3-01 │ GET /api/v1/notes (lista)      │    6h  │  E   │ S2-14       │ Paginação cursor-based. Filtros: mes,       │
│       │                                  │        │      │              │ classification, status, search. Ordenação.  │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S3-02 │ GET /api/v1/notes/:id          │    6h  │  E   │ S3-01       │ Retorna NfeJson completo + inconsistências  │
│       │ (detalhe + itens + inconsist.) │        │      │              │ + itens. JOIN com nfe_items e inconsist.    │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S3-03 │ GET /api/v1/notes/:id/         │    3h  │  E   │ S3-02       │ Retorna apenas inconsistências da nota.     │
│       │ inconsistencies                │        │      │              │ Atalho para T5 sem carregar nota inteira.   │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S3-04 │ GET /api/v1/inconsistencies    │    5h  │  E   │ S2-10       │ Lista com filtros: mes, classification,     │
│       │ (lista)                        │        │      │              │ status, rule_id. Paginação cursor-based.    │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S3-05 │ GET /api/v1/inconsistencies/   │    5h  │  E   │ S3-04       │ Detalhe completo + checklist + histórico    │
│       │ :id (detalhe + checklist +     │        │      │              │ (audit_log JOIN). nfe embutida.             │
│       │ histórico)                     │        │      │              │                                              │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S3-06 │ PATCH /api/v1/inconsistencies/ │    5h  │  E   │ S3-05       │ Atualiza status, checklist, ignore_reason.  │
│       │ :id (status, checklist, motivo)│        │      │              │ Validação: IGNORADA exige motivo.           │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S3-07 │ Tela T3 — Lista de notas       │    8h  │  F   │ S3-01       │ Scroll infinito. Filtro por mês. Indicador   │
│       │ (scroll infinito + filtros)    │        │      │              │ de risco (🔴⚠️✅). Busca por fornecedor.     │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S3-08 │ Tela T4 — Detalhe da nota      │    8h  │  F   │ S3-02       │ Dados da nota + lista de inconsistências +   │
│       │ (dados + inconsistências)      │        │      │              │ itens. Tooltips "O que significa CFOP?".    │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S3-09 │ Tela T5 — Detalhe da           │   10h  │  F   │ S3-06       │ Seções: o que aconteceu, o que significa,    │
│       │ inconsistência + checklist     │        │      │              │ o que fazer. Checklist interativo. Status    │
│       │ + histórico                    │        │      │              │ dropdown. Histórico de ações.               │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S3-10 │ F03 — Ingestão via e-mail      │    8h  │  F   │ S1-14       │ Postfix configurado. Pipe para script Node. │
│       │ (Postfix + email-receiver.js)  │        │      │              │ E-mail com XML → pipeline normal.           │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S3-11 │ F22 — Status da inconsistência │    5h  │  F   │ S3-09       │ Dropdown: Pendente, Em andamento, Resolvida,│
│       │ (UI interativa)                │        │      │              │ Ignorada. Ignorada expande campo motivo.    │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S3-12 │ F28 — Relatório do contador    │    8h  │  E   │ S3-02       │ GET /api/v1/report/pdf?mes=YYYY-MM → PDF.   │
│       │ (pdfkit + endpoint)            │        │      │              │ Conteúdo: resumo + tabela inconsistências.  │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S3-13 │ Tela T6 — Relatório do         │    6h  │  F   │ S3-12       │ Preview do mês + botão download PDF +       │
│       │ contador (UI + preview)        │        │      │              │ botão enviar WhatsApp (mensagem pré-preench).│
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S3-14 │ GET /api/v1/upload/batches     │    4h  │  E   │ S1-14       │ Histórico de uploads com paginação.         │
│       │ (histórico)                    │        │      │              │ Dados: data, status, qtd notas, usuário.    │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S3-15 │ Tela T9 — Histórico de         │    4h  │  F   │ S3-14       │ Lista agrupada por mês. Status colorido.    │
│       │ uploads (UI)                   │        │      │              │ Toque no item → navega para dashboard.      │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S3-16 │ F06 — Histórico de uploads     │    3h  │  F   │ S3-15       │ Últimos 10 uploads visíveis na T2.          │
│       │ (seção na T2)                  │        │      │              │ Dados: data, qtd notas, status, pontos.     │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S3-17 │ RLS — testar isolamento        │    4h  │  E   │ S2-14       │ Tenant A não acessa dados de Tenant B.      │
│       │ multi-tenant (testes e2e)      │        │      │              │ Teste: Supertest com 2 organizações.        │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S3-18 │ Auditoria — INSERT audit_log   │    6h  │  E   │ S2-14,S3-06 │ Todos os 14 eventos registrados. Trigger    │
│       │ em todos os eventos + trigger  │        │      │              │ bloqueia UPDATE/DELETE.                     │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S3-19 │ Testes e2e — Playwright        │   10h  │  F   │ S3-01 a     │ Jornada principal: login → upload →         │
│       │ (jornada completa)             │        │      │ S3-09       │ dashboard → detalhe → checklist → PDF.      │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S3-20 │ Nginx + SSL (certbot) +        │    4h  │  F   │ S1-26       │ HTTPS ativo. HSTS header presente.          │
│       │ security headers               │        │      │              │ Redireciona HTTP → HTTPS.                   │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│       │ **TOTAL SPRINT 3**              │**128h**│      │              │                                              │
└──────┴────────────────────────────────┴────────┴──────┴──────────────┴─────────────────────────────────────────────┘
```

---

#### SPRINT 4 — Notificações e Beta (Semanas 7-8, 128h)

```
┌──────┬────────────────────────────────┬────────┬──────┬──────────────┬─────────────────────────────────────────────┐
│  ID  │ Tarefa                          │   Hrs  │ Resp │ Dependências │ Critério de Aceitação                       │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S4-01 │ WhatsApp Business API — setup  │    6h  │  F   │ —            │ Conta verificada. Templates submetidos:     │
│       │ (Meta developer account +      │        │      │              │ W1-W6. Webhook configurado.                 │
│       │ templates)                     │        │      │              │                                              │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S4-02 │ F25 — W1 Resumo semanal        │    6h  │  F   │ S4-01       │ Cron job: segunda 8h. Mensagem enviada com  │
│       │ (cron job + envio)             │        │      │              │ link mágico. Dados reais do dashboard.      │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S4-03 │ F26 — W2 Alerta risco alto     │    5h  │  F   │ S4-01,S2-10 │ Score ≥70 → alerta imediato. Máximo 1/hora. │
│       │ (imediato pós-processamento)   │        │      │              │ Template preenchido com dados da nota.      │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S4-04 │ F27 — W5 Silêncio positivo     │    3h  │  F   │ S4-01       │ Segunda com 0 inconsistências → W5 enviada. │
│       │ (semanal sem inconsistências)  │        │      │              │ Tom tranquilizador.                          │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S4-05 │ W4 — Lembrete de pendências    │    4h  │  F   │ S4-01,S3-06 │ Quinta 14h. Só se pendente ≥3 dias com      │
│       │ (cron job quinta-feira)        │        │      │              │ score ≥70. "O mês está acabando".           │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S4-06 │ W3 + W6 — Upload concluído +   │    4h  │  F   │ S4-01       │ W3 enviada após upload. W6 com link mágico  │
│       │ convite equipe                 │        │      │              │ para novo usuário.                           │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S4-07 │ pending_notifications —        │    5h  │  E   │ S4-02 a     │ INSERT na tabela. Retry: 1min, 5min, 15min, │
│       │ fila de retry                  │        │      │ S4-06       │ 1h. Máximo 5 tentativas. Status: PENDING →  │
│       │                                  │        │      │              │ SENT ou FAILED.                             │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S4-08 │ F23 — Filtro por período       │    4h  │  F   │ S3-07       │ Seletor de mês no dashboard e lista de      │
│       │ (UI + query)                   │        │      │              │ notas. Padrão: mês atual.                    │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S4-09 │ F24 — Busca por fornecedor     │    4h  │  F   │ S3-01       │ Campo de busca textual. ILIKE com índice    │
│       │ (UI + query ILIKE)             │        │      │              │ GIN trigram. Resultados parciais.           │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S4-10 │ F34 — Log de auditoria (UI)    │    6h  │  F   │ S3-18       │ Tela exclusiva ADMIN. Lista eventos         │
│       │ — endpoint + tela              │        │      │              │ filtráveis. GET /api/v1/admin/audit-log.    │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S4-11 │ F35 — Log de processamento     │    3h  │  E   │ S3-18       │ Eventos de sistema: NFE_PROCESSED,          │
│       │ (eventos do pipeline)          │        │      │              │ NFE_REJECTED, UPLOAD_COMPLETED.             │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S4-12 │ Deploy staging — VPS +         │    8h  │  F   │ S3-20       │ staging.copilotofiscal.com online. HTTPS.   │
│       │ domínio + CI/CD (GitHub Actions)│       │      │              │ Push na branch staging → deploy automático. │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S4-13 │ Backup — pg_dump → S3          │    4h  │  F   │ S4-12       │ Cron job diário. Backup restaurado com      │
│       │ (script + cron)                │        │      │              │ sucesso em teste. Retenção configurada.     │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S4-14 │ Teste de carga — 200 XMLs      │    4h  │  F   │ S4-12       │ Script envia ZIP com 200 XMLs. Tempo total  │
│       │ (benchmark na VPS real)        │        │      │              │ <60s. Sem OOM. Sem timeout.                 │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S4-15 │ Correções de bugs (staging)    │   12h  │ F+E  │ S4-12       │ Bugs críticos corrigidos. Regressão testada.│
│       │                                  │        │      │              │ Zero bugs P0 em staging.                    │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S4-16 │ LlmParaphraser — implementar   │    6h  │  F   │ S2-23,S2-11 │ Feature flag ENABLE_LLM_PARAPHRASE=false.   │
│       │ (OpenRouter + fallback)        │        │      │              │ Se true, chama GPT-4o-mini após explicação. │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S4-17 │ LlmParaphraser — auditoria     │    3h  │  F   │ S4-16       │ LLM_PARAPHRASE_GENERATED no audit_log.      │
│       │ (audit_log + métricas)         │        │      │              │ Prompt, resposta, latência registrados.     │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S4-18 │ Onboarding — preparar guia     │    4h  │  F   │ —            │ PDF 1 página: "Como usar o Copiloto".       │
│       │ rápido (PDF + script)          │        │      │              │ Screenshots. Enviado por WhatsApp.          │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S4-19 │ Uptime Robot + Sentry setup    │    3h  │  F   │ S4-12       │ Monitorando /api/v1/health. Alerta e-mail   │
│       │                                  │        │      │              │ se downtime. Erros JS no Sentry.            │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S4-20 │ Checklist LGPD — revisão final │    4h  │  F   │ S4-12       │ RLS ativo? Dados pessoais mapeados? Canal   │
│       │                                  │        │      │              │ de direitos? Termos de Uso no app?          │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S4-21 │ 🚀 BETA — ativar 5 lojas      │   16h  │  F   │ S4-12       │ Onboarding guiado de 5 lojas (3h cada +     │
│       │ (onboarding + suporte inicial) │        │      │              │ follow-up). Upload real. Dashboard com dados│
│       │                                  │        │      │              │ reais. Zero bugs críticos em 48h.           │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│       │ **TOTAL SPRINT 4**              │**128h**│      │              │                                              │
└──────┴────────────────────────────────┴────────┴──────┴──────────────┴─────────────────────────────────────────────┘
```

---

#### SPRINT 5 — Correções e Primeiras Vendas (Semanas 9-10, 104h)

```
┌──────┬────────────────────────────────┬────────┬──────┬──────────────┬─────────────────────────────────────────────┐
│  ID  │ Tarefa                          │   Hrs  │ Resp │ Dependências │ Critério de Aceitação                       │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S5-01 │ Correção de bugs P0 (beta)     │   20h  │ F+E  │ Beta fdbk   │ Zero bugs P0. Issues do beta fechadas.      │
│       │                                  │        │      │              │ Regressão testada.                           │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S5-02 │ Melhorias de UX (beta          │   16h  │  F   │ Beta fdbk   │ 3 melhorias pedidas pelos beta testers.     │
│       │ feedback)                      │        │      │              │ Ex.: botão maior, texto mais claro, etc.    │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S5-03 │ F03 — Ingestão via e-mail      │    8h  │  F   │ S3-10       │ Se não concluído no Sprint 3. Teste com     │
│       │ (se não feito)                 │        │      │              │ e-mail real. Resposta automática E1.         │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S5-04 │ F25-F27 — WhatsApp notify      │   12h  │  F   │ S4-02 a     │ Se não concluído no Sprint 4. Templates     │
│       │ (se não feito)                 │        │      │ S4-04       │ aprovados. Mensagens chegando.               │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S5-05 │ Performance — otimizar parser  │    8h  │  E   │ S4-14       │ Se benchmark >60s: otimizar loops, usar     │
│       │ (se benchmark >60s)            │        │      │              │ streaming, paralelizar regras.               │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S5-06 │ E2 — E-mail de processamento   │    4h  │  F   │ S5-03       │ E2 enviado após upload por e-mail. Template │
│       │ concluído                      │        │      │              │ com/sem inconsistências.                     │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S5-07 │ Get /api/v1/ui-messages        │    3h  │  F   │ S3-07 a     │ Endpoint retorna UI_STATES como JSON.       │
│       │ (centralizar textos do front)  │        │      │ S3-09       │ Front consome via react-query.              │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S5-08 │ Testes de regressão —          │    8h  │  E   │ S5-01       │ Playwright: jornada completa após correções.│
│       │ funcionalidades existentes     │        │      │              │ Nenhum teste quebrado pelas alterações.     │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S5-09 │ Feature extra — mais pedida    │   10h  │ F+E  │ Beta fdbk   │ 1 feature sugerida pelos beta testers que   │
│       │ pelos beta testers             │        │      │              │ tenha alto impacto e baixo esforço.         │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S5-10 │ 💰 CALLS DE CONVERSÃO          │   15h  │  F   │ S5-01       │ 5 calls de 3h cada (preparação + call +     │
│       │ (vendas — founder)             │        │      │              │ follow-up). Meta: ≥3 conversões.            │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│       │ **TOTAL SPRINT 5**              │**104h**│      │              │                                              │
└──────┴────────────────────────────────┴────────┴──────┴──────────────┴─────────────────────────────────────────────┘
```

---

#### SPRINT 6 — QA, Deploy e Features P2 (Semanas 11-12, 90h)

```
┌──────┬────────────────────────────────┬────────┬──────┬──────────────┬─────────────────────────────────────────────┐
│  ID  │ Tarefa                          │   Hrs  │ Resp │ Dependências │ Critério de Aceitação                       │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S6-01 │ QA completo — todas as 27      │   20h  │ F+E  │ S5-01       │ Checklist QA preenchido. 16 P0 + 7 P1 +    │
│       │ funcionalidades                │        │      │              │ 4 P2 testadas. Bugs encontrados corrigidos. │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S6-02 │ Playwright e2e — jornadas      │   12h  │  F   │ S6-01       │ Cobre: login → upload → dashboard →        │
│       │ críticas                       │        │      │              │ detalhe inconsistência → checklist → PDF.   │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S6-03 │ Security review — OWASP        │    8h  │  F   │ S6-01       │ Top 10 verificado. Headers HTTP corretos.   │
│       │ checklist                      │        │      │              │ Sem vulnerabilidades HIGH/CRITICAL.         │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S6-04 │ Performance — Lighthouse       │    4h  │  F   │ S6-01       │ Mobile score ≥80. LCP <2.5s. FCP <1.8s.    │
│       │ + Core Web Vitals              │        │      │              │ Sem blocking requests.                       │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S6-05 │ Deploy produção                │    8h  │  F   │ S6-01       │ app.copilotofiscal.com online. HTTPS ativo. │
│       │ (app.copilotofiscal.com)       │        │      │              │ CI/CD: push tag → deploy prod.              │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S6-06 │ Backup restore — teste real    │    4h  │  F   │ S6-05       │ Restaurar backup em VPS limpa. App sobe     │
│       │                                  │        │      │              │ com todos os dados. RTO <2h.                │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S6-07 │ Documentação — runbook de      │    6h  │  F   │ S6-05       │ Documento com: setup VPS, deploy, rollback, │
│       │ operações                      │        │      │              │ backup restore, troubleshooting comum.     │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S6-08 │ Documentação — onboarding de   │    4h  │ F+E  │ S6-01       │ README.dev.md: como rodar local, estrutura  │
│       │ dev                            │        │      │              │ do projeto, convenções, scripts.            │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S6-09 │ F24 — Busca por fornecedor     │    4h  │  F   │ S4-09       │ Se não concluído no Sprint 4. Campo busca   │
│       │ (se não feito)                 │        │      │              │ textual na T3. ILIKE com índice GIN.        │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S6-10 │ F06 — Histórico na T2          │    3h  │  F   │ S3-16       │ Se não concluído no Sprint 3. Lista dos     │
│       │ (se não feito)                 │        │      │              │ últimos uploads com status.                │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S6-11 │ Feature P2 — mais votada       │   12h  │  E   │ —            │ 1 feature P2 sugerida por clientes pagantes.│
│       │                                  │        │      │              │ Ex.: exportar CSV, dark mode, etc.          │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│ S6-12 │ Retrospectiva + planejamento   │    5h  │ F+E  │ S6-05       │ Documento de aprendizados. Métricas finais. │
│       │ Fase 2                         │        │      │              │ Decisão go/no-go. Prioridades Fase 2.       │
├──────┼────────────────────────────────┼────────┼──────┼──────────────┼─────────────────────────────────────────────┤
│       │ **TOTAL SPRINT 6**              │ **90h** │      │              │                                              │
└──────┴────────────────────────────────┴────────┴──────┴──────────────┴─────────────────────────────────────────────┘
```

---

#### Resumo de Horas por Sprint

```
┌──────────────────────────────────────────────────────────────────┐
│                    DISTRIBUIÇÃO DE HORAS                          │
│                                                                    │
│  Sprint 1 (Sem 1-2):  ████████████████████████████  128h (18%)   │
│  Sprint 2 (Sem 3-4):  ████████████████████████████  128h (18%)   │
│  Sprint 3 (Sem 5-6):  ████████████████████████████  128h (18%)   │
│  Sprint 4 (Sem 7-8):  ████████████████████████████  128h (18%)   │
│  Sprint 5 (Sem 9-10): ██████████████████████        104h (15%)   │
│  Sprint 6 (Sem 11-12):███████████████████             90h (13%)   │
│  ─────────────────────────────────────────────────────────────  │
│  TOTAL:                                                706h      │
│  TETO MÁXIMO:                                          720h      │
│  FOLGA:                                                 14h      │
│                                                                    │
│  Responsável:                                                      │
│  Founder  (F):  ~370h (52%)                                        │
│  Engenheiro (E): ~285h (40%)                                      │
│  Pareamento (F+E): ~51h (7%)                                      │
│                                                                    │
│  Carga semanal média:                                              │
│  Founder:  31h/semana (código) + ~15h/semana (vendas/aquisição)   │
│  Engenheiro: 24h/semana (código) + QA                             │
└──────────────────────────────────────────────────────────────────┘
```

### Riscos e pontos de atenção

| Risco | Severidade | Mitigação |
|---|---|---|
| Sprint 1 (128h) é o mais denso — 27 tarefas. Se parser for complexo, pode estourar | Alta | S1-22 (teste com 200 XMLs) é gate: se parser falhar, priorizar correções sobre features novas. Buffer de 2 dias no sprint |
| Sprint 4 depende de aprovação de templates do WhatsApp (Meta) — pode atrasar semanas | Média | Submeter templates na S4-01 (semana 7). Se não aprovados até semana 8, fallback: founder envia notificações manuais |
| Sprint 5 assume 60% de conversão de beta → pago. Se for 0%, as horas de venda (S5-10) viram horas de pivot | Crítico | Se 0 conversões, S5-10 (15h) é redirecionado para: pesquisar motivo, ajustar produto, tentar novo ICP |
| Engenheiro back-end com 40% das horas pode ter gargalo em sprints com muitas tarefas sequenciais (Sprint 1-2) | Média | Founder cobre tarefas de front-end enquanto engenheiro foca no core. Pareamento em tarefas críticas (parser, regras) |
| Estimativas podem estar erradas em 20-30% (otimismo de planejamento) | Média | 14h de folga cobre ~2% de erro. Se estourar, cortar P2 no Sprint 6 (S6-09, S6-10, S6-11 = 19h economizadas) |

---

## Etapa 31 — QA e Validação

### Objetivo da etapa

Definir a estratégia completa de quality assurance para o FiscoPilot MVP — testes automatizados (unitários, integração, e2e), checklist de validação pré-lançamento, cenários de teste críticos, critérios de aceitação para beta e produção, e plano de testes com usuários reais. O objetivo é garantir que o produto funcione, seja seguro, rápido e compreensível para o Roberto.

### Premissas adotadas

| # | Premissa | Justificativa |
|---|---|---|
| P1 | Pirâmide de testes: 60% unitários (Vitest), 25% integração (Supertest), 15% e2e (Playwright) | Custo-benefício: unitários são rápidos e previnem regressão; e2e cobrem jornadas críticas |
| P2 | Cobertura mínima: 80% para módulos críticos (parser, rule engine, auth). 60% para suporte (dashboard, notas, notificações) | Parser e regras não podem ter bug silencioso |
| P3 | Testes de carga antes do beta (semana 7): benchmark 200 XMLs na VPS real | Validar promessa de <60s em condições reais |
| P4 | Testes de usabilidade com 3 lojistas antes do beta (semana 5) | Validar que o Roberto entende o dashboard sem explicação |
| P5 | QA contínuo: todo PR roda lint + typecheck + unit + integration tests no CI | Bloqueia regressão antes do staging |

### Análise

A estratégia de QA do FiscoPilot tem um desafio específico: **os bugs mais graves não são crashes, são falsos positivos/negativos nas regras fiscais**. Um falso positivo corrói confiança. Um falso negativo gera falsa sensação de segurança. Ambos são piores que um erro 500. Por isso, a camada mais importante são os testes unitários das 8 regras com XMLs reais anonimizados.

O segundo desafio é testar no dispositivo real do Roberto: Android 8-10, Chrome desatualizado, tela 360px, 3G. Testes no Playwright emulando essas condições são obrigatórios antes do beta.

### Decisões recomendadas

| Decisão | Conteúdo | Status |
|---|---|---|
| D1 | 3 camadas: unitário (Vitest, ≥80% mods críticos), integração (Supertest, 14 endpoints), e2e (Playwright, 3 jornadas) | Decisão de QA |
| D2 | Testes de regras com dataset de 50 XMLs reais anonimizados, não sintéticos | Decisão de qualidade |
| D3 | Benchmark: 200 XMLs <60s na VPS real. Medido via audit_log metrics | Decisão de performance |
| D4 | Testes de usabilidade presenciais com 3 lojistas, tarefa cronometrada, sem interferência | Decisão de UX |
| D5 | Checklist pré-lançamento: 20 itens. Todos devem passar para deploy em produção | Decisão de processo |

### Entregáveis

---

#### 5.1 Pirâmide de Testes

```
┌──────────────────────────────────────────────────────────────┐
│                    PIRÂMIDE DE TESTES                         │
│                                                               │
│                         ┌─────┐                               │
│                         │ E2E │  15%  · Playwright            │
│                         │ 3   │       · 3 jornadas críticas   │
│                         │ JRN │       · Chrome Android emul.  │
│                        ┌┴─────┴┐                              │
│                        │ INTEG. │ 25%  · Supertest            │
│                        │  14    │       · 14 endpoints        │
│                        │  EP's  │       · Cenários erro       │
│                       ┌┴───────┴┐                             │
│                       │  UNIT    │ 60%  · Vitest              │
│                       │  ~80     │       · Parser, 8 regras   │
│                       │  TESTS   │       · Auth, Utils, Cache │
│                       └──────────┘                            │
│                                                               │
│  CI Pipeline:                                                 │
│  · Push → lint + typecheck → unit tests → build Docker       │
│  · Merge main → + integration tests → deploy staging         │
│  · Nightly 03:00 → + e2e tests                               │
└──────────────────────────────────────────────────────────────┘
```

---

#### 5.2 Testes Unitários — Cenários Críticos

##### Parser (10 cenários)

| # | Cenário | Esperado |
|---|---|---|
| U01 | XML NF-e válido (layout 4.00) | NfeJson com todos os campos |
| U02 | XML sem namespace NF-e (CT-e) | NFE_INVALID_NAMESPACE, ignorado |
| U03 | XML com encoding ISO-8859-1 (SAP) | NfeJson com acentos corretos |
| U04 | XML com chave de acesso DV errado | NFE_INVALID_CHECK_DIGIT, ignorado |
| U05 | XML de nota cancelada (cStat=101) | NFE_CANCELED, ignorado |
| U06 | XML sem campo valor_total | NFE_MISSING_FIELD, ignorado |
| U07 | XML com 50 itens (atacadista) | 50 NfeItemJson extraídos |
| U08 | XML com `<!DOCTYPE` (XXE) | Rejeitado |
| U09 | XML com `<!ENTITY` (XXE) | Rejeitado |
| U10 | 200 XMLs em batch | Todos parseados, sem OOM |

##### Rule Engine (17 cenários)

| # | Regra | Cenário | Esperado |
|---|---|---|---|
| U11 | R1 | CFOP 6102 (saída) em compra Simples | score 85, RISCO_ALTO |
| U12 | R1 | CFOP 1102 (entrada) em compra Simples | null (OK) |
| U13 | R1 | CFOP "9999" inexistente | score 90, RISCO_ALTO |
| U14 | R1 | Regime != SIMPLES | null (não se aplica) |
| U15 | R2 | Alíquota 18% SP→SP (esperado 12%) | score 70 |
| U16 | R2 | Alíquota 12% SP→MG (correto) | null (OK) |
| U17 | R2 | Tolerância 1pp | null (OK) |
| U18 | R3 | NCM 0201 (carne) em mat. constr. | score 50, ATENCAO |
| U19 | R3 | NCM 2523 (cimento) em mat. constr. | null (OK) |
| U20 | R4 | CNPJ BAIXADO | score 100 |
| U21 | R4 | CNPJ ATIVO | null (OK) |
| U22 | R5 | Valor R$100, itens R$85 (>5%) | score 90 |
| U23 | R5 | Tolerância R$0,05 | null (OK) |
| U24 | R7 | Chave DV correto | null (OK) |
| U25 | R7 | Chave DV incorreto | score 100 |
| U26 | R8 | ST para NCM fora da lista | score 75 |
| U27 | R8 | ST para NCM na lista | null (OK) |

##### Auth (8 cenários)

| # | Cenário | Esperado |
|---|---|---|
| U28 | Magic link: WhatsApp válido | 200, token armazenado |
| U29 | Magic link: WhatsApp inválido | 400 |
| U30 | Magic link: 4ª tentativa em 15min | 429 |
| U31 | Verify: token válido → JWT | 200 |
| U32 | Verify: token já usado | 401 |
| U33 | Verify: token expirado (>24h) | 401 |
| U34 | Rota sem header Authorization | 401 |
| U35 | Rota com JWT expirado | 401 |

---

#### 5.3 Testes de Integração — 14 Endpoints

| # | Endpoint | Cenários |
|---|---|---|
| I01 | POST /auth/magic-link | Sucesso + rate limit + formato inválido |
| I02 | GET /auth/verify | Sucesso + token inválido + expirado + usado |
| I03 | POST /upload | Sucesso + sem arquivo + ZIP corrompido + >200 |
| I04 | GET /upload/batches | Paginação + vazio |
| I05 | GET /dashboard | Com/sem inconsistências + filtro mês |
| I06 | GET /notes | Paginação + filtros + busca |
| I07 | GET /notes/:id | Detalhe completo + 404 |
| I08 | GET /notes/:id/inconsistencies | Lista de inconsistências |
| I09 | GET /inconsistencies/:id | Detalhe + checklist + histórico |
| I10 | PATCH /inconsistencies/:id | Status + checklist + ignorar sem motivo (422) + resolver |
| I11 | GET /inconsistencies | Filtros (mes, status, rule_id) |
| I12 | GET /report/pdf | PDF + mês inválido (422) + sem notas (404) |
| I13 | GET /health | 200 com DB ok + 503 com DB offline |
| I14 | Multi-tenant | Tenant A não acessa dados de B (404) |

---

#### 5.4 Testes E2E — 3 Jornadas (Playwright)

##### Jornada 1: Upload e Dashboard (Fernanda)

```
Dispositivo: Galaxy S9 (360x740, Android 8, Chrome, 3G)
1. Login com link mágico (mock)
2. Dashboard vazio: "Carregar agora"
3. FAB + → Upload ZIP (10 XMLs)
4. Barra progresso → "10 notas. 2 pontos de atenção"
5. Dashboard com cards e lista
Tempo máximo: 45s
```

##### Jornada 2: Checklist e Resolução (Roberto)

```
Dispositivo: Moto G4 (360x640, Android 7, Chrome, 3G)
1. Dashboard com inconsistências
2. Clicar card RISCO_ALTO → T5
3. Ler "O que aconteceu" + "O que significa"
4. Marcar checklist (4 itens)
5. Sugestão "Marcar como Resolvida?" → Sim
6. Status muda. Card fade verde.
7. Dashboard atualizado (inconsistência removida)
Tempo máximo: 60s
```

##### Jornada 3: Relatório do Contador (Fernanda)

```
Dispositivo: Desktop 1366x768 (PC da loja)
1. Login como Fernanda
2. Navegar T6 (Relatório)
3. Preview: resumo + inconsistências
4. Baixar PDF → arquivo com nome correto
5. Enviar WhatsApp → mensagem pré-preenchida
Tempo máximo: 30s
```

---

#### 5.5 Teste de Carga

```bash
# scripts/benchmark-upload.sh
# ZIP com 200 XMLs reais anonimizados → POST /upload
# Medir: tempo total, HTTP status, batch.processed, memória

# Critérios de aceitação:
# | Métrica          | Alvo    | Crítico |
# | Tempo total      | <45s    | <60s    |
# | HTTP status      | 200     | 200     |
# | Notas processadas| 200/200 | 200/200 |
# | Memória container| <1.5GB  | <2GB    |
# | CPU média        | <80%    | <95%    |
```

---

#### 5.6 Testes de Segurança (OWASP — 12 itens)

| # | Verificação | Critério |
|---|---|---|
| S01 | RLS isola tenants? | Tenant A nunca vê dados de B |
| S02 | Role-based access? | Operador → admin = 403 |
| S03 | TLS 1.3 ativo? | SSL connection using TLSv1.3 |
| S04 | HSTS header? | max-age=31536000 |
| S05 | SQL injection via search? | Resposta vazia, nunca erro SQL |
| S06 | XXE via upload XML? | XML malicioso rejeitado |
| S07 | Security headers? | CSP, X-Frame, X-Content-Type |
| S08 | Docker não-root? | User: "nodejs" |
| S09 | npm audit? | Zero HIGH/CRITICAL |
| S10 | Rate limit magic-link? | 4ª+ request = 429 |
| S11 | Token single-use? | Reuso = 401 |
| S12 | Sem SSRF? | Sem fetch de URLs arbitrárias |

---

#### 5.7 Testes de Usabilidade com Usuários Reais

**Formato:** Presencial na loja do beta tester. Founder observa, não ajuda. 3 participantes.

```
TAREFA 1 — Primeiro upload (10 min)
  "Você recebeu 10 notas fiscais. Faça o upload no Copiloto."
  Métrica: tempo até concluir <3min, sucesso 100%

TAREFA 2 — Resolver inconsistência (10 min)
  "O sistema encontrou um problema. Descubra qual e o que fazer."
  Métrica: identifica problema <90s, completa checklist Sim/Não

TAREFA 3 — Relatório do contador (5 min)
  "Envie um resumo das notas para seu contador."
  Métrica: encontra T6 sem ajuda Sim/Não

PÓS-TESTE:
  NPS: "0-10, recomendaria?" Meta ≥40
  Disposição: "Pagaria R$ 97/mês?" Meta ≥2/3
```

---

#### 5.8 Checklist Pré-Lançamento (20 itens)

```
☐ 1.  57 testes unitários passam (Vitest)
☐ 2.  14 testes de integração passam (Supertest)
☐ 3.  3 jornadas e2e passam (Playwright)
☐ 4.  Cobertura ≥80% em parser, rules, auth
☐ 5.  Benchmark 200 XMLs <60s na VPS real
☐ 6.  Lighthouse mobile score ≥80
☐ 7.  5 uploads simultâneos sem degradação
☐ 8.  Usabilidade: ≥2/3 completam tarefas
☐ 9.  OWASP: 12/12 passam
☐ 10. RLS multi-tenant testado
☐ 11. Backup e restore testados
☐ 12. CI/CD: push → deploy staging automático
☐ 13. HTTPS TLS 1.3 + HSTS ativos
☐ 14. WhatsApp: 6 templates aprovados
☐ 15. E-mail: envio e recebimento OK
☐ 16. PDF abrindo em celular e desktop
☐ 17. Disclaimers visíveis em todas telas
☐ 18. Erro 500 não expõe stack trace
☐ 19. Termos de Uso no login
☐ 20. 🚀 BETA: 5 lojas, zero bugs P0 em 48h
```

---

#### 5.9 Definition of Done

```
☐ Código implementado e auto-revisado
☐ Testes unitários escritos e passando
☐ Testes de integração atualizados (se afeta endpoint)
☐ Lint + typecheck passando (CI verde)
☐ Testado manualmente no staging
☐ Sem "TODO" ou "FIXME" sem ticket
☐ Audit log registra nova funcionalidade
☐ Documentação interna atualizada
☐ PR revisado pelo outro dev (não auto-merge)
```

### Riscos e pontos de atenção

| Risco | Severidade | Mitigação |
|---|---|---|
| XMLs sintéticos não capturam variações reais de encoding | Alta | Dataset de 50 XMLs reais anonimizados de 5 ERPs. Versionado em `data/test-xmls/` |
| Playwright emulando Android 8 pode não reproduzir bugs reais do Chrome 70 | Média | Teste manual em dispositivo real (Samsung antigo) antes do beta |
| Teste de usabilidade com 3 pessoas pode não ser representativo | Baixa | Complementar com feedback dos 5 beta testers nas semanas 8-10 |
| 5 uploads simultâneos podem causar degradação mesmo com benchmark OK | Média | Adicionar teste de concorrência. Se P95 >90s, implementar fila |
| Cobertura 80% ambiciosa para time de 2 pessoas | Média | Se <80% na semana 10, aceitar ≥70% com justificativa documentada |

---

## Etapa 32 — Métricas do Produto

### Objetivo da etapa

Definir o framework de métricas do FiscoPilot MVP — o que medir, como medir, com que frequência e com que metas — usando a taxonomia AARRR (Pirate Metrics) complementada por métricas de qualidade (HEART). As métricas guiam decisões de produto, validam hipóteses e determinam o go/no-go da semana 12.

### Premissas adotadas

| # | Premissa | Justificativa |
|---|---|---|
| P1 | Métricas são extraídas de 3 fontes: banco de dados (SQL), audit_log (eventos), Google Sheets (funil de vendas manual). Sem ferramenta de analytics paga no MVP | Mixpanel/Amplitude custam >US$ 1.000/ano. PostgreSQL + SQL é suficiente para <20 clientes |
| P2 | Métricas de funil de aquisição são manuais (Google Sheets) até a Fase 2 (Stripe + CRM) | Founder é o único vendedor; volume não justifica automação de CRM |
| P3 | Métricas de produto (ativação, engajamento, retenção) são extraídas via SQL queries semanais no PostgreSQL | Dados estão no audit_log e nas tabelas de domínio. Founder roda queries toda segunda-feira |
| P4 | Métricas financeiras (MRR, churn, LTV) são calculadas no Google Sheets de controle de cobrança (Etapa 27) | Pix manual não tem API. Planilha é fonte da verdade para receita |
| P5 | Toda métrica tem uma meta de 90 dias e um limiar de "pivot" — se abaixo do limiar na semana 12, acionar replanejamento | Evita "vanity metrics". Se métrica não serve para decidir algo, não é métrica, é curiosidade |

### Análise

O FiscoPilot é um produto early-stage com volume baixo (5-10 clientes). Métricas tradicionais de SaaS (MAU, CAC payback, net revenue retention) não fazem sentido estatístico com n=5. O foco deve estar em **métricas binárias de valor**:

- **Alguém usou?** (ativação → sim/não por cliente)
- **Alguém pagou?** (monetização → sim/não por cliente)
- **Alguém indicou?** (referral → sim/não por cliente)
- **Alguém cancelou?** (churn → motivo qualitativo)

Com 5-10 clientes, a métrica mais importante não é um número — é uma **história**. "O Roberto pagou R$ 97 no segundo mês porque encontrou uma nota errada de R$ 8.400" vale mais que qualquer gráfico de coorte.

**Framework AARRR adaptado para early-stage B2B:**

| Estágio | Pergunta | Métrica principal | n=5 faz sentido? |
|---|---|---|---|
| **Acquisition** | Como nos descobrem? | Leads qualificados/semana | Sim (volume de topo) |
| **Activation** | Primeira experiência de valor? | Tempo até primeiro "aha moment" | Sim (binário por cliente) |
| **Retention** | Voltam a usar? | WAU (usuários ativos/semana) | Parcial (n pequeno, olhar individual) |
| **Revenue** | Pagam? Quanto? | MRR, conversão trial→pago | Sim (binário + valor) |
| **Referral** | Indicam? | K-factor, NPS | Sim (binário + score) |

### Decisões recomendadas

| Decisão | Conteúdo | Status |
|---|---|---|
| D1 | Framework AARRR com 12 métricas principais. Cada métrica tem: definição, fonte, frequência, meta 90 dias, limiar de pivot | Decisão de framework |
| D2 | Dashboard de métricas: Google Sheets público (apenas founder) + queries SQL semanais | Decisão de ferramenta |
| D3 | Foco em métricas binárias/qualitativas para n<20. Métricas agregadas (MAU, churn %) entram na Fase 2 | Decisão de pragmatismo |
| D4 | Toda segunda-feira: "Métrica Second" — 30 min para revisar números, atualizar Google Sheets, decidir ações | Decisão de ritual |
| D5 | NPS coletado manualmente (WhatsApp) a cada 30 dias. CSAT após cada interação de suporte | Decisão de coleta |

### Entregáveis

---

#### 5.1 Métricas AARRR — Visão Geral

```
┌──────────────────────────────────────────────────────────────────┐
│                    PIRATE METRICS (AARRR)                         │
│                                                                    │
│  ACQUISITION    ACTIVATION      RETENTION       REVENUE   REFERRAL│
│  ───────────    ──────────      ─────────       ───────   ───────│
│                                                                   │
│  A1. Leads/     A3. Trial →     A5. WAU         A8. MRR   A11.NPS│
│      semana        1º upload    A6. Retenção     A9. Churn A12.K-│
│  A2. Taxa de    A4. Tempo até      semanal       A10.LTV   factor│
│      conversão      valor                                           │
│                                                                   │
│  Fonte:          Fonte:          Fonte:          Fonte:    Fonte:│
│  Google Sheets   audit_log +     audit_log +     Google    NPS   │
│  (manual)        SQL             SQL             Sheets    WhatsApp│
│                                                                   │
└──────────────────────────────────────────────────────────────────┘
```

---

#### 5.2 ACQUISITION — Como nos descobrem?

##### A1 — Leads Qualificados por Semana

| Dimensão | Valor |
|---|---|
| **Definição** | Número de lojistas que demonstraram interesse genuíno (respondeu WhatsApp, pediu demo, aceitou visita) |
| **Fórmula** | `COUNT(DISTINCT lead) WHERE status IN ('CONTATADO', 'QUALIFICADO', 'TRIAL', 'CLIENTE')` |
| **Fonte** | Google Sheets (funil de vendas — Etapa 28) |
| **Frequência** | Semanal (toda segunda-feira) |
| **Meta semana 4** | 5 leads qualificados |
| **Meta semana 8** | 15 leads qualificados (antes do beta) |
| **Meta semana 12** | 30 leads qualificados acumulados |
| **Limiar de pivot** | <10 leads qualificados na semana 8 → canal de aquisição não está funcionando. Testar novo canal |

##### A2 — Taxa de Conversão (Lead → Trial)

| Dimensão | Valor |
|---|---|
| **Definição** | Percentual de leads qualificados que iniciam o trial de 15 dias |
| **Fórmula** | `trials_iniciados / leads_qualificados * 100` |
| **Fonte** | Google Sheets |
| **Frequência** | Quinzenal |
| **Meta semana 12** | ≥50% (metade dos leads qualificados viram trial) |
| **Limiar de pivot** | <20% → pitch ou demo não estão convertendo. Revisar roteiro de demo |

---

#### 5.3 ACTIVATION — Primeira experiência de valor

##### A3 — Trial → Primeiro Upload

| Dimensão | Valor |
|---|---|
| **Definição** | Percentual de trials que realizam ao menos 1 upload na primeira semana |
| **Fórmula** | `trials_com_upload_semana1 / trials_iniciados * 100` |
| **Fonte** | SQL: `SELECT COUNT(DISTINCT organization_id) FROM upload_batches WHERE created_at >= trial_start AND created_at <= trial_start + 7 days` |
| **Frequência** | Semanal |
| **Meta semana 12** | ≥80% (4 de 5 trials fazem upload na 1ª semana) |
| **Limiar de pivot** | <50% → onboarding não está funcionando. Investigar: Fernanda não sabe o que é XML? Interface confusa? |

##### A4 — Tempo até Primeiro Valor (Time-to-Value)

| Dimensão | Valor |
|---|---|
| **Definição** | Tempo (em dias) entre o primeiro upload e a primeira ação no checklist (marcar item como feito) |
| **Fórmula** | `MIN(checklist_updated_at) - MIN(upload_created_at)` por organização |
| **Fonte** | SQL: `audit_log WHERE event_type = 'INCONSISTENCY_STATUS_CHANGED'` |
| **Frequência** | Quinzenal |
| **Meta semana 12** | ≤7 dias (mediana entre todos os clientes) |
| **Limiar de pivot** | >14 dias → inconsistências detectadas não estão gerando ação. Possível: explicações confusas, checklist irrelevante, ou nenhuma inconsistência grave detectada |

---

#### 5.4 RETENTION — Voltam a usar?

##### A5 — WAU (Weekly Active Users)

| Dimensão | Valor |
|---|---|
| **Definição** | Número de usuários únicos que acessaram o dashboard ao menos 1 vez na semana |
| **Fórmula** | `COUNT(DISTINCT user_id) FROM audit_log WHERE event_type = 'USER_LOGIN' AND created_at >= week_start` |
| **Fonte** | SQL: `audit_log` |
| **Frequência** | Semanal |
| **Meta semana 12** | ≥80% dos usuários ativos por semana (Roberto + Fernanda) |
| **Limiar de pivot** | <50% → produto não criou hábito. Investigar: notificações WhatsApp não estão engajando? Dashboard não mostra valor? |

##### A6 — Retenção Semanal (Coorte)

| Dimensão | Valor |
|---|---|
| **Definição** | Percentual de clientes que retornam na semana N após o primeiro upload |
| **Fórmula** | `clientes_ativos_semana_N / clientes_que_fizeram_upload_semana_0 * 100` |
| **Fonte** | SQL: `audit_log` agrupado por `organization_id` e semana |
| **Frequência** | Semanal (atualizado a cada coorte) |
| **Meta semana 12** | Semana 4 ≥ 60% (3 de 5 clientes ativos após 4 semanas) |
| **Limiar de pivot** | Semana 4 < 40% → retenção crítica. Produto não gera hábito semanal |

**Exemplo de coorte (5 clientes que começaram na semana 8):**

```
CLIENTE       S0    S1    S2    S3    S4
─────────────────────────────────────────
Material ABC  ✅    ✅    ✅    ✅    ✅
Ferragens Zé  ✅    ✅    ✅    —     —
ConstruFácil  ✅    ✅    —     ✅    —
CasaNova Mat. ✅    —     —     —     —
Pisos & Cia   ✅    ✅    ✅    ✅    ✅
─────────────────────────────────────────
RETENÇÃO      100%  80%   60%   60%   40%
```

---

#### 5.5 REVENUE — Pagam? Quanto?

##### A7 — Trial → Paid Conversion Rate

| Dimensão | Valor |
|---|---|
| **Definição** | Percentual de trials que convertem para pagantes |
| **Fórmula** | `clientes_pagantes / trials_concluidos * 100` |
| **Fonte** | Google Sheets (controle de cobrança) |
| **Frequência** | Quinzenal |
| **Meta semana 12** | ≥50% (5 de 10 trials convertem) |
| **Limiar de pivot** | <30% → produto não gera disposição de pagamento. Investigar: preço? valor? concorrência? |

##### A8 — MRR (Monthly Recurring Revenue)

| Dimensão | Valor |
|---|---|
| **Definição** | Receita recorrente mensal somada de todos os clientes ativos |
| **Fórmula** | `SOMA(R$ 97 * clientes_ativos)` |
| **Fonte** | Google Sheets |
| **Frequência** | Mensal (todo dia 1º) |
| **Meta mês 3** | R$ 485 (5 × R$ 97) |
| **Meta mês 6** | R$ 970 (10 × R$ 97) |
| **Meta mês 12** | R$ 2.910 (30 × R$ 97) |
| **Limiar de pivot** | <R$ 291 (3 clientes) no mês 3 → monetização não validada |

##### A9 — Churn Rate Mensal

| Dimensão | Valor |
|---|---|
| **Definição** | Percentual de clientes que cancelaram no mês |
| **Fórmula** | `cancelamentos_mes / total_clientes_inicio_mes * 100` |
| **Fonte** | Google Sheets |
| **Frequência** | Mensal |
| **Meta semana 12** | <10% (ideal: 0% nos primeiros 3 meses) |
| **Limiar de pivot** | >20% → investigar motivo de cada cancelamento. Entrevista qualitativa obrigatória |

##### A10 — LTV Estimado (Lifetime Value)

| Dimensão | Valor |
|---|---|
| **Definição** | Receita total estimada por cliente durante o tempo de vida |
| **Fórmula** | `ARPU * (1 / churn_rate)`. MVP: `R$ 97 * (1 / 0.083)` = R$ 1.164 (assumindo 12 meses) |
| **Fonte** | Calculado a partir de MRR e churn |
| **Frequência** | Trimestral (poucos dados para mensal) |
| **Meta mês 12** | LTV ≥ R$ 1.164 (12 meses de retenção) |
| **Limiar de pivot** | LTV < R$ 582 (6 meses) → produto não retém. Custo de aquisição > LTV no longo prazo |

---

#### 5.6 REFERRAL — Indicam?

##### A11 — NPS (Net Promoter Score)

| Dimensão | Valor |
|---|---|
| **Definição** | "De 0 a 10, quanto você recomendaria o FiscoPilot para outro lojista?" |
| **Fórmula** | `% promotores (9-10) - % detratores (0-6)` |
| **Fonte** | WhatsApp — founder pergunta manualmente a cada 30 dias |
| **Frequência** | Mensal (a partir da semana 10 — primeiros pagantes) |
| **Meta semana 12** | NPS ≥ 40 |
| **Meta mês 6** | NPS ≥ 50 |
| **Limiar de pivot** | NPS < 0 → clientes não recomendariam. Problema grave de produto |

##### A12 — K-Factor (Coeficiente de Viralidade)

| Dimensão | Valor |
|---|---|
| **Definição** | Número médio de novos leads gerados por cada cliente existente |
| **Fórmula** | `novos_leads_por_indicacao / clientes_ativos` |
| **Fonte** | Google Sheets (coluna "Origem = Indicação") |
| **Frequência** | Mensal |
| **Meta semana 12** | K-factor ≥ 1.0 (cada cliente gera ≥1 lead) |
| **Meta mês 6** | K-factor ≥ 1.5 |
| **Limiar de pivot** | K-factor < 0.5 → clientes não indicam. Investigar: NPS baixo? Kit indicação não usado? Sem incentivo? |

---

#### 5.7 Métricas de Qualidade (HEART adaptado)

##### H1 — CSAT (Customer Satisfaction)

| Dimensão | Valor |
|---|---|
| **Definição** | Satisfação após interação de suporte (onboarding, dúvida, bug) |
| **Fórmula** | "Como foi sua experiência? 😊 😐 ☹️" — enviado após cada interação |
| **Fonte** | WhatsApp |
| **Meta** | ≥80% respostas 😊 |

##### H2 — Task Success Rate (Usabilidade)

| Dimensão | Valor |
|---|---|
| **Definição** | Percentual de usuários que completam a tarefa principal sem ajuda |
| **Fórmula** | Medido em teste de usabilidade (Etapa 31) e observação no beta |
| **Fonte** | Observação direta |
| **Meta** | ≥80% completam upload na 1ª tentativa |

##### H3 — Time-to-Resolution (Suporte)

| Dimensão | Valor |
|---|---|
| **Definição** | Tempo médio entre o cliente reportar um problema e ele ser resolvido |
| **Fórmula** | `data_resolucao - data_report` em horas |
| **Fonte** | WhatsApp (founder anota) |
| **Meta** | <4h em horário comercial, <24h em fim de semana |

---

#### 5.8 Dashboard de Métricas (Google Sheets)

```
┌──────────────────────────────────────────────────────────────────┐
│              FISCOPILOT — MÉTRICAS (SEMANA 10)                    │
│                                                                    │
│  ACQUISITION                                                       │
│  ┌──────────────────────────────────────────────────────────────┐│
│  │ Leads total: 24  │  Qualificados: 12  │  Trials: 5  │  Cli: 3││
│  │ Conv. Lead→Trial: 50%  │  Conv. Trial→Paid: 60%             ││
│  └──────────────────────────────────────────────────────────────┘│
│                                                                    │
│  ACTIVATION                                                        │
│  ┌──────────────────────────────────────────────────────────────┐│
│  │ Upload na 1ª sem: 4/5 (80%)  │  Time-to-Value mediano: 3d   ││
│  └──────────────────────────────────────────────────────────────┘│
│                                                                    │
│  ENGAGEMENT                                                        │
│  ┌──────────────────────────────────────────────────────────────┐│
│  │ WAU: 5/6 usuários (83%)  │  Uploads/semana: 2.1 (média)    ││
│  └──────────────────────────────────────────────────────────────┘│
│                                                                    │
│  RETENTION                                                         │
│  ┌──────────────────────────────────────────────────────────────┐│
│  │ Sem 1: 100%  │  Sem 2: 80%  │  Sem 3: 60%  │  Sem 4: —     ││
│  └──────────────────────────────────────────────────────────────┘│
│                                                                    │
│  REVENUE                                                           │
│  ┌──────────────────────────────────────────────────────────────┐│
│  │ MRR: R$ 291  │  ARPU: R$ 97  │  Churn: 0%  │  LTV est: R$1.164│
│  └──────────────────────────────────────────────────────────────┘│
│                                                                    │
│  REFERRAL                                                          │
│  ┌──────────────────────────────────────────────────────────────┐│
│  │ NPS: 60  │  Indicações: 2  │  K-factor: 0.67               ││
│  └──────────────────────────────────────────────────────────────┘│
└──────────────────────────────────────────────────────────────────┘
```

---

#### 5.9 Queries SQL para Extração de Métricas

```sql
-- ====== A3: Trial → Primeiro Upload ======
WITH trials AS (
  SELECT organization_id, MIN(created_at) as trial_start
  FROM audit_log
  WHERE event_type = 'USER_LOGIN'
  GROUP BY organization_id
)
SELECT
  t.organization_id,
  CASE WHEN MIN(u.created_at) <= t.trial_start + INTERVAL '7 days'
       THEN true ELSE false
  END as uploaded_in_first_week
FROM trials t
LEFT JOIN upload_batches u ON u.organization_id = t.organization_id
GROUP BY t.organization_id, t.trial_start;

-- ====== A5: WAU ======
SELECT COUNT(DISTINCT user_id) as wau
FROM audit_log
WHERE event_type = 'USER_LOGIN'
  AND created_at >= date_trunc('week', NOW())
  AND created_at < date_trunc('week', NOW()) + INTERVAL '7 days';

-- ====== A6: Retenção Semanal ======
WITH first_upload AS (
  SELECT organization_id, MIN(created_at) as week0
  FROM upload_batches WHERE status = 'COMPLETED'
  GROUP BY organization_id
),
weekly_activity AS (
  SELECT DISTINCT
    fu.organization_id,
    FLOOR(EXTRACT(DAY FROM (a.created_at - fu.week0)) / 7) as week_number
  FROM first_upload fu
  JOIN audit_log a ON a.organization_id = fu.organization_id
  WHERE a.event_type IN ('USER_LOGIN', 'UPLOAD_COMPLETED')
)
SELECT week_number, COUNT(DISTINCT organization_id) as active_clients
FROM weekly_activity
GROUP BY week_number
ORDER BY week_number;

-- ====== A4: Time-to-Value ======
SELECT
  organization_id,
  MIN(u.created_at) as first_upload,
  MIN(i.updated_at) as first_checklist_action,
  EXTRACT(DAY FROM (MIN(i.updated_at) - MIN(u.created_at))) as days_to_value
FROM upload_batches u
JOIN inconsistencies i ON i.organization_id = u.organization_id
WHERE u.status = 'COMPLETED'
  AND i.status IN ('EM_ANDAMENTO', 'RESOLVIDA', 'IGNORADA')
GROUP BY organization_id;
```

---

### Resumo das 12 Métricas

| # | Métrica | Frequência | Meta Semana 12 | Limiar de Pivot |
|---|---|---|---|---|
| A1 | Leads qualificados/semana | Semanal | 30 acumulados | <10 na sem 8 |
| A2 | Conv. Lead→Trial | Quinzenal | ≥50% | <20% |
| A3 | Trial→Upload 1ª sem | Semanal | ≥80% | <50% |
| A4 | Time-to-Value (dias) | Quinzenal | ≤7d | >14d |
| A5 | WAU | Semanal | ≥80% | <50% |
| A6 | Retenção semanal | Semanal | Sem 4 ≥60% | Sem 4 <40% |
| A7 | Conv. Trial→Paid | Quinzenal | ≥50% | <30% |
| A8 | MRR | Mensal | R$ 970 | <R$ 291 |
| A9 | Churn mensal | Mensal | <10% | >20% |
| A10 | LTV estimado | Trimestral | ≥R$ 1.164 | <R$ 582 |
| A11 | NPS | Mensal | ≥40 | <0 |
| A12 | K-factor | Mensal | ≥1.0 | <0.5 |

### Riscos e pontos de atenção

| Risco | Severidade | Mitigação |
|---|---|---|
| Métricas agregadas (WAU, churn %) com n=5 não têm significância estatística — qualquer variação parece enorme | Alta | Olhar métricas por cliente individualmente, não apenas o agregado. "4 de 5 clientes ativos" é mais informativo que "WAU 80%" |
| Founder pode ficar obcecado com métricas e esquecer de falar com clientes | Média | "Métrica Second" na segunda-feira dura 30 min. O resto da semana é para falar com clientes, não olhar planilha |
| Google Sheets manual é frágil — founder esquece de atualizar, dados ficam desatualizados | Baixa | Rotina fixa: toda segunda 9h, 30 min para atualizar planilha. Alerta no Google Calendar. Se pular 2 semanas, repensar processo |
| NPS coletado por WhatsApp pode ter viés (cliente não quer "magoar" o founder) | Média | Perguntar de forma neutra: "A gente quer melhorar. De 0 a 10, o que você daria? Pode ser sincero, não vai me ofender." Enviar link de formulário anônimo como alternativa |
| Métricas de retenção nas primeiras 4 semanas podem ser artificiais (cliente ainda no trial, não pagou) | Baixa | Separar coorte de trial vs coorte de pagantes a partir da semana 10. Métricas de trial medem valor; métricas de pagantes medem negócio |

---

## Etapa 33 — Riscos do Negócio

### Objetivo da etapa

Mapear todos os riscos de negócio do FiscoPilot MVP que podem impedir o sucesso do produto — da concepção à operação — com probabilidade, impacto, indicadores antecipados e planos de mitigação. O objetivo não é eliminar riscos, mas saber quais são aceitáveis, quais são monitorados e quais acionam pivot.

### Premissas adotadas

| # | Premissa | Justificativa |
|---|---|---|
| P1 | Riscos são avaliados em probabilidade × impacto numa matriz 3×3 (Baixo/Médio/Alto) | Priorização objetiva: mitigar primeiro o que pode matar o negócio |
| P2 | Todo risco tem um "early warning sign" — sinal observável que indica materialização ANTES do dano completo | Permite ação proativa, não reativa |
| P3 | Riscos são revisados a cada 2 semanas no sprint planning. Novos riscos podem ser adicionados; riscos mitigados são marcados como "controlado" | Mapa de risco é vivo |
| P4 | Risco zero não existe. Objetivo: todos os riscos na zona amarela ou verde até a semana 8 (beta) | Zona vermelha no lançamento = adiar lançamento |

### Análise

Os riscos se agrupam em 7 categorias. Os 3 mais críticos (zona vermelha):

1. **Mercado**: PME não percebe o risco fiscal até tomar multa → baixo senso de urgência
2. **Execução**: Motor de regras não encontra inconsistências suficientes → produto sem valor percebido
3. **Dependência técnica**: WhatsApp como único canal de auth e notificação → se Meta bloquear, produto quebra

Os 4 riscos secundários (zona amarela) são monetização, founder, churn e segurança. Os 3 riscos verdes são regulação, concorrência e custo.

### Decisões recomendadas

| Decisão | Conteúdo | Status |
|---|---|---|
| D1 | Matriz 3×3 com 10 riscos mapeados. 3 vermelhos (mitigação antes do beta), 4 amarelos (monitoramento ativo), 3 verdes (aceitos) | Decisão de gestão |
| D2 | Revisão a cada sprint planning (2 semanas). Founder é o risk owner de todos | Decisão de processo |
| D3 | R2 (execução) é o primeiro a validar: teste com 200 XMLs reais na semana 1-2, antes de escrever código | Decisão de prioridade |
| D4 | R5 (WhatsApp) tem plano B documentado: SMS via Twilio para auth, e-mail para notificações | Decisão de contingência |

### Entregáveis

---

#### 5.1 Matriz de Risco 3×3

```
┌──────────────────────────────────────────────────────────────────┐
│                    MATRIZ DE RISCO (P × I)                        │
│                                                                    │
│  IMPACTO                                                           │
│    ▲                                                               │
│  A │  R4 (Regul.)   │  R3 (Monetiz.)  │  R1 (Mercado)            │
│  L │  R7 (Concorr.) │  R6 (Founder)   │  R2 (Execução)           │
│  T │                │                 │  R5 (WhatsApp)            │
│  O │────────────────┼─────────────────┼──────────────────────────│
│    │                │                 │                           │
│  M │  R10 (Custo)   │  R8 (Churn)     │                           │
│  É │                │  R9 (Segurança) │                           │
│  D │                │                 │                           │
│  I │────────────────┼─────────────────┼──────────────────────────│
│  O │                │                 │                           │
│    │                │                 │                           │
│  B │                │                 │                           │
│  A │                │                 │                           │
│  I │                │                 │                           │
│  X │                │                 │                           │
│  O │                │                 │                           │
│    └────────────────┴─────────────────┴──────────────────────────▶
│    BAIXA            MÉDIA              ALTA        PROBABILIDADE
│
│  ZONA VERDE:  R4, R7, R10 — aceitos, monitoramento leve
│  ZONA AMARELA: R3, R6, R8, R9 — monitoramento ativo, mitigação parcial
│  ZONA VERMELHA: R1, R2, R5 — exigem mitigação antes do beta
└──────────────────────────────────────────────────────────────────┘
```

---

#### 5.2 Catálogo de Riscos

##### R1 — Risco de Mercado (ninguém quer) 🔴

| Dimensão | Valor |
|---|---|
| **Probabilidade** | Média (50%) |
| **Impacto** | Alto — produto morre se ninguém comprar |
| **Descrição** | PMEs não percebem o risco fiscal como urgente. O comportamento atual ("não fazer nada e torcer") é o concorrente mais forte |
| **Early warning** | <10 leads qualificados na semana 4. <3 beta testers engajados na semana 8. 0 conversões na semana 10 |
| **Mitigação** | (1) Demo com raio-x ao vivo usando dados reais do prospect. (2) Onboarding mostra riscos ocultos em segundos. (3) Depoimentos de clientes. (4) Se risco se materializar: pivotar ICP ou proposta de valor |

##### R2 — Risco de Execução (motor não detecta) 🔴

| Dimensão | Valor |
|---|---|
| **Probabilidade** | Média (40%) |
| **Impacto** | Alto — produto sem valor percebido |
| **Descrição** | As 8 regras podem não encontrar inconsistências suficientes. Se 200 notas gerarem 0 inconsistências, produto é inútil |
| **Early warning** | Teste com 200 XMLs mostra <5 inconsistências. Beta testers sem alerta nas primeiras 2 semanas |
| **Mitigação** | (1) Validar regras contra 200 XMLs reais ANTES de codificar. (2) 4 regras reservas (R9-R12). (3) Ajustar sensibilidade. (4) Pivotar ICP se necessário |

##### R3 — Risco de Monetização (ninguém paga) 🟡

| Dimensão | Valor |
|---|---|
| **Probabilidade** | Média (35%) |
| **Impacto** | Alto — produto sem receita |
| **Descrição** | Clientes podem não pagar R$ 97/mês mesmo vendo valor. "Meu contador já faz de graça", "vou usar e cancelar" |
| **Early warning** | <30% conversão trial→pago. Clientes usam trial mas não convertem |
| **Mitigação** | (1) Onboarding guiado garante valor antes do pagamento. (2) Preço ancorado em custo de multa. (3) Se 0 conversões: testar R$ 47, freemium, ou pivotar B2B2C |

##### R4 — Risco Regulatório (CRC/LGPD/CTN) 🟢

| Dimensão | Valor |
|---|---|
| **Probabilidade** | Baixa (15%) |
| **Impacto** | Alto — multa, processo, proibição de operar |
| **Mitigação** | Disclaimers em toda tela. Produto nunca calcula imposto nem emite guia. Dados pessoais mínimos. RLS. DPA. Posicionamento: "ferramenta de organização, não consultoria" |

##### R5 — Risco de Dependência do WhatsApp 🔴

| Dimensão | Valor |
|---|---|
| **Probabilidade** | Média (30%) |
| **Impacto** | Alto — sem WhatsApp = sem auth, sem notificações, sem vendas |
| **Mitigação** | (1) API oficial (menor risco de bloqueio). (2) Seguir políticas Meta. (3) Plano B: SMS Twilio + e-mail + PWA push. (4) Core functions sem WhatsApp |

##### R6 — Risco de Dependência do Founder 🟡

| Dimensão | Valor |
|---|---|
| **Probabilidade** | Média (25%) |
| **Impacto** | Médio — produto sobrevive mas com atraso |
| **Mitigação** | Documentação desde dia 1. Runbook de operações. Engenheiro treinado para deploy. CNPJ próprio, não conta pessoal |

##### R7 — Risco de Concorrência 🟢

| Dimensão | Valor |
|---|---|
| **Probabilidade** | Baixa (20%) |
| **Impacto** | Médio — concorrente entra no nicho |
| **Mitigação** | Vantagem do primeiro movimento. Nicho pequeno para ERP. Switching cost com histórico de notas. Velocidade de execução |

##### R8 — Risco de Churn 🟡

| Dimensão | Valor |
|---|---|
| **Probabilidade** | Média (30%) |
| **Impacto** | Médio — perda de receita e prova social |
| **Mitigação** | "Silêncio positivo" (W5). Relatório mensal. Check-in pessoal a cada 60 dias. Entrevistar todo cancelamento |

##### R9 — Risco de Segurança 🟡

| Dimensão | Valor |
|---|---|
| **Probabilidade** | Baixa (10%) |
| **Impacto** | Médio — dano reputacional |
| **Mitigação** | RLS. OWASP checklist. Backup AES-256. CI/CD com security audit. Plano de comunicação em 24h |

##### R10 — Risco de Custo de Infra 🟢

| Dimensão | Valor |
|---|---|
| **Probabilidade** | Baixa (10%) |
| **Impacto** | Baixo — R$ 40-200/mês adicional |
| **Mitigação** | Upgrade VPS trivial. LLM opcional. S3 lifecycle. Planilha de custos mensal |

---

#### 5.3 Early Warning Dashboard

```
┌──────────────────────────────────────────────────────────────────┐
│              EARLY WARNING SIGNS                                   │
│                                                                    │
│  RISCO  SINAL                                    LIMIAR   STATUS │
│  ─────  ──────────────────────────────────────  ───────  ────── │
│  R1     Leads qualificados <10 na semana 4      🟡       🟢 OK │
│  R2     Inconsistências <10 em 200 XMLs         🔴       🟡     │
│  R3     Conversão trial→pago <30% semana 10     🟡       —      │
│  R4     Denúncia/notificação regulatória         🔴       🟢 OK │
│  R5     Templates WhatsApp rejeitados            🟡       🟢 OK │
│  R6     Founder >60h/semana 3+ semanas           🟡       🟢 OK │
│  R7     ERP anuncia feature concorrente          🟢       🟢 OK │
│  R8     Churn >20% ou WAU <50%                   🟡       —      │
│  R9     Vulnerabilidade HIGH/CRITICAL npm        🟡       🟢 OK │
│  R10    Custo mensal >R$ 200                     🟢       🟢 OK │
│                                                                    │
│  🟢 Normal   🟡 Atenção   🔴 Crítico   — Sem dados              │
└──────────────────────────────────────────────────────────────────┘
```

---

#### 5.4 Plano de Contingência

```
R1 (Mercado): Se 0 vendas na semana 12
  → Entrevistar 10 leads. Testar: A) R$ 47, B) novo ICP, C) novo produto
  → Decidir em 1 semana. Pivotar ou abandonar.

R2 (Execução): Se <5 inconsistências em 200 XMLs
  → Ativar R9-R12. Reduzir score mínimo. Pivotar ICP se necessário.

R5 (WhatsApp): Se conta bloqueada
  → Dia 1: auth via SMS (Twilio). Notificações via e-mail + PWA push.
  → Dia 1: comunicar clientes. Dia 7: campanha de atualização.

R4 (Regulatório): Se notificação CRC/ANPD
  → Advogado em 24h. Disclaimers mais explícitos em 48h. Limitar sugestões.

R6 (Founder): Se incapacitado >1 semana
  → Engenheiro assume deploy e suporte. Clientes avisados.
  → Se >1 mês: buscar substituto ou encerrar.
```

---

### Resumo dos 10 Riscos

| # | Risco | P | I | Zona | Mitigação chave |
|---|---|---|---|---|---|
| R1 | Mercado | M | A | 🔴 | Validar antes de construir. Demo raio-x ao vivo |
| R2 | Execução | M | A | 🔴 | Testar 200 XMLs na semana 1. Regras reservas |
| R3 | Monetização | M | A | 🟡 | Onboarding guiado. Depoimentos. Testar preço |
| R4 | Regulatório | B | A | 🟢 | Disclaimers. Não calcular imposto. DPA |
| R5 | WhatsApp | M | A | 🔴 | Plano B: SMS + e-mail. Core sem WhatsApp |
| R6 | Founder | M | M | 🟡 | Documentação. Treinar engenheiro. CNPJ |
| R7 | Concorrência | B | M | 🟢 | Nicho pequeno. Switching cost. Velocidade |
| R8 | Churn | M | M | 🟡 | Silêncio positivo. Check-in. Relatório mensal |
| R9 | Segurança | B | M | 🟡 | RLS. OWASP. Backup criptografado |
| R10 | Custo infra | B | B | 🟢 | Upgrade VPS trivial. LLM opcional |

### Riscos e pontos de atenção

| Risco | Severidade | Mitigação |
|---|---|---|
| Análise de risco pode gerar "paralisia por análise" — founder fica com medo de executar | Média | Riscos são mapeados para decidir, não para parar. Revisão a cada 2 semanas |
| Riscos de baixa probabilidade e alto impacto (R4, R9) podem ser negligenciados por otimismo | Média | Revisão trimestral de riscos de cauda longa. "O que mudou no ambiente?" |
| Plano de contingência documentado mas nunca testado | Baixa | Simulação anual (Fase 2): medir RTO real em cenário de desastre |

---

## Etapa 34 — Resumo Executivo Final

### Objetivo da etapa

Sintetizar as 33 etapas anteriores em um documento executivo de 1 página — denso, acionável, sem tabelas longas — para apresentação a investidores, parceiros ou novos membros do time. Este é o "deck de 60 segundos" do FiscoPilot.

---

### FiscoPilot — Copiloto Fiscal para PME

**Visão:** Ser a primeira ferramenta que traduz documentos fiscais em riscos compreensíveis para donos de pequenas empresas brasileiras — antes que inconsistências virem multas. Evoluir de "analisador de XML" para **sistema de prevenção fiscal recorrente**.

**Problema:** PMEs brasileiras perdem entre R$ 7.700 e R$ 29.600 por ano com multas, imposto pago a maior e retrabalho contábil — porque ninguém lê XML de nota fiscal. Os dados estão lá, trancados em arquivos ilegíveis e linguagem técnica inacessível. O dono decide comprar, vender e contratar às cegas do ponto de vista fiscal.

**Solução:** O FiscoPilot lê NF-e de compra, detecta inconsistências com 8 regras determinísticas, explica o problema em português claro com impacto em reais e sugere ações concretas — tudo em 2 minutos, no celular. Pós-MVP, adiciona download automático de XML via certificado digital, portal do contador, score de fornecedores e mais 12 features de prevenção fiscal recorrente.

**ICP:** Donos de loja de material de construção, Simples Nacional, 5-20 funcionários, faturamento R$ 80-300 mil/mês, que recebem 60-200 NF-e de entrada por mês. Persona: Roberto, 51 anos, ensino médio, usa WhatsApp intensamente, não sabe o que é XML.

**Proposta de valor:** "Suas notas fiscais explicadas." R$ 97/mês (MVP) → R$ 147/mês (Fase B) → R$ 197/mês (Fase D). 15 dias grátis. Sem contrato.

**Diferenciação:** Não é ERP (não emite nota, não faz gestão). Não é software de contador (não apura imposto, não entrega declaração). É a camada de tradução entre o fiscal e o dono da PME — um segmento sem concorrente direto hoje.

**Stack:** TypeScript ponta a ponta (Next.js 14 + Fastify 5). PostgreSQL 16 com RLS multi-tenant. Drizzle ORM. Docker Compose em VPS única (Hetzner CX22, R$ 120/mês → CX32, R$ 240/mês na Fase D). WhatsApp Business API para auth e notificações. GPT-4o-mini via OpenRouter como paráfrase opcional de explicações (feature flag, desligável). Custo total de infra: ~R$ 168/mês (MVP) → ~R$ 338/mês (Fase D).

**Modelo de negócio:** SaaS B2B. Plano único R$ 97/mês no MVP, evoluindo para R$ 147/mês na Fase B e R$ 197/mês na Fase D com features premium. Cobrança via Pix manual nos primeiros 6 meses. Meta: 10 clientes = R$ 970 MRR em 90 dias. 80 clientes = R$ 15.760 MRR em 12 meses.

**Roadmap:** MVP (90 dias, 35 funcionalidades) → Fase A: Retenção/Atrito (mês 4-5, 6 features) → Fase B: Monitoramento (mês 5-7, 3 features) → Fase C: Inteligência (mês 7-9, 3 features) → Fase D: Plataforma (mês 9-12, 3 features). Total: 65 funcionalidades, 57 requisitos de usuário, 76 requisitos de sistema, 12 requisitos de contorno, 23 telas, 34 tabelas.

**Métricas-chave (meta 90 dias):**
- 30 leads qualificados acumulados
- 50% conversão trial → pago (5 de 10)
- R$ 970 MRR (10 × R$ 97)
- NPS ≥ 40
- K-factor ≥ 1.0 (cada cliente indica ≥1)
- Churn < 10%

**Métricas-chave (meta 12 meses):**
- 80 clientes pagantes
- R$ 15.760 MRR (80 × R$ 197)
- NPS ≥ 40 mantido
- Churn < 5%
- 4 fases de expansão lançadas

**Riscos principais:**
1. **Mercado (🔴):** PME não percebe risco fiscal. Mitigação: demo raio-x ao vivo com dados reais do prospect.
2. **Execução (🔴):** Regras não detectam inconsistências. Mitigação: validar contra 200 XMLs reais na semana 1.
3. **WhatsApp (🔴):** Dependência única para auth e notificações. Mitigação: plano B com SMS + e-mail documentado.
4. **Monetização (🟡):** Ninguém paga R$ 97. Mitigação: onboarding guiado + depoimentos + opção de teste de preço menor.
5. **Regulatório (🟢):** Risco baixo. Disclaimers em toda tela. Produto não calcula imposto.
6. **Complexidade (🟡):** 12 novos módulos podem sobrecarregar time. Mitigação: cada fase auto-contida. Contratar antes da Fase C.

**Equipe:** 1 founder full-stack + 1 engenheiro back-end + 1 designer UX part-time. MVP: 90 dias, 706 horas. Pós-MVP: +155 dias, ~1.240 horas. Contratar dev adicional antes da Fase C.

**Próximo passo:** Começar a construir. Semana 1, Sprint 1, tarefa S1-01: inicializar monorepo.

---

## Etapa 35 — Features Pós-MVP: Sistema de Prevenção Fiscal Recorrente

### Objetivo da etapa

Expandir o FiscoPilot de "analisador de XML" para **sistema de prevenção fiscal recorrente** — adicionando 15 features que transformam o produto de ferramenta reativa (espera upload manual) em plataforma proativa (monitora, alerta, age e demonstra valor continuamente). As features estão organizadas em 4 fases (A, B, C, D) com critério de priorização baseado em redução de atrito, retenção, esforço, diferenciação e dependência de dados acumulados.

### Premissas adotadas

| # | Premissa | Justificativa |
|---|---|---|
| P1 | O MVP (Etapas 1-34) está funcional e em produção com ao menos 3-5 clientes pagantes antes de iniciar qualquer feature pós-MVP | Validação de valor precede expansão de escopo |
| P2 | A arquitetura existente (monorepo TypeScript, Fastify + Next.js + PostgreSQL 16) suporta todas as 15 features sem reescrita | Monolito modular já definido; cada feature vira sub-módulo |
| P3 | O diagnóstico continua 100% determinístico; IA generativa é camada explicativa opcional | Premissa central do produto (D5 da Etapa 1) mantida |
| P4 | O contador (Dona Célia) passa de persona influenciadora para persona usuária ativa via portal dedicado | Feature #2 transforma o contador em aliado com acesso próprio |
| P5 | Features que exigem histórico acumulado (score de fornecedores, economia) só ativam após 90 dias de dados | Sem dados, essas features não geram valor; não adianta construir antes |
| P6 | Cada fase é auto-contida: pode ser lançada independentemente e gera valor incremental | Evita "big bang" de lançamento; cada fase é um mini-release |

### Decisões recomendadas

| Decisão | Conteúdo | Status |
|---|---|---|
| D1 | 15 features organizadas em 4 fases: A (Retenção/Atrito), B (Monitoramento), C (Inteligência), D (Plataforma) | Decisão de roadmap |
| D2 | Fase A é prioritária: reduz atrito de ingestão (#11 WhatsApp, #1 Download auto) e demonstra ROI (#5 Mensagem, #6 Economia, #7 Relatório, #8 Tudo certo+, #15 Onboarding) | Decisão de priorização |
| D3 | 23 novas tabelas + 1 view materializada + ~65 novas rotas API + 14 novas telas + 12 novos módulos backend | Decisão de escopo |
| D4 | Custo de infra sobe de ~R$ 168/mês para ~R$ 338/mês na Fase D (VPS maior, mais LLM) | Decisão de infraestrutura |
| D5 | Esforço total estimado: ~155 dias de desenvolvimento distribuídos em ~9 meses (Fases A-D) | Decisão de cronograma |
| D6 | Cada feature mantém RFC-001 a RFC-008 (Etapa 9): sem edição de campos fiscais, sem cálculo de imposto, sem substituição do contador | Decisão de compliance |

---

### Visão geral das 15 features

| # | Feature | Fase | Esforço | Impacto principal |
|---|---|---|---|---|
| 1 | Download automático de XML via certificado digital | B | 15 dias | Elimina upload manual; monitoramento contínuo |
| 2 | Modo contador (portal) | C | 15 dias | Transforma contador em aliado; reduz veto |
| 3 | Score de fornecedores | C | 8 dias | Retenção via inteligência de negócio |
| 4 | Gestão de pendências como Kanban | B | 12 dias | Transforma alerta em ação rastreável |
| 5 | Mensagem pronta para fornecedor | A | 5 dias | Sensação de produto "mágico" |
| 6 | Histórico de economia / risco evitado | A | 5 dias | Demonstração contínua de ROI |
| 7 | Relatório mensal do dono | A | 5 dias | Retenção mesmo sem erros |
| 8 | "Tudo certo" mais inteligente | A | 2 dias | Percepção de trabalho realizado |
| 9 | Simulador da Reforma Tributária | D | 15 dias | Diferenciação competitiva forte |
| 10 | Integração com ERPs brasileiros | D | 20 dias | Elimina upload; "lê do sistema que você já usa" |
| 11 | Ingestão por WhatsApp | A | 8 dias | Canal natural do ICP brasileiro |
| 12 | Assistente de IA com limites claros | C | 10 dias | Explicação contextual sem risco fiscal |
| 13 | Biblioteca de regras por UF e setor | D | 15 dias | Plataforma de regras expansível |
| 14 | Alerta de certificado e dados cadastrais | B | 10 dias | Mini-monitor cadastral proativo |
| 15 | Checklist de onboarding "raio-x fiscal" | A | 5 dias | Primeira experiência polida e guiada |

---

### FASE A — Retenção e Redução de Atrito (Mês 4-5, ~30 dias)

**Objetivo da fase:** Reduzir o atrito de ingestão de dados (hoje dependente de upload manual) e demonstrar valor continuamente — mesmo quando não há inconsistências.

**Features incluídas:** #5, #6, #7, #8, #11, #15

---

#### Feature #5 — Mensagem Pronta para Fornecedor

**Descrição:** Quando uma nota apresenta inconsistência, o sistema gera automaticamente uma mensagem contextualizada para o fornecedor — pronta para copiar, enviar por WhatsApp ou e-mail. Transforma o alerta em ação concreta com um toque.

**Novo módulo:** `apps/api/src/modules/messages/`

```
modules/messages/
├── index.ts          # Plugin Fastify
├── templates.ts      # Templates por tipo de regra (R1-R8)
├── routes.ts         # GET/POST/PUT
└── generators.ts     # Geração de mensagem contextual
```

**Novas tabelas:**

```sql
CREATE TABLE supplier_message_templates (
  id              uuid PRIMARY KEY DEFAULT gen_random_uuid(),
  rule_id         rule_id NOT NULL,
  variant         varchar(30) NOT NULL DEFAULT 'default',
  template_text   text NOT NULL,
  is_active       boolean NOT NULL DEFAULT true,
  created_at      timestamptz NOT NULL DEFAULT now()
);

CREATE TABLE supplier_messages (
  id                uuid PRIMARY KEY DEFAULT gen_random_uuid(),
  organization_id   uuid NOT NULL REFERENCES organizations(id),
  inconsistency_id  uuid NOT NULL REFERENCES inconsistencies(id),
  user_id           uuid REFERENCES users(id),
  channel           varchar(20) NOT NULL,
  message_text      text NOT NULL,
  status            varchar(20) NOT NULL DEFAULT 'GENERATED',
  sent_at           timestamptz,
  created_at        timestamptz NOT NULL DEFAULT now()
);
```

**Novas rotas API:**

| Método | Rota | Descrição |
|---|---|---|
| GET | `/api/v1/inconsistencies/:id/message` | Gera mensagem pronta para o fornecedor |
| POST | `/api/v1/inconsistencies/:id/message/send` | Envia via WhatsApp ou e-mail |
| POST | `/api/v1/inconsistencies/:id/message/copy` | Registra que foi copiada |

**Exemplo de mensagem (R1 — CFOP divergente):**

```
Olá, {fornecedor}. Recebemos a NF-e nº {numero} e identificamos possível
divergência no código da operação fiscal (CFOP). O código registrado foi
{cfop_encontrado}, mas nosso sistema indica que o correto para esta operação
seria {cfop_esperado}. Poderiam verificar e, se necessário, emitir carta
de correção? Obrigado.
```

**Critério de aceitação:** Para cada regra R1-R8, o sistema gera uma mensagem contextual com dados reais da nota. Botões "Copiar", "Enviar por WhatsApp" e "Enviar por e-mail" funcionais. Status da mensagem persistido.

---

#### Feature #6 — Histórico de Economia / Risco Evitado

**Descrição:** Painel "Riscos Evitados" que mostra o impacto acumulado do FiscoPilot — quantas inconsistências foram detectadas, qual o valor em risco e quanto foi potencialmente economizado. Demonstra ROI continuamente.

**Novo módulo:** `apps/api/src/modules/savings/`

```
modules/savings/
├── index.ts          # Plugin Fastify
├── routes.ts         # GET /api/v1/savings
└── calculator.ts     # Agregação sobre inconsistencies
```

**Sem novas tabelas** — usa agregação sobre `inconsistencies` + `nfe_documents` existentes.

**Novas rotas API:**

| Método | Rota | Descrição |
|---|---|---|
| GET | `/api/v1/savings` | Painel de riscos evitados (mês/trimestre/ano) |
| GET | `/api/v1/savings/history` | Série histórica mensal |

**Lógica de cálculo:**

```
risco_evitado = SUM(estimated_impact) WHERE status IN ('RESOLVIDA')
risco_detectado = SUM(estimated_impact) WHERE classification = 'RISCO_ALTO'
taxa_resolucao = COUNT(RESOLVIDA) / COUNT(total) * 100
```

**Mockup do painel:**

```
┌──────────────────────────────────┐
│  Riscos Evitados       Maio 2026│
│                                  │
│  ┌──────────────────────────────┐│
│  │  Este mês o FiscoPilot       ││
│  │  encontrou 4 inconsistências ││
│  │  em R$ 18.430 de notas.      ││
│  │                              ││
│  │  Impacto potencial           ││
│  │  estimado:                   ││
│  │                              ││
│  │      ~R$ 1.240               ││
│  │                              ││
│  │  3 resolvidos · 1 pendente   ││
│  └──────────────────────────────┘│
│                                  │
│  ── HISTÓRICO ──                 │
│  Abr: ~R$ 890 (3 resolvidos)    │
│  Mar: ~R$ 2.100 (5 resolvidos)  │
│  Fev: ~R$ 340 (2 resolvidos)    │
└──────────────────────────────────┘
```

**Critério de aceitação:** Painel exibe valores corretos para mês, trimestre e ano. Gráfico de barras com últimos 6 meses. Atualiza em tempo real após mudança de status de inconsistência.

---

#### Feature #7 — Relatório Mensal do Dono ("Fechamento Fiscal")

**Descrição:** Além do PDF para contador (existente), um relatório mensal visual de 1 página para o dono — mostrando notas analisadas, valor processado, inconsistências, fornecedores problemáticos e recomendação para o próximo mês. Gera retenção mesmo quando não há erros.

**Expansão do módulo:** `apps/api/src/modules/report/`

```
modules/report/
├── index.ts
├── accountant-pdf.ts   # Existente (PDF contador)
└── owner-report.ts     # NOVO: relatório mensal do dono
```

**Nova rota API:**

| Método | Rota | Descrição |
|---|---|---|
| GET | `/api/v1/report/owner-pdf?month=YYYY-MM` | PDF do dono (1 página) |

**Conteúdo do PDF (1 página A4):**

```
┌─────────────────────────────────────────────┐
│  FiscoPilot — Seu Mês Fiscal               │
│  {nome_loja} · {mês}/{ano}                  │
│                                              │
│  NOTAS ANALISADAS          VALOR PROCESSADO  │
│       143                  R$ 284.500        │
│                                              │
│  INCONSISTÊNCIAS          RISCOS RESOLVIDOS  │
│       5                        3             │
│                                              │
│  FORNECEDORES             PENDÊNCIAS         │
│  PROBLEMÁTICOS             ABERTAS           │
│       2                        2             │
│                                              │
│  TOP 3 FORNECEDORES COM MAIS PROBLEMAS      │
│  1. CimentoBom — 3 notas, R$ 1.200 risco   │
│  2. Telhanorte — 1 nota, R$ 340 risco      │
│  3. Pisos Sul — 1 nota, R$ 87 risco        │
│                                              │
│  RECOMENDAÇÃO PARA O PRÓXIMO MÊS            │
│  "Atenção ao fornecedor CimentoBom.         │
│   Considere pedir carta de correção."       │
│                                              │
│  ⓘ Análise preliminar. Confirme com         │
│  seu contador.                              │
└─────────────────────────────────────────────┘
```

**Critério de aceitação:** PDF gerado em <5s. Contém todos os dados do mês. Botão "Baixar meu mês fiscal" visível no dashboard.

---

#### Feature #8 — "Tudo Certo" Mais Inteligente

**Descrição:** Quando não há inconsistências, a notificação de silêncio positivo inclui contexto rico — número de notas, valor total, quantidade de fornecedores — para que o usuário sinta que o sistema realmente trabalhou.

**Expansão do módulo:** `apps/api/src/modules/notify/`

Sem novas tabelas ou rotas. Expansão dos templates de notificação existentes.

**Template W5 atualizado:**

```
✅ FiscoPilot — Tudo certo essa semana

Analisamos {N} notas, R$ {valor_total} em compras,
{N_fornecedores} fornecedores diferentes.

Nenhuma inconsistência crítica encontrada.

Seu fiscal está em dia.

{link_magico}
```

**Template W1 atualizado (resumo semanal com contexto):**

```
📊 FiscoPilot — Resumo da semana

{periodo}: {N} notas processadas, R$ {valor_total} em compras.

{N_ok} sem problemas · {N_atencao} atenção · {N_risco} risco

{Se há risco > 0:}
⚠️ {N_risco} questões precisam da sua atenção:
{top_risco_fornecedor}: {top_risco_tipo} (~R$ {impacto})

{link_magico}
```

**Critério de aceitação:** Notificações W1 e W5 incluem agregações de `valor_total` e `COUNT(DISTINCT cnpj_emitente)`. Tom contextual, não genérico.

---

#### Feature #11 — Ingestão por WhatsApp

**Descrição:** A funcionária recebe XML no WhatsApp do fornecedor, encaminha para o número do FiscoPilot, e o sistema processa automaticamente. Canal natural do ICP brasileiro — elimina a necessidade de abrir computador para fazer upload.

**Novo módulo:** `apps/api/src/modules/whatsapp-ingest/`

```
modules/whatsapp-ingest/
├── index.ts          # Plugin Fastify
├── webhook.ts        # POST /api/v1/whatsapp/webhook
├── processor.ts      # Extrai XML de mensagem, dispara pipeline
└── media.ts          # Download de mídia via WhatsApp API
```

**Nova tabela:**

```sql
CREATE TABLE whatsapp_ingestion_log (
  id                uuid PRIMARY KEY DEFAULT gen_random_uuid(),
  organization_id   uuid REFERENCES organizations(id),
  user_id           uuid REFERENCES users(id),
  whatsapp_from     varchar(20) NOT NULL,
  message_id        varchar(100) NOT NULL,
  message_type      varchar(30) NOT NULL,
  media_url         text,
  media_mime_type   varchar(100),
  processed         boolean NOT NULL DEFAULT false,
  upload_batch_id   uuid REFERENCES upload_batches(id),
  error_message     text,
  created_at        timestamptz NOT NULL DEFAULT now()
);
```

**Novas rotas API:**

| Método | Rota | Descrição |
|---|---|---|
| POST | `/api/v1/whatsapp/webhook` | Webhook da Meta (recebe mensagens) |
| GET | `/api/v1/whatsapp/ingestion-log` | Histórico de mensagens recebidas |

**Fluxo:**

```
1. Fernanda encaminha XML para número FiscoPilot no WhatsApp
2. Meta envia webhook → POST /api/v1/whatsapp/webhook
3. Sistema identifica remetente → busca organization por whatsapp
4. Download do documento (XML/PDF/ZIP) via WhatsApp Media API
5. Se XML → pipeline de ingestão existente (validate → parse → rules)
6. Se ZIP → extrai e processa
7. Se não-reconhecido → responde: "Formato não suportado. Envie .xml ou .zip"
8. Confirma processamento: "✅ 3 notas recebidas e analisadas."
```

**Variáveis de ambiente novas:**

```
WHATSAPP_WEBHOOK_VERIFY_TOKEN=<random>
WHATSAPP_BUSINESS_ACCOUNT_ID=
```

**Critério de aceitação:** XML encaminhado via WhatsApp é processado em <60s. Confirmação enviada ao remetente. Histórico visível na interface.

---

#### Feature #15 — Checklist de Onboarding "Raio-X Fiscal"

**Descrição:** Fluxo de onboarding extremamente guiado em 5 passos — do primeiro upload ao envio do PDF para o contador. Transforma o momento "raio-x imediato" (ponto de venda) numa feature de produto polida e repetível.

**Novo módulo:** `apps/api/src/modules/onboarding/`

```
modules/onboarding/
├── index.ts          # Plugin Fastify
├── routes.ts         # GET/POST onboarding state
└── steps.ts          # Definição dos passos do raio-x
```

**Nova tabela:**

```sql
CREATE TABLE onboarding_sessions (
  id                uuid PRIMARY KEY DEFAULT gen_random_uuid(),
  organization_id   uuid NOT NULL REFERENCES organizations(id),
  user_id           uuid NOT NULL REFERENCES users(id),
  current_step      integer NOT NULL DEFAULT 0,
  steps_completed   jsonb NOT NULL DEFAULT '[]',
  first_upload_batch_id uuid REFERENCES upload_batches(id),
  risks_found       integer DEFAULT 0,
  high_risks_found  integer DEFAULT 0,
  completed_at      timestamptz,
  created_at        timestamptz NOT NULL DEFAULT now()
);
```

**Novas rotas API:**

| Método | Rota | Descrição |
|---|---|---|
| GET | `/api/v1/onboarding` | Estado atual do onboarding |
| POST | `/api/v1/onboarding/start` | Inicia sessão de onboarding |
| PATCH | `/api/v1/onboarding/step` | Avança para próximo passo |
| POST | `/api/v1/onboarding/complete` | Marca como concluído |

**Fluxo do Raio-X (5 passos):**

```
PASSO 1: "Envie seus XMLs dos últimos 30 dias"
  → Tela de upload simplificada (sem menus, sem histórico)

PASSO 2: "Analisando suas notas..."
  → Animação de processamento com contador

PASSO 3: "Encontramos {X} riscos"
  → Tela de resultado com números grandes

PASSO 4: "Aqui estão os {3} mais importantes"
  → Cards dos top 3 riscos com explicação simplificada

PASSO 5: "Envie este PDF para seu contador"
  → Geração automática do PDF do contador
  → Botão "Enviar por WhatsApp" + "Baixar PDF"
```

**Mockup do wizard:**

```
┌──────────────────────────────────┐
│  FiscoPilot — Raio-X Fiscal      │
├──────────────────────────────────┤
│                                  │
│  ● ─── ○ ─── ○ ─── ○ ─── ○     │
│  1      2      3      4      5   │
│                                  │
│  ┌──────────────────────────────┐│
│  │                              ││
│  │    📤                        ││
│  │                              ││
│  │    Envie seus XMLs dos       ││
│  │    últimos 30 dias.          ││
│  │                              ││
│  │    [Arraste arquivos aqui]   ││
│  │    ou                        ││
│  │    [Selecionar do celular]   ││
│  │                              ││
│  │    Dica: peça para sua       ││
│  │    auxiliar ou contador      ││
│  │    os arquivos .xml          ││
│  │                              ││
│  └──────────────────────────────┘│
│                                  │
│  [Pular]              [Avançar →]│
└──────────────────────────────────┘
```

**Critério de aceitação:** Wizard de 5 passos funcional. Upload simplificado. Resultados com animação. PDF gerado automaticamente no passo 5. Sessão persistida (pode retomar se sair).

---

### Riscos e pontos de atenção da Fase A

| Risco | Severidade | Mitigação |
|---|---|---|
| WhatsApp Business API pode rejeitar webhook de ingestão de documentos | Média | Testar com conta de teste da Meta antes de implementar. Fallback: e-mail para notas@copilotofiscal.com |
| Feature #6 (Economia) pode superestimar impacto financeiro se `estimated_impact` estiver errado | Média | Sempre usar "~" (aproximado). Disclaimer: "Estimativa conservadora. Confirme com seu contador." |
| Onboarding wizard (Feature #15) pode ser pulado por usuários que já conhecem o produto | Baixa | Wizard é obrigatório apenas para novas organizações. Usuários existentes veem dashboard direto |
| Templates de mensagem (Feature #5) podem soar robóticos ou formais demais para WhatsApp | Média | Testar com 5 donos de loja reais. Ajustar tom para linguagem coloquial brasileira |
| Ingestão por WhatsApp (Feature #11) pode receber arquivos não-XML (fotos, áudios, PDFs) | Média | Pipeline de validação rejeita silenciosamente. Responde: "Formato não suportado. Envie .xml ou .zip" |

---

### FASE B — Monitoramento Contínuo (Mês 5-7, ~40 dias)

**Objetivo da fase:** Transformar o FiscoPilot de ferramenta reativa (espera upload) em sistema de monitoramento contínuo — baixando XMLs automaticamente, rastreando pendências como Kanban e monitorando dados cadastrais de fornecedores.

**Features incluídas:** #1, #4, #14

---

#### Feature #1 — Download Automático de XML via Certificado Digital

**Descrição:** "Conecte seu certificado digital uma vez e o FiscoPilot puxa suas NF-e de entrada automaticamente." Elimina o upload manual e transforma o produto em monitoramento contínuo. Feature mais impactante pós-MVP.

**Novo módulo:** `apps/api/src/modules/sefaz/`

```
modules/sefaz/
├── index.ts              # Plugin Fastify
├── routes.ts             # CRUD certificado, trigger download
├── certificate-store.ts  # Armazenamento seguro de certificados A1
├── nfe-download.ts       # Cliente SOAP para Sefaz WS
├── scheduler.ts          # Cron de download automático
└── queue.ts              # Fila de downloads (pg-boss)
```

**Novas tabelas:**

```sql
CREATE TABLE digital_certificates (
  id                uuid PRIMARY KEY DEFAULT gen_random_uuid(),
  organization_id   uuid NOT NULL REFERENCES organizations(id),
  certificate_type  varchar(5) NOT NULL,
  certificate_pem   bytea NOT NULL,
  certificate_key   bytea NOT NULL,
  encryption_iv     bytea NOT NULL,
  cnpj_titular      varchar(14) NOT NULL,
  valid_from        date NOT NULL,
  valid_until       date NOT NULL,
  is_active         boolean NOT NULL DEFAULT true,
  last_used_at      timestamptz,
  created_at        timestamptz NOT NULL DEFAULT now(),

  CONSTRAINT CK_cert_type CHECK (certificate_type IN ('A1', 'A3'))
);

CREATE TABLE sefaz_download_sessions (
  id                uuid PRIMARY KEY DEFAULT gen_random_uuid(),
  organization_id   uuid NOT NULL REFERENCES organizations(id),
  certificate_id    uuid NOT NULL REFERENCES digital_certificates(id),
  status            varchar(20) NOT NULL DEFAULT 'PENDING',
  period_start      date NOT NULL,
  period_end        date NOT NULL,
  total_found       integer DEFAULT 0,
  total_downloaded  integer DEFAULT 0,
  total_new         integer DEFAULT 0,
  total_duplicate   integer DEFAULT 0,
  error_message     text,
  started_at        timestamptz,
  completed_at      timestamptz,
  created_at        timestamptz NOT NULL DEFAULT now()
);

CREATE TABLE sefaz_download_queue (
  id                uuid PRIMARY KEY DEFAULT gen_random_uuid(),
  organization_id   uuid NOT NULL REFERENCES organizations(id),
  certificate_id    uuid NOT NULL REFERENCES digital_certificates(id),
  scheduled_at      timestamptz NOT NULL,
  period_start      date NOT NULL,
  period_end        date NOT NULL,
  status            varchar(20) NOT NULL DEFAULT 'SCHEDULED',
  attempts          integer NOT NULL DEFAULT 0,
  max_attempts      integer NOT NULL DEFAULT 3,
  created_at        timestamptz NOT NULL DEFAULT now()
);
```

**Novas rotas API:**

| Método | Rota | Descrição |
|---|---|---|
| POST | `/api/v1/certificates` | Upload certificado A1 (multipart, criptografado) |
| GET | `/api/v1/certificates` | Lista certificados da org |
| DELETE | `/api/v1/certificates/:id` | Remove certificado |
| POST | `/api/v1/sefaz/download` | Trigger manual de download |
| GET | `/api/v1/sefaz/download/:id` | Status do download |
| GET | `/api/v1/sefaz/download-history` | Histórico de downloads |
| PATCH | `/api/v1/sefaz/schedule` | Configura download automático (diário/semanal) |

**Segurança do certificado:**
- Criptografia AES-256-GCM em repouso
- Chave de criptografia derivada de `CERTIFICATE_ENCRYPTION_KEY` (env var)
- Certificado NUNCA logado, NUNCA exposto via API
- Alerta de vencimento 30/15/7 dias antes

**Dependências npm novas:** `node-forge` (certificado X.509/PFX), `soap` (webservices Sefaz)

**Variáveis de ambiente novas:**

```
CERTIFICATE_ENCRYPTION_KEY=<64-char-hex>
SEFAZ_DOWNLOAD_ENABLED=true
SEFAZ_DOWNLOAD_SCHEDULE="0 5 * * *"
```

**Critério de aceitação:** Certificado A1 uploadado e criptografado. Download automático diário funcional. Notas baixadas entram no pipeline de processamento existente. Alerta de vencimento do certificado.

---

#### Feature #4 — Gestão de Pendências como Kanban

**Descrição:** Mini-CRM de pendências fiscais. Cada inconsistência ganha responsável, prazo, comentários, anexos de comprovação e botões "enviar para contador" e "enviar mensagem para fornecedor". Transforma o alerta em ação rastreável.

**Novo módulo:** `apps/api/src/modules/kanban/`

```
modules/kanban/
├── index.ts          # Plugin Fastify
├── routes.ts         # CRUD comentários, anexos, atribuições
└── board.ts          # Query de board (colunas = status)
```

**Novas tabelas:**

```sql
CREATE TABLE inconsistency_comments (
  id                uuid PRIMARY KEY DEFAULT gen_random_uuid(),
  inconsistency_id  uuid NOT NULL REFERENCES inconsistencies(id) ON DELETE CASCADE,
  organization_id   uuid NOT NULL REFERENCES organizations(id),
  user_id           uuid REFERENCES users(id),
  author_type       varchar(20) NOT NULL,
  comment_text      text NOT NULL,
  created_at        timestamptz NOT NULL DEFAULT now()
);

CREATE TABLE inconsistency_attachments (
  id                uuid PRIMARY KEY DEFAULT gen_random_uuid(),
  inconsistency_id  uuid NOT NULL REFERENCES inconsistencies(id) ON DELETE CASCADE,
  organization_id   uuid NOT NULL REFERENCES organizations(id),
  user_id           uuid REFERENCES users(id),
  file_name         varchar(255) NOT NULL,
  file_path         text NOT NULL,
  file_size         integer NOT NULL,
  mime_type         varchar(100) NOT NULL,
  description       text,
  created_at        timestamptz NOT NULL DEFAULT now()
);

CREATE TABLE inconsistency_assignments (
  id                uuid PRIMARY KEY DEFAULT gen_random_uuid(),
  inconsistency_id  uuid NOT NULL REFERENCES inconsistencies(id) ON DELETE CASCADE,
  organization_id   uuid NOT NULL REFERENCES organizations(id),
  assigned_to       uuid REFERENCES users(id),
  assigned_by       uuid REFERENCES users(id),
  due_date          date,
  created_at        timestamptz NOT NULL DEFAULT now(),
  updated_at        timestamptz NOT NULL DEFAULT now(),

  CONSTRAINT UQ_assignment_per_inconsistency UNIQUE (inconsistency_id)
);
```

**Novas rotas API:**

| Método | Rota | Descrição |
|---|---|---|
| GET | `/api/v1/kanban` | Board completo (colunas por status) |
| POST | `/api/v1/inconsistencies/:id/comments` | Adicionar comentário |
| GET | `/api/v1/inconsistencies/:id/comments` | Listar comentários |
| POST | `/api/v1/inconsistencies/:id/attachments` | Upload anexo |
| GET | `/api/v1/inconsistencies/:id/attachments` | Listar anexos |
| PUT | `/api/v1/inconsistencies/:id/assignment` | Atribuir responsável + prazo |
| POST | `/api/v1/inconsistencies/:id/send-to-accountant` | Envia para contador |
| POST | `/api/v1/inconsistencies/:id/send-to-supplier` | Envia mensagem para fornecedor |

**Mockup do Kanban:**

```
┌──────────────────────────────────────────────────────────┐
│  Pendências Fiscais                          Maio 2026   │
├──────────────┬──────────────┬──────────────┬─────────────┤
│  PENDENTE    │ EM ANDAMENTO │  RESOLVIDA   │  IGNORADA   │
│     (3)      │     (2)      │     (5)      │     (1)     │
├──────────────┼──────────────┼──────────────┼─────────────┤
│ ┌──────────┐ │ ┌──────────┐ │ ┌──────────┐ │ ┌─────────┐│
│ │🔴 Cimento│ │ │⚠️ Telha- │ │ │✅ Ferrag.│ │ │⚠️ Pisos ││
│ │  Bom     │ │ │  norte   │ │ │  do Zé   │ │ │  Sul    ││
│ │ R$ 8.400 │ │ │ R$ 3.200 │ │ │ R$ 2.890 │ │ │ R$ 520  ││
│ │ CFOP     │ │ │ Valor    │ │ │ CST      │ │ │ NCM     ││
│ │          │ │ │          │ │ │          │ │ │         ││
│ │ Fernanda │ │ │ Roberto  │ │ │ ✅       │ │ │Motivo:  ││
│ │ Prazo:   │ │ │ Prazo:   │ │ │          │ │ │contador ││
│ │ 20/05    │ │ │ 25/05    │ │ │          │ │ │ok       ││
│ └──────────┘ │ └──────────┘ │ └──────────┘ │ └─────────┘│
│ ┌──────────┐ │ ┌──────────┐ │ ┌──────────┐ │             │
│ │🔴 Areal  │ │ │⚠️ C&C    │ │ │✅ Sodimac│ │             │
│ │  Brita   │ │ │          │ │ │          │ │             │
│ │ R$ 5.200 │ │ │ R$ 1.150 │ │ │ R$ 4.300 │ │             │
│ │ CNPJ     │ │ │ Soma     │ │ │ CFOP     │ │             │
│ └──────────┘ │ └──────────┘ │ └──────────┘ │             │
└──────────────┴──────────────┴──────────────┴─────────────┘
```

**Critério de aceitação:** Board com 4 colunas funcionais. Drag & drop entre colunas. Comentários persistidos. Anexos uploadados. Atribuição com prazo. Botões "Enviar para contador" e "Enviar para fornecedor" integrados com Features #2 e #5.

---

#### Feature #14 — Alerta de Certificado Digital e Dados Cadastrais

**Descrição:** Mini-monitor cadastral que alerta sobre certificado digital vencendo, CNPJ de fornecedor inapto, inscrição estadual irregular, CNAE incompatível e fornecedores recorrentes com problema. Expande a regra R4 (CNPJ ativo) para monitoramento contínuo.

**Novo módulo:** `apps/api/src/modules/cadastral/`

```
modules/cadastral/
├── index.ts              # Plugin Fastify
├── routes.ts             # GET alertas, configurações
├── certificate-monitor.ts # Verifica vencimento de certificados
├── cnpj-monitor.ts        # Consulta situação cadastral (RFB)
├── ie-monitor.ts          # Inscrição estadual (Sintegra)
└── scheduler.ts           # Cron de verificação
```

**Novas tabelas:**

```sql
CREATE TABLE cadastral_alerts (
  id                uuid PRIMARY KEY DEFAULT gen_random_uuid(),
  organization_id   uuid NOT NULL REFERENCES organizations(id),
  alert_type        varchar(30) NOT NULL,
  entity_type       varchar(30) NOT NULL,
  entity_cnpj       varchar(14),
  entity_name       varchar(200),
  severity          varchar(20) NOT NULL,
  message           text NOT NULL,
  details           jsonb,
  is_read           boolean NOT NULL DEFAULT false,
  dismissed_at      timestamptz,
  created_at        timestamptz NOT NULL DEFAULT now()
);

CREATE TABLE cadastral_monitoring_config (
  id                uuid PRIMARY KEY DEFAULT gen_random_uuid(),
  organization_id   uuid NOT NULL REFERENCES organizations(id),
  monitor_type      varchar(30) NOT NULL,
  enabled           boolean NOT NULL DEFAULT true,
  check_interval    varchar(20) NOT NULL DEFAULT 'weekly',
  last_checked_at   timestamptz,
  created_at        timestamptz NOT NULL DEFAULT now(),

  CONSTRAINT UQ_monitor_per_org UNIQUE (organization_id, monitor_type)
);
```

**Novas rotas API:**

| Método | Rota | Descrição |
|---|---|---|
| GET | `/api/v1/cadastral/alerts` | Lista alertas cadastrais |
| PATCH | `/api/v1/cadastral/alerts/:id/read` | Marca como lido |
| PATCH | `/api/v1/cadastral/alerts/:id/dismiss` | Descarta alerta |
| GET | `/api/v1/cadastral/config` | Configuração de monitoramento |
| PUT | `/api/v1/cadastral/config` | Atualiza configuração |

**Tipos de alerta:**

| Tipo | Severidade | Gatilho |
|---|---|---|
| `CERTIFICATE_EXPIRING` | WARNING | Certificado vence em 30/15/7 dias |
| `CERTIFICATE_EXPIRED` | CRITICAL | Certificado vencido |
| `CNPJ_INAPTO` | CRITICAL | Fornecedor com CNPJ inapto/suspenso |
| `IE_IRREGULAR` | WARNING | Inscrição estadual irregular |
| `CNAE_INCOMPATIVEL` | WARNING | CNAE do fornecedor incompatível com NF-e |
| `SUPPLIER_RECURRENT_ISSUE` | WARNING | Fornecedor com >3 inconsistências em 90 dias |

**Critério de aceitação:** Verificação cadastral automática semanal. Alertas visíveis no dashboard com badge de contagem. Alertas críticos disparam notificação WhatsApp.

---

### Riscos e pontos de atenção da Fase B

| Risco | Severidade | Mitigação |
|---|---|---|
| Webservices da Sefaz (NFeConsultaDest) têm histórico de instabilidade e downtime | Alta | Retry com backoff exponencial. Fila de downloads (pg-boss). Alerta founder se API falhar >3x |
| Armazenar certificado digital cria responsabilidade legal e risco de segurança | Alta | Criptografia AES-256-GCM. Certificado NUNCA em logs. Pen-test antes de lançar. Termo de responsabilidade |
| Kanban (Feature #4) pode adicionar complexidade desnecessária se usuário não adotar | Média | Lançar como feature opcional. Dashboard simples continua sendo a tela principal |
| API da Receita Federal para consulta de CNPJ tem rate limit e instabilidade | Média | Cache de 7 dias por CNPJ. Batch processing noturno (não em tempo real) |
| Download automático pode baixar notas que o fornecedor cancelou depois | Baixa | Pipeline verifica `status_nfe` e marca canceladas. Não gera inconsistência para nota cancelada |

---

### FASE C — Inteligência e Ecossistema (Mês 7-9, ~35 dias)

**Objetivo da fase:** Adicionar inteligência ao produto — portal do contador (transforma gatekeeper em aliado), score de fornecedores (valor de negócio além do fiscal) e assistente de IA (explicação contextual sem risco).

**Features incluídas:** #2, #3, #12

---

#### Feature #2 — Modo Contador (Portal)

**Descrição:** Portal dedicado para o contador com login próprio, lista de clientes atendidos, comentários por inconsistência, botão "validado pelo contador", exportação mensal e histórico de ações. Transforma o contador de influenciador cético em aliado do ecossistema.

**Novo módulo:** `apps/api/src/modules/accountant/`

```
modules/accountant/
├── index.ts          # Plugin Fastify
├── routes.ts         # Auth, CRUD clientes, comentários, validação
├── auth.ts           # Auth separado para contadores (CPF + senha)
└── export.ts         # Exportação mensal consolidada
```

**Novas tabelas:**

```sql
CREATE TABLE accountants (
  id                uuid PRIMARY KEY DEFAULT gen_random_uuid(),
  nome              varchar(150) NOT NULL,
  cpf               varchar(11) NOT NULL UNIQUE,
  email             varchar(255) NOT NULL UNIQUE,
  password_hash     varchar(255) NOT NULL,
  crc_numero        varchar(30),
  crc_uf            char(2),
  whatsapp          varchar(15),
  is_active         boolean NOT NULL DEFAULT true,
  last_login_at     timestamptz,
  created_at        timestamptz NOT NULL DEFAULT now(),
  updated_at        timestamptz NOT NULL DEFAULT now()
);

CREATE TABLE accountant_clients (
  id                uuid PRIMARY KEY DEFAULT gen_random_uuid(),
  accountant_id     uuid NOT NULL REFERENCES accountants(id) ON DELETE CASCADE,
  organization_id   uuid NOT NULL REFERENCES organizations(id) ON DELETE CASCADE,
  invited_by        uuid REFERENCES users(id),
  status            varchar(20) NOT NULL DEFAULT 'PENDING',
  invited_at        timestamptz NOT NULL DEFAULT now(),
  accepted_at       timestamptz,

  CONSTRAINT UQ_accountant_client UNIQUE (accountant_id, organization_id)
);

CREATE TABLE accountant_comments (
  id                uuid PRIMARY KEY DEFAULT gen_random_uuid(),
  accountant_id     uuid NOT NULL REFERENCES accountants(id),
  organization_id   uuid NOT NULL REFERENCES organizations(id),
  inconsistency_id  uuid REFERENCES inconsistencies(id),
  comment_text      text NOT NULL,
  is_validation     boolean NOT NULL DEFAULT false,
  validated_at      timestamptz,
  created_at        timestamptz NOT NULL DEFAULT now()
);

CREATE TABLE accountant_monthly_exports (
  id                uuid PRIMARY KEY DEFAULT gen_random_uuid(),
  accountant_id     uuid NOT NULL REFERENCES accountants(id),
  organization_id   uuid NOT NULL REFERENCES organizations(id),
  month             varchar(7) NOT NULL,
  status            varchar(20) NOT NULL DEFAULT 'PENDING',
  pdf_url           text,
  generated_at      timestamptz,
  downloaded_at     timestamptz,
  created_at        timestamptz NOT NULL DEFAULT now()
);
```

**Novas rotas API (prefixo `/api/v1/accountant/`):**

| Método | Rota | Descrição |
|---|---|---|
| POST | `/api/v1/accountant/auth/login` | Login CPF + senha |
| POST | `/api/v1/accountant/auth/register` | Registro do contador |
| GET | `/api/v1/accountant/clients` | Lista de clientes |
| POST | `/api/v1/accountant/clients/:orgId/accept` | Aceita convite |
| GET | `/api/v1/accountant/clients/:orgId/dashboard` | Dashboard do cliente |
| GET | `/api/v1/accountant/clients/:orgId/inconsistencies` | Inconsistências |
| POST | `/api/v1/accountant/clients/:orgId/comments` | Comentar |
| POST | `/api/v1/accountant/clients/:orgId/validate/:inconsistencyId` | "Validado" |
| POST | `/api/v1/accountant/clients/:orgId/export` | Gerar exportação mensal |
| GET | `/api/v1/accountant/exports` | Lista exportações |

**Novo app web:** `apps/web/src/app/accountant/`

```
app/accountant/
├── page.tsx                    # Login do contador
├── dashboard/
│   └── page.tsx                # Lista de clientes
├── clients/[orgId]/
│   ├── page.tsx                # Dashboard do cliente
│   ├── inconsistencies/
│   │   └── page.tsx            # Lista com comentários
│   └── exports/
│       └── page.tsx            # Exportações mensais
└── register/
    └── page.tsx                # Registro
```

**Critério de aceitação:** Contador faz login com CPF + senha. Vê lista de clientes. Comenta em inconsistências. Valida com selo "Validado pelo contador". Gera exportação mensal consolidada.

---

#### Feature #3 — Score de Fornecedores

**Descrição:** Dashboard de fornecedores com score baseado em histórico de 90 dias — erros, valor em risco, CNPJ irregular, recorrência de problemas. Cards de "fornecedores confiáveis", "fornecedores com mais erros" e "fornecedores com maior valor em risco". Valor de negócio além do fiscal.

**Novo módulo:** `apps/api/src/modules/suppliers/`

```
modules/suppliers/
├── index.ts          # Plugin Fastify
├── routes.ts         # GET lista, GET detalhe
├── scorer.ts         # Cálculo de score por fornecedor
└── categories.ts     # Classificação (confiável, atenção, risco)
```

**View materializada:**

```sql
CREATE MATERIALIZED VIEW supplier_scores AS
SELECT
  d.organization_id,
  d.cnpj_emitente AS supplier_cnpj,
  MAX(d.nome_emitente) AS supplier_name,
  COUNT(DISTINCT d.id) AS total_notes_90d,
  SUM(d.valor_total) AS total_value_90d,
  COUNT(DISTINCT i.id) AS total_inconsistencies_90d,
  COUNT(DISTINCT i.id) FILTER (WHERE i.classification = 'RISCO_ALTO') AS high_risk_count,
  COALESCE(SUM(i.estimated_impact), 0) AS total_risk_value,
  CASE
    WHEN COUNT(DISTINCT d.id) = 0 THEN 0
    ELSE ROUND(
      COUNT(DISTINCT i.id)::numeric / COUNT(DISTINCT d.id)::numeric * 100, 1
    )
  END AS error_rate,
  CASE
    WHEN COUNT(DISTINCT i.id) = 0 THEN 'CONFIÁVEL'
    WHEN COUNT(DISTINCT i.id) FILTER (WHERE i.classification = 'RISCO_ALTO') > 0 THEN 'RISCO'
    WHEN COUNT(DISTINCT i.id)::numeric / GREATEST(COUNT(DISTINCT d.id), 1)::numeric > 0.2 THEN 'ATENCAO'
    ELSE 'CONFIÁVEL'
  END AS category
FROM nfe_documents d
LEFT JOIN inconsistencies i ON i.nfe_document_id = d.id
WHERE d.data_emissao >= CURRENT_DATE - INTERVAL '90 days'
GROUP BY d.organization_id, d.cnpj_emitente;
```

**Novas rotas API:**

| Método | Rota | Descrição |
|---|---|---|
| GET | `/api/v1/suppliers` | Lista de fornecedores com score |
| GET | `/api/v1/suppliers/:cnpj` | Detalhe do fornecedor |
| GET | `/api/v1/suppliers/ranking` | Ranking por categoria |

**Mockup do card de fornecedor:**

```
┌──────────────────────────────────┐
│  🔴 RISCO                        │
│                                  │
│  Distribuidora CimentoBom        │
│  CNPJ 12.345.678/0001-90        │
│                                  │
│  18 notas em 90 dias            │
│  5 com inconsistências (27,8%)  │
│  3 de risco alto                │
│                                  │
│  Valor em risco: ~R$ 2.340      │
│                                  │
│  Problemas recorrentes:         │
│  · CFOP divergente (3x)         │
│  · Alíquota ICMS (2x)           │
│                                  │
│  [Ver histórico completo →]     │
└──────────────────────────────────┘
```

**Critério de aceitação:** View materializada atualizada diariamente via cron. Ranking por categoria (Confiável, Atenção, Risco). Detalhe do fornecedor com histórico de 90 dias. Só ativa após 90 dias de dados acumulados.

---

#### Feature #12 — Assistente de IA com Limites Claros

**Descrição:** Assistente de IA contextual que responde perguntas sobre inconsistências — "Explique esse alerta em linguagem simples", "O que devo perguntar ao contador?", "Gere uma mensagem para o fornecedor". Sempre baseado nos dados do motor de regras. Nunca calcula imposto nem dá parecer fiscal definitivo.

**Expansão do módulo:** `apps/api/src/modules/explain/`

```
modules/explain/
├── index.ts              # Existente (templates)
├── llm.ts                # Existente (OpenRouter)
├── ai-assistant.ts       # NOVO: chat contextual
├── prompts.ts            # NOVO: system prompts com guardrails
└── guardrails.ts         # NOVO: validação de output
```

**Nova tabela:**

```sql
CREATE TABLE ai_conversations (
  id                uuid PRIMARY KEY DEFAULT gen_random_uuid(),
  organization_id   uuid NOT NULL REFERENCES organizations(id),
  user_id           uuid NOT NULL REFERENCES users(id),
  inconsistency_id  uuid REFERENCES inconsistencies(id),
  question          text NOT NULL,
  answer            text NOT NULL,
  model_used        varchar(50),
  tokens_used       integer,
  latency_ms        integer,
  feedback          varchar(10),
  created_at        timestamptz NOT NULL DEFAULT now()
);
```

**Novas rotas API:**

| Método | Rota | Descrição |
|---|---|---|
| POST | `/api/v1/ai/ask` | Pergunta contextual sobre inconsistência |
| GET | `/api/v1/ai/conversations` | Histórico de conversas |
| POST | `/api/v1/ai/feedback` | Feedback (bom/ruim) |

**Perguntas pré-definidas (botões rápidos):**

```
- "Explique esse alerta em linguagem simples"
- "O que devo perguntar ao contador?"
- "Gere uma mensagem para o fornecedor"
- "Qual o risco real se eu não fizer nada?"
- "Isso é comum no meu setor?"
```

**System prompt com guardrails:**

```
Você é o assistente do FiscoPilot, um copiloto fiscal para PMEs brasileiras.

REGRAS OBRIGATÓRIAS:
1. NUNCA calcule imposto devido ou dê parecer fiscal definitivo
2. NUNCA substitua o contador — sempre recomende confirmação
3. SEMPRE baseie suas respostas nos dados detectados pelo motor de regras
4. SEMPRE inclua disclaimer: "Esta é uma orientação preliminar"
5. Use português simples, nível ensino médio
6. Máximo 150 palavras por resposta
```

**Critério de aceitação:** Assistente responde perguntas contextuais sobre inconsistências. Guardrails impedem respostas que calculem imposto ou deem parecer definitivo. Disclaimer em toda resposta. Feedback (thumbs up/down) persistido.

---

### Riscos e pontos de atenção da Fase C

| Risco | Severidade | Mitigação |
|---|---|---|
| Contador pode sentir que o portal (Feature #2) é "fiscalização do trabalho dele" | Alta | Posicionar como "ferramenta que facilita seu trabalho". Selo "Validado pelo contador" dá autoridade |
| Score de fornecedores (Feature #3) pode gerar conflitos entre lojista e fornecedor | Média | Score é privado (só o lojista vê). Nunca enviar score para fornecedor |
| IA (Feature #12) pode alucinar e dar orientação fiscal errada | Alta | Guardrails rígidos no prompt. Output validado antes de exibir. Fallback para template se IA falhar |
| Portal do contador exige auth separado (CPF + senha) — mais superfície de ataque | Média | bcrypt cost ≥10. Rate limit. 2FA na Fase D |
| View materializada (Feature #3) pode ficar desatualizada se cron falhar | Baixa | Refresh diário via cron. Alerta se refresh falhar. Botão "Atualizar agora" na interface |

---

### FASE D — Plataforma e Escala (Mês 9-12, ~50 dias)

**Objetivo da fase:** Transformar o FiscoPilot em plataforma — simulador da Reforma Tributária (diferenciação competitiva), integrações com ERPs (elimina upload) e biblioteca de regras por UF/setor (expansão para novos mercados).

**Features incluídas:** #9, #10, #13

---

#### Feature #9 — Simulador da Reforma Tributária (CBS/IBS)

**Descrição:** Módulo "Preparação CBS/IBS" que verifica se XMLs já trazem campos de CBS/IBS, alerta campos ausentes, explica o que muda para empresas do Simples, oferece checklist de preparação 2026-2033 e gera relatório "sua loja está pronta para a Reforma Tributária?". Posiciona o FiscoPilot como produto atual e inevitável.

**Novo módulo:** `apps/api/src/modules/reform/`

```
modules/reform/
├── index.ts              # Plugin Fastify
├── routes.ts             # GET readiness, checklist
├── cbs-ibs-checker.ts    # Verifica campos CBS/IBS nos XMLs
├── checklist-engine.ts   # Checklist de preparação
├── timeline.ts           # Timeline 2026-2033
└── report.ts             # Relatório de preparação
```

**Novas tabelas:**

```sql
CREATE TABLE reform_checklist (
  id                uuid PRIMARY KEY DEFAULT gen_random_uuid(),
  organization_id   uuid NOT NULL REFERENCES organizations(id),
  item_key          varchar(50) NOT NULL,
  item_text         text NOT NULL,
  category          varchar(30) NOT NULL,
  is_done           boolean NOT NULL DEFAULT false,
  done_at           timestamptz,
  notes             text,
  created_at        timestamptz NOT NULL DEFAULT now(),
  updated_at        timestamptz NOT NULL DEFAULT now(),

  CONSTRAINT UQ_checklist_per_org UNIQUE (organization_id, item_key)
);

CREATE TABLE cbs_ibs_alerts (
  id                uuid PRIMARY KEY DEFAULT gen_random_uuid(),
  organization_id   uuid NOT NULL REFERENCES organizations(id),
  nfe_document_id   uuid REFERENCES nfe_documents(id),
  alert_type        varchar(30) NOT NULL,
  severity          varchar(20) NOT NULL,
  message           text NOT NULL,
  details           jsonb,
  created_at        timestamptz NOT NULL DEFAULT now()
);
```

**Novas rotas API:**

| Método | Rota | Descrição |
|---|---|---|
| GET | `/api/v1/reform/readiness` | Score de preparação (0-100%) |
| GET | `/api/v1/reform/checklist` | Checklist de itens |
| PATCH | `/api/v1/reform/checklist/:key` | Marcar item como feito |
| GET | `/api/v1/reform/alerts` | Alertas CBS/IBS |
| GET | `/api/v1/reform/timeline` | Timeline 2026-2033 personalizada |
| GET | `/api/v1/reform/report-pdf` | PDF "Sua loja está pronta?" |

**Checklist de preparação:**

```
CADASTRO:
☐ CNPJ atualizado na Receita Federal
☐ Inscrição estadual regular
☐ CNAE principal compatível com atividade

SISTEMAS:
☐ ERP atualizado para suportar CBS/IBS
☐ Fornecedor principal já emite com campos CBS/IBS

PROCESSOS:
☐ Contador informado sobre a transição
☐ Plano de classificação de produtos revisado

TRIBUTOS:
☐ Entendeu a diferença entre ICMS e IBS
☐ Sabe quando CBS começa a valer para o Simples
```

**Critério de aceitação:** Score de preparação calculado (0-100%). Checklist interativo por categoria. Timeline 2026-2033 personalizada. PDF de preparação gerado. Alertas CBS/IBS nos XMLs quando aplicável.

---

#### Feature #10 — Integração com ERPs Brasileiros

**Descrição:** Conectores para Bling, Omie, Tiny e Conta Azul que leem notas fiscais diretamente do ERP do cliente — eliminando upload manual. Vendido como: "Não precisa fazer upload. O FiscoPilot lê as notas do sistema que você já usa."

**Novo módulo:** `apps/api/src/modules/erp/`

```
modules/erp/
├── index.ts              # Plugin Fastify
├── routes.ts             # CRUD conexões, trigger sync
├── connectors/
│   ├── base.ts           # Interface ErpConnector
│   ├── bling.ts          # Conector Bling (API v3)
│   ├── omie.ts           # Conector Omie
│   ├── tiny.ts           # Conector Tiny
│   └── conta-azul.ts     # Conector Conta Azul
├── sync-engine.ts        # Motor de sincronização
└── mapper.ts             # Mapeia dados ERP → NfeDocument
```

**Novas tabelas:**

```sql
CREATE TABLE erp_connections (
  id                uuid PRIMARY KEY DEFAULT gen_random_uuid(),
  organization_id   uuid NOT NULL REFERENCES organizations(id),
  erp_type          varchar(20) NOT NULL,
  access_token      text NOT NULL,
  refresh_token     text,
  token_expires_at  timestamptz,
  config            jsonb NOT NULL DEFAULT '{}',
  is_active         boolean NOT NULL DEFAULT true,
  last_sync_at      timestamptz,
  last_sync_status  varchar(20),
  created_at        timestamptz NOT NULL DEFAULT now(),
  updated_at        timestamptz NOT NULL DEFAULT now()
);

CREATE TABLE erp_sync_logs (
  id                uuid PRIMARY KEY DEFAULT gen_random_uuid(),
  connection_id     uuid NOT NULL REFERENCES erp_connections(id),
  organization_id   uuid NOT NULL REFERENCES organizations(id),
  sync_type         varchar(20) NOT NULL,
  status            varchar(20) NOT NULL,
  total_found       integer DEFAULT 0,
  total_synced      integer DEFAULT 0,
  total_skipped     integer DEFAULT 0,
  error_message     text,
  started_at        timestamptz,
  completed_at      timestamptz,
  created_at        timestamptz NOT NULL DEFAULT now()
);
```

**Novas rotas API:**

| Método | Rota | Descrição |
|---|---|---|
| GET | `/api/v1/erp/connectors` | Lista ERPs suportados |
| POST | `/api/v1/erp/connect` | Inicia fluxo OAuth do ERP |
| GET | `/api/v1/erp/connections` | Lista conexões ativas |
| DELETE | `/api/v1/erp/connections/:id` | Remove conexão |
| POST | `/api/v1/erp/sync` | Trigger manual de sincronização |
| GET | `/api/v1/erp/sync/:id` | Status da sincronização |
| GET | `/api/v1/erp/sync-history` | Histórico de syncs |

**Interface do conector:**

```typescript
interface ErpConnector {
  name: string;
  type: 'BLING' | 'OMIE' | 'TINY' | 'CONTA_AZUL';
  getAuthUrl(orgId: string): string;
  exchangeCode(code: string): Promise<ErpTokens>;
  refreshToken(token: string): Promise<ErpTokens>;
  fetchNfes(token: string, period: DateRange): Promise<RawNfeData[]>;
  mapToNfeDocument(raw: RawNfeData): ParsedNfe;
}
```

**Critério de aceitação:** Ao menos 2 conectores funcionais (Bling + Tiny). OAuth flow completo. Sincronização automática diária. Notas do ERP entram no pipeline de processamento existente.

---

#### Feature #13 — Biblioteca de Regras por UF e Setor

**Descrição:** Plataforma de regras empacotáveis por UF e setor — "pacote SP material de construção", "pacote MG material de construção", "pacote restaurantes", "pacote confecção", "pacote distribuidora de bebidas", "pacote Lucro Presumido". Cada novo setor/estado vira um módulo testável. Permite expansão sem bagunça.

**Refatoração do módulo:** `apps/api/src/modules/rules/`

```
modules/rules/
├── engine.ts             # Existente (orquestrador)
├── types.ts              # Existente
├── packs/                # NOVO: pacotes de regras
│   ├── index.ts          # Registry de pacotes
│   ├── base/             # Regras universais (R1-R8)
│   │   └── index.ts
│   ├── sp-construcao/    # SP + material de construção
│   │   └── index.ts
│   ├── mg-construcao/    # MG + material de construção
│   │   └── index.ts
│   ├── restaurantes/     # Setor restaurantes
│   │   └── index.ts
│   ├── confeccao/        # Setor confecção
│   │   └── index.ts
│   ├── bebidas/          # Distribuidora de bebidas
│   │   └── index.ts
│   └── lucro-presumido/  # Regime Lucro Presumido
│       └── index.ts
└── rule-loader.ts        # NOVO: carrega pacotes por org
```

**Novas tabelas:**

```sql
CREATE TABLE rule_packs (
  id                uuid PRIMARY KEY DEFAULT gen_random_uuid(),
  pack_key          varchar(50) NOT NULL UNIQUE,
  pack_name         varchar(150) NOT NULL,
  description       text,
  sector            varchar(50) NOT NULL,
  uf                char(2),
  regime            organization_regime,
  version           varchar(20) NOT NULL,
  rules_json        jsonb NOT NULL,
  is_active         boolean NOT NULL DEFAULT true,
  activated_at      timestamptz,
  created_at        timestamptz NOT NULL DEFAULT now()
);

CREATE TABLE organization_rule_packs (
  id                uuid PRIMARY KEY DEFAULT gen_random_uuid(),
  organization_id   uuid NOT NULL REFERENCES organizations(id),
  rule_pack_id      uuid NOT NULL REFERENCES rule_packs(id),
  is_enabled        boolean NOT NULL DEFAULT true,
  enabled_at        timestamptz NOT NULL DEFAULT now(),
  disabled_at       timestamptz,

  CONSTRAINT UQ_org_pack UNIQUE (organization_id, rule_pack_id)
);
```

**Novas rotas API:**

| Método | Rota | Descrição |
|---|---|---|
| GET | `/api/v1/rule-packs` | Lista pacotes disponíveis |
| GET | `/api/v1/rule-packs/:key` | Detalhe do pacote |
| POST | `/api/v1/organizations/rule-packs` | Ativar pacote para org |
| DELETE | `/api/v1/organizations/rule-packs/:id` | Desativar pacote |

**Critério de aceitação:** Ao menos 3 pacotes funcionais (SP construção, MG construção, Lucro Presumido). Pacotes ativáveis/desativáveis por organização. Motor de regras carrega pacotes ativos dinamicamente.

---

### Riscos e pontos de atenção da Fase D

| Risco | Severidade | Mitigação |
|---|---|---|
| Reforma Tributária (Feature #9) pode ter regulamentação incompleta ou mudar | Alta | Acompanhar publicações da Receita Federal. Checklist genérico + alertas específicos quando campos CBS/IBS disponíveis |
| APIs de ERPs (Feature #10) podem mudar sem aviso ou ter rate limits restritivos | Média | Versionamento de conectores. Testes de integração contínuos. Fallback para upload manual |
| Biblioteca de regras (Feature #13) pode gerar inconsistência entre pacotes (mesma nota, resultados diferentes) | Média | Pacote base (R1-R8) sempre ativo. Pacotes setoriais adicionam regras, não substituem. Testes cruzados entre pacotes |
| Esforço total da Fase D (~50 dias) pode exceder capacidade do time | Média | Priorizar Feature #10 (ERPs) — maior impacto comercial. Features #9 e #13 podem ser adiadas |
| Lucro Presumido (pacote da Feature #13) tem regras fiscais significativamente diferentes do Simples | Média | Contratar contador consultor para validar regras do pacote Lucro Presumido antes de lançar |

---

### Resumo consolidado da expansão

| Dimensão | MVP (Etapas 1-34) | Pós-MVP (Etapa 35) | Total |
|---|---|---|---|
| Tabelas | 10 | +23 + 1 view | 34 |
| Rotas API | ~13 | +~65 | ~78 |
| Telas | 9 | +14 | 23 |
| Módulos backend | 7 | +12 | 19 |
| Funcionalidades | 35 (F01-F35) | +30 (F36-F65) | 65 |
| Custo infra/mês | ~R$ 168 | +R$ 170 | ~R$ 338 |
| Esforço | 90 dias | +155 dias | 245 dias |

### Diagrama de componentes atualizado

```
apps/api/src/modules/
├── auth/              # Existente
├── ingest/            # Existente
├── parser/            # Existente
├── rules/             # Existente + packs/ (Feature #13)
├── dashboard/         # Existente
├── notify/            # Existente + smart templates (Feature #8)
├── report/            # Existente + owner-report (Feature #7)
├── explain/           # Existente + ai-assistant (Feature #12)
├── messages/          # NOVO (Feature #5)
├── savings/           # NOVO (Feature #6)
├── whatsapp-ingest/   # NOVO (Feature #11)
├── onboarding/        # NOVO (Feature #15)
├── sefaz/             # NOVO (Feature #1)
├── kanban/            # NOVO (Feature #4)
├── cadastral/         # NOVO (Feature #14)
├── accountant/        # NOVO (Feature #2)
├── suppliers/         # NOVO (Feature #3)
├── reform/            # NOVO (Feature #9)
└── erp/               # NOVO (Feature #10)
```

### Riscos gerais da expansão

| Risco | Severidade | Mitigação |
|---|---|---|
| Complexidade total do produto pode crescer além da capacidade do time de 2-3 devs | Alta | Cada fase é auto-contida. Se capacity apertar, adiar Fase D. Contratar dev adicional antes da Fase C |
| Produto pode perder foco ao tentar atender muitos setores/UFs (Feature #13) | Média | Manter ICP original (material de construção, Simples, SP/MG) como core. Novos pacotes são expansões, não pivots |
| Custo de infra pode crescer mais que receita se features não converterem em vendas | Média | Cada fase deve gerar ao menos 5 novos clientes ou permitir aumento de preço (R$ 97 → R$ 147 → R$ 197) |
| Dependência de APIs externas (Sefaz, ERPs, Receita Federal) cria fragilidade | Alta | Toda integração externa tem fallback: upload manual, cache local, retry com backoff |
| Concorrente pode surgir com produto similar antes da Fase D | Baixa | Velocidade de execução é a defesa. 155 dias de vantagem com produto em produção e clientes pagantes |

---

_Conteúdo completo do plano FiscoPilot — 35 etapas, da definição do problema à expansão pós-MVP._

---
