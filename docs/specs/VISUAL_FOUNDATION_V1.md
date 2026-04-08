# VISUAL FOUNDATION V1

## Objetivo
Estabelecer as regras **não negociáveis** da base visual do roguelite para evitar retrabalho e manter leitura de combate.

## 1) Hierarquia de leitura (ordem fixa)
1. Player
2. Ameaças imediatas (inimigos próximos/telegráficos)
3. Ataques e projéteis
4. Pickups
5. Feedbacks (números/VFX secundários)
6. Cenário

Regra: qualquer asset que quebre essa ordem deve ser simplificado ou refeito.

## 2) Perspectiva oficial
- Falsa top-down 3/4 com leitura frontal preservada.
- Não buscar realismo de câmera.
- Pivô visual sempre no contato com o chão.

## 3) Escala e canvas base

| Classe | Canvas base | Altura visual alvo | Observação |
|---|---:|---:|---|
| Player | 64x64 | 42–48 px | Silhueta principal do jogo |
| Inimigo pequeno | 48x48 | 28–34 px | Rush/frágil |
| Inimigo médio | 64x64 | 38–44 px | Faixa padrão |
| Elite | 96x96 | 56–64 px | Presença sem virar boss |
| Boss (V1) | 128x128 | 84–96 px | Um único boss na slice |
| Pickup comum | 24x24 | 12–16 px | Nunca competir com player |
| Arma equipada | 32x32 / 48x48 | - | Modular por slot |
| VFX hit/kill | 64x64 / 96x96 | - | Escala por impacto |

## 4) Pivô e sombra
- **Pivô padrão**: centro inferior do sprite (ponto de contato com chão).
- **Sombra padrão**: elipse no chão (sprite separado), opacidade baixa, sem contorno forte.
- Sombra nunca deve comunicar hitbox maior que a real.

## 5) Regras de silhueta do player
- Ler em miniatura (25% da resolução de trabalho).
- Manter contorno principal reconhecível com 2 armas + 3 itens ativos.
- Evitar detalhes finos no contorno externo.
- “Leitura > detalhe” é regra de corte.

## 6) Sistema visual no corpo (slots)
Slots permitidos na V1:
- Cabeça
- Costas
- Braço esquerdo
- Braço direito
- Torso
- Aura (máx. 1)

Limites:
- Máximo de 1 item dominante grande por vez.
- Máximo de 2 médios e 2 pequenos simultâneos.
- Upgrade no mesmo slot **substitui estágio anterior** (não empilha sem limite).

## 7) Regras obrigatórias de feedback
### 7.1 Morte de inimigo = explosão
Toda morte deve ter:
- flash curto de impacto,
- ruptura (partículas/fragmentos),
- dissipação rápida.

Sem “sumir seco”.

### 7.2 Arma pega = aparece no personagem
Toda arma equipada precisa existir visualmente no corpo (mão/costas/órbita curta).

### 7.3 Item pega = altera visual do personagem
Item relevante precisa gerar mudança visível em slot corporal/mutação leve/marca.

## 8) Fundo humilde
- Textura de chão de baixa frequência.
- Props com baixo contraste.
- Sem elementos que rivalizem com entidades e projéteis.

## 9) Honestidade visual de hitbox
- Hitbox lógica simples.
- Sprite pode exagerar forma, mas não pode mentir alcance crítico.

## 10) Checklist de aprovação de asset (gate)
Um asset só entra se passar:
1. Leitura em arena com caos (30+ entidades).
2. Coerência com perspectiva/pivô/sombra.
3. Não quebra hierarquia visual.
4. Custo de produção sustentável (sem pipeline inviável).

## 11) Escopo travado da vertical slice V1
- 1 personagem
- 1 biome
- 6 inimigos base
- 1 elite
- 1 boss
- 4 armas
- 8 upgrades visuais
- Run alvo: 10–12 minutos
