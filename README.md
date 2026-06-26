# Extracted - Ragexe Latam

Esta pasta contem os arquivos extraidos dos patches `.rgz` do servidor Ragnarok Online Latam (ro1patch.gnjoylatam.com).

## Estrutura de pastas

```
Extracted/
  2025-03-14/                        <- Data do patch
    2025-03-14_Ragexe_1741940954.exe <- Entrada ativa (Default)
    2025-03-14_Ragexe_1742279237.exe <- Outra entrada ativa na mesma data
    Comentados/                      <- Entradas comentadas no patch.txt
      2025-03-14_Ragexe_1741940954.exe
    Escondido/                       <- Descobertas pela Procura Avancada
      ...
  2025-03-18/
    ...
```

## Como os arquivos sao organizados

### Modo Default (entradas ativas)
- Arquivos listados em `patch.txt` como ativos (nao comentados)
- Ficam diretamente na pasta da data: `Extracted/YYYY-MM-DD/arquivo.exe`
- Baixados e extraidos pelo modo "Default" na GUI

### Modo Comentados
- Entradas que estao em `patch.txt` mas iniciadas com `//` (comentadas)
- O cliente oficial de patch ignora estas linhas, mas os arquivos existem no servidor
- Ficam em: `Extracted/YYYY-MM-DD/Comentados/arquivo.exe`
- Baixados e extraidos pelo modo "Comentados" na GUI

### Modo Procura Avancada
- Arquivos Ragexe descobertos fora do `patch.txt` (nao listados)
- A busca varre todos os timestamps Unix de cada data, testando com HEAD requests
- Ficam em: `Extracted/YYYY-MM-DD/Escondido/arquivo.exe`
- Usa checkpoint em `ragexe_progress.json` para retomar de onde parou

## Sobre os arquivos

Cada arquivo `.rgz` contem um `Ragexe.exe` que e renomeado para o nome do arquivo original:
- `2025-03-14_Ragexe_1741940954.rgz` extrai `2025-03-14_Ragexe_1741940954.exe`
- O timestamp no nome (ex: `1741940954`) e o timestamp Unix de quando o build foi gerado