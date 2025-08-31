# 🤖 Chatbot Inteligente 100% Offline com Prompt API do Chrome

**Chatbot Inteligente 100% Offline com Prompt API do Chrome**

<div align="center">

[![Repo stars](https://img.shields.io/github/stars/luisguedesdev/semana-javascript-expert09?style=social)](https://github.com/luisguedesdev/semana-javascript-expert09/stargazers)
[![Repo forks](https://img.shields.io/github/forks/luisguedesdev/semana-javascript-expert09?style=social)](https://github.com/luisguedesdev/semana-javascript-expert09/fork)
![Made with JavaScript](https://img.shields.io/badge/Made%20with-JavaScript-yellow)
![License](https://img.shields.io/badge/license-MIT-blue)
![Last Commit](https://img.shields.io/github/last-commit/luisguedesdev/semana-javascript-expert09)

</div>

> Widget de chatbot embarcado que roda **100% no cliente**, explorando a **Prompt API for Gemini Nano** com **Multimodal Input** (texto/voz/imagem\*), seguindo o conceito de **Web 4.0**: experiências mais inteligentes, privadas e rápidas — **sem backend**.

_Suporte a multimodalidade depende da versão/flags do navegador._

---

## 🎥 Demo



- **Repositório do projeto original / referência**: [Semana JS Expert 09 por Erick Wendel](https://github.com/ErickWendel/semana-javascript-expert09)

---

## 🧭 Sumário

- [Objetivo](#-objetivo)
- [Destaques](#-destaques)
- [Arquitetura](#-arquitetura)
- [Requisitos](#-requisitos)
- [Instalação](#-instalação)
- [Execução](#-execução)
- [Embutindo em Outro Site](#-embutindo-em-outro-site)
- [Configuração do Bot](#-configuração-do-bot)
- [Flags do Chrome (AI/Prompt API)](#-flags-do-chrome-aiprompt-api)
- [Limitações](#-limitações)
- [Roadmap](#-roadmap)
- [FAQ](#-faq)
- [Contribuição](#-contribuição)
- [Licença](#-licença)
- [Agradecimentos](#-agradecimentos)

---

## 🎯 Objetivo

Demonstrar, de forma prática, como integrar **IA local** ao front-end usando **Prompt API for Gemini Nano** (com **Multimodal Input**), entregando um **widget reutilizável** que pode ser plugado em qualquer página e operar **offline**.

---

## ⚡ Destaques

- **100% Client-Side**: sem chamadas a servidor para o core do chatbot.
- **Web 4.0 na prática**: IA próxima do usuário, com privacidade e baixa latência.
- **Prompt API for Gemini Nano**: acesso a modelos embarcados do Chrome.
- **Multimodal Input**: suporte a entrada de texto e, quando disponível, voz/imagem.
- **Streaming & Cancelamento**: respostas parciais e controle via `AbortController`.
- **Tema customizável**: personalização simples via CSS e JSON.

---

## 🧱 Arquitetura

```
sdk/
  ew-chatbot.html
  ew-chatbot.css
  src/
    index.js
    controllers/chatBotController.js
    views/chatBotView.js
    services/promptService.js
botData/
  systemPrompt.txt
  chatbot-config.json
  avatar.webp
```

- Separação clara entre **Controller**, **View** e **Service**.
- `promptService.js` concentra a integração com a Prompt API.
- `botData` isola a configuração do bot e estilo.

---

## 🔧 Requisitos

- **Node.js 20+** (scripts utilitários / servidor local).
- **Google Chrome** com suporte às **Chrome AI APIs / Prompt API**.

> Nota: essas APIs são **experimentais** e exigem flags específicas.

---

## 📦 Instalação

```bash
git clone https://github.com/luisguedesdev/semana-javascript-expert09.git
cd semana-javascript-expert09
npm ci
```

---

## ▶️ Execução

```bash
npm start
```

Abra o navegador no endereço indicado (ex.: `http://localhost:5173`) e interaja com o widget.

---

## 🔌 Embutindo em Outro Site

Publique os arquivos da pasta `sdk/` em um servidor ou CDN. Em seguida, adicione no site de destino:

```html
<!DOCTYPE html>
<html lang="pt-BR">
  <head>
    <meta charset="UTF-8" />
    <title>Meu Site com IA Local</title>
    <link rel="icon" href="./botData/avatar.webp" />
  </head>
  <body>
    <script type="module" src="https://<SEU_DOMÍNIO>/sdk/src/index.js"></script>
  </body>
</html>
```

O widget carrega automaticamente ao abrir a página.

---

## 🎨 Configuração do Bot

**`botData/systemPrompt.txt`**  
Define o comportamento do bot (persona, tom, limites).

**`botData/chatbot-config.json`**

```json
{
  "name": "GuedesBot",
  "themeColor": "#5e6b58",
  "welcomeBubble": "Olá! Sou seu assistente Web 4.0, rodando 100% no navegador ✨",
  "avatar": "./botData/avatar.webp",
  "ui": {
    "position": "bottom-right",
    "showTyping": true
  }
}
```

---

## 🏳️‍🌈 Flags do Chrome (AI/Prompt API)

Acesse:

- `chrome://flags/#prompt-api-for-gemini-nano` → **Enable**
- Eventuais outras flags relacionadas a **Chrome AI**/**Local AI**

> Não esqueça de reiniciar o navegador após habilitar.

---

## ⚠️ Limitações

- APIs ainda em fase experimental — sujeitas a mudanças.
- Suporte a **multimodalidade** pode variar conforme o navegador.
- Desempenho depende do hardware local.

---

## 🗺 Roadmap

- [ ] Melhorias de UX (history, atalhos, tema escuro).
- [ ] Suporte a **voz e imagem** via Web Speech API e APIs visuais.
- [ ] Modo RAG local para consultas em documentos.
- [ ] Temas prontos (dark, glass, minimal).

---

## ❓ FAQ

**Funciona em Firefox/Safari?**

> Ainda não — foco atual no Chrome devido às APIs.

**Precisa de backend?**

> Não — toda lógica roda no navegador.

**Como editar o comportamento do bot?**

> Altere o arquivo `systemPrompt.txt`.

**Como interrompo um envio longo?**

> Use o `AbortController` via UI (botão Stop).

---

## 🤝 Contribuição

Contribuições são bem-vindas!

1. Fork
2. `git checkout -b feat/sua-ideia`
3. Commit: `git commit -m "feat: descrição"`
4. Push: `git push origin feat/sua-ideia`
5. Envie um Pull Request

Se este projeto te ajudou, deixe uma ⭐!

---

## 📄 Licença

MIT — veja o arquivo [LICENSE](LICENSE) para detalhes.

---

## 🙌 Agradecimentos

- 🎓 **Erick Wendel** — pela inspiração e conteúdo transformador.

---

_Feito com ❤️ e muito aprendizado durante a Semana JS Expert 09._
