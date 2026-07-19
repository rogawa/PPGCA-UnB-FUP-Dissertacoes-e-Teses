# Template LaTeX – PPGCA/UnB Planaltina
**Projeto de Pesquisa / Dissertação de Mestrado / Tese de Doutorado**  
*Programa de Pós-Graduação em Ciências Ambientais*  
*Faculdade UnB de Planaltina – Universidade de Brasília*

---

## Créditos

**Autor do template:** Rui Ogawa  
**Afiliação:** PPGCA/UnB | Fiocruz Brasília | IFB Planaltina  
**Contato:** ruiogawa@gmail.com  
**Versão:** 2.0 (2026)  
**Licença:** Creative Commons BY 4.0

---

## Estrutura de arquivos

```
ppgca-unb/
├── main.tex                      ← Arquivo principal (compile este)
├── referencias.bib               ← Referências bibliográficas (BibTeX)
├── unb-logo.png                  ← Logo da UnB (baixe em http://www.marca.unb.br/)
├── ficha-catalografica.pdf       ← Gerada automaticamente pela BCE/UnB (adicionar depois)
└── capitulos/
    ├── 01-introducao.tex                  ← modelo tradicional
    ├── 02-materiais-metodos.tex           ← modelo tradicional
    ├── 03-recursos-financeiros.tex        ← usado nos dois modelos
    ├── 04-cronograma.tex                  ← usado nos dois modelos
    ├── 05-resultados.tex                  ← modelo tradicional
    ├── 06-conclusao.tex                   ← modelo tradicional
    ├── 07-exemplos.tex                    ← usado nos dois modelos (tabelas, figuras, equações, código)
    ├── capitulado-01-fundamentacao.tex    ← modelo por capítulos autônomos
    ├── capitulado-02-exemplo.tex          ← modelo por capítulos autônomos (com hipótese)
    ├── capitulado-03-exemplo.tex          ← modelo por capítulos autônomos (sem hipótese)
    ├── capitulado-04-conclusao.tex        ← modelo por capítulos autônomos
    ├── apendice-a.tex
    ├── apendice-b.tex
    └── anexo-a.tex
```

> **Nota:** Todo o conteúdo dos capítulos é fictício e serve apenas para demonstrar
> o layout. Substitua pelo conteúdo real da sua pesquisa antes de submeter.

---

## Tipo de documento

Este template suporta três tipos de documento. Edite **apenas quatro linhas** no
topo da seção de configuração do `main.tex`:

```latex
%\projetotrue\mestradotrue    % Projeto de Pesquisa de Mestrado
%\projetotrue\mestradofalse   % Projeto de Pesquisa de Doutorado
%\projetofalse\mestradotrue   % Dissertação de Mestrado
\projetofalse\mestradofalse   % Tese de Doutorado  ← padrão
```

O template ajusta automaticamente todos os textos, a folha de aprovação e os
elementos pré/pós-textuais:

| Elemento                     | Projeto | Dissertação | Tese |
|------------------------------|:-------:|:-----------:|:----:|
| Capa                         | ✅      | ✅          | ✅   |
| Folha de rosto               | ✅      | ✅          | ✅   |
| Ficha catalográfica          | ❌      | ✅          | ✅   |
| Folha de aprovação           | ✅      | ✅          | ✅   |
| Dedicatória                  | ❌      | ✅          | ✅   |
| Agradecimentos               | ❌      | ✅          | ✅   |
| Epígrafe                     | ❌      | ✅          | ✅   |
| Resumo / Abstract            | ✅      | ✅          | ✅   |
| Listas e Sumário             | ✅      | ✅          | ✅   |
| Considerações Finais / Capítulo de Conclusão | ❌      | ✅          | ✅   |
| Título da banca              | BANCA EXAMINADORA DE QUALIFICAÇÃO | BANCA EXAMINADORA | BANCA EXAMINADORA |

---

## Modelo estrutural dos capítulos

Independentemente do tipo de documento acima, o template suporta dois modelos
de organização do corpo do texto. Edite **uma linha** logo abaixo da
configuração de tipo de documento em `main.tex`:

```latex
\capituladofalse               % Modelo tradicional  ← padrão
%\capituladotrue               % Modelo por capítulos autônomos
```

| Modelo | Quando usar | Estrutura |
|--------|-------------|-----------|
| **Tradicional** (`\capituladofalse`) | Trabalho com um único fio narrativo | Introdução → Materiais e Métodos → Recursos Financeiros → Cronograma → Resultados e Discussão → Considerações Finais |
| **Capítulos autônomos** (`\capituladotrue`) | Trabalho organizado como uma sequência de capítulos publicáveis de forma independente (um por Objetivo Específico) | Capítulo 1 (Fundamentação, Problema, Área de Estudo, Objetivo Geral e seção consolidada de Objetivos Específicos e Hipóteses) → Capítulos de conteúdo (2, 3, 4...) → Recursos Financeiros → Cronograma → Capítulo final de Contribuições Integradas e Conclusão |

