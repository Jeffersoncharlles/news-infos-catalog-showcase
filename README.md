# 🎬 News Infos - Catálogo de Filmes e Séries (Showcase)

> **Nota sobre o Repositório:** Este é um repositório de documentação e demonstração técnica. O código-fonte original é privado por questões contratuais de licenciamento. Abaixo, detalho as decisões de arquitetura e desafios superados neste projeto.

Este projeto é um catálogo moderno e interativo de entretenimento, construído com foco em **performance de carregamento** e **experiência do usuário (UX)**. A aplicação consome dados dinâmicos e gerencia estados complexos de cache para garantir uma navegação fluida em múltiplos dispositivos.

---

## 📸 Demonstração Visual

| Dashboard Principal | Detalhes do Conteúdo | Modo Mobile |
| :--- | :--- | :--- |
| ![Dashboard]([LINK_DO_SEU_PRINT_1]) | ![Detalhes]([LINK_DO_SEU_PRINT_2]) | ![Mobile]([LINK_DO_SEU_PRINT_3]) |

---

## 🧠 Arquitetura e Decisões Técnicas

Diferente de projetos de estudo, o **News Infos** foi estruturado para ser escalável e fácil de manter. Minhas principais decisões foram:

### 1. Gerenciamento de Estado vindo do Servidor (TanStack Query)
Em vez de usar `useEffect` para tudo, utilizei o **React Query**. 
- **Por que?** Para implementar cache inteligente. Se o usuário volta para uma página de filme que já visitou, a carga é instantânea.
- **Resultado:** Redução de chamadas desnecessárias à API e feedback visual imediato para o usuário.

### 2. Validação Estrita com Zod + TypeScript
Todos os dados que chegam das APIs externas são validados via **Zod schemas** antes de entrarem nos componentes.
- **Benefício:** Evita os famosos erros de `undefined` em produção e garante que o TypeScript saiba exatamente o que está sendo renderizado.

### 3. UI System com Tailwind e Radix UI
Optei por não usar bibliotecas de componentes "fechadas" (como Material UI puro) para ter controle total sobre o design.
- Usei o **Radix UI** para garantir acessibilidade (A11y) em modais e carrosséis.
- Usei **Tailwind CSS** com `class-variance-authority` (CVA) para criar componentes reutilizáveis com múltiplas variantes de estilo.

---

## 🛠️ Stack Técnica Principal

- **Frontend:** React 18 + Vite + TypeScript.
- **Estilização:** TailwindCSS + Lucide Icons + Radix UI.
- **Data Fetching:** Axios + TanStack React Query.
- **Formulários:** Zod + EmailJS para contato direto.
- **Performance:** LocalForage para persistência de dados em disco do navegador.

---

## 🚀 Desafios Superados

- **Performance em Carrosséis:** Implementar carrosséis com autoplay (Embla Carousel) que fossem performáticos em dispositivos mobile com baixa memória.
- **Tipagem Complexa:** Mapear DTOs (Data Transfer Objects) complexos para filmes e séries, garantindo que o frontend fosse resiliente a mudanças no esquema da API.

---

## 👨‍💻 Autor e Contato

Desenvolvido por **Jefferson Campos**.

- **GitHub:** [@jeffersoncharlles](https://github.com/jeffersoncharlles)
- **LinkedIn:** [SEU_LINK_DO_LINKEDIN]
- **Portfólio:** [jeffersonc.dev](https://jeffersonc.dev)
