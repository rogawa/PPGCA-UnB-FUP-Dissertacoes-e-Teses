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
    ├── 01-introducao.tex
    ├── 02-materiais-metodos.tex
    ├── 03-recursos-financeiros.tex
    ├── 04-cronograma.tex
    ├── 05-resultados.tex
    ├── 06-conclusao.tex
    ├── 07-exemplos.tex           ← Exemplos de tabelas, figuras, equações e código
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
| Considerações Finais         | ❌      | ✅          | ✅   |
| Título da banca              | BANCA EXAMINADORA DE QUALIFICAÇÃO | BANCA EXAMINADORA | BANCA EXAMINADORA |

---

## Como usar no Overleaf

1. **Importe o projeto:**
   - No Overleaf, clique em *New Project → Upload Project*
   - Envie o arquivo `.zip` com todos os arquivos

2. **Configure o compilador:**
   - Menu (⚙) → Compiler → **pdfLaTeX**

3. **Escolha o tipo de documento** em `main.tex` (veja seção acima)

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
