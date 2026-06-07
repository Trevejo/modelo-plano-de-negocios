# Modelo de Plano de Negocios

Modelo em LaTeX para elaboracao de planos de negocios em conformidade com a
norma ABNT NBR 14724, estruturado segundo as metodologias de Dornelas (2006),
SEBRAE e Pirola. O documento resultante e um PDF profissional de 13 capitulos,
com tabelas formatadas, cabecalho com numero de pagina e folha de rosto
automatica.

**[Visualizar o PDF do modelo (27 paginas)](modelo-plano-de-negocios.pdf)**


## Requisitos

- **Distribuicao TeX**: [TeX Live](https://www.tug.org/texlive/) (Windows,
  Linux, macOS) ou [MiKTeX](https://miktex.org/) (Windows)
- **Motor**: pdfLaTeX (incluido na distribuicao)
- **Bibliografia**: Biber (incluido na distribuicao)

A instalacao padrao do TeX Live ou MiKTeX ja contem todos os pacotes
necessarios. Se algum pacote estiver ausente, o proprio MiKTeX oferecera
instalacao automatica na primeira compilacao.


## Compilacao

Abra um terminal no diretorio do projeto e execute:

```sh
pdflatex modelo-plano-de-negocios
biber   modelo-plano-de-negocios
pdflatex modelo-plano-de-negocios
pdflatex modelo-plano-de-negocios
```

A sequencia exige tres passagens do `pdflatex` e uma do `biber`:

1. `pdflatex` -- gera os arquivos auxiliares (`.aux`, `.bcf`, `.toc`)
2. `biber`    -- processa as referencias bibliograficas (`.bcf` -> `.bbl`)
3. `pdflatex` -- resolve as citacoes e referencias cruzadas
4. `pdflatex` -- finaliza numeracao e links internos

Alternativamente, use um editor com compilacao automatica (TeXstudio,
VS Code com extensao LaTeX Workshop, Overleaf) que executara as
passagens necessarias de forma transparente.


## Como editar

O arquivo principal e `modelo-plano-de-negocios.tex`. A edicao segue
tres etapas:

### 1. Dados da capa e folha de rosto

Localize o bloco `% --- Informacoes da capa / folha de rosto ---` e
preencha os campos entre chaves:

```latex
\titulo{Plano de Negocios}
\autor{Nome do Empreendedor ou Equipe}
\local{Cidade -- UF}
\data{[\today]}
\instituicao{%
    Nome da Empresa
    \par
    Setor de Atuacao / Segmento%
}
\preambulo{Plano de negocios apresentado como ferramenta de planejamento
    e captacao de recursos para o empreendimento Nome da Empresa.}
```

### 2. Conteudo dos capitulos

Cada secao contem campos preenchiveis identificados por `\tcampo{}` ou
`\icampo`. Substitua o conteudo entre chaves pelas informacoes do seu
negocio. Exemplo:

```latex
% Antes (campo vazio):
\textbf{Nome da Empresa:} & \campo[8cm]{} \\

% Depois (preenchido):
\textbf{Nome da Empresa:} & \campo[8cm]{Minha Empresa Ltda.} \\
```

Instrucoes de preenchimento aparecem em caixas azuis claras com o
comando `\instrucao{...}`. Elas sao apenas orientacao e devem ser
removidas quando o conteudo real for inserido.

### 3. Referencias bibliograficas

Edite o arquivo `referencias.bib` no formato BibTeX. Exemplo:

```bibtex
@online{sebrae2024,
    author   = {SEBRAE},
    title    = {Como Elaborar um Plano de Negocios},
    year     = {2024},
    url      = {https://www.sebrae.com.br},
    urldate  = {2026-05-25}
}
```

As citacoes no texto usam `\cite{chave}` (ex.: `\cite{sebrae2024}`).


## Estrutura do documento

| Capitulo | Conteudo |
|----------|----------|
| 1. Sumario Executivo | Resumo completo do plano em 1--2 paginas |
| 2. Conceito do Negocio | Historico, missao, visao, valores, aspectos legais |
| 3. Analise de Mercado | PEST, mercado-alvo, concorrencia, tendencias |
| 4. Produtos e Servicos | Portfolio, diferenciais, tecnologia, seguranca |
| 5. Plano de Marketing | 4Ps, posicionamento, projecao de vendas |
| 6. Plano Operacional | Estrutura organizacional, processos, infraestrutura, MVP |
| 7. Equipe de Gestao | Perfis dos socios, conselho, crescimento de RH |
| 8. Plano Financeiro | Investimento, custos pre/pos-lancamento, DRE, fluxo de caixa, indicadores |
| 9. Analise de Cenarios e Riscos | Cenarios, riscos, plano de contingencia |
| 10. Estrategia de Crescimento | SWOT, SMART, matriz Ansoff |
| 11. Consideracoes Finais | Conclusao e proximos passos |
| 12. Referencias | Fontes consultadas (gerada automaticamente pelo BibLaTeX) |
| 13. Anexos | Documentos complementares |


## Personalizacao visual

O modelo utiliza a classe `abntex2` com as seguintes configuracoes
visuais que podem ser ajustadas:

- **Cores**: definidas no bloco `% --- Definicao de cores ---`
  (`azul-abnt`, `azul-claro`, `cinza-instrucao`)
- **Cabecalho**: estilo `planoheader` (linha 112)
- **Fontes**: Times New Roman via `newtxtext`/`newtxmath` (padrao ABNT)
- **Espacamento**: `\OnehalfSpacing` (1.5 entrelinhas)


## Arquivos do projeto

```
modelo-plano-de-negocios.tex   -- documento principal (edite este)
referencias.bib                -- bibliografia em formato BibTeX
modelo-plano-de-negocios.pdf   -- PDF compilado (27 paginas)
```


## Licenca

Uso livre. Nenhuma restricao de distribuicao ou modificacao.
