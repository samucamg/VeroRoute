# 🔀 Rotas, Pool de Chaves e Estratégia de Economia

O coração financeiro e operacional do VeroRoute está no seu painel administrativo. É aqui que a "mágica" dos **90% de economia** acontece: definindo a ordem das requisições e isolando sua aplicação de rate limits.

[⬅️ Anterior: Provedores Suportados](provedores.md) | [🏠 Voltar para o Início](README.md) | [Próximo: Uso via API ➡️](uso-api.md)

---

## 1. Rotas Mestre (Cascata de Inteligência)

Na hora de criar uma rota, você decide exatamente quais modelos devem ser acionados primeiro. Essa priorização é o que despenca os seus custos.

<div align="center">
  <img src="https://cdn.jsdelivr.net/gh/samucamg/imagens/Outros/2026/05/veroroute_pool_1779314263.jpg" alt="Cadastro de rotas" width="80%">
</div>

**Estratégia Recomendada:**
1. **Camada 1 (Máxima economia e velocidade):** Coloque modelos grátis (ex: Gemini Flash) ou absurdamente baratos (Groq).
2. **Camada 2 (Continuidade):** Adicione provedores intermediários ou agregadores (OpenRouter).
3. **Camada 3 (Rede de segurança):** Deixe os modelos premium (OpenAI / Azure) no final. Eles só gerarão custo se as camadas 1 e 2 falharem.

---

## 2. Pool de Chaves e Load Balance (Round-Robin)

O VeroRoute resolve o problema crônico de *Rate Limits* em planos gratuitos ou tiers baixos. Você pode cadastrar **várias chaves do mesmo provedor**. 

O sistema fará o rodízio automático (Load Balance) entre as contas. Se uma chave bater no limite, o VeroRoute usa a próxima instantaneamente, sem que sua aplicação cliente perceba a troca.

<div align="center">
  <img src="https://cdn.jsdelivr.net/gh/samucamg/imagens/Outros/2026/05/veroroute_pool2_1779315069.jpg" alt="Pool de contas e Load Balance" width="80%">
</div>

---

## 3. Gestão Fina: Modelos por Chave

Ao cadastrar uma chave (API Key), você não abre as portas para tudo. O sistema permite selecionar exatamente **quais modelos estão liberados** para cada chave. 
* Exemplo: Você pode ter uma chave corporativa da OpenAI onde libera apenas `gpt-3.5-turbo` para o fluxo de atendimento, bloqueando o acesso acidental ao `gpt-4o`.

<div align="center">
  <img src="https://cdn.jsdelivr.net/gh/samucamg/imagens/Outros/2026/05/veroroute_chaves_1779315664.jpg" alt="Modelos por chave" width="80%">
</div>

---

## 4. Testes e Validação no Chat Interno

Antes de virar a chave da sua aplicação de produção para o VeroRoute, você pode testar todo o roteamento dentro do próprio painel.

<div align="center">
  <img src="https://cdn.jsdelivr.net/gh/samucamg/imagens/Outros/2026/05/veroroute_chat_1779316089.jpg" alt="Chat de teste" width="80%">
</div>

Simule *prompts*, force falhas em chaves específicas (desativando-as) e valide se o seu **Fallback** está redirecionando o tráfego da forma correta. 

---
[⬅️ Anterior: Provedores Suportados](provedores.md) | [🏠 Voltar para o Início](README.md) | [Próximo: Uso via API ➡️](uso-api.md)
