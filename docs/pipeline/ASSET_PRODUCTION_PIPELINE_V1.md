# Asset Production Pipeline V1

## Ordem de produção (curta)
1. Player base (silhueta e animações mínimas)
2. Sistema modular de armas e itens no corpo
3. 3 inimigos base (rush/tank/ranged)
4. VFX hit/kill (com explosão obrigatória)
5. HUD base
6. Expansão para conteúdo da vertical slice

## Fluxo por asset
1. Silhueta P&B
2. Pose-chave (idle/move/attack/hit/death)
3. Sprite sheet mínima
4. Import com pivô padrão
5. Teste em arena
6. Aprovar / simplificar / descartar

## Regras de modularidade
- Camadas separadas: body / weapon / item / vfx.
- Slots padronizados para acoplamento.
- Reuso de base de animação quando possível.

## Timebox anti-refação
- Máximo de 2 iterações por asset antes de decisão de corte/rework.
- Se falhar em leitura, prioridade é simplificar, não detalhar.

## Critérios de consistência (manual + IA)
- Normalização obrigatória de paleta, contorno, escala e pivô.
- Saída de IA nunca entra direta sem ajuste de linguagem visual.
