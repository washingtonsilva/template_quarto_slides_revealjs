
# Template de Apresentação com Quarto + Revealjs

Este é um template para criar **apresentações acadêmicas em HTML** utilizando o sistema **Quarto**, com o formato `revealjs`. Ele foi desenvolvido para atender às necessidades dos orientandos do [Mestrado Profissional em Administração do IFMG - Campus Formiga](https://www.formiga.ifmg.edu.br/mestrado), mas pode ser facilmente adaptado por outros usuários.



## Estrutura do Projeto

O template é composto pelos seguintes arquivos:

- `template-slides-revealjs-seunome.qmd`: arquivo principal em formato 
  Quarto (`.qmd`), onde você irá redigir o conteúdo da sua apresentação.
- `estilos.css`: define as dimensões do logotipo institucional, reduz o 
   tamanho da fonte do título principal dos slides, ajusta o tamanho da 
   fonte dos autores e permite estilizar a afiliação institucional 
   exibida no slide de abertura.
- `img/logo.jpeg`: logotipo do IFMG - Campus Formiga, exibido no cabeçalho 
  da apresentação.
- `referencias.bibtex`: arquivo contendo as referências bibliográficas. 
   Substitua seu conteúdo pelas suas próprias referências.
- `associacao-brasileira-de-normas-tecnicas-ipea.csl`: arquivo de estilo 
para formatação automática de citações e referências conforme a norma ABNT 2023.



## Como utilizar o template

### Pré-requisitos

Antes de começar, você precisa ter instalados:

- [Quarto](https://quarto.org/docs/download/) (versão mais **recente**);
- Um editor ou IDE como [RStudio](https://posit.co/download/rstudio-desktop/), [VS Code](https://code.visualstudio.com/) ou [Positron](https://posit.co/blog/announcing-positron/);
- [TinyTeX](https://quarto.org/docs/output-formats/pdf-basics.html#installing-tex): sistema TeX simplificado (necessário apenas se desejar também gerar arquivos PDF);
- R ou Python ou Julia (necessários apenas se incluir com código).



### Criando um novo repositório a partir do template

1. Na página principal deste repositório, clique no botão verde <p>
  <a href="https://github.com/seu-usuario/seu-repositorio/generate" target="_blank">
    <img alt="Use this template" src="https://img.shields.io/badge/Use this template-brightgreen?style=flat-square" />
  </a>
</p>



2. Selecione a opção **Create a new repository**.
3. Escolha um nome **descritivo** para o novo repositório 
(por exemplo: `slides-qualificacao-2025`).
4. Clique em **Create repository** para finalizar.



### Clonando o repositório para sua máquina

5. No Windows, abra o **Explorador de Arquivos** e acesse a pasta onde 
deseja armazenar seus projetos.

> 💡 **Dica**: crie uma pasta chamada `Projetos` ou `Git` para organizar 
seus repositórios locais.

6. Dentro da pasta escolhida, clique com o botão direito e selecione 
**Git Bash Here** para abrir o terminal Git Bash na pasta escolhida.

7. Copie o endereço do seu repositório e, no Git Bash, execute o comando:

```bash
git clone https://github.com/seu-usuario/seu-repositorio.git
```

Substitua o link acima pelo endereço do seu repositório.

8. Abra o RStudio, vá até **File → Open Project**, navegue até a pasta 
clonada e abra o projeto RStudio (caso exista um arquivo `.Rproj`).

9. Abra o arquivo `template-slides-revealjs-seunome.qmd` e personalize 
o conteúdo.



## Estrutura do cabeçalho YAML

```yaml
title: "*Pay for Luck* no Mercado Brasileiro..."
subtitle: "Exame de Qualificação <br> Mestrado Profissional em Administração"
author: "Igor Neves Nunes"
institute: "IFMG - Campus Formiga"
date: 2025-08-01
format:
  revealjs:
    theme: simple                # Tema visual do slide
    embed-resources: true        # Gera HTML autocontido (sem arquivos externos)
    controls: true               # Exibe setas de navegação
    scrollable: true             # Permite rolagem de conteúdo longo
    slide-number: true           # Numeração no rodapé
    progress: true               # Barra de progresso inferior
    incremental: false           # Todos os tópicos aparecem ao mesmo tempo
    transition: concave          # Estilo de transição dos slides
    code-link: true              # Exibe link para código, se houver
    overview: true               # Visão geral com tecla ESC
    fig-cap-location: bottom     # Legenda de figuras na parte inferior
    logo: img/logo.jpeg          # Logotipo institucional no canto
    css: estilos.css                # CSS para personalização
crossref:               
  fig-prefix: 'Fig.'             # Prefixo para figuras
  tbl-prefix: 'Tab.'             # Prefixo para tabelas
  eq-prefix: 'Eq.'               # Prefixo para equações
bibliography: referencias.bibtex # Arquivo com as referências bibliográficas
csl: associacao-brasileira-de-normas-tecnicas-ipea.csl # Estilo ABNT para citações
```

> ℹ️ **Nota**: defina `incremental: true` se desejar que os tópicos 
de uma lista apareçam um a um.



## Recursos utilizados no template

### Revealjs

- Sistema de apresentação em HTML interativo.
- Permite uso de teclado, clique, rolagem e visão geral dos slides.

### Equações com LaTeX

Equações matemáticas podem ser escritas com a sintaxe do LaTeX usando `$$...$$`:

```latex
$$
y_{it} = \beta_0 + \beta_1 y_{it-1} + \epsilon_{it}
$$
```

### Tabelas com `gt`

- Criação de tabelas com estilo moderno e responsivo.
- Ideal para descrição de variáveis e resultados estatísticos.

### Gráficos com `ggplot2`

- Inserção de gráficos descritivos e cronogramas, como gráficos de Gantt.

### Blocos `callout`

- Caixas de destaque para introduções, definições, objetivos e justificativas:

```markdown
::: {.callout-note icon=false}
## Título
- Item 1
- Item 2
:::
```

### Estilo CSS personalizado

Arquivo `logo.css` para personalizar logotipo e título principal:

```css
.reveal .slide-logo {
  height: 90px !important;
  width: 70px !important;
}

.reveal h1.title {
  font-size: 1.8em !important;
  line-height: 1.2;
  margin-bottom: 0.3em;
}
```



## Recomendações para adaptação por outros orientandos

- Atualize `title`, `subtitle`, `author` e `date` no cabeçalho YAML.
- Substitua os tópicos e textos conforme o conteúdo da sua apresentação.
- Use `callouts` para estruturar seções com clareza.
- Adicione tabelas e gráficos a partir de seus dados.
- Atualize o arquivo `.bibtex` com suas próprias referências bibliográficas.



## Dicas para apresentação

- O arquivo gerado é um HTML portátil: basta abrir no navegador.
- Comandos úteis durante a apresentação:

- `→` ou `↓`: avançar
- `←` ou `↑`: voltar
- `ESC`: visão geral dos slides
- `S`: modo apresentador (disponível em navegadores compatíveis)












