<div align="center">
  <img src="banner.jpg" alt="VeroRoute - Pare de pagar caro por tokens" width="100%">
</div>
<br>
<div align="center">
  <img src="https://cdn.jsdelivr.net/gh/samucamg/imagens/Outros/2026/05/veroRoute_logo_1779314376.png" alt="Logo VeroRoute" width="100">
  <h1>VeroRoute Docs</h1>
  <p><b>A sua camada de roteamento inteligente para IA. Corte custos em até 90%, ganhe eficiência com modelos ultrarrápidos e assuma o controle total da sua operação.</b></p>
</div>

---

## 🎯 Pare de pagar caro por tokens!

O **VeroRoute** funciona como um endpoint nativo e 100% compatível com a API da OpenAI, mas com um superpoder: **por trás dele, você decide a ordem real dos provedores, o pool de chaves e a estratégia de fallback.**

Em vez de prender o seu sistema em uma única conta cara, você cria uma infraestrutura flexível. Na prática, você reduz a dependência, aproveita opções gratuitas (como Gemini) ou baratas/rápidas (como Groq) primeiro, e só aciona os provedores premium (OpenAI, Azure) quando realmente for necessário. O resultado? **Uma economia que facilmente ultrapassa a marca de 90%.**

### 🚀 Por que o VeroRoute é um divisor de águas?
* **1 Endpoint, Múltiplos LLMs:** Sua aplicação continua simples, falando com um único ponto de entrada.
* **Fallback Automático Inteligente:** Se uma opção falhar (rate limit, indisponibilidade), a próxima da sua lista assume instantaneamente.
* **Load Balance de Chaves (Round-Robin):** Distribua requisições entre várias contas do mesmo provedor para aliviar limites e picos.
* **Cascata de Inteligência:** Coloque o que é grátis e rápido na frente. Deixe o que é caro como última camada de segurança.

---

## 📑 Navegue pela Documentação

Esta documentação foi dividida em módulos para facilitar a sua integração e gestão:

1. 📖 **[Visão Geral e Arquitetura do Projeto](README.md)** *(Você está aqui)*
2. ⚙️ **[Guia de Instalação (Docker & cPanel)](instalacao.md)**
3. 🧠 **[Provedores de IA Suportados](provedores.md)**
4. 🔀 **[Rotas, Pool de Chaves e Estratégia de Economia](rotas-e-chaves.md)**
5. 💻 **[Guia de Uso via API (Substituindo a OpenAI)](uso-api.md)**
6. ❓ **[FAQ - Perguntas Frequentes](faq.md)**

---

### 📂 Estrutura do Projeto (Para Desenvolvedores)

Se você for explorar o código-fonte, esta é a visão geral da arquitetura:

```text
.
├── adapters               # Conectores para diferentes LLMs
├── admin                  # Painel de controle e dashboard
├── config.php             # Configurações globais
├── core                   # Lógica de roteamento e fallback
├── docker-compose.yml     # Orquestração Docker
├── Dockerfile             # Definição da imagem container
├── docs                   # Documentação HTML original
├── index.php              # Ponto de entrada
├── install.php            # Wizard de instalação web
└── v1
    ├── chat
    │   └── completions.php # Endpoint final compatível com OpenAI
    └── models
        └── index.php       # Listagem de modelos disponíveis
```

<div align="center">
  <b>Pronto para cortar seus custos de API?</b> <br>
  👉 <a href="instalacao.md">Comece pela Instalação</a>
</div>
