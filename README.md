# 🔐 Miniguia de Estudos: LGPD para quem trabalha com dados

Caderno temático criado no **NotebookLM** para estudar a Lei Geral de Proteção de Dados Pessoais (LGPD) com foco em quem atua ou quer atuar com análise de dados.
Projeto do desafio da **DIO** · [@soaresjp7](https://github.com/soaresjp7)

---

## 🎯 Contexto e Objetivos

### Por que escolhi esse tema
Quem trabalha com dados lida o tempo todo com informações de pessoas: cadastros, compras, localização, comportamento de navegação. No Brasil, isso é regulado pela **LGPD (Lei nº 13.709/2018)**. Estou em transição de carreira para **análise de dados** e queria entender os limites legais do que posso coletar, tratar e compartilhar. Também achei o tema bom para testar o NotebookLM, já que a lei é um texto denso e as respostas vêm ancoradas nas fontes.

### Objetivos de estudo
1. Entender os conceitos-base da LGPD (dado pessoal, titular, controlador, operador, encarregado, tratamento).
2. Conhecer princípios, bases legais e direitos dos titulares.
3. Diferenciar dado anonimizado de pseudonimizado e entender por que isso importa em análises.
4. Montar um checklist prático para projetos de dados.
5. Documentar como usei a IA para estudar: prompts, erros e ajustes.

> ⚠️ Este material é de estudo e **não é aconselhamento jurídico**. Em casos reais, consulte um profissional da área.

---

## 📚 Curadoria de Fontes

Fontes consultadas em **29/09/2026** e carregadas no NotebookLM como links ou PDFs.

| # | Fonte | Tipo | Link | Por que escolhi |
|---|-------|------|------|-----------------|
| 1 | Lei nº 13.709/2018 (texto compilado) | Legislação | http://www.planalto.gov.br/ccivil_03/_ato2015-2018/2018/lei/l13709compilado.htm | Texto oficial e atualizado da lei |
| 2 | Guia Rápido da LGPD (Escola Superior do MPU) | Guia (PDF) | https://escola.mpu.mp.br/transparencia/lei-geral-de-protecao-de-dados/guiarapidolgpd.pdf | Explica definições e agentes de tratamento citando os artigos |
| 3 | Guia Orientativo da ANPD: Agentes de Tratamento e Encarregado | Guia oficial (PDF) | PDF baixado do site da ANPD (gov.br/anpd) | Interpretação da própria autoridade sobre controlador, operador e encarregado |
| 4 | Lei nº 13.853/2019 | Legislação | https://www.planalto.gov.br/ccivil_03/_ato2019-2022/2019/lei/l13853.htm | Alterou a LGPD e estruturou a ANPD |
| 5 | LGPD e regimes de informação (SciELO) | Artigo científico | https://www.scielo.br/j/rdbci/a/DWntpkXMB9GgCPKycFcxtts/?lang=en | Visão acadêmica e contexto de políticas de informação |

**Critérios:** priorizei fontes oficiais e institucionais, usei o artigo acadêmico como apoio e deixei de fora blogs comerciais e conteúdo de consultorias, por terem interesse comercial e menor rastreabilidade.

---

## 🧪 Engenharia de Prompts e "Cicatrizes"

### Prompt 1: Visão geral
- **Versão 1:** "O que é a LGPD?"
- **Resultado:** resposta bem organizada, com definição da lei, abrangência (meios digitais e físicos, pessoas naturais e jurídicas), objetivo (liberdade, privacidade e livre desenvolvimento da personalidade), autodeterminação informativa, ciclo de vida dos dados, princípios, inspiração no GDPR e os atores (titular, controlador, operador, encarregado).
- **O que faltou:** ligar as afirmações a artigos específicos e ao contexto de análise de dados.
- **Versão ajustada:** "Explique a LGPD para quem está começando em análise de dados, em 6 tópicos curtos, citando o artigo de cada afirmação. Use apenas as fontes do caderno."
- **Aprendizado:** o prompt genérico dá um panorama correto, mas sem foco no meu perfil. Além disso, nessa rodada o caderno tinha só 2 fontes carregadas (o artigo acadêmico e o guia da ANPD), então a resposta refletia apenas esse recorte.

### Prompt 2: Agentes de tratamento
- **Versão 1:** "Quem são os agentes da LGPD?"
- **Resultado:** identificou que os agentes de tratamento são o controlador e o operador (Art. 5º, IX) e trouxe também controladoria conjunta, suboperador e quem **não** é agente (funcionários e equipes subordinadas, que atuam sob o poder diretivo da organização). Fechou com encarregado (DPO) e titular como outros papéis.
- **O que faltou:** exemplos em projetos de dados e um formato mais fácil de consultar.
- **Versão ajustada:** "Monte uma tabela com titular, controlador, operador e encarregado: definição, exemplo em um projeto de dados e artigo de referência."
- **Aprendizado:** o prompt curto já trouxe conteúdo que eu nem tinha pedido (suboperador, quem não é agente). Fixei a distinção: **agente de tratamento** (controlador/operador) não é o mesmo que **encarregado**.

### Prompt 3: Bases legais
- **Versão 1:** "Quais são as bases legais?"
- **Resultado:** resposta incompleta. Listou as hipóteses para **dados sensíveis** (consentimento, obrigação legal, políticas públicas, estudos por órgão de pesquisa, exercício regular de direitos, proteção da vida, tutela da saúde, prevenção à fraude) e a hipótese do poder público. O próprio NotebookLM avisou que as fontes carregadas não traziam a lista completa das 10 hipóteses do Art. 7º, como legítimo interesse e proteção do crédito.
- **Versão ajustada:** "Liste as bases legais para tratamento de dados pessoais e, para cada uma, dê um exemplo de situação em análise de dados. Diga quais exemplos vêm das fontes e quais são inferência sua."
- **Aprendizado (cicatriz principal):** a lacuna veio da minha curadoria, não de erro da ferramenta. O texto da lei não estava no caderno, então a resposta ficou restrita ao que o guia e o artigo cobriam. O ponto positivo é que o NotebookLM sinalizou o limite das fontes em vez de completar por conta própria.

### Prompt 4: Anonimização x pseudonimização
- **Versão ajustada:** "Explique a diferença entre dado anonimizado e pseudonimizado segundo as fontes e em quais condições um dado anonimizado ainda pode ser considerado dado pessoal."
- **Resultado:** a resposta separou bem os dois conceitos.
  - **Dado anonimizado:** não pode ser identificado usando meios técnicos razoáveis e disponíveis na ocasião do tratamento, por isso não é considerado dado pessoal para a LGPD.
  - **Dado pseudonimizado:** perde a associação direta ao indivíduo, mas ela pode ser refeita com uma informação adicional mantida separadamente pelo controlador em ambiente controlado e seguro. Por isso continua sendo dado pessoal e segue submetido à lei.
  - **Quando o anonimizado volta a ser pessoal:** se o processo puder ser revertido, ou se a reidentificação for possível com meios próprios ou com meios técnicos razoáveis e disponíveis na ocasião.
- **Aprendizado:** a pergunta ajustada, ao pedir a diferença e as condições, trouxe uma resposta direta e fácil de transformar em glossário. Para o dia a dia de análise, o ponto central é que **pseudonimizar não tira o dado do alcance da LGPD**, então trocar CPF por um código não basta se a tabela de correspondência existir.

### Prompt 5: Dados sensíveis e perfis comportamentais
- **Versão ajustada:** "O que a lei diz sobre dados sensíveis e sobre dados usados para formar perfil comportamental? Isso afeta um analista que faz segmentação de clientes?"
- **Resultado:** a resposta veio dividida em três partes.
  - **Dados sensíveis:** origem racial ou étnica, convicção religiosa, opinião política, filiação a sindicato ou organização religiosa, filosófica ou política, saúde, vida sexual e dados genéticos ou biométricos. Como têm alto potencial discriminatório, o regime é mais rígido (Art. 11): consentimento explícito e destacado para finalidades específicas, ou hipóteses legais restritas (obrigação legal, políticas públicas, estudos por órgão de pesquisa, exercício regular de direitos, prevenção à fraude).
  - **Perfil comportamental:** hábitos de consumo, preferências, geolocalização, dados de navegação e dados inferidos (como escore de crédito) são tratados como dados pessoais. Isso vale tanto para dados fornecidos quanto para observados e inferidos, que precisam de base legal e de respeito à finalidade, necessidade e transparência.
  - **Impacto para o analista:** o analista, como profissional subordinado, não é agente de tratamento; quem responde perante a ANPD e os titulares é a empresa. Mesmo assim, a rotina dele muda: cuidado ao usar ou inferir dados sensíveis na segmentação, uso só do necessário, registro das atividades no Inventário de Dados Pessoais (IDP) e possível necessidade de um Relatório de Impacto (RIPD) quando há criação de perfis.
- **Aprendizado:** incluir um cenário concreto (segmentação de clientes) transformou uma resposta teórica em algo aplicável ao trabalho de análise. Ficou claro também que a responsabilidade jurídica é da empresa, mas as decisões do dia a dia (quais colunas usar, o que cruzar) são do analista. Esse prompt complementa o anterior: mesmo sem identificar diretamente a pessoa, dados de perfil comportamental continuam sob a LGPD.

### Prompt 6: Divergências entre fontes (pensamento crítico)
- **Versão ajustada:** "Aponte diferenças de nomenclatura, atualização ou interpretação entre as fontes. Quais afirmações dependem da data de publicação?"
- **Resultado:** a resposta comparou o Guia Orientativo da ANPD (versão 2.0, abril de 2022) com o artigo acadêmico da RDBCI (2024).
  - **Nomenclatura:** o guia da ANPD é prático e detalha o suboperador, comparando com o "subcontratante" do RGPD europeu. O artigo usa o referencial da Ciência da Informação e reclassifica a lei como dispositivo informacional, com controlador, operador e encarregado como atores sociais. O artigo também discute a diferença entre "dado pessoal" (LGPD) e "informação pessoal" (Lei de Acesso à Informação).
  - **Dependem da data:** (1) o guia de 2022 diz que, naquele momento, não havia necessidade de registrar o encarregado na ANPD, tema que estava na agenda regulatória; (2) o artigo de 2024 considera a Emenda Constitucional nº 115/2022, que elevou a proteção de dados a direito fundamental (Art. 5º, LXXIX); (3) o artigo analisa documentos posteriores ao guia, como o Guia de Inventário de Dados Pessoais (2023) e o Estudo Técnico sobre Anonimização da ANPD (2023).
- **Aprendizado:** esse foi o prompt que mais mexeu com pensamento crítico. Mostrou que uma afirmação correta na data de publicação pode estar defasada hoje, como a regra sobre o encarregado no guia de 2022. Por isso, antes de usar qualquer orientação como regra atual, preciso conferir a data e se houve regulamentação posterior. Também notei que a comparação envolveu apenas o guia da ANPD e o artigo acadêmico, o que reforça a importância de conferir quais fontes estão de fato carregadas no caderno.

### 🩹 Outras cicatrizes

| Problema | O que fiz / como resolver |
|----------|---------------------------|
| Três fontes em forma de link (lei compilada, guia do MPU e Lei 13.853) apareceram com erro de importação no NotebookLM; só o artigo do SciELO e o PDF da ANPD foram lidos | Verificar o ícone de erro de cada fonte, baixar as páginas como PDF (ou copiar o texto) e importar de novo |
| Caderno com poucas fontes (2 das 5 previstas) | Conferir o painel de fontes antes de rodar os prompts e incluir a lei compilada |
| Nomenclatura desatualizada: as respostas falam em "Autoridade Nacional de Proteção de Dados", mas o texto compilado do Planalto já trata a ANPD como "Agência" | Comparar a data de cada fonte e conferir a redação atual na lei |
| Prompt genérico gera resposta genérica | Delimitar escopo, pedir formato (tabela/tópicos) e exigir citação do artigo |
| Exemplos práticos misturados com o texto da lei | Pedir para separar "o que a fonte diz" de "exemplo ilustrativo" |
| Risco de número de artigo errado | Conferir o artigo citado no texto original da lei |

---

## 📖 Miniguia de Estudo

### 1. Resumos estruturados

#### O que é a LGPD
Lei que regula o tratamento de dados pessoais, inclusive nos meios digitais, por pessoas físicas e jurídicas, de direito público ou privado. Seu objetivo é proteger os direitos fundamentais de liberdade e privacidade e o livre desenvolvimento da personalidade da pessoa natural.

#### Princípios (art. 6º)
O tratamento deve respeitar a boa-fé e os princípios de finalidade, adequação, necessidade, livre acesso, qualidade dos dados, transparência, segurança, prevenção, não discriminação e responsabilização e prestação de contas. Para quem analisa dados, **finalidade** (coletar para um propósito claro) e **necessidade** (só o mínimo indispensável) pesam em quase toda decisão.

#### Bases legais (art. 7º)
Todo tratamento precisa de uma base legal. Entre elas estão consentimento, obrigação legal, políticas públicas, estudos por órgão de pesquisa, execução de contrato, exercício de direitos em processos, proteção da vida, tutela da saúde, legítimo interesse e proteção do crédito. No legítimo interesse, só podem ser tratados os dados estritamente necessários para a finalidade (art. 10, §1º).

#### Direitos do titular (art. 18)
A qualquer momento, o titular pode pedir ao controlador: confirmação de que há tratamento, acesso, correção, anonimização, bloqueio ou eliminação de dados desnecessários ou excessivos, portabilidade, eliminação de dados tratados com consentimento, informação sobre compartilhamento e revogação do consentimento.

#### Agentes de tratamento
- **Controlador:** decide sobre o tratamento dos dados.
- **Operador:** trata os dados em nome do controlador.
- **Encarregado (DPO):** canal de comunicação entre controlador, titulares e ANPD.

#### Anonimização e pseudonimização
Dado anonimizado, que não permite identificar o titular por meios técnicos razoáveis, em regra não é dado pessoal. Já dados usados para formar perfil comportamental de uma pessoa identificada podem ser considerados pessoais (art. 12, §2º). Na pseudonimização, a reidentificação continua possível com uma informação adicional guardada separadamente (art. 13, §4º).

#### Checklist para projetos de dados
- [ ] Defini finalidade e base legal antes de coletar?
- [ ] Estou coletando só o necessário?
- [ ] Removi ou mascarei identificadores diretos (nome, CPF, e-mail) nas análises?
- [ ] Sei quem é o controlador e o operador no projeto?
- [ ] Há dados sensíveis? Se sim, existe base legal específica?
- [ ] Defini prazo de retenção e forma de descarte?
- [ ] Ferramentas e serviços de terceiros (nuvem, por exemplo) têm contrato adequado?
- [ ] Existe plano de resposta a incidentes e canal para o titular?

### 2. Glossário

| Termo | Definição | Referência |
|-------|-----------|------------|
| **Dado pessoal** | Informação relacionada a pessoa natural identificada ou identificável | Art. 5º, I |
| **Dado pessoal sensível** | Dado sobre origem racial ou étnica, convicção religiosa, opinião política, saúde, vida sexual, dado genético ou biométrico, entre outros | Art. 5º, II |
| **Dado anonimizado** | Dado que não permite identificar o titular, considerados os meios técnicos razoáveis | Art. 5º, III |
| **Titular** | Pessoa natural a quem se referem os dados | Art. 5º, V |
| **Controlador** | Quem decide sobre o tratamento dos dados | Art. 5º, VI |
| **Operador** | Quem realiza o tratamento em nome do controlador | Art. 5º, VII |
| **Encarregado** | Canal entre controlador, titulares e ANPD | Art. 5º, VIII |
| **Agentes de tratamento** | Controlador e operador | Art. 5º, IX |
| **Tratamento** | Qualquer operação com dados: coleta, uso, armazenamento, compartilhamento, eliminação etc. | Art. 5º, X |
| **Anonimização** | Uso de meios técnicos para que o dado perca a possibilidade de associação a um indivíduo | Art. 5º, XI |
| **Consentimento** | Manifestação livre, informada e inequívoca do titular para uma finalidade determinada | Art. 5º, XII |
| **Finalidade** | Propósito legítimo, específico, explícito e informado ao titular | Art. 6º, I |
| **Necessidade (minimização)** | Limitar o tratamento ao mínimo necessário | Art. 6º, III |
| **Legítimo interesse** | Base legal que exige tratar apenas o estritamente necessário | Art. 7º, IX e art. 10 |
| **Perfil comportamental** | Dados sobre hábitos de uma pessoa identificada, que podem ser considerados pessoais | Art. 12, §2º |
| **Pseudonimização** | Tratamento em que a associação ao titular só é possível com informação adicional mantida separadamente | Art. 13, §4º |
| **RIPD** | Relatório de Impacto à Proteção de Dados Pessoais: documentação dos processos de tratamento que podem gerar riscos às liberdades e direitos dos titulares | Art. 5º, XVII |
| **Incidente de segurança** | Evento que compromete dados pessoais e pode exigir comunicação à ANPD e ao titular | Art. 48 |
| **ANPD** | Órgão responsável por zelar, implementar e fiscalizar o cumprimento da LGPD | Art. 55-A e seguintes |

---

## ✅ Conclusões
- **O que funcionou:** trabalhar só com fontes oficiais deixou as respostas ancoradas e fáceis de conferir, e o NotebookLM avisou quando as fontes não cobriam o assunto.
- **O que faria diferente:** carregaria o texto da lei desde o início e conferiria o painel de fontes antes de começar os testes.
- **Limitações que encontrei:** a qualidade da resposta depende diretamente das fontes carregadas, e prompts genéricos geram respostas genéricas. Também percebi que fontes de datas diferentes podem trazer orientações defasadas, então sempre confiro a data de publicação.
- **Próximos passos:** aprofundar em anonimização na prática (mascaramento de dados com Python/pandas) e em relatório de impacto à proteção de dados.