No modelo por capítulos autônomos, **cada capítulo de conteúdo repete a mesma
estrutura interna**: Resumo do Capítulo, Introdução, Objetivo, Hipótese
(quando aplicável — omita esta seção em capítulos que não testam uma
hipótese formal, como os que constroem infraestrutura ou ferramentas),
Metodologia e Contribuições Esperadas. Os identificadores de Objetivo
Específico (OE) e de Hipótese (H) usados em cada capítulo remetem de volta à
seção consolidada no Capítulo 1, evitando que o leitor precise localizar cada
objetivo e hipótese espalhados ao longo do texto.

Para adicionar mais capítulos de conteúdo:

1. Copie `capitulos/capitulado-02-exemplo.tex` (ou `capitulado-03-exemplo.tex`,
   se o capítulo não testar uma hipótese) para um novo arquivo.
2. Ajuste o conteúdo, mantendo os rótulos (`\label`) únicos.
3. Em `main.tex`, dentro do bloco `\ifcapitulado`, acrescente o par
   `\chapter{...}` / `\input{...}` correspondente, antes do capítulo final de
   conclusão.
4. Atualize a tabela e a lista de Objetivos Específicos e Hipóteses no
   `capitulos/capitulado-01-fundamentacao.tex`.

---

## Idioma do corpo do texto

Independente das duas opções acima, o corpo do texto pode ser redigido em
português ou em inglês. Edite uma linha em `main.tex`:

```latex
\inglesfalse   % Corpo do texto em português  ← padrão
%\inglestrue   % Corpo do texto em inglês
```

Essa opção troca o idioma ativo do babel — e com ele, automaticamente,
todos os textos padronizados do abnTeX2 (Sumário/Contents, Capítulo/
Chapter, Referências/References, Lista de Ilustrações/List of Figures
etc.) e os títulos dos capítulos definidos em `main.tex` (`\titIntroducao`,
`\titFundamentacao` etc.).

**O que permanece em português mesmo com `\inglestrue`** — por exigência
das normas de pós-graduação da UnB (ex.: PPGENF, PPGSC), que listam
"Resumo na Língua Portuguesa" como item pré-textual obrigatório
independentemente do idioma de redação:

| Elemento | Comportamento |
|----------|----------------|
| Capa, folha de rosto, folha de aprovação, natureza do trabalho, título da banca | Sempre em português (registro institucional oficial) |
| Resumo | Sempre em português e sempre antes do Abstract |
| Abstract | Sempre em inglês (já existia no template) |
| Conteúdo dos capítulos de exemplo (`capitulos/*.tex`) | Não é traduzido automaticamente — o conteúdo fictício é só um exemplo de layout; escreva seu texto real no idioma escolhido |

Se o seu programa exigir uma **segunda folha de rosto em inglês** (prática
documentada em outros programas, como o IF/USP — não confirmada para o
PPGCA/UnB no momento em que este template foi escrito; **verifique com a
secretaria do seu programa**), há um bloco pronto porém comentado logo
após a folha de rosto em português no `main.tex`. Para usá-lo:

1. Preencha `\tituloingles{...}` na seção de configuração.
2. Descomente o bloco `% \ifingles ... \fi` da folha de rosto em inglês.

---

## Estilo de citação/referência

Também independente do idioma: as normas de pós-graduação da UnB (ex.:
PPGSC) permitem tanto **ABNT** quanto **Vancouver/numérico**, desde que
uma única norma seja seguida em todo o trabalho — a escolha não é
determinada pelo idioma de redação. Verifique o regimento do seu programa
antes de decidir. Edite uma linha em `main.tex`:

```latex
\citacaonumericafalse   % ABNT autor-data (NBR 10520/6023)  ← padrão
%\citacaonumericatrue   % Numérico (estilo Vancouver-like)
```

| Estilo | Exemplo no texto | Quando usar |
|--------|-------------------|-------------|
| ABNT autor-data (`alf`) | (SILVA; SOUZA, 2024) | Padrão ABNT, comum em programas brasileiros |
| Numérico (`num`) | (1), (2) ou [1], [2] | Comum em periódicos internacionais das ciências naturais |

---

## Como usar no Overleaf

1. **Importe o projeto:**
   - No Overleaf, clique em *New Project → Upload Project*
   - Envie o arquivo `.zip` com todos os arquivos

2. **Configure o compilador:**
   - Menu (⚙) → Compiler → **pdfLaTeX**

3. **Escolha o tipo de documento, o modelo estrutural, o idioma e o estilo de citação** em `main.tex` (veja seções acima)

4. **Configure seus dados** em `main.tex`:
   - `\titulo{...}` — título do trabalho
   - `\autor{...}` — seu nome completo
   - `\orientador{...}` — nome do orientador
   - `\MesAno` — mês/ano de defesa ou qualificação
   - Membros da banca (`\bancaPresidente`, `\bancaTitularI`, etc.)
   - Área de concentração e linha de pesquisa

