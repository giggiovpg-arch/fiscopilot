# Copiloto Fiscal para PME

SaaS B2B brasileiro que ajuda pequenas e médias empresas a importar, interpretar e agir sobre seus dados fiscais — antes que inconsistências virem multas.

---

## Etapa 2 — Escolha do ICP Principal

### Objetivo da etapa

Selecionar, entre 5 perfis de cliente distintos, o **único ICP** para o qual o MVP do Copiloto Fiscal será projetado e comercializado nos primeiros 6 meses. A escolha deve maximizar probabilidade de venda e minimizar complexidade do MVP.

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

> "Você recebe 150 notas por mês dos seus fornecedores. Se uma só vier com CFOP errado, sua DAS pode sair errada e você toma multa de R$ 500 a R$ 5.000. O Copiloto Fiscal lê todas as suas notas, acha os erros e te avisa em português claro. Custa R$ 147/mês."

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

---

## Etapa 3 — Personas

### Objetivo da etapa

Criar 3 personas detalhadas e realistas — compradora, usuária principal e influenciadora — para orientar todas as decisões de produto, UX, comunicação e vendas do Copiloto Fiscal no contexto de lojas de material de construção (Simples Nacional, 5–20 funcionários).

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

Mapear os trabalhos (jobs) que Roberto, Fernanda e Dona Célia precisam realizar — nos níveis funcional, emocional e social — e priorizar qual job o MVP do Copiloto Fiscal deve resolver primeiro. Toda decisão de funcionalidade nas próximas etapas deriva desta priorização.

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
| D4 | Tagline: "Copiloto Fiscal — suas notas fiscais explicadas." | Decisão de comunicação |
| D5 | A mensagem de demo deve incluir obrigatoriamente um "raio-x ao vivo" com dados reais do prospect | Decisão de vendas |

### Proposta de valor em 1 frase

> **O Copiloto Fiscal lê suas notas fiscais de compra, encontra o que está errado e te explica em português claro o que fazer — antes que o erro vire multa.**

### Proposta expandida

Toda semana você recebe dezenas de notas fiscais dos seus fornecedores. Cada nota tem códigos como CFOP, NCM, CST e alíquotas que você não entende — e nem deveria entender. Mas se qualquer um desses códigos vier errado, você pode pagar imposto a mais ou cair na malha fina da Receita. Seu contador só vê isso no fim do mês. Às vezes nem vê. O Copiloto Fiscal analisa cada nota no momento em que você carrega, cruza com as regras do Simples Nacional e te mostra: "3 notas com problema. 1 grave. Se você corrigir essa aqui, economiza R$ 340 na DAS desse mês." Você não precisa aprender fiscal. Você precisa saber o que fazer. É para isso que serve o Copiloto.

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
> *Copiloto Fiscal — Para donos de loja que querem dormir tranquilos.*

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

Definir o menor produto vendável possível — o "Copiloto Fiscal MVP" — com escopo cirúrgico, construível em 90 dias por uma equipe de 2 a 3 pessoas, que gere valor perceptível na primeira semana de uso e justifique uma cobrança mensal a partir do primeiro mês.

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

> Se o Copiloto Fiscal detectar ao menos 1 inconsistência fiscal grave a cada 2 meses (evitando R$ 500+ em multa ou imposto pago a mais), o Roberto percebe valor suficiente para continuar pagando R$ 97/mês e recomendar o produto para outros lojistas.

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

Desenhar a jornada completa que Roberto (dono) e Fernanda (auxiliar) percorrem — do primeiro contato com o Copiloto Fiscal até o uso semanal consolidado — identificando exatamente onde o valor é percebido, onde o abandono ameaça e como cada canal de contato opera, considerando baixa maturidade digital e uso intenso de WhatsApp.

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
| **O que o Roberto faz** | No almoço da associação comercial, comenta com outro lojista: "Tô usando Copiloto Fiscal. Já me salvou de duas notas erradas. Custa 97 conto." Colega pede contato. Roberto encaminha o WhatsApp do founder. |
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

## Etapa 8 — Funcionalidades do MVP

### Objetivo da etapa

