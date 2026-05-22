# Gerador de dc.provenance — DSpace

Ferramenta web para registrar substituições e adições de bitstream em repositórios DSpace, gerando o texto padronizado de proveniência (`dc.provenance`) com checksum MD5.

**[Acessar a ferramenta](https://raphaelxavier79.github.io/dspace-provenance/)**

---

## Sobre

Quando um bitstream é substituído ou adicionado manualmente no DSpace — fora do fluxo normal de submissão —, o sistema não registra automaticamente o evento no campo `dc.provenance`. Essa ausência compromete a rastreabilidade e a cadeia de custódia do objeto digital.

Esta ferramenta gera o texto de proveniência no mesmo padrão utilizado pelo DSpace, permitindo que o registro seja inserido manualmente nos metadados do item.

---

## Funcionalidades

- Suporte a **substituição** e **adição** de bitstreams
- Cálculo de **checksum MD5** e tamanho em bytes diretamente no navegador
- Geração do texto `dc.provenance` padronizado, pronto para copiar e colar no DSpace
- Suporte a **múltiplos arquivos** por operação, com mapeamento de correspondência entre novos arquivos e bitstreams existentes
- Importação do `dc.provenance` atual do item para manter o histórico completo de bitstreams
- **Processamento 100% local** — nenhum arquivo é enviado a qualquer servidor

---

## Como usar

**1. Informe a origem**
Indique se o item já possui um `dc.provenance` registrado. Se sim, cole o texto completo — a ferramenta extrairá automaticamente os bitstreams existentes.

**2. Preencha os dados**
Informe nome, e-mail (conforme cadastro no DSpace), motivo da operação e o tipo: substituição ou adição. Em caso de substituição, indique se o bitstream anterior será preservado no repositório.

**3. Selecione os arquivos**
Faça upload do(s) arquivo(s) novo(s). O checksum MD5 e o tamanho em bytes são calculados localmente. Se houver múltiplos arquivos em uma substituição, a ferramenta solicita o mapeamento de correspondência.

**4. Copie o resultado**
O texto `dc.provenance` gerado pode ser copiado e inserido nos metadados do item no DSpace via interface administrativa.

---

## Formato gerado

O texto segue o padrão nativo do DSpace:

```
Bitstream substituído por Nome Sobrenome (email@instituicao.br) em 2026-05-22T14:30:00Z: motivo da substituição. Bitstream anterior não preservado. No. of bitstreams: 1 arquivo.pdf: 123456 bytes, checksum: abc123def456... (MD5)
```

---

## Contexto

Desenvolvido para uso interno no **Repositório Digital FGV**, no âmbito das práticas de preservação digital do **Sistema de Bibliotecas da FGV (FGV SB)**.

---

## Desenvolvimento

Desenvolvido por **Raphael Xavier**  
raphael.xavier@fgv.br  
Fundação Getulio Vargas — Biblioteca Digital - Sistema de Bibliotecas
