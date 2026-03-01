---
description: Este documento define o workflow obrigatório para todas as missões no Antigravity. Todos os agentes devem operar como uma unidade coordenada, garantindo que a informação flua sem redundâncias, aproveitando o ecossistema de skills e MCPs, e respeitando as identidades definidas em GEMINI.md.
---

FASE 1: Planejamento e Arquitetura (Architect Agent)

Responsabilidade: Receber a intenção do orquestrador e estruturar a solução completa de alto nível.

Ação Obrigatória: 
1. Antes de qualquer geração de código, leia o @Codebase e o arquivo GEMINI.md para alinhar a solução aos padrões do projeto.
2. Consulte a pasta `skills/` para identificar módulos reutilizáveis que já existam, evitando trabalho duplicado.
3. Avalie as conexões MCP disponíveis (GitHub, Stitch, Maps) para mapear corretamente o fluxo de dados e integrações necessárias.

Item de Conhecimento: Identifique dependências técnicas, integrações essenciais ou restrições de hardware e registre-as na aba Knowledge se forem persistentes para o projeto.

Handoff: Gere um Blueprint Técnico detalhado e envie para o Agente Desenvolvedor. Não prossiga para a codificação sem um plano estruturado e validado.

FASE 2: Implementação e Artefatos (Developer Agent)

Responsabilidade: Transformar o Blueprint em código funcional, limpo e performático.

Ação Obrigatória: Implementar a lógica seguindo estritamente o plano do Arquiteto. Sempre que possível, integre e utilize os scripts ou lógicas já contidas na pasta `skills/`, especialmente para manipulação de APIs e rotas do Stitch/Maps.

Gestão de Artefatos: Crie ou modifique arquivos conforme a Review Policy definida e as regras globais do projeto.

Comunicação de Saída: Ao concluir a etapa de código, liste todos os arquivos afetados e descreva brevemente a lógica implementada e os MCPs utilizados para o Agente Q.A.

FASE 3: Validação e Teste (Q.A. / Verificador)

Responsabilidade: Garantir a integridade técnica, funcional e de segurança da entrega.

Skill de Terminal: Utilize exclusivamente os comandos da Allow List para diagnósticos de ambiente.

Skill de Browser: Utilize o Browser Preview via porta 9222 para validar interfaces e fluxos de usuário em tempo real.

Segurança e Compliance: Verifique rigorosamente se as regras globais foram seguidas e garanta que nenhuma credencial ou chave de API (GitHub, Stitch, Maps) foi exposta no código-fonte em plain text.

Loop de Feedback:
- Falha Técnica: Se o terminal reportar erro ou o browser apresentar falha visual, envie o log técnico imediatamente de volta ao Desenvolvedor com instruções claras de correção.
- Limite de Tentativas (Circuit Breaker): Se a correção da mesma falha não for resolvida em 3 interações consecutivas com o Desenvolvedor, aborte o loop automaticamente e solicite a intervenção do Orquestrador/Humano.
- Sucesso: Somente após a validação bem-sucedida de código e segurança, notifique o Orquestrador que a missão foi cumprida.

Protocolo de Comunicação e Segurança

Acesso a Arquivos: Respeite a política de Non-Workspace File Access. Se precisar de regras globais externas ou modificar configurações do MCP, solicite permissão explícita ao orquestrador.

Persistência: Documente decisões críticas de arquitetura, banco de dados (Stitch) ou rede na aba Knowledge para que a memória técnica persista entre ciclos de missões e não se perca.

Ambiente de Execução: Identifique imediatamente o shell em uso (PowerShell vs. Git Bash) logo no início da missão e adapte a sintaxe dos comandos para evitar erros contínuos de execução.