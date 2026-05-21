# 💻 Guia de Uso via API (Integração Direta)

A adoção do VeroRoute é desenhada para ser *Drop-in Replacement*. Ou seja, onde hoje a sua aplicação ou automação (N8N, WordPress, Scripts) aponta para a OpenAI, você altera **apenas duas coisas**:

1. **A URL Base:** Troque `api.openai.com` pelo domínio do seu VeroRoute.
2. **A Chave API:** Troque o *Bearer Token* da OpenAI por uma chave que você criou no painel do VeroRoute.

A arquitetura e os payloads JSON de *Chat Completions* permanecem idênticos!

[⬅️ Anterior: Rotas e Chaves](rotas-e-chaves.md) | [🏠 Voltar para o Início](README.md) | [Próximo: FAQ ➡️](faq.md)

---

## 🌐 Endpoint Padrão
**POST** `https://seu-dominio.com/v1/chat/completions`

*(Nota: Embora você envie um parâmetro `model` no JSON, a decisão real de qual modelo será executado é governada pela sua Rota Mestre configurada no painel VeroRoute, garantindo a economia invisível ao cliente).*

---

## Exemplos de Código

### 1. Chamada Rápida (cURL)
Teste rapidamente pelo terminal:

```bash
curl -X POST "[https://seu-dominio.com/v1/chat/completions](https://seu-dominio.com/v1/chat/completions)" \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer sk-vr-sua-chave-criada-no-painel" \
  -d '{
    "model": "veroroute-default",
    "messages": [
      { "role": "user", "content": "Explique rapidamente o que é o VeroRoute." }
    ]
  }'
```

### 2. Frontend / Node.js (fetch)
Integração clássica via JS:

```javascript
const response = await fetch("[https://seu-dominio.com/v1/chat/completions](https://seu-dominio.com/v1/chat/completions)", {
  method: "POST",
  headers: {
    "Content-Type": "application/json",
    "Authorization": "Bearer sk-vr-sua-chave-criada-no-painel"
  },
  body: JSON.stringify({
    model: "veroroute-default",
    messages: [
      { role: "user", content: "Olá, me dê 3 dicas de SEO." }
    ]
  })
});

const data = await response.json();
console.log(data);
```

### 3. Backend (PHP)
Ideal para plugar em rotinas web clássicas:

```php
<?php

$payload = [
  "model" => "veroroute-default",
  "messages" => [
    ["role" => "user", "content" => "Olá, teste de integração PHP."]
  ]
];

$ch = curl_init("[https://seu-dominio.com/v1/chat/completions](https://seu-dominio.com/v1/chat/completions)");
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
curl_setopt($ch, CURLOPT_POST, true);
curl_setopt($ch, CURLOPT_HTTPHEADER, [
  "Content-Type: application/json",
  "Authorization: Bearer sk-vr-sua-chave-criada-no-painel"
]);
curl_setopt($ch, CURLOPT_POSTFIELDS, json_encode($payload));

$response = curl_exec($ch);
curl_close($ch);

echo $response;
```

### 4. Data Science / Backend (Python)
Para integrações via script Python e automações robustas:

```python
import requests

url = "[https://seu-dominio.com/v1/chat/completions](https://seu-dominio.com/v1/chat/completions)"
headers = {
    "Content-Type": "application/json",
    "Authorization": "Bearer sk-vr-sua-chave-criada-no-painel"
}
payload = {
    "model": "veroroute-default",
    "messages": [
        {"role": "user", "content": "Faça um resumo curto sobre o conceito de Fallback inteligente em IA."}
    ]
}

response = requests.post(url, headers=headers, json=payload, timeout=60)
print(response.json())
```

### 🎯 Casos de Uso Comuns
* **Fluxos no N8N:** Basta usar o Node HTTP Request ou o Node OpenAI mudando a base URL (Lembrando: a interface N8N facilita isso nativamente em suas configs de credencial).
* **Plugins WordPress:** Como o *AI Engine*, que possuem campo nativo para sobrepor o endpoint da OpenAI.
* **Agentes de Atendimento:** Centralize todo o tráfego do seu bot omnichannel em um único router para estancar a sangria financeira em picos de mensagens.

---
[⬅️ Anterior: Rotas e Chaves](rotas-e-chaves.md) | [🏠 Voltar para o Início](README.md) | [Próximo: FAQ ➡️](faq.md)