Listar exaustivamente as funcionalidades visíveis ao usuário que compõem o Copiloto Fiscal MVP, com descrição, prioridade, critério de aceitação, persona associada, etapa da jornada e esforço estimado. Esta lista será a fonte de verdade para o sprint de construção de 90 dias.

### Premissas adotadas

| # | Premissa | Justificativa |
|---|---|---|
| P1 | "Funcionalidade" = algo que o usuário vê ou sente, não componente interno de arquitetura | Ex.: "Upload de XMLs" é funcionalidade; "fila de processamento assíncrono" é implementação (Etapa 17) |
| P2 | P0 = sem isso, a venda não fecha. P1 = sem isso, a retenção quebra em 30 dias. P2 = sem isso, o usuário não reclama no primeiro mês | Critério pragmático de priorização para MVP |
| P3 | Esforço em dias de desenvolvimento de 1 pessoa sênior (8h/dia útil) | Para time de 2 devs, esforço total é aproximadamente metade dos dias corridos |
| P4 | Cada funcionalidade tem exatamente 1 critério de aceitação principal — binário, testável, sem ambiguidade | Evita funcionalidades que "nunca ficam prontas" |
| P5 | Ordem de construção segue a cadeia de dependência: sem ingestão, nada funciona; sem regras, sem valor; sem dashboard, usuário não vê nada | Construir na ordem da jornada do usuário |

### Decisões recomendadas

| Decisão | Conteúdo | Status |
|---|---|---|
| D1 | 16 funcionalidades P0 (obrigatórias), 7 P1 (importantes), 4 P2 (desejáveis) = total de 27 funcionalidades para o MVP | Decisão de escopo |
| D2 | A ordem de construção é estritamente M1 → M2 → M3 → M4, com M5 sendo construído incrementalmente ao longo do caminho | Decisão de execução |
| D3 | Nenhuma funcionalidade de IA generativa é P0 — o diagnóstico é 100% determinístico; IA só melhora redação das explicações (P2) | Decisão técnica |
| D4 | Funcionalidades que dependem de API externa (Sefaz, Receita Federal) são P1 ou P2; o MVP funciona totalmente offline de serviços públicos | Decisão de arquitetura |

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

### Funcionalidades Explicitamente Excluídas do MVP

| Funcionalidade excluída | Motivo | Quando entra |
|---|---|---|
| Cadastro self-service | Onboarding guiado pelo founder nos primeiros 10 clientes | Fase 2 (mês 4) |
| Download automático de XML via Sefaz | Complexidade alta; upload manual resolve MVP | Fase 2 (mês 4-6) |
| Ingestão via WhatsApp | Exige WhatsApp Business API com webhook complexo | Fase 2 (mês 6) |
| App nativo iOS/Android | Web app responsivo + PWA cobre 100% das necessidades | Fase 3 (mês 9+) |
| Integração com ERP (Tiny, Bling, Omie) | Cada ERP tem API diferente; volume inicial baixo | Fase 2 (mês 5-7) |
| Módulo de contador (login dedicado, multi-cliente) | Contador não é usuário pagante no MVP | Fase 2 (mês 5) |
| IA generativa para diagnóstico fiscal | Diagnóstico é 100% determinístico no MVP; IA é arriscada | Fase 2-3 (mês 7+) |
| Gateway de pagamento | Volume <20 clientes; Pix manual funciona | Fase 2 (mês 4) |
| Trial automatizado | Controle manual do founder | Fase 2 (mês 4) |
| Dashboard de fornecedores | Requer volume acumulado; sem valor nos 3 primeiros meses | Fase 3 (mês 9+) |
| Suporte a Lucro Presumido/Lucro Real | Cada regime tem regras distintas | Fase 2-3 |
| Suporte a NFS-e, CT-e, NFC-e | Cada documento tem schema XML diferente | Fase 2-3 |
| Edição de dados da nota pelo usuário | Risco regulatório: falsificação fiscal | Nunca |
| Apuração de imposto (cálculo da DAS) | Atribuição legal exclusiva do contador | Nunca |
| Envio de obrigações acessórias (SPED, DIRF) | Atribuição exclusiva do contador habilitado | Nunca |

### Ordem de Construção (Sprint Plan)

