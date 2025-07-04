
# WhatsApp Bot IA – N8N + Gemini + Machine Learning

Este projeto é a prova real de automação avançada para WhatsApp, desenvolvido do zero e customizado para a rotina da loja **Kleber Celulares**. Todo o setup foi feito por mim, Nayderson Oliveira.

---

## **Estrutura do Projeto**

```
whatsapp-bot-n8n/
│
├── README.md
├── whatsapp-bot.json            # Export do workflow n8n
│
├── images/                      # Prints do bot rodando (coloque 1.jpg, 2.jpg, 3.jpg...)
│     ├── 1.jpg
│     ├── 2.jpg
│     └── 3.jpg
│
├── docs/
│     └── configuracoes.md       # Configurações detalhadas dos serviços usados
│
└── src/
      ├── docker/
      │     └── docker-compose.yml  # Orquestração de containers (n8n, redis, webhook, etc)
      ├── webhook.md               # Explicação do endpoint usado para WhatsApp API
      └── gemini.md                # Detalhes da integração e personalização do Gemini
```

---

## **Tecnologias e Serviços Utilizados**

- **n8n** (workflows e automações visuais)
- **Docker** (para rodar tudo isolado e fácil de replicar)
- **Redis** (banco de dados em memória, para contexto, cache e histórico)
- **API do Gemini** (LLM do Google para respostas inteligentes e personalizadas)
- **Webhook HTTP** (integração do WhatsApp com n8n)
- **Machine Learning** (fine tuning/treinamento de respostas no Gemini via API + armazenamento de aprendizado no Redis)
- **PowerShell** (para automação de deploy e setup)
- **JavaScript** (funções customizadas dentro do n8n)
- **YAML** (configuração do Docker Compose)

---

## **Como Funciona**

1. **Recebimento de Mensagens:**
   - Webhook recebe mensagem do WhatsApp.
   - n8n processa e interpreta o texto.

2. **Processamento Inteligente:**
   - Gemini faz a análise, gera resposta humana e personalizada (usando a API).
   - Redis guarda contexto do cliente, histórico e aprendizado de máquina.

3. **Aprendizado Contínuo:**
   - Bot aprende com as interações: feedback dos clientes é armazenado e influencia respostas futuras.
   - Personalização total: treinei o bot com perguntas reais da loja, gírias locais e informações dos nossos produtos.

4. **Resposta Automática e Humana:**
   - O bot responde de forma natural, como um atendente humano (inclusive usando o estilo “moço”, “moça”).
   - Resolve dúvidas, agenda serviços, informa status de pedidos, envia orçamentos, e mais.

---

## **Deploy e Execução**

- O projeto roda 100% em containers Docker, fácil de subir em qualquer servidor.
- O arquivo `docker-compose.yml` já orquestra tudo: n8n, Redis, endpoints e integrações externas.
- Todos os fluxos do n8n estão exportados em `whatsapp-bot.json`.

---

## **Como Replicar / Rodar**

1. Clone este repositório  
2. Instale Docker no seu servidor  
3. Rode:
    ```bash
    docker-compose -f src/docker/docker-compose.yml up -d
    ```
4. Importe o `whatsapp-bot.json` no n8n  
5. Configure os webhooks de acordo com o seu provedor de WhatsApp  
6. Pronto! O bot já está online e aprendendo com cada interação.

---

## **Evolução e Resultados**

- Hoje o bot atende automaticamente 70% das solicitações da loja, reduz tempo do time, aumenta vendas e não deixa cliente sem resposta.
- O atendimento é tão natural que cliente acha que está falando com humano de verdade.
- A cada semana o bot aprende algo novo: o Redis armazena perguntas e feedbacks para deixar as respostas cada vez mais certeiras.

---

## **Demonstração Real**

Abaixo prints reais do bot em ação, conversando com clientes de verdade:

| Fluxo real de conversa |                                                                                 |
|------------------------|---------------------------------------------------------------------------------|
| ![1.jpg](images/1.png) | ![2.jpg](images/2.png) | ![3.jpg](images/3.png) |

---

## **Autor**

**Nayderson Oliveira**  
Desenvolvedor, especialista em automações de WhatsApp, IA e integração de sistemas para negócios.

---

**_Esse projeto é 100% autoral, desenvolvido do zero e já está em produção na Kleber Celulares. Se quiser saber como funciona, me chama!_**
