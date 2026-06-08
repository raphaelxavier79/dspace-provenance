# Gerador de dc.provenance — DSpace

Ferramenta web para registrar operações em bitstreams e alterações de metadado em repositórios DSpace, gerando o texto padronizado de proveniência (`dc.provenance`) com checksum MD5.

**[Acessar a ferramenta](https://raphaelxavier79.github.io/dspace-provenance/)**

---

## Sobre

Quando um bitstream é substituído ou adicionado manualmente no DSpace — fora do fluxo normal de submissão —, o sistema não registra automaticamente o evento no campo `dc.provenance`. O mesmo ocorre em alterações significativas de metadado, como mudanças de autoria, identificadores ou intervenções em massa. Essa ausência compromete a rastreabilidade e a cadeia de custódia do objeto digital.

Esta ferramenta gera o texto de proveniência no mesmo padrão utilizado pelo DSpace, permitindo que o registro seja inserido manualmente nos metadados do item.

---

## Funcionalidades

- Suporte a três tipos de operação: **substituição**, **adição** de bitstreams e **alteração de metadado**
- Cálculo de **checksum MD5** e tamanho em bytes diretamente no navegador
- Geração do texto `dc.provenance` padronizado, pronto para copiar e colar no DSpace
- Suporte a **múltiplos arquivos** por operação, com mapeamento de correspondência entre novos arquivos e bitstreams existentes
- Importação do `dc.provenance` atual do item para manter o histórico completo de bitstreams
- Para alterações de metadado: suporte a **atualização de identificação**, **autoria** e **atualização em massa** (com registro do número de itens afetados)
- **Processamento 100% local** — nenhum arquivo é enviado a qualquer servidor

---

## Como usar

**1. Informe a origem**
Indique se o item já possui um `dc.provenance` registrado. Se sim, cole o texto completo — a ferramenta extrairá automaticamente os bitstreams existentes e os incluirá no novo registro.

**2. Preencha os dados**
Informe nome, e-mail (conforme cadastro no DSpace), motivo da operação e o tipo:
- **Substituição** — indique se o bitstream anterior será preservado no repositório
- **Adição** — nenhuma informação adicional necessária
- **Alteração de metadado** — selecione o tipo de proveniência (identificação, autoria ou atualização em massa); para atualização em massa, informe o número de itens afetados

**3. Selecione os arquivos** *(substituição e adição)*
Faça upload do(s) arquivo(s) novo(s). O checksum MD5 e o tamanho em bytes são calculados localmente. Se houver múltiplos arquivos em uma substituição, a ferramenta solicita o mapeamento de correspondência entre novos arquivos e bitstreams existentes. Para alterações de metadado, esta etapa é ignorada.

**4. Copie o resultado**
O texto `dc.provenance` gerado pode ser copiado e inserido nos metadados do item no DSpace via interface administrativa.

---

## Formatos gerados

**Substituição de bitstream:**
```
Bitstream substituído por Nome Sobrenome (email@instituicao.br) em 2026-05-22T14:30:00Z: motivo da substituição. Bitstream anterior não preservado. No. of bitstreams: 1 arquivo.pdf: 123456 bytes, checksum: abc123def456... (MD5)
```

**Adição de bitstream:**
```
Bitstream adicionado por Nome Sobrenome (email@instituicao.br) em 2026-05-22T14:30:00Z: motivo da adição. No. of bitstreams: 2 arquivo_pt.pdf: 123456 bytes, checksum: abc123... (MD5) arquivo_en.pdf: 654321 bytes, checksum: def456... (MD5)
```

**Alteração de metadado:**
```
Metadado atualizado por Nome Sobrenome (email@instituicao.br) em 2026-05-22T14:30:00Z: Atualização de autoria — correção de nome de autor. No. of bitstreams: 1 arquivo.pdf: 123456 bytes, checksum: abc123... (MD5)
```

**Atualização em massa:**
```
Metadado atualizado por Nome Sobrenome (email@instituicao.br) em 2026-05-22T14:30:00Z: Atualização em massa dos registros — normalização de nomes de autores. Operação afetou 847 itens.
```

---

## Contexto

Desenvolvido para uso interno no **Repositório Digital FGV**, no âmbito das práticas de preservação digital do **Sistema de Bibliotecas da FGV (FGV SB)**.

---

## Desenvolvimento

Desenvolvido por **Raphael Xavier**
raphael.xavier@fgv.br
Fundação Getulio Vargas — Biblioteca Digital · Sistema de Bibliotecas
