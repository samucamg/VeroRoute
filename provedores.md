# 🧠 Provedores com Suporte Nativo

O VeroRoute já nasce preparado para trabalhar com múltiplos LLMs e provedores do mercado. Isso acelera sua implementação, corta dependências exclusivas e permite montar rotas híbridas de altíssima economia desde o primeiro dia.

[⬅️ Anterior: Instalação](instalacao.md) | [🏠 Voltar para o Início](README.md) | [Próximo: Rotas e Chaves ➡️](rotas-e-chaves.md)

---

### Por que múltiplos provedores importam?
Quanto mais opções você tem no núcleo do roteamento, maior a sua capacidade de distribuir custos e evitar indisponibilidades. Não deixe sua aplicação refém de um único serviço!

## 🟢 Foco em Velocidade e Economia

* **Groq** *(Suporte Nativo)*
  * **Onde usar:** Ótimo para rotas rápidas, testes, automações N8N e cenários onde latência e custo importam muito. A velocidade de inferência (Llama, Mixtral) é absurdamente alta.
* **Gemini (Google)** *(Suporte Nativo)*
  * **Onde usar:** Excelente opção para compor rotas econômicas, reduzir o uso prematuro de provedores caros e aproveitar os generosos limites gratuitos do Google AI Studio.

## 🔵 Foco em Resiliência e Agregação

* **OpenRouter** *(Suporte Nativo)*
  * **Onde usar:** Permite plugar dezenas de modelos alternativos de uma só vez, ampliando instantaneamente o leque da sua estratégia de fallback.
* **1min.ai** *(Suporte Nativo)*
  * **Onde usar:** Pode entrar como camada adicional dentro da sua cascata de rotas.
* **Pollination AI** *(Suporte Nativo)*
  * **Onde usar:** Mais uma via para diversificar e evitar *rate limits* em fluxos pesados.

## 🟣 Foco em Qualidade Premium (Cofre Final)

* **OpenAI** *(Suporte Nativo)*
  * **Onde usar:** Perfeito para funcionar como sua **última camada de segurança** (fallback final) ou para cenários hiper complexos que exigem os modelos mais robustos (GPT-4o).
* **Azure OpenAI** *(Suporte Nativo)*
  * **Onde usar:** Ideal para quem já opera workloads corporativos no ecossistema da Microsoft e necessita de altíssima confiabilidade e compliance.

---

> 💡 **Extensibilidade:** A arquitetura do projeto já possui a base estruturada na pasta `/adapters/` para a inclusão fácil de novos provedores conforme o mercado de IA evolui.

---
[⬅️ Anterior: Instalação](instalacao.md) | [🏠 Voltar para o Início](README.md) | [Próximo: Rotas e Chaves ➡️](rotas-e-chaves.md)
