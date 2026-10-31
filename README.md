# Agenda da Carinha do Tempo

Lembretes mostrados no rodapé da tela da cozinha (Echo Show 5). Edite `agenda.json` aqui no GitHub e faça commit; a tela pega a mudança em uns 10 a 20 minutos.

**Atenção: este repositório é público.** Não coloque nada que não possa ser visto por qualquer pessoa.

## Formato

```json
[
  { "semanal": [2, 4], "texto": "Educação física" },
  { "data": "2026-11-12", "texto": "Reunião na escola 17h" },
  { "data": "2026-11-20", "texto": "Dia sem aula" }
]
```

- `semanal`: dias da semana em que o lembrete aparece (0 = domingo, 1 = segunda … 6 = sábado).
- `data`: dia específico, no formato `AAAA-MM-DD`.
- `texto`: o que aparece na tela. Até uns 45 caracteres cabem sem reduzir a fonte.
- Depois das 20h a tela mostra os lembretes de amanhã, com "Amanhã: " na frente.
- Se o JSON estiver inválido (vírgula sobrando, aspas faltando), a tela continua mostrando a última agenda válida.
