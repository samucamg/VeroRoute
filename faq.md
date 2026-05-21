# ❓ Perguntas Frequentes (FAQ)

Reunimos as principais dúvidas de arquitetura e instalação para garantir o pleno funcionamento da sua instância VeroRoute.

[⬅️ Anterior: Uso via API](uso-api.md) | [🏠 Voltar para o Início](README.md)

---

### Preciso escolher os modelos no cliente (na minha aplicação)?
**Não necessariamente.** A lógica mais poderosa do VeroRoute é definir a estratégia de cascata dentro das rotas mestres. Assim, o cliente aponta para um único endpoint (ex: envia a flag `veroroute-default`) e a inteligência de custo, balanceamento e priorização fica toda centralizada no painel administrativo do VeroRoute, blindada do usuário final.

### Posso usar várias contas do mesmo provedor simultaneamente?
**Sim.** O sistema foi projetado exatamente para isso. Você pode criar um *pool de chaves*, aplicando load balance e rodízio contínuo (round-robin) entre várias contas (ex: usar 4 contas gratuitas do Gemini), dividindo a carga e anulando bloqueios por limite de uso.

### Qual o momento certo para usar modelos caros (OpenAI GPT-4o)?
Eles devem ser acionados quando a sua lógica exigir raciocínios extremamente complexos ou quando as camadas econômicas iniciais (Groq, Gemini, modelos abertos) falharem por timeout ou sobrecarga. Em regra geral: **deixe modelos caros no fim da rota.**

### É difícil migrar um sistema/projeto que já foi todo construído em cima da OpenAI?
**A dificuldade beira o zero.** Na vasta maioria dos casos, tudo o que você precisa fazer é:
1. Ajustar a `Base URL` na configuração da sua aplicação ou SDK para apontar para o domínio do seu VeroRoute.
2. Trocar a *API Key* original da OpenAI pela *API Key* do painel do VeroRoute.
A estrutura de *Chat Completions* JSON é transparente e idêntica.

### O que eu devo conferir impreterivelmente antes de ativar a minha licença?
Verifique de forma exata qual será o **domínio final da operação**. Como o sistema de licença do VeroRoute (baseado em ionCube) é rigorosamente vinculado ao domínio ativado, tenha absoluta certeza de que a URL final (subdomínio ou domínio raiz) é a correta, evitando instalações provisórias que quebrem a chave de ativação.

---
[⬅️ Anterior: Uso via API](uso-api.md) | [🏠 Voltar para o Início](README.md)