5. **Escreva seu conteúdo** nos arquivos dentro de `capitulos/`

6. **Referências bibliográficas:**
   - Adicione entradas no arquivo `referencias.bib`
   - Cite com `\cite{chave}` ou `\citeonline{chave}`

---

## Ficha catalográfica

A ficha catalográfica é gerada **automaticamente** pela BCE/UnB:  
🔗 https://bce.unb.br/elaboracao-de-fichas-catalograficas/

Quando receber o PDF:
1. Salve como `ficha-catalografica.pdf` na raiz do projeto
2. Descomente `\includepdf{ficha-catalografica}` na seção da ficha em `main.tex`
3. Apague o bloco `\fbox{...}` do placeholder
4. Descomente `\usepackage{pdfpages}` no preâmbulo

---

## Recursos avançados

### Backref – Citação reversa
- Ao clicar em uma citação no texto → vai para a entrada nas referências
- Cada referência exibe em quais páginas foi citada e quantas vezes
- Ao clicar na página → retorna ao local da citação no texto

### Tipografia
- Fonte **Times New Roman** em todo o documento, incluindo títulos (sem sans-serif)
- **Hifenização desativada** — espaçamento entre palavras ajustado automaticamente
- Links clicáveis em **preto** (sem cores), conforme exigido pelos programas de pós

### Tabelas
- Três espessuras de régua:
  - `\toprule` / `\bottomrule` → 1,5 pt (borda externa)
  - `\midrule` → 0,5 pt (separador de grupos)
  - `\thinrule` → 0,2 pt (separador entre linhas individuais)
- Exemplos em `capitulos/07-exemplos.tex`: tabela simples, multicoluna com
  divisores verticais e longtable (código comentado para referência)

### Gráficos
- Exemplos de figura simples e subfiguras lado a lado
- `pgfplots` disponível mas comentado (pesado para Overleaf free)
- Recomendação: exporte gráficos como PDF do R ou Python e insira via
  `\includegraphics` — compila instantaneamente

### Código-fonte
- Pacote `listings` configurado para Python e R
- Lista de Códigos gerada automaticamente

### Citações longas
- Use `\begin{citacao}...\end{citacao}` (ambiente nativo do abntex2)
- Fonte 10 pt, recuo 4 cm, espaço simples — conforme NBR 10520

---

## Normas ABNT verificadas

| Norma | Conteúdo |
|---|---|
| **NBR 14724:2011** | Trabalhos acadêmicos — apresentação |
| **NBR 6023:2018** | Referências bibliográficas |
| **NBR 6024:2012** | Numeração progressiva de seções |
| **NBR 6027:2012** | Sumário |
| **NBR 6028:2003** | Resumo |
| **NBR 10520:2002** | Citações |

Formatação aplicada:
- Margens: esquerda/superior 3 cm, direita/inferior 2 cm
- Fonte: Times New Roman 12 pt (texto), 10 pt (legendas, notas, citações longas)
- Espaçamento: 1,5 no texto; simples em notas de rodapé, legendas e referências
- Recuo de parágrafo: 1,25 cm
- Filete de notas de rodapé: 3 cm a partir da margem esquerda
- Legendas: `Figura X –` e `Tabela X –` (travessão, rótulo em negrito)
- Palavras-chave separadas por ponto-e-vírgula

---

## Compatibilidade com Overleaf gratuito

Otimizado para compilar dentro do limite de **20 segundos** do plano gratuito.
Pacotes pesados (`pgfplots`, `pdfpages`, `siunitx`, `microtype`, `rotating`)
estão comentados no preâmbulo com instruções para reativação.

Para uso em **Overleaf self-hosted** ou compilação **local (TeX Live)**,
descomente o bloco de pacotes avançados indicado no preâmbulo.

---

## Pacotes ativos

| Pacote | Finalidade |
|---|---|
| `abntex2` | Classe base ABNT |
| `abntex2cite` | Citações e referências ABNT (autor-data) |
| `backref` | Citação reversa com links |
| `hyperref` | Links clicáveis no PDF |
| `mathptmx` | Times New Roman |
| `graphicx` | Figuras |
| `caption` + `subcaption` | Legendas 10 pt e subfiguras |
| `booktabs` | Réguas calibradas em tabelas |
| `tabularx` | Colunas de largura flexível |
| `multirow` | Células multilinhas |
| `listings` | Código-fonte (Python, R) |
| `amsmath` | Equações |
| `xcolor` | Cores |
| `url` | URLs |
| `lastpage` | Referência à última página |
| `indentfirst` | Recuo no primeiro parágrafo |

---

## Suporte

- Documentação abntex2: https://www.abntex.net.br
- Overleaf Learn: https://www.overleaf.com/learn
- Repositório GitHub: https://github.com/ruiogawa/ppgca-unb-template
- Overleaf Gallery: [link após publicação]
