# Contexto desta pasta

Objetivo principal deste diretorio: procurar emprego, adaptar materiais de candidatura e preencher cadastros com consistencia.

- Chat alvo: `https://zai.zanotti.com.br/api/chat-demo`
- Site de referencia de produtos: `https://zanotti.com.br/`
- Foco principal: vagas de Analista de Desenvolvimento, IA/LLMs, automacao de processos, dados, inovacao e areas correlatas entre negocio e tecnologia.

## Comportamento padrao esperado do assistente nesta pasta

Assumir, por padrao, que o usuario quer uma ou mais destas acoes:

1. analisar uma vaga e extrair os requisitos mais importantes;
2. adaptar curriculo, resumo profissional, mensagem de apresentacao e respostas de formulario;
3. preencher ou preparar respostas para cadastros de vagas;
4. registrar novas informacoes confirmadas do usuario nas fontes canonicas estruturadas e melhorar este `AGENTS.md` quando isso facilitar usos futuros.

## Padrao de execucao recomendado

1. Consultar primeiro as fontes de verificacao obrigatorias antes de responder sobre o perfil do usuario.
2. Priorizar fontes estruturadas e canonicas em JSON antes de interpretar texto solto.
3. Ao tratar de cursos e certificacoes, consultar primeiro `cursos_certificados/inventario_certificados.json`; usar a pasta `cursos_certificados` para validar comprovacoes especificas ou detectar novos PDFs ainda nao consolidados.
4. Ao tratar de projetos, portfolio tecnico ou GitHub, consultar primeiro `github_inventario.json`; se o acesso remoto ao GitHub estiver indisponivel, usar esse inventario como base e sinalizar quando houver apenas inferencia.
5. Nao perguntar algo que ja esteja documentado nos curriculos, nos JSON canonicos, no inventario de certificados, no inventario do GitHub ou nos certificados.
6. Quando faltar informacao importante, perguntar de forma objetiva e em poucas perguntas por vez.
7. Depois que o usuario responder, atualizar primeiro a fonte canonica estruturada mais adequada.
8. Manter todas as respostas fieis a experiencia real do usuario; se faltar experiencia direta, posicionar como capacidade de aprendizado rapido sem inventar vivencias.
9. Ao adaptar textos para vagas, priorizar aderencia aos requisitos da vaga, clareza e objetividade.
10. Ao preencher formularios, preferir respostas curtas, reutilizaveis e coerentes com o curriculo completo.
11. Em etapas de `Personalizar candidatura`, preencher sempre usando a base confirmada nos arquivos locais e adaptar o texto aos requisitos da vaga, sem inventar experiencia.
12. Antes de escrever apresentacao personalizada, identificar os requisitos centrais da vaga e refleti-los no texto com evidencias reais do curriculo, dos JSON canonicos, de `github_inventario.json` e de `cursos_certificados/inventario_certificados.json`.
13. Quando houver necessidade de navegar ou preencher sites, validar antes os dados que serao enviados.
14. Antes de sugerir vaga, abrir candidatura ou iniciar preenchimento em sites, conferir primeiro `job_preferences.json`.
15. Nao escolher para teste ou candidatura vaga que exija mudanca de cidade quando `job_preferences.json` indicar `allow_city_change = false`, salvo se o usuario pedir explicitamente.
16. Ao testar candidaturas, priorizar vagas aderentes ao objetivo-base e tambem compatveis com a localizacao do usuario e com o modelo de trabalho preferido registrado em `job_preferences.json`.
17. Informar claramente quando algo foi confirmado em arquivo e quando for apenas inferencia.
18. Quando o usuario adicionar novos certificados na pasta `cursos_certificados`, atualizar primeiro `cursos_certificados/inventario_certificados.json`.
19. Quando houver novos repositorios relevantes ou mudancas importantes no GitHub do usuario, atualizar primeiro `github_inventario.json`.
20. Em candidaturas da Gupy, seguir preferencialmente o fluxo definido em `application_rules.json`.
21. Considerar como padrao operacional da Gupy que voltar etapas pode exigir novo preenchimento; evitar navegar para tras durante a candidatura depois que a personalizacao ja estiver pronta.
22. Em vagas da Gupy com personalizacao por habilidades, priorizar destacar ate 3 habilidades que tenham relacao direta com os requisitos centrais da vaga e que existam de forma real no historico do usuario.
23. Antes de sugerir, abrir ou finalizar qualquer candidatura, consultar `candidaturas_log.json` para evitar duplicidade e reaproveitar historico de decisoes.
24. Depois de concluir, descartar ou interromper uma candidatura relevante, registrar o resultado em `candidaturas_log.json`.
25. Ao procurar vagas, priorizar tambem oportunidades com boa aderencia pratica em `Python`, `automacao`, `backend` e `dados`, mesmo quando a formacao academica ideal ou algum requisito formal nao sejam perfeitos, desde que isso seja sinalizado com clareza.
26. Quando houver requisito nao plenamente atendido, nao esconder nem inventar experiencia: se a empresa perguntar ou houver campo para apresentacao, posicionar com transparencia o ponto nao atendido e reforcar as evidencias reais de aderencia tecnica e capacidade de aprendizado.
27. Em candidaturas da Gupy com perguntas eliminatorias ou de corte, ler essas perguntas antes de responder; se a base local permitir resposta objetiva, usar a resposta confirmada em arquivo; se houver ambiguidade real, interromper e confirmar com o usuario.
28. Em perguntas sobre tempo de experiencia com Python, usar como referencia padrao a informacao confirmada em `profile.json` e `application_rules.json`, salvo quando a empresa pedir um recorte mais especifico.
29. Em perguntas de pretensao salarial na Gupy sem contexto melhor da vaga, usar provisoriamente o valor padrao registrado em `job_preferences.json` e sinalizar depois quando isso merecer calibracao.
30. Em automacoes da Gupy, consultar primeiro `gupy_selectors.json` para reaproveitar seletores de botoes e etapas recorrentes antes de reinspecionar o DOM da pagina.

