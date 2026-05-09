# Template LaTeX – PPGCA/UnB Planaltina
**Tese de Doutorado / Dissertação de Mestrado**
*Programa de Pós-Graduação em Ciências Ambientais*
*Faculdade UnB de Planaltina – Universidade de Brasília*

---

## Créditos

**Autor do template:** Rui Ogawa  
**Afiliação:** PPGCA/UnB | Fiocruz Brasília | IFB Planaltina  
**Contato:** ruiogawa@gmail.com  
**Versão:** 1.0 (2026)  
**Licença:** Creative Commons BY 4.0

---

## Estrutura de arquivos

```
ppgca-unb/
├── main.tex                  ← Arquivo principal (compile este)
├── referencias.bib           ← Referências bibliográficas (BibTeX)
├── unb-logo.png              ← Logo da UnB (baixe em unb.br/identidade-visual)
├── ficha-catalografica.pdf   ← Gerada em ficha.bce.unb.br (adicionar depois)
└── capitulos/
    ├── 01-introducao.tex
    ├── 02-objetivos.tex
    ├── 03-contextualizacao.tex
    ├── cap1.tex              ← Capítulo 1 (artigo/estudo)
    ├── cap2.tex              ← Capítulo 2
    ├── cap3.tex              ← Capítulo 3
    ├── conclusao.tex
    ├── apendice-a.tex
    ├── apendice-b.tex
    └── anexo-a.tex
```

---

## Como usar no Overleaf

1. **Importe o projeto:**
   - No Overleaf, clique em *New Project → Upload Project*
   - Envie o arquivo `.zip` com todos os arquivos
   
2. **Configure o compilador:**
   - Menu (⚙) → Compiler → **pdfLaTeX**
   - O Overleaf compilará automaticamente na sequência
     `pdfLaTeX → BibTeX → pdfLaTeX → pdfLaTeX`

3. **Adicione a logo da UnB:**
   - Baixe em: https://www.unb.br/identidade-visual
   - Faça upload do arquivo como `unb-logo.png` (ou `.pdf`)

4. **Configure seus dados** em `main.tex`:
   - `\titulo{...}` — título do trabalho
   - `\autor{...}` — seu nome completo
   - `\orientador{...}` — nome do orientador
   - `\data{...}` — mês/ano de defesa
   - Membros da banca (`\bancaPresidente`, `\bancaTitularI`, etc.)
   - Escolha entre `\tipodotrabalho{Tese de Doutorado}` ou
     `{Dissertação de Mestrado}`

5. **Escreva seu conteúdo** nos arquivos dentro de `capitulos/`

6. **Referências bibliográficas:**
   - Adicione entradas no arquivo `referencias.bib`
   - Cite no texto com `\cite{chave}` ou `\citeonline{chave}`

---

## Recursos avançados: Backref (citação reversa)

O template inclui o pacote `backref` configurado para que:
- **Ao clicar em uma citação** no texto → vai para a entrada na lista de referências
- **Na lista de referências**, cada entrada exibe quantas vezes foi citada
  e em quais páginas
- **Ao clicar na página** mencionada → retorna para onde está a citação no texto

Exemplo de saída nas referências:
> Silva, J. et al. Título do artigo. *Revista X*, 2024.  
> <span style="color:gray">*Citado 3 vezes nas páginas 15, 32, 47.*</span>

---

## Normas ABNT atendidas

- **NBR 14724:2011** – Trabalhos acadêmicos (apresentação)
- **NBR 6023:2018** – Referências bibliográficas
- **NBR 6024:2012** – Numeração progressiva
- **NBR 6027:2012** – Sumário
- **NBR 6028:2003** – Resumo
- **NBR 10520:2002** – Citações

---

## Elementos pré-textuais incluídos

| Elemento | Status |
|---|---|
| Capa | ✅ |
| Folha de rosto | ✅ |
| Ficha catalográfica | ✅ (rascunho; substitua pelo PDF da BCE) |
| Folha de aprovação | ✅ |
| Dedicatória | ✅ |
| Agradecimentos | ✅ |
| Epígrafe | ✅ |
| Resumo (português) | ✅ |
| Abstract (inglês) | ✅ |
| Lista de figuras | ✅ |
| Lista de tabelas | ✅ |
| Lista de abreviaturas e siglas | ✅ |
| Lista de símbolos | ✅ |
| Sumário | ✅ |

## Elementos pós-textuais incluídos

| Elemento | Status |
|---|---|
| Referências bibliográficas | ✅ |
| Apêndices | ✅ |
| Anexos | ✅ |
| Índice remissivo | ✅ (opcional) |

---

## Pacotes utilizados

| Pacote | Finalidade |
|---|---|
| `abntex2` | Classe base ABNT para trabalhos acadêmicos brasileiros |
| `abntex2cite` | Citações e referências no estilo ABNT |
| `backref` | Citação reversa (backlinks nas referências) |
| `hyperref` | Links clicáveis no PDF |
| `mathptmx` | Fonte Times New Roman |
| `graphicx` | Figuras e imagens |
| `booktabs` | Tabelas com formatação profissional |
| `listings` | Código-fonte com destaque de sintaxe |
| `siunitx` | Unidades do SI e formatação numérica |
| `microtype` | Melhoras tipográficas avançadas |

---

## Suporte

- Documentação abntex2: https://www.abntex.net.br
- Overleaf Learn: https://www.overleaf.com/learn
- Repositório deste template: [link do Overleaf Gallery]
