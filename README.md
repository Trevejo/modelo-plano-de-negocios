# Modelo de Plano de Negócios

Modelo LaTeX para elaboração de planos de negócios no padrão ABNT, baseado nas metodologias de Dornelas, Sebrae e Pirola.

## Como usar

1. Clone o repositório
2. Edite o arquivo `modelo-plano-de-negocios.tex`
3. Substitua os campos `[]{}` e `\tcampo{}` com as informações do seu negócio
4. Compile com `pdflatex` + `biber` + `pdflatex` (duas vezes)

## Estrutura do documento

1. **Sumário Executivo** -- Resumo completo do plano
2. **Conceito do Negócio** -- Histórico, missão, visão, valores, aspectos legais
3. **Análise de Mercado** -- PEST, mercado-alvo, concorrência, tendências
4. **Produtos e Serviços** -- Portfólio, diferenciais, tecnologia, segurança
5. **Plano de Marketing** -- 4Ps, posicionamento, projeção de vendas
6. **Plano Operacional** -- Estrutura, processos, infraestrutura, MVP
7. **Equipe de Gestão** -- Perfis, conselho, crescimento de RH
8. **Plano Financeiro** -- Investimento, custos pré/pós-lançamento, DRE, fluxo de caixa, indicadores
9. **Análise de Cenários e Riscos** -- Cenários, riscos, contingência
10. **Estratégia de Crescimento** -- SWOT, SMART, Ansoff
11. **Considerações Finais** -- Conclusão e próximos passos
12. **Referências** -- Fontes consultadas
13. **Anexos** -- Documentos complementares

## Compilação

```bash
pdflatex modelo-plano-de-negocios
biber modelo-plano-de-negocios
pdflatex modelo-plano-de-negocios
pdflatex modelo-plano-de-negocios
```

## Requisitos

- TeX Live ou MiKTeX com pacotes: `abntex2`, `newtxtext`, `newtxmath`, `biblatex`, `biber`, `pgfplots`, `tabularx`, `booktabs`, `enumitem`

## Licença

Uso livre para qualquer empreendedor.
