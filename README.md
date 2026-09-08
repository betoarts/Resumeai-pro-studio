# ResumeAI Studio

**ResumeAI Studio** é uma aplicação web moderna e inteligente para criação de currículos profissionais. Utilizando o poder da **Google Gemini AI**, a ferramenta auxilia na escrita, refatoração e otimização do seu currículo para sistemas ATS (Applicant Tracking Systems).

## 🚀 Funcionalidades Principais

- **Editor em Tempo Real**: Visualize as alterações no seu currículo instantaneamente enquanto edita.
- **Refatoração com IA**: Melhore a descrição das suas experiências profissionais com um clique, utilizando a inteligência artificial para tornar o texto mais impactante e profissional.
- **Análise ATS**: Compare seu currículo com a descrição de uma vaga específica. A IA analisa a compatibilidade e sugere melhorias e palavras-chave para aumentar suas chances de ser notado.
- **Gestão Completa**:
  - **Dados Pessoais**: Foto, contato e resumo.
  - **Experiência Profissional**: Histórico detalhado com suporte a IA.
  - **Formação Acadêmica**: Graduações e especializações.
  - **Cursos e Certificações**: Área dedicada para cursos técnicos e certificações.
  - **Habilidades**: Listagem de competências técnicas e comportamentais.
- **Exportação PDF**: Gere um arquivo PDF pronto para impressão ou envio, com layout limpo e profissional.
- **Interface Moderna**: Design elegante, responsivo e fácil de usar, com abas de navegação intuitivas.

## 🛠️ Tecnologias Utilizadas

- **React** (v19)
- **TypeScript**
- **Vite**
- **Tailwind CSS**
- **Lucide React** (Ícones)
- **Google Gemini API** (Inteligência Artificial)

## 📦 Como Rodar Localmente

**Pré-requisitos:** Node.js instalado.

1.  **Clone o repositório** (se aplicável) ou baixe os arquivos.

2.  **Instale as dependências**:

    ```bash
    npm install
    ```

3.  **Configuração da API Key**:

    - Você pode configurar sua chave da Gemini API diretamente na interface da aplicação (ícone de engrenagem).
    - Alternativamente, crie um arquivo `.env.local` na raiz do projeto e adicione:
      ```env
      VITE_GEMINI_API_KEY=sua_chave_aqui
      ```

4.  **Inicie o servidor de desenvolvimento**:

    ```bash
    npm run dev
    ```

5.  **Acesse a aplicação**:
    Abra seu navegador em `http://localhost:3000` (ou a porta indicada no terminal).

---

<div align="center">
  Desenvolvido por Humberto Moura Neto
</div>
