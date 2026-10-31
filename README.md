# Agenda da Carinha do Tempo

Lembretes mostrados no rodapé da tela (Echo Show 5). Edite `agenda.json` e faça commit; a tela pega a mudança em uns 10 a 20 minutos.

**Atenção: este repositório é público.** Não coloque nada que não possa ser visto por qualquer pessoa.

## Formato

Uma lista de itens. Cada item tem `texto` e um destes:

| Campo | Significado |
|---|---|
| `"data": "2026-11-04"` | dia único |
| `"semanal": [1, 3]` | dias da semana (0 = domingo, 1 = segunda … 6 = sábado); pode ter `de`/`ate` para valer só nesse período |
| `"de": "2026-12-22", "ate": "2027-01-07"` | intervalo de datas, inclusive |

Opcionais:

- `"escolar": true`: rotina escolar; **não aparece em dias sem aula**.
- `"sem_aula": true`: dia ou intervalo sem aula (feriado, livre disposição, férias); esconde os itens `escolar` desses dias e aparece como lembrete.

```json
[
  { "data": "2026-11-04", "texto": "Reunião 8h30" },
  { "semanal": [2], "texto": "Ed. Física (uniforme)", "escolar": true, "de": "2026-09-08", "ate": "2027-06-21" },
  { "data": "2026-11-02", "texto": "Sem aula (livre disposição)", "sem_aula": true },
  { "de": "2026-12-22", "ate": "2027-01-07", "texto": "Férias de Natal", "sem_aula": true }
]
```

- No mesmo dia, a ordem é: itens de `data`, depois `sem_aula`, depois `semanal`. Vários lembretes alternam a cada 3 s.
- Depois das 20h a tela mostra os lembretes de amanhã, com "Amanhã: " na frente.
- Até uns 40 caracteres cabem sem reduzir a fonte; textos maiores encolhem e, no limite, terminam em "…".
- Se o JSON estiver inválido, a tela continua mostrando a última agenda válida.