## Perfil base ja identificado

- Nome: David Silva Cardoso
- Cidade atual informada no curriculo: Jaragua do Sul - SC
- Telefone: (11) 97698-6161
- Email: davidsilcard@gmail.com
- Objetivo-base: Analista de Desenvolvimento (IA/LLMs) | Automacao de Processos | Dados e Inovacao
- Ferramentas ja confirmadas: Excel (VBA), Access, Python, UiPath
- Idioma confirmado: ingles intermediario (leitura)
- Restricao confirmada em `job_preferences.json`: nao possui disponibilidade para mudanca de cidade
- Preferencias de modelo de trabalho devem ser lidas de `job_preferences.json` antes de sugerir ou testar vagas

## Regras para respostas sobre o usuario

- Priorizar o curriculo de 1 pagina quando a resposta precisar ser curta.
- Priorizar o curriculo completo quando a resposta exigir historico detalhado.
- Usar os JSON canonicos para preferencias de candidatura, respostas padrao e fatos confirmados.
- Usar `cursos_certificados/inventario_certificados.json` como fonte canonica para cursos e certificacoes ja consolidados.
- Usar `github_inventario.json` como fonte canonica para projetos e sinais tecnicos ja consolidados do GitHub.
- Ao avaliar aderencia tecnica para vagas, consultar `github_inventario.json` antes de concluir se existe evidencia de backend, automacao, ETL, scraping, APIs, testes automatizados e stack Python/TypeScript.
- Ao sugerir vagas ou fazer testes de candidatura, cruzar sempre `job_preferences.json` com `github_inventario.json` para equilibrar preferencias logisticas e aderencia tecnica.
- Consultar a pasta `cursos_certificados` quando a vaga exigir comprovacoes especificas ou quando houver suspeita de novos certificados ainda nao consolidados.

## Fontes de verificacao obrigatorias

- `Curriculo-David-Silva-Cardoso-1pagina-FINAL.docx`
- `Curriculo-David-Silva-Cardoso-Completo-FINAL.docx`
- `profile.json`
- `job_preferences.json`
- `application_rules.json`
- `cursos_certificados/inventario_certificados.json`
- `github_inventario.json`
- `candidaturas_log.json`
- `gupy_selectors.json`
- pasta `cursos_certificados`

## Checklist de candidatura

Usar este protocolo antes de sugerir vaga, abrir candidatura ou preencher formulario:

1. Ler primeiro `profile.json`, `job_preferences.json`, `application_rules.json`, `candidaturas_log.json` e, quando relevante, `github_inventario.json` e `cursos_certificados/inventario_certificados.json`.
2. Consultar `candidaturas_log.json` antes de iniciar uma nova candidatura para evitar repeticao da mesma vaga.
3. Identificar e aplicar como restricoes duras tudo o que estiver confirmado em `job_preferences.json` sobre cidade, mudanca de cidade, modelo de trabalho, faixa salarial minima, tipo de vaga aceito e disponibilidade.
4. Cruzar a vaga com o objetivo-base do usuario e com a aderencia tecnica confirmada nos curriculos e em `github_inventario.json`.
5. Antes de candidatar, resumir explicitamente:
   - vaga escolhida;
   - por que ela e compativel;
   - quais restricoes foram verificadas;
   - quais pontos sao confirmados em arquivo e quais seriam inferencia.
6. Se a vaga for boa para teste tecnico do fluxo, mas ruim para candidatura real, dizer isso claramente antes de prosseguir.
7. Se nao houver vaga compativel com as restricoes duras, informar isso em vez de forcar uma candidatura inadequada.
8. Ao preencher formularios, nao inventar experiencia, nao contradizer os JSON canonicos e nao sobrescrever preferencias confirmadas sem nova confirmacao do usuario.
9. Em tarefas ambiguas, preferir confirmar o criterio de selecao da vaga antes de avancar para candidatura.
10. Em formularios com perguntas eliminatorias, validar primeiro as respostas mais sensiveis, como tempo de experiencia, escolaridade, disponibilidade, escala e pretensao salarial.
11. Em fluxos recorrentes da Gupy, tentar primeiro os seletores registrados em `gupy_selectors.json` e so depois partir para uma nova inspecao ampla do DOM.
