# ResumeAI Studio

> Crie currículos profissionais, adapte seu perfil para cada oportunidade e aumente sua compatibilidade com sistemas ATS usando inteligência artificial.

![ResumeAI Studio — currículo, ATS e IA](https://github.com/betoarts/Resumeai-pro-studio/raw/main/docs/resumeai-studio-cover.jpg)

[![React](https://img.shields.io/badge/React-19-61DAFB?logo=react&logoColor=20232a)](https://react.dev/)
[![TypeScript](https://img.shields.io/badge/TypeScript-5.8-3178C6?logo=typescript&logoColor=white)](https://www.typescriptlang.org/)
[![Vite](https://img.shields.io/badge/Vite-6-646CFF?logo=vite&logoColor=white)](https://vitejs.dev/)
[![Google Gemini](https://img.shields.io/badge/Google_Gemini-AI-4285F4?logo=google&logoColor=white)](https://ai.google.dev/)
[![Docker](https://img.shields.io/badge/Docker-ready-2496ED?logo=docker&logoColor=white)](https://www.docker.com/)
[![License](https://img.shields.io/badge/license-MIT-green.svg)](LICENSE)

O **ResumeAI Studio** é uma aplicação web para criação e otimização de currículos. A plataforma combina um editor estruturado, preview em tempo real, recursos de inteligência artificial e análise direcionada para ATS — sistemas usados por empresas para filtrar candidaturas.

## O que o projeto resolve

Um currículo genérico nem sempre comunica corretamente a experiência de um candidato para uma vaga específica. O ResumeAI Studio ajuda a:

- organizar informações profissionais em um formato claro;
- transformar descrições comuns em resultados mais objetivos;
- comparar o currículo com uma descrição de vaga;
- identificar palavras-chave e competências que podem ser adicionadas;
- exportar uma versão pronta para impressão ou envio.

## Recursos

### Editor de currículo

- Dados pessoais, cargo, contato, localização e resumo profissional.
- Experiências com empresa, cargo, período e descrição.
- Formação acadêmica.
- Cursos e certificações.
- Habilidades técnicas e comportamentais.
- Edição com visualização simultânea do currículo.
- Layout de página A4 preparado para impressão.

### Inteligência artificial

Com uma chave válida do Google Gemini, o sistema oferece:

- refatoração de experiências no formato ação, contexto e resultado;
- escrita mais objetiva e profissional;
- análise do currículo comparada à descrição de uma vaga;
- sugestões de palavras-chave e habilidades;
- recomendações para melhorar a compatibilidade com ATS.

As respostas são geradas como apoio à escrita. O candidato deve revisar o conteúdo e confirmar se todas as informações representam sua experiência real.

### Organização e acompanhamento

- Dashboard com versões de currículo e métricas de candidatura.
- Controle de vagas aplicadas, respostas e entrevistas.
- Indicadores de abertura e pontuação ATS.
- Persistência automática do currículo no navegador.
- Backup e restauração dos dados em arquivo JSON.
- Modal de configuração da API Gemini.
- Interface responsiva para desktop e dispositivos móveis.

## Fluxo de uso

1. Abra o editor e preencha suas informações profissionais.
2. Adicione experiências, formação, cursos e habilidades.
3. Revise o currículo no preview em tempo real.
4. Use a IA para melhorar descrições de experiência.
5. Cole a descrição da vaga na ferramenta de análise ATS.
6. Aplique as sugestões que fizerem sentido.
7. Imprima ou salve o currículo como PDF pelo navegador.
8. Faça backup dos dados para preservar seu trabalho.

## Stack

| Camada | Tecnologia |
| --- | --- |
| Interface | React 19 |
| Linguagem | TypeScript 5.8 |
| Build e desenvolvimento | Vite 6 |
| Estilização | Tailwind CSS via CDN |
| IA | Google Gemini via @google/genai |
| Gráficos | Recharts |
| Ícones | Lucide React |
| QR Code | qrcode.react |
| Servidor de produção | Nginx |
| Containerização | Docker |

## Pré-requisitos

- Node.js 20 ou superior recomendado.
- npm.
- Chave do Google Gemini para usar os recursos de IA.
- Docker opcional para execução conteinerizada.

## Instalação local

Clone o repositório e instale as dependências:

~~~bash
git clone https://github.com/betoarts/Resumeai-pro-studio.git
cd Resumeai-pro-studio
npm install
~~~

Inicie o ambiente de desenvolvimento:

~~~bash
npm run dev
~~~

A aplicação ficará disponível em:

~~~text
http://localhost:3000
~~~

Para gerar e visualizar o build de produção:

~~~bash
npm run build
npm run preview
~~~

## Configuração da API Gemini

O projeto usa a variável GEMINI_API_KEY durante o build local. Crie um arquivo .env.local na raiz:

~~~env
GEMINI_API_KEY=sua_chave_do_google_gemini
~~~

Também é possível informar a chave diretamente pela interface, em **Configurar IA**. Nesse caso, ela é armazenada no localStorage do navegador para uso naquele ambiente.

Obtenha uma chave no [Google AI Studio](https://aistudio.google.com/app/apikey).

> Atenção: como a aplicação é frontend, qualquer chave usada diretamente no navegador pode ser exposta ao cliente. Para um cenário público ou multiusuário, recomenda-se criar um backend intermediário com autenticação, limites de uso, controle de custos e proteção da chave.

## Docker

O projeto inclui um build em múltiplos estágios: Node.js compila a aplicação e Nginx serve os arquivos estáticos.

~~~bash
docker build -t resumeai-pro-studio .
docker run --name resumeai-pro-studio -p 8080:80 resumeai-pro-studio
~~~

Acesse:

~~~text
http://localhost:8080
~~~

A configuração do Nginx inclui:

- fallback para index.html em rotas da SPA;
- compressão Gzip;
- cache para arquivos estáticos;
- suporte à impressão do currículo.

## Dados e privacidade

O currículo atual e a chave configurada pela interface são mantidos localmente no navegador. O projeto não possui backend próprio ou sincronização automática entre dispositivos nesta versão.

Use a função **Backup** para exportar seus dados em JSON e mantenha esse arquivo em local seguro. Evite inserir informações sensíveis em ambientes compartilhados e nunca publique chaves de API no repositório.

## Estrutura do projeto

~~~text
.
├── components/       # Editor, preview, landing page, dashboard e modais
├── services/         # Integração com o Google Gemini
├── App.tsx           # Estado principal e navegação da aplicação
├── types.ts          # Modelos de currículo, análise ATS e dashboard
├── index.tsx         # Ponto de entrada React
├── index.html        # Metadados, Tailwind e estilos de impressão
├── vite.config.ts    # Configuração do Vite e variáveis de ambiente
├── Dockerfile        # Build e servidor Nginx
├── nginx.conf        # Configuração de SPA e cache
└── package.json      # Scripts e dependências
~~~

## Scripts disponíveis

| Comando | Finalidade |
| --- | --- |
| npm run dev | Inicia o servidor de desenvolvimento na porta 3000 |
| npm run build | Gera a versão de produção em dist |
| npm run preview | Executa uma prévia do build de produção |

## Boas práticas

- Use resultados reais e métricas verificáveis nas experiências.
- Adapte o currículo para cada vaga sem copiar palavras-chave fora de contexto.
- Revise as sugestões da IA antes de utilizá-las.
- Mantenha uma versão geral e versões específicas por área ou vaga.
- Faça backups frequentes usando a exportação JSON.
- Execute npm run build antes de publicar alterações.

## Contribuição

Contribuições são bem-vindas:

1. Crie uma branch para sua melhoria.
2. Preserve a tipagem e a organização dos componentes.
3. Teste editor, preview, impressão e análise ATS.
4. Execute o build de produção.
5. Abra um pull request descrevendo claramente a alteração.

## Licença

Este projeto está licenciado sob a [MIT License](LICENSE).

## Autor

Desenvolvido por [Humberto Moura Neto](https://github.com/betoarts).