| Sprint (2 semanas) | Funcionalidades | Marco |
|---|---|---|
| **Sprint 1** (Sem 1-2) | F01, F02, F04, F30, F31, F32 | **M1**: Upload + Auth funcionando |
| **Sprint 2** (Sem 3-4) | F07, F12, F14, F16, F29 | **M2**: Parser + validação básica |
| **Sprint 3** (Sem 5-6) | F08, F09, F10, F13 | **M3**: 5 regras fiscais rodando |
| **Sprint 4** (Sem 7-8) | F17, F18, F19, F20, F21 | **M4 — MVP Interno**: Dashboard completo |
| **Sprint 5** (Sem 9-10) | F03, F05, F22, F28, F33 | **M5 — Beta**: Produto usável em beta |
| **Sprint 6** (Sem 11-12) | F25, F26, F27, P1s/P2s remanescentes, QA | **M6 — Lançamento**: MVP completo |

### Riscos e pontos de atenção

| Risco | Severidade | Mitigação |
|---|---|---|
| Sprint 2 (parser NF-e) pode estourar esforço — XML tem dezenas de namespaces e variações por UF | Alta | Usar biblioteca open source brasileira (nfe-io, python-nfe, BR-NFe). Alocar 2 dias de buffer. |
| Sprint 5 (WhatsApp Business API) pode ter atraso de aprovação do Meta | Média | Iniciar cadastro na Semana 1. Fallback: SMS ou PWA push notification. |
| Funcionalidades P1 do M4 (WhatsApp) impactam retenção mas estão no Sprint 6 | Média | Se Sprint 5 atrasar, cortar F03/F05 para liberar dias para WhatsApp. |
| 16 funcionalidades P0 pode ser alto para 90 dias | Média | 6 P0 são regras fiscais simples (7 dias total). Esforço concentrado no parser (8d) e dashboard (16d). |

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
| D1 | 52 requisitos funcionais: 22 de usuário (RFU), 22 de sistema (RFS), 8 de contorno (RFC) | Decisão de escopo |
| D2 | Cada requisito DEVE ser rastreável a uma funcionalidade FXX e a uma etapa da jornada | Decisão de qualidade |
| D3 | Requisitos são ordem de implementação, não ordem de numeração — a numeração segue o agrupamento por módulo | Decisão de organização |

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
| **RFS-025** | O sistema DEVE gerar PDF do contador em até 5s, com disclaimer obrigatório: "Este relatório foi gerado pelo Copiloto Fiscal como apoio à análise do contador responsável. Trata-se de uma análise automática preliminar que não substitui a validação profissional. Confirme todas as informações com seu contador antes de qualquer ação." | F28 | E4 |
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

### Riscos e pontos de atenção

| Risco | Severidade | Mitigação |
|---|---|---|
| Templates de explicação (RFS-018) podem gerar textos robóticos ou confusos com dados atípicos | Média | Testar com 20 inconsistências reais antes do beta; validar com 3 usuários do ICP |
| Lista de capítulos NCM da regra R3 (RFS-011) pode ser incompleta | Média | Tratar R3 como "sugestão de verificação" (score 50, não 100); permitir founder adicionar capítulos à lista branca |
| Impacto financeiro estimado (RFS-019) pode estar errado para casos complexos (ex.: redução de base de cálculo) | Média | Incluir sempre "estimado" e "confirme com seu contador" ao lado do valor em reais |
| Limite de 1 alerta/hora (RFS-023) pode atrasar detecção de segundo problema grave | Baixa | Uploads são manuais (2-3x/semana); cenário improvável no MVP. Revisar Fase 2. |
| Validação de CNPJ (RFS-028) não garante existência real na RFB | Baixa | Aceitável; RFS-012 complementa com consulta de CNPJ ativo |

---

## Etapa 10 — Requisitos Não Funcionais

### Objetivo da etapa

Especificar os atributos de qualidade do Copiloto Fiscal MVP — desempenho, disponibilidade, segurança, usabilidade, compatibilidade, escalabilidade e manutenibilidade — com metas numéricas testáveis, adequadas a um produto de 90 dias operado por time de 2-3 pessoas e usado por PMEs de baixa maturidade digital.

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
