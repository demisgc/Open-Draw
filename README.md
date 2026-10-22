# 🎯 Open Draw

> **Sorteador imparcial, seguro e auditável para resultados de pesquisas e formulários.**

[![Licença MIT](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![Zero Backend](https://img.shields.io/badge/arquitetura-100%25%20client--side-brightgreen.svg)](#privacidade-e-segurança)
[![GitHub Pages](https://img.shields.io/badge/deploy-GitHub%20Pages-orange.svg)](#como-publicar-no-github-pages)

O **Open Draw** é uma aplicação web *open source* desenvolvida para realizar sorteios justos a partir de listas e respostas exportadas de formulários e pesquisas (Google Forms, Typeform, Microsoft Forms, SurveyMonkey ou planilhas Excel).

Tudo roda diretamente no navegador do usuário, com garantia de privacidade, auditoria criptográfica e uma interface escura moderna com animações ao vivo.

---

## ✨ Principais Funcionalidades

- **📥 Leitura Universal de CSV (`PapaParse`)**:
  - Detecção automática de delimitadores: suporta arquivos com vírgula (`,`) e ponto-e-vírgula (`;` padrão do Excel no Brasil).
  - Trata quebras de linha e textos com aspas internas perfeitamente.
  - Suporta arrastar e soltar (*drag & drop*) ou seleção manual.

- **🧹 Desduplicação Inteligente de Participantes**:
  - Elimina envios duplicados com base em uma coluna identificadora (como *E-mail* ou *CPF*), garantindo a regra de *"1 participação por pessoa"*.

- **🔍 Filtro Condicional de Elegibilidade**:
  - Filtre os participantes antes do sorteio (ex: sortear apenas quem respondeu *"Sim"* na pergunta de participação ou atingiu determinado critério).

- **👥 Titulares e Suplentes (Reservas)**:
  - Defina separadamente a quantidade de ganhadores titulares e suplentes para o caso de desclassificação ou não comparecimento.

- **🔒 Auditoria e Aleatoriedade Criptográfica (`Web Crypto API`)**:
  - Utiliza `crypto.getRandomValues()` em vez de geradores pseudo-aleatórios simples.
  - Cada sorteio gera um **Código de Sessão** e um **Hash de Autenticação** único por ganhador para comprovação pública.

- **🎉 Experiência Visual e Gamificação**:
  - Efeito de embaralhamento rápido de nomes (*shuffle slot*) durante a contagem regressiva.
  - Velocidade ajustável: Instantâneo (0s), Rápido (3s), Apresentação (5s) ou Suspense Máximo (10s).
  - Chuva de confetes animada ao revelar os premiados.
  - Opção de sortear os restantes em lote com 1 clique.

- **📊 Exportação Completa de Resultados**:
  - **Planilha (.CSV)**: Contém todas as colunas originais do respondente, data/hora e hash de autenticação.
  - **Comprovante de Auditoria (.TXT)**: Relatório pronto para publicação e transparência em redes sociais ou eventos ao vivo.

- **🛡️ Privacidade Total (LGPD / Zero Backend)**:
  - Nenhum dado de participante é enviado para servidores externos. O processamento ocorre 100% na memória local do navegador.

---

## 🚀 Como Executar Localmente

Como o projeto é construído em HTML5, CSS3 e JavaScript puro, não é necessário instalar Node.js ou configurar servidores.

1. Clone o repositório:
   ```bash
   git clone https://github.com/SEU_USUARIO/open-draw.git
   cd open-draw
   ```
2. Abra o arquivo `index.html` em qualquer navegador:
   - No macOS: `open index.html`
   - No Linux: `xdg-open index.html`
   - No Windows: duplo clique no arquivo `index.html`

> [!TIP]
> Caso queira testar imediatamente sem ter um CSV em mãos, clique no botão **"⚡ Carregar Dados de Demonstração"** na tela inicial ou utilize o arquivo [exemplo_pesquisa.csv](exemplo_pesquisa.csv) incluído no repositório.

---

## 🌐 Como Publicar no GitHub Pages (Grátis em 1 Minuto)

Você pode hospedar o **Open Draw** gratuitamente no GitHub Pages para acessá-lo de qualquer dispositivo:

1. Crie um repositório no GitHub chamado `open-draw`.
2. Envie os arquivos para o repositório:
   ```bash
   git remote add origin https://github.com/SEU_USUARIO/open-draw.git
   git branch -M main
   git push -u origin main
   ```
3. No GitHub, acesse seu repositório e vá em:
   **Settings** (Configurações) ➔ **Pages** (no menu lateral esquerdo).
4. Em **Build and deployment** / **Branch**:
   - Selecione a branch `main`.
   - Mantenha a pasta como `/(root)`.
   - Clique em **Save**.
5. Em instantes, seu sorteador estará online no endereço:
   `https://SEU_USUARIO.github.io/open-draw/`

---

## 📋 Formato Recomendado do CSV

O Open Draw aceita qualquer arquivo CSV com cabeçalhos na primeira linha. Exemplo:

```csv
Carimbo de data/hora,Nome Completo,E-mail,Nota da Pesquisa,Participar do Sorteio
2026-10-22 14:01:10,Ana Clara Souza,ana.souza@gmail.com,10,Sim
2026-10-22 14:02:44,Carlos Eduardo Silva,carlos.silva@outlook.com,9,Sim
```

---

## 🛠️ Tecnologias Utilizadas

- **HTML5 & CSS Moderno**: Paleta Dark Mode, flexbox/grid e animações puras.
- **JavaScript Vanilla**: Lógica de manipulação de estados e Web APIs nativas.
- **[PapaParse](https://www.papaparse.com/)**: Parser robusto de arquivos CSV.
- **[canvas-confetti](https://www.kirilv.com/canvas-confetti/)**: Efeito visual de confetes na celebração.
- **Web Crypto API**: Geração criptograficamente segura de números aleatórios e chaves de auditoria.

---

## 📄 Licença

Este projeto é de código aberto e está licenciado sob a [Licença MIT](LICENSE). Sinta-se livre para usar, modificar e distribuir.
