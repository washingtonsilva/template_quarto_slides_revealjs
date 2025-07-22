
# Template de Apresentação com Quarto + Revealjs

Este é um template para criar **apresentações acadêmicas em HTML** utilizando o sistema **Quarto**, com o formato `revealjs`. Ele foi desenvolvido para atender às necessidades dos orientandos do [Mestrado Profissional em Administração do IFMG - Campus Formiga](https://www.formiga.ifmg.edu.br/mestrado), mas pode ser facilmente adaptado por outros usuários.



## Estrutura do Projeto

O template é composto pelos seguintes arquivos:

- `template-slides-revealjs-seunome.qmd`: arquivo principal em formato 
  Quarto (`.qmd`), onde você irá redigir o conteúdo da sua apresentação.
- `estilos.css`: define as dimensões do logotipo institucional, reduz o 
   tamanho da fonte do título principal dos slides, ajusta o tamanho da 
   fonte dos autores e permite estilizar a afiliação institucional 
   exibida no slide de abertura. Altere o conteúdo deste arquivo somente 
   se souber o que está fazendo.
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
- [TinyTeX](https://quarto.org/docs/output-formats/pdf-basics.html#installing-tex): sistema TeX simplificado;
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

5. Em seu computador, abra o **Windows Explorer** e acesse a pasta onde 
deseja clonar seu repositório.

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
clonada e abra o projeto RStudio: `template-slides-revealjs-seunome.Rproj`

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



### Slides 

- Os títulos de nível 1 (`# Título Principal`) são utilizados 
para definir as **seções principais** da apresentação, 
como Revisão da Literatura, Metodologia, Resultados Esperados, etc, 
mas não são obrigatórios.

- Cada slide é definido por um título de nível 2 (`## Título do Slide`). 



### Blocos `callout`

- Caixas de destaque para introduções, definições, objetivos e justificativas:

```markdown
::: {.callout-note icon=false}
## Título

- Item 1
- Item 2

:::
```



### Listas incremetais com .fragment

- Itens que aparecem um a um ao clicar ou pressionar a seta para baixo:

```markdown
::: incremental
- Ponto 1

- Ponto 2

- Ponto 3
:::
```



### Controle da dimensão global de um slide

Utilize o comando `:::: {style="font-size: 90%;"}` para definir o 
tamanho de um slide específico, alterando o tamanho da fonte e 
dimensões do slide. Por exemplo:

```markdown
## Título do Slide 

:::: {style="font-size: 90%;"}

::: {.callout-note icon=false}
## Título

- Item 1
- Item 2
:::

::::
```

reduz em 90% o tamanho do slide, permitindo incluir mais conteúdo 
se necessário.



### Equações com LaTeX

Equações matemáticas em blocos podem ser escritas com a sintaxe do LaTeX 
usando `$$...$$`:

```latex
$$
y_{it} = \beta_0 + \beta_1 y_{it-1} + \epsilon_{it}
$$
```

Símbolos e outros elementos podem ser escritos em uma linha usando 
`$...$`, como em: 

A variável resposta $y_{it}$ é influenciada por sua 
própria defasagem $y_{it-1}$ e um erro aleatório $\epsilon_{it}$.



### Citações e referências

Citações no texto são feitas com `@label`, como em 
"conforme @nunes_2025". As referências são formatadas automaticamente 
no final do slide, com o estilo ABNT 2023. 

Você pode inserir referências em diversas partes de um slide, incluindo 
no título de um slide, no título de um callout, ou em qualquer outro 
local. Por exemplo:

É importante inserir o seguinte div ao final para que as 
referências sejam exibidas corretamente:

```markdown
## Referências

::: {#refs}
:::
```



## Recomendações para adaptação por outros orientandos

- Atualize `title`, `subtitle`, `author` e `date` no cabeçalho YAML.
- Substitua os tópicos e textos conforme o conteúdo da sua apresentação.
- Use `callouts` para estruturar seções com clareza.
- Adicione tabelas e gráficos a partir de seus dados.
- Atualize o arquivo `.bibtex` com suas próprias referências bibliográficas.



## Aprenda mais sobre Quarto e Revealjs

- Estude a [Documentação do Formato `revealjs` do Sistema Quarto](https://quarto.org/docs/presentations/revealjs/)












