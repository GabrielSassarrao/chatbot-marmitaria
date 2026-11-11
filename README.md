# 🍱 Marmitaria Sabor Caseiro — Chatbot com Agente LLM

Aplicação web interativa e 100% client-side que implementa um assistente de vendas para marmitaria, utilizando a API do Google Gemini com respostas estruturadas e sistema de guardrails contra prompt injection.

## 🚀 Links do Projeto
- **Aplicação Online (GitHub Pages):** https://gabrielsassarrao.github.io/chatbot-marmitaria/
- **Repositório GitHub:** https://github.com/GabrielSassarrao/chatbot-marmitaria

---

## 📋 Funcionalidades Implementadas

1. **Cardápio e Preços Diários:**
   - Pratos fixos ("Clássicos Todo Dia") e pratos sazonais de segunda a domingo com valores unitários tabelados.
   - Apresentação dinâmica tanto via chat quanto na vitrine visual.

2. **Personalização de Pedidos por Linguagem Natural:**
   - Reconhecimento automático de itens e quantidades via IA.
   - Customização de **Ponto de Cozimento** (mal passado, ao ponto, bem passado).
   - Customização de **Temperos/Ingredientes** (ex.: remover cebola do bife de vaca, pouco sal, sem pimenta).

3. **Cálculo Determinístico de Total e Entrega:**
   - Subtotal calculado no cliente com base nos preços oficiais dos itens.
   - Cálculo dinâmico de taxa de entrega por região com valor final consolidado.

4. **Guardrails de Segurança (Anti-Prompt Injection & Jailbreak):**
   - **Camada Heurística (Client-side Regex):** Intercepta padrões de ataque (ex.: `ignore previous instructions`, `modo DAN`, injeções de script/SQL e manipulação indevida de preços) antes de qualquer chamada de rede.
   - **Isolamento Estruturado (XML):** Sanitização e encapsulamento dos comandos do usuário em `<mensagem_cliente>`.
   - **Contrato JSON Estrito:** Força respostas estruturadas via API schema, impedindo alucinações de formato.
   - **Integridade Comercial:** Os cálculos são estritamente matemáticos no JavaScript; o modelo não altera preços nem concede descontos não autorizados.

---

## 🛠️ Tecnologias
- HTML5, Tailwind CSS (via CDN), JavaScript Moderno (ES6+).
- Google Gemini API (`gemini-2.5-flash`).
- Hospedagem estática via GitHub Pages.

---

## 💻 Como Rodar e Testar
1. Acesse o link da aplicação no GitHub Pages ou abra o arquivo `index.html` no navegador.
2. Insira uma chave de API gratuita do Google AI Studio no campo indicado na interface.
3. Realize pedidos em linguagem natural e teste o envio de comandos maliciosos para verificar a atuação dos guardrails.