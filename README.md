# 🔐 Miniguia de Estudos: LGPD e Privacidade de Dados com NotebookLM

> Projeto do Desafio de Projeto da DIO: uso de IA como ferramenta de **aprendizagem ativa**, com curadoria de fontes abertas, engenharia de prompts documentada e um miniguia de estudo consolidado.

**Autor(a):** _[seu nome]_ · **GitHub:** _[seu usuário]_ · **Data da curadoria:** 19/09/2026

---

## Sumário

1. [Contexto e objetivos](#1-contexto-e-objetivos)
2. [Curadoria de fontes](#2-curadoria-de-fontes)
3. [Engenharia de prompts e "cicatrizes"](#3-engenharia-de-prompts-e-cicatrizes)
4. [Miniguia de estudo (entrega final)](#4-miniguia-de-estudo-entrega-final)
   - [4.1 Resumos estruturados](#41-resumos-estruturados)
   - [4.2 Glossário](#42-glossário)
   - [4.3 Prompts reutilizáveis](#43-prompts-reutilizáveis)
5. [Limitações e próximos passos](#5-limitações-e-próximos-passos)
6. [Como reproduzir este projeto](#6-como-reproduzir-este-projeto)

---

## 1. Contexto e objetivos

### Tema escolhido

**LGPD (Lei nº 13.709/2018) e privacidade de dados pessoais no Brasil.**

Por que este tema? Quem trabalha com tecnologia (formulários, cadastros, APIs, bancos de dados, logs, IA) trata dados pessoais o tempo todo. Entender a lei deixou de ser assunto só do jurídico: influencia decisões de arquitetura, coleta, armazenamento e resposta a incidentes.

### Objetivos de estudo

| # | Objetivo | Como saberei que atingi |
|---|----------|-------------------------|
| 1 | Entender **o que a LGPD protege e a quem se aplica** | Explico objeto, escopo e exceções sem consultar o texto |
| 2 | Diferenciar **dado pessoal, dado sensível e dado anonimizado** | Classifico exemplos reais corretamente |
| 3 | Dominar as **bases legais** (art. 7º e 11) e saber quando o consentimento é (ou não) necessário | Escolho a base legal adequada para um caso prático |
| 4 | Conhecer **direitos do titular** e **papéis** (controlador, operador, encarregado) | Monto uma tabela "quem faz o quê" de memória |
| 5 | Saber como agir em **incidente de segurança** e quais são as **sanções** | Descrevo o fluxo e os prazos corretamente |
| 6 | Praticar **pensamento crítico com IA**: exigir citações, checar contra a fonte primária e detectar respostas sem lastro | Registro os testes de prompt com gabarito de conferência |

> ⚠️ **Aviso:** material de estudo. Não constitui aconselhamento jurídico.

---

## 2. Curadoria de fontes

Foram escolhidas **5 fontes abertas e oficiais**, priorizando a norma (fonte primária) e as orientações da própria autoridade que a fiscaliza. Todas são carregadas no NotebookLM como link ou PDF (passo a passo na [seção 6](#6-como-reproduzir-este-projeto)).

| # | Fonte | Tipo | Por que entrou no caderno | Link |
|---|-------|------|---------------------------|------|
| 1 | **Lei nº 13.709/2018 (LGPD), texto compilado**, Planalto | Norma (fonte primária) | É a base de tudo: definições (art. 5º), princípios (art. 6º), bases legais (art. 7º e 11), direitos (art. 18), sanções (art. 52) | [planalto.gov.br](https://www.planalto.gov.br/ccivil_03/_ato2015-2018/2018/lei/l13709compilado.htm) |
| 2 | **Guia Orientativo para Definições dos Agentes de Tratamento de Dados Pessoais e do Encarregado**, ANPD | Guia oficial | Explica, com casos hipotéticos, quem é controlador, operador e encarregado e como fica a responsabilidade | [gov.br/anpd](https://www.gov.br/anpd/pt-br/centrais-de-conteudo/materiais-educativos-e-publicacoes/guia-orientativo-para-definicoes-dos-agentes-de-tratamento-de-dados-pessoais-e-do-encarregado) |
| 3 | **Guia Orientativo: Hipóteses Legais de Tratamento, Legítimo Interesse**, ANPD (fev/2024) | Guia oficial | Base legal mais versátil e mais mal compreendida; traz o teste de balanceamento | [gov.br/anpd](https://www.gov.br/anpd/pt-br/centrais-de-conteudo/materiais-educativos-e-publicacoes/guia_orientativo_hipoteses_legais_tratamento_de_dados_pessoais_legitimo_interesse) |
| 4 | **Como Proteger seus Dados Pessoais**, guia do Conselho Nacional de Defesa do Consumidor com a ANPD | Guia para o público leigo | Visão do titular, com linguagem simples: contrapõe o "juridiquês" das fontes 1–3 | [gov.br/anpd](https://www.gov.br/anpd/pt-br/centrais-de-conteudo/materiais-educativos-e-publicacoes/guia_orientativo_como_proteger_seus_dados_pessoais) |
| 5 | **Comunicação de Incidente de Segurança (CIS)**, ANPD (Regulamento: Resolução CD/ANPD nº 15/2024) | Orientação oficial / regulamento | O art. 48 da lei fala em "prazo razoável"; o regulamento define prazos concretos | [gov.br/anpd](https://www.gov.br/anpd/pt-br/canais_atendimento/agente-de-tratamento/comunicado-de-incidente-de-seguranca-cis) |

### Notas de curadoria

- **Fontes de datas diferentes.** O guia de agentes de tratamento é de 2021, o de legítimo interesse de 2024 e a lei compilada é de 2026. Vale conferir se o NotebookLM não mistura terminologia antiga com atual.
- **Mudança recente na lei.** A [Lei nº 15.352/2026](https://www.planalto.gov.br/ccivil_03/_ato2023-2026/2026/lei/l15352.htm) (sancionada em 25/02/2026) transformou a ANPD de *Autoridade* em **Agência Nacional de Proteção de Dados**, autarquia de natureza especial vinculada ao Ministério da Justiça e Segurança Pública. O texto compilado do Planalto (fonte 1) já reflete essa alteração; guias anteriores ainda usam "Autoridade".
- **Sigla ANPD** permanece a mesma.

---

## 3. Engenharia de prompts e "cicatrizes"

### Metodologia

Para cada pergunta estratégica segui o ciclo:

1. **v1: prompt ingênuo** (como qualquer pessoa perguntaria);
2. **v2: prompt estruturado** (papel + escopo + formato + exigência de citação);
3. **v3: prompt de verificação** (peço que o notebook aponte artigo/página e admita quando a fonte não diz);
4. **Conferência** da resposta contra o **gabarito** (extraído da fonte primária, a lei) e registro das falhas.

**Princípios que guiaram os prompts:**

- Limitar a resposta às fontes ("com base **apenas** nas fontes carregadas");
- Pedir **citação com artigo/página**;
- Definir o **formato** (tabela, lista, N linhas);
- Permitir o "não sei": *"se as fontes não trouxerem a informação, diga explicitamente"*;
- Incluir ao menos uma **pergunta-armadilha** para testar alucinação.

> ✍️ **Como usar esta seção:** os prompts e gabaritos abaixo estão prontos. Rode cada versão no seu NotebookLM e preencha os campos **"Registro do teste"**. As respostas e dificuldades precisam ser as **suas**, observadas de verdade: é isso que o mercado valoriza nas "cicatrizes".

---

### Teste 1: Visão geral e escopo

| Versão | Prompt |
|--------|--------|
| v1 | `Me explique a LGPD.` |
| v2 | `Com base apenas nas fontes, explique em até 10 linhas: (a) o objetivo da LGPD, (b) a quem ela se aplica e (c) em quais casos NÃO se aplica. Cite os artigos.` |
| v3 | `Refaça a resposta anterior indicando, para cada afirmação, a fonte e o artigo. Se algum ponto não estiver nas fontes, marque como "não encontrado".` |

**Gabarito (Lei 13.709):** objetivo = proteger direitos fundamentais de liberdade e privacidade e o livre desenvolvimento da personalidade (art. 1º); aplica-se a operações de tratamento no Brasil, à oferta de bens/serviços a pessoas no Brasil ou a dados coletados no Brasil, independentemente da sede (art. 3º); **não** se aplica, por exemplo, ao tratamento por pessoa natural para fins exclusivamente particulares e não econômicos, a fins jornalísticos/artísticos/acadêmicos (com ressalvas) e a segurança pública/defesa nacional (art. 4º).

**Registro do teste**

- Resposta obtida (resumo): ✍️
- Citações apresentadas pelo NotebookLM: ✍️
- Conferência com o gabarito (✅ correto / ⚠️ parcial / ❌ errado): ✍️
- Dificuldade encontrada e ajuste feito: ✍️

---

### Teste 2: Dados pessoais, sensíveis e bases legais

| Versão | Prompt |
|--------|--------|
| v1 | `Quando posso usar dados pessoais de alguém?` |
| v2 | `Liste em tabela as bases legais do art. 7º da LGPD (nome curto + uma frase de explicação). Depois, diga em que o art. 11 (dados sensíveis) difere.` |
| v3 | `Dos exemplos abaixo, classifique como dado pessoal, sensível ou anonimizado e justifique com o artigo: (1) CPF, (2) resultado de exame médico, (3) impressão digital vinculada a um funcionário, (4) estatística agregada sem como identificar ninguém.` |

**Gabarito:** o art. 7º prevê **10 hipóteses** (consentimento; obrigação legal/regulatória; administração pública e políticas públicas; estudos por órgão de pesquisa; execução de contrato; exercício regular de direitos em processo; proteção da vida; tutela da saúde; legítimo interesse; proteção do crédito). O art. 11 tem lista própria para dados sensíveis: consentimento **específico e destacado**, ou hipóteses sem consentimento (obrigação legal, políticas públicas, pesquisa, exercício de direitos, proteção da vida, tutela da saúde, prevenção à fraude na autenticação); **legítimo interesse e proteção do crédito não constam** ali. Exemplos: (1) pessoal, (2) sensível, (3) sensível (biométrico vinculado a pessoa natural), (4) anonimizado, desde que a anonimização não seja reversível com esforços razoáveis (art. 12).

**Registro do teste**

- Resposta obtida (resumo): ✍️
- Conferência com o gabarito: ✍️
- Dificuldade encontrada e ajuste feito: ✍️

---

### Teste 3: Legítimo interesse na prática

| Versão | Prompt |
|--------|--------|
| v1 | `O que é legítimo interesse?` |
| v2 | `Com base no guia da ANPD, explique o teste de balanceamento: quais são as fases e o que se avalia em cada uma.` |
| v3 | `Uma loja online quer enviar e-mails de promoção a clientes atuais sobre produtos semelhantes aos que já compraram. Aplique o teste de balanceamento passo a passo e diga se o legítimo interesse seria adequado. Indique o que o guia diz e o que é interpretação sua.` |

**Gabarito:** base no art. 7º, IX e art. 10; o guia apresenta o teste em **3 fases**: (i) finalidade, (ii) necessidade, (iii) balanceamento e salvaguardas; **não se aplica a dados sensíveis**; para crianças e adolescentes é possível, desde que prevaleça o melhor interesse (Enunciado CD/ANPD nº 1/2023).

**Registro do teste**

- Resposta obtida (resumo): ✍️
- O notebook separou o que é do guia e o que é raciocínio próprio? ✍️
- Dificuldade encontrada e ajuste feito: ✍️

---

### Teste 4: Papéis (controlador, operador, encarregado)

| Versão | Prompt |
|--------|--------|
| v1 | `Quem é responsável pelos dados?` |
| v2 | `Monte uma tabela com controlador, operador e encarregado: definição, exemplo prático e principais obrigações. Cite a fonte de cada linha.` |
| v3 | `Uma startup contrata um serviço de nuvem para armazenar os dados dos seus clientes. Quem é controlador e quem é operador? Em que situação o operador responde solidariamente por danos?` |

**Gabarito:** art. 5º, VI–VIII (controlador decide; operador trata em nome do controlador; encarregado é o canal de comunicação com titulares e ANPD); art. 41, §2º (atividades do encarregado); art. 42, §1º, I (operador responde solidariamente ao descumprir a legislação ou as instruções lícitas do controlador). No exemplo, a startup é controladora e o provedor de nuvem, operador.

**Registro do teste**

- Resposta obtida (resumo): ✍️
- Dificuldade encontrada e ajuste feito: ✍️

---

### Teste 5: Incidente de segurança e prazos

| Versão | Prompt |
|--------|--------|
| v1 | `O que fazer se vazar dado?` |
| v2 | `Descreva em passos numerados o que o controlador deve fazer diante de um incidente de segurança, incluindo a quem comunicar e em quais prazos. Cite a fonte.` |
| v3 | `Diferencie o que diz a LGPD (art. 48) do que diz o regulamento da ANPD sobre prazos. Se houver diferença, explique qual regra é mais específica.` |

**Gabarito:** o art. 48 exige comunicar à ANPD e ao titular incidentes que possam acarretar **risco ou dano relevante**, "em prazo razoável"; o regulamento (Resolução CD/ANPD nº 15/2024) concretiza: **3 dias úteis** a partir do conhecimento de que o incidente afetou dados pessoais, com possibilidade de **complementar em 20 dias úteis**; prazos em dobro para agentes de pequeno porte.

**Registro do teste**

- Resposta obtida (resumo): ✍️
- O notebook confundiu lei com regulamento? ✍️
- Dificuldade encontrada e ajuste feito: ✍️

---

### Teste 6: Direitos do titular

| Versão | Prompt |
|--------|--------|
| v1 | `Quais são meus direitos?` |
| v2 | `Liste os direitos do titular previstos no art. 18 da LGPD, com uma frase explicando cada um.` |
| v3 | `Quero descobrir quais dados uma empresa tem sobre mim e pedir a exclusão. Diga o passo a passo, em quanto tempo ela deve responder e o que fazer se ela não responder.` |

**Gabarito:** art. 18 tem **9 incisos** (confirmação de tratamento; acesso; correção; anonimização/bloqueio/eliminação de dados desnecessários; portabilidade; eliminação dos dados tratados com consentimento; informação sobre compartilhamento; informação sobre a possibilidade de não consentir; revogação do consentimento). Art. 19: resposta em formato simplificado imediatamente ou declaração completa em até **15 dias**. Se não resolver: petição à ANPD (art. 18, §1º) ou aos órgãos de defesa do consumidor (§8º).

**Registro do teste**

- Resposta obtida (resumo): ✍️
- Dificuldade encontrada e ajuste feito: ✍️

---

### Teste 7: Sanções e pergunta-armadilha (anti-alucinação)

| Versão | Prompt |
|--------|--------|
| v1 | `Qual a multa da LGPD?` |
| v2 | `Liste as sanções administrativas do art. 52 e o teto da multa simples.` |
| v3 (armadilha) | `Qual o valor MÍNIMO da multa da LGPD? Se as fontes não informarem, diga claramente que não informam.` |

**Gabarito:** multa simples de até **2% do faturamento** da pessoa jurídica no Brasil no último exercício, limitada a **R$ 50 milhões por infração** (art. 52, II); há também advertência, multa diária, publicização, bloqueio, eliminação, suspensões e proibição de atividades. O art. 52 fixa **teto, não mínimo**: a resposta correta à armadilha é admitir que as fontes não trazem um valor mínimo.

**Registro do teste**

- Resposta obtida (resumo): ✍️
- O notebook inventou um mínimo? ✍️
- Dificuldade encontrada e ajuste feito: ✍️

---

### 3.1 Quadro-resumo de "cicatrizes" (preencher após os testes)

| # | Problema encontrado | Causa provável | O que resolveu |
|---|---------------------|----------------|----------------|
| 1 | ✍️ | ✍️ | ✍️ |
| 2 | ✍️ | ✍️ | ✍️ |
| 3 | ✍️ | ✍️ | ✍️ |

**Padrões a observar durante os testes** (marque os que realmente ocorrerem): respostas genéricas com prompt curto · citação sem artigo · mistura de lei e regulamento · mistura de terminologia antiga ("Autoridade") e nova ("Agência") · afirmação sem lastro nas fontes · resposta longa demais.

---

## 4. Miniguia de estudo (entrega final)

### 4.1 Resumos estruturados

#### A) Visão geral

- **Lei nº 13.709/2018 (LGPD)** regula o tratamento de dados pessoais, inclusive em meios digitais, por pessoa natural ou jurídica, pública ou privada, para proteger liberdade, privacidade e o livre desenvolvimento da personalidade (art. 1º).
- **Fundamentos** (art. 2º): respeito à privacidade, autodeterminação informativa, liberdade de expressão, inviolabilidade da intimidade/honra/imagem, desenvolvimento econômico e tecnológico, livre iniciativa e defesa do consumidor, direitos humanos.
- **Alcance** (art. 3º): vale independentemente do país da sede, desde que o tratamento ocorra no Brasil, vise oferta de bens/serviços a pessoas no Brasil ou envolva dados coletados no Brasil.
- **Exceções** (art. 4º): uso exclusivamente particular e não econômico; fins jornalísticos, artísticos e acadêmicos (com regras próprias); segurança pública, defesa nacional, segurança do Estado e investigação penal (regidos por lei específica).

#### B) Tipos de dado

| Categoria | Ideia central | Base |
|-----------|---------------|------|
| Dado pessoal | Informação relacionada a pessoa natural **identificada ou identificável** | art. 5º, I |
| Dado pessoal sensível | Origem racial/étnica, convicção religiosa, opinião política, filiação sindical ou a organização religiosa/filosófica/política, saúde, vida sexual, dado genético ou biométrico (quando vinculado a pessoa) | art. 5º, II |
| Dado anonimizado | Não permite identificar o titular com meios técnicos razoáveis; **deixa de ser pessoal**, salvo se a anonimização puder ser revertida | art. 5º, III e art. 12 |
| Pseudonimização | Dado só se associa a alguém com informação adicional mantida separadamente pelo controlador | art. 13, §4º |

#### C) Os 10 princípios (art. 6º)

Finalidade · Adequação · Necessidade · Livre acesso · Qualidade dos dados · Transparência · Segurança · Prevenção · Não discriminação · Responsabilização e prestação de contas.

> 💡 Mnemônico usado: **F-A-N-L-Q-T-S-P-N-R**.

#### D) Bases legais (art. 7º) e dados sensíveis (art. 11)

- Tratamento **só** pode ocorrer se houver uma das **10 hipóteses** do art. 7º. O **consentimento é apenas uma delas**, e não a "principal por padrão".
- **Consentimento válido:** livre, informado, inequívoco e para finalidade determinada (art. 5º, XII); autorizações genéricas são nulas (art. 8º, §4º); pode ser revogado a qualquer momento, de forma gratuita e facilitada (art. 8º, §5º); o **ônus da prova é do controlador** (art. 8º, §2º).
- **Dados sensíveis** seguem lista própria (art. 11): consentimento específico e destacado **ou** hipóteses sem consentimento. Legítimo interesse e proteção do crédito **não** estão nessa lista.
- **Crianças e adolescentes:** tratamento no seu melhor interesse; para crianças, consentimento específico e em destaque de ao menos um dos pais ou responsável (art. 14).
- **Legítimo interesse** (art. 7º, IX e art. 10): exige análise concreta; o guia da ANPD propõe teste de balanceamento em três fases (finalidade → necessidade → balanceamento e salvaguardas).

#### E) Direitos do titular (arts. 17–22)

Confirmação · Acesso · Correção · Anonimização/bloqueio/eliminação · Portabilidade · Eliminação (dados tratados com consentimento) · Informação sobre compartilhamento · Informação sobre negar consentimento · Revogação do consentimento.

- Atendimento **sem custos** (art. 18, §5º); resposta simplificada imediata ou declaração completa em até **15 dias** (art. 19).
- **Revisão de decisões automatizadas** que afetem interesses do titular (art. 20).
- Reclamação: controlador → petição à ANPD; também aos órgãos de defesa do consumidor (art. 18, §§1º e 8º).

#### F) Agentes de tratamento e encarregado

| Papel | Quem é | Exemplos de obrigações |
|-------|--------|------------------------|
| **Controlador** | Quem toma as decisões sobre o tratamento (art. 5º, VI) | Indicar encarregado (art. 41); comprovar o consentimento (art. 8º, §2º); comunicar incidentes (art. 48); elaborar RIPD quando exigido (art. 38) |
| **Operador** | Quem trata dados **em nome do controlador** (art. 5º, VII) | Seguir instruções lícitas do controlador (art. 39); adotar medidas de segurança |
| **Encarregado** | Pessoa indicada como **canal de comunicação** entre controlador, titulares e ANPD (art. 5º, VIII) | Receber reclamações e comunicações da ANPD; orientar equipe (art. 41, §2º) |

- **Responsabilidade civil** (art. 42): quem causar dano em violação à lei deve repará-lo; o operador responde **solidariamente** se descumprir a lei ou as instruções lícitas do controlador; o juiz pode inverter o ônus da prova a favor do titular.
- O guia da ANPD é **orientativo e não vinculante**; a definição do papel depende de **quem decide** no caso concreto, e não do que o contrato diz.

#### G) Segurança, boas práticas e incidentes

- **Segurança** (art. 46): medidas técnicas e administrativas desde a **concepção** do produto ou serviço até sua execução (*privacy by design*).
- **Governança** (art. 50): programa de governança em privacidade, planos de resposta a incidentes, avaliação de impacto e riscos.
- **Incidente** (art. 48): comunicar à ANPD e ao titular quando puder haver risco ou dano relevante. O regulamento da ANPD (Res. CD/ANPD nº 15/2024) fixa **3 dias úteis** para comunicar e **20 dias úteis** para complementar, com prazo em dobro para agentes de pequeno porte.

#### H) Fiscalização e sanções

- A **ANPD** é o órgão central de interpretação, fiscalização e aplicação das sanções (arts. 55-J e 55-K); desde a Lei 15.352/2026 é uma **agência** (autarquia de natureza especial) vinculada ao MJSP.
- **Sanções (art. 52):** advertência; multa simples de até 2% do faturamento no Brasil, limitada a R$ 50 milhões por infração; multa diária; publicização da infração; bloqueio e eliminação dos dados; suspensão parcial do banco de dados e do exercício da atividade (até 6 meses, prorrogável); proibição parcial ou total de atividades.
- As sanções são aplicadas de forma gradativa, com **ampla defesa**, considerando gravidade, boa-fé, reincidência, cooperação e adoção de boas práticas (art. 52, §1º).

#### I) Transferência internacional (visão rápida)

Só é permitida em hipóteses do art. 33, como: país com grau de proteção adequado; garantias oferecidas pelo controlador (cláusulas contratuais específicas ou padrão, normas corporativas globais, selos/certificados); consentimento específico e em destaque; autorização da ANPD, entre outras.

---

### 4.2 Glossário

| Termo | Definição (linguagem direta) | Onde aparece |
|-------|------------------------------|--------------|
| **LGPD** | Lei Geral de Proteção de Dados Pessoais (Lei 13.709/2018) | Fonte 1 |
| **Dado pessoal** | Informação sobre pessoa natural identificada ou identificável | art. 5º, I |
| **Dado pessoal sensível** | Dado com maior risco de discriminação (saúde, biometria, religião, etc.) | art. 5º, II |
| **Dado anonimizado** | Dado que não permite identificar a pessoa por meios técnicos razoáveis | art. 5º, III |
| **Anonimização** | Processo que retira a possibilidade de associar o dado a um indivíduo | art. 5º, XI |
| **Pseudonimização** | Dado só é ligado à pessoa com uma informação adicional guardada separadamente | art. 13, §4º |
| **Titular** | Pessoa natural a quem os dados se referem | art. 5º, V |
| **Controlador** | Quem decide como e por que os dados são tratados | art. 5º, VI |
| **Operador** | Quem trata os dados em nome do controlador | art. 5º, VII |
| **Agentes de tratamento** | Controlador e operador | art. 5º, IX |
| **Encarregado** | Canal de comunicação entre controlador, titulares e ANPD (equivale ao "DPO" no jargão, mas não são idênticos) | art. 5º, VIII e art. 41 |
| **Tratamento** | Qualquer operação com dados: coleta, uso, armazenamento, compartilhamento, eliminação etc. | art. 5º, X |
| **Consentimento** | Manifestação livre, informada e inequívoca para finalidade determinada | art. 5º, XII |
| **Base legal (hipótese legal)** | Fundamento que autoriza o tratamento de dados | arts. 7º e 11 |
| **Legítimo interesse** | Base legal que atende a interesse legítimo do controlador ou de terceiro, se não prevalecerem os direitos do titular | art. 7º, IX e art. 10 |
| **Teste de balanceamento** | Avaliação em fases (finalidade, necessidade, balanceamento e salvaguardas) que sustenta o uso do legítimo interesse | Fonte 3 |
| **Finalidade** | Princípio: o tratamento deve ter propósito legítimo, específico, explícito e informado | art. 6º, I |
| **Minimização (necessidade)** | Tratar só o mínimo necessário para a finalidade | art. 6º, III |
| **RIPD** | Relatório de Impacto à Proteção de Dados Pessoais: documento que descreve tratamentos de risco e medidas de mitigação | art. 5º, XVII e art. 38 |
| **Portabilidade** | Direito de levar os dados a outro fornecedor de serviço | art. 18, V |
| **Incidente de segurança** | Evento adverso confirmado que viola a confidencialidade, integridade, disponibilidade ou autenticidade de dados pessoais | Fonte 5 |
| **Privacy by design** | Segurança e privacidade previstas desde a concepção do produto ou serviço | art. 46, §2º |
| **Transferência internacional** | Envio de dados pessoais a outro país ou organismo internacional | art. 5º, XV e art. 33 |
| **ANPD** | Agência Nacional de Proteção de Dados: fiscaliza, regulamenta e sanciona | arts. 55-A a 55-K |

---

### 4.3 Prompts reutilizáveis

Basta substituir os campos entre `[colchetes]`. Todos partem do princípio "**responda só com base nas fontes e cite**".

**1. Resumo estruturado de um tópico**
```
Com base apenas nas fontes carregadas, resuma [TÓPICO] em no máximo [N] linhas,
com subtítulos. Cite o artigo ou a página de cada afirmação.
Se algum ponto não estiver nas fontes, escreva "não encontrado nas fontes".
```

**2. Glossário sob demanda**
```
Crie um glossário com os termos: [LISTA DE TERMOS]. Para cada um: definição em
uma frase simples, um exemplo do dia a dia e a fonte (com artigo/página).
```

**3. Quiz de revisão**
```
Crie [N] perguntas de múltipla escolha sobre [TÓPICO], com 4 alternativas,
gabarito e explicação com citação. Misture níveis: memorização, aplicação e caso prático.
```

**4. Caso prático com análise passo a passo**
```
Situação: [DESCREVER CASO]. Analise à luz das fontes: (1) que dados estão
envolvidos e de que tipo; (2) qual base legal poderia se aplicar e por quê;
(3) quais direitos do titular são relevantes; (4) quais riscos existem.
Separe o que está nas fontes do que é sua interpretação.
```

**5. Comparação em tabela**
```
Compare [CONCEITO A] e [CONCEITO B] em uma tabela com colunas: definição,
quando se aplica, exemplo, artigo/fonte. Ao final, aponte a diferença mais
confundida na prática.
```

**6. Detector de alucinação (verificação)**
```
Releia sua resposta anterior. Para cada afirmação, indique a fonte exata que a
sustenta. Marque como "SEM LASTRO" qualquer trecho que você não consiga
ancorar nas fontes e reescreva sem ele.
```

**7. Conflito entre fontes**
```
Existe divergência ou diferença de nível de detalhe entre as fontes sobre
[TÓPICO]? Liste o que cada fonte diz, qual é norma e qual é orientação, e qual
prevalece.
```

**8. Explique como se eu fosse iniciante**
```
Explique [TÓPICO] para alguém sem formação jurídica, em até [N] parágrafos, com
uma analogia, e depois liste 3 erros comuns de interpretação.
```

**9. Flashcards para memorização**
```
Gere [N] flashcards (frente: pergunta curta; verso: resposta objetiva + artigo)
sobre [TÓPICO]. Priorize números, prazos, listas e definições.
```

**10. Checklist prático**
```
Transforme o conteúdo de [TÓPICO] em um checklist de conformidade com itens
verificáveis (sim/não). Ao lado de cada item, o artigo ou a fonte.
```

**11. Plano de estudo**
```
Monte um plano de estudo de [N] dias sobre [TEMA] usando somente as fontes do
caderno: para cada dia, o que ler, o que praticar e uma pergunta de
autoavaliação.
```

---

## 5. Limitações e próximos passos

- **Não é aconselhamento jurídico.** A interpretação da lei em casos concretos cabe a profissionais habilitados e, em última instância, à ANPD e ao Judiciário.
- **Escopo:** ficaram de fora temas correlatos como o ECA Digital (Lei nº 15.211/2025), Marco Civil da Internet, LAI e regulamentos setoriais (saúde, finanças).
- **Próximos passos sugeridos:**
  - adicionar o **regulamento do encarregado** e o **Regulamento de Aplicação da LGPD para agentes de pequeno porte**;
  - montar um caderno separado sobre **RIPD e governança em privacidade**;
  - criar um **mapeamento de dados** (ROPA) simulado para um sistema fictício.

---

## 6. Como reproduzir este projeto

1. Acesse o [NotebookLM](https://notebooklm.google.com) e crie um caderno novo.
2. Adicione as **5 fontes** da [seção 2](#2-curadoria-de-fontes) (como link ou PDF).
3. Rode os prompts da [seção 3](#3-engenharia-de-prompts-e-cicatrizes), comparando cada resposta com o **gabarito**.
4. Registre respostas, citações e dificuldades nos campos **"Registro do teste"**.
5. Use o [miniguia](#4-miniguia-de-estudo-entrega-final) para revisão e adapte os prompts da [seção 4.3](#43-prompts-reutilizáveis) a novos temas.

---

_Projeto desenvolvido para o Desafio de Projeto da [DIO](https://www.dio.me/)._
