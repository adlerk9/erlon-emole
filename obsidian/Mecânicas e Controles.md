# Mecânicas e Controles — Enduro: National Rally

Este documento detalha o modelo físico, a lógica de entrada (input), as variáveis de estado e as regras de ultrapassagem e colisão de *Enduro: National Rally*.

---

## 1. O Sistema de Condução em 3 Faixas

A rodovia é estruturada em uma perspectiva pseudo-3D com **três faixas de rolamento virtuais**:

```
             PONTO DE FUGA (Horizonte)
                      /\
                     /  \
                    /    \
                   / |  | \
                  /  |  |  \
                 /   |  |   \
   FAIXA 1      / F1 |F2| F3 \     FAIXA 3
 (Esquerda)    /     |  |     \   (Direita)
              /______|__|______\
                   FAIXA 2
                  (Central)
```

* **Faixa 1 (Esquerda):** Posição segura para ultrapassar retardatários lentos pelo lado interno.
* **Faixa 2 (Centro):** Linha ideal de largada e aceleração em reta.
* **Faixa 3 (Direita):** Linha externa, usada para desvios rápidos de veículos centrais.

### Movimentação Lateral
Ao pressionar `←` ou `A`, o carro translada suavemente em direção à faixa da esquerda. Ao pressionar `→` ou `D`, desloca-se para a direita. Na maioria das etapas, a resposta é imediata; na [[Cenas do Jogo#4-etapa-4-pista-de-gelo-noturna|Etapa de Gelo]], aplica-se uma inércia de escorregamento.

---

## 2. Aceleração, Frenagem e Velocidade de Cruzeiro

O carro possui um motor simulado com taxa de aceleração progressiva:

* **Velocidade Mínima:** 60 km/h (velocidade base de cruzeiro se nenhuma tecla for pressionada).
* **Velocidade Máxima:** 220 km/h (alcançada mantendo `↑` ou `W` pressionado em reta).
* **Frenagem:** Pressionar `↓` ou `S` aplica desaceleração rápida (cerca de -40 km/h por segundo), essencial para evitar choques iminentes.
* **Relação Velocidade × Aproximação:** A velocidade do jogador controla o fator de incremento vertical ($\Delta Y$) dos carros rivais. Quanto mais rápido o jogador corre, mais velozes os adversários descem a tela em sua direção.

---

## 3. Lógica de Ultrapassagem e Cota

O objetivo primordial é atingir a marca de **200 ultrapassagens**:

$$\text{Carros Restantes} = 200 - \text{Ultrapassagens Realizadas}$$

### Detecção de Ultrapassagem
1. Os carros adversários nascem no horizonte ($Y \approx 300$ na resolução 1600 × 900) e movem-se para baixo até $Y = 900$.
2. O carro do jogador situa-se em posição fixa no eixo vertical ($Y \approx 720$).
3. No exato instante em que a posição $Y_{\text{rival}}$ ultrapassa a linha traseira do jogador ($Y_{\text{jogador}}$), o sistema incrementa o contador de ultrapassagens e emite o efeito sonoro de corte de ar em estéreo.

---

## 4. Sistema de Colisão e Penalidades

Colidir contra a traseira de outro veículo prejudica severamente a corrida:

* **Detecção:** A colisão ocorre quando a caixa delimitadora (hitbox) do jogador intercepta a hitbox de um rival na mesma faixa.
* **Penalidade Imediata:** 
  1. A velocidade do carro cai bruscamente para **40 km/h**.
  2. O veículo vibra lateralmente por 0.5 segundo (efeito de impacto).
  3. Toca o efeito sonoro metálico de batida.
  4. Perde-se entre 3 a 5 segundos cruciais de corrida na retomada de aceleração.
* **Limite de Danos:** 5 colisões na mesma etapa ativam o estado de perda de rendimento do motor, aumentando o risco de encerramento prematuro por tempo.

---

## 5. Efeitos Climáticos na Jogabilidade

### Neblina (Cena 3)
* **Distância de Visão Reduzida:** Carros rivais só se tornam visíveis a partir de 45% do traçado da estrada.
* **Faróis e Lanternas:** As lanternas traseiras vermelhas dos adversários acendem a uma distância maior para servir de alerta visual prévio.

### Pista de Gelo (Cena 4)
* **Aderência (Atrito):** O coeficiente de atrito lateral é reduzido em 65%.
* **Efeito de Deslizamento:** Ao soltar o direcional para virar, o veículo continua deslizando na mesma direção por mais 250 a 400 milissegundos.
* **Contraesterço:** O jogador deve realizar correções sutis de direção em vez de manter a tecla pressionada.

---

## 6. Mapeamento de Teclas

| Comando | Tecla Principal | Alternativa | Descrição |
| :--- | :---: | :---: | :--- |
| **Virar à Esquerda** | `←` | `A` | Move o carro para a faixa esquerda |
| **Virar à Direita** | `→` | `D` | Move o carro para a faixa direita |
| **Acelerar** | `↑` | `W` | Incrementa rotação e velocidade até 220 km/h |
| **Frear** | `↓` | `S` | Aplica freios a disco de emergência |
| **Luzes / Faróis** | `L` | `F` | Alterna iluminação dianteira |
| **Pausar / Menu** | `Esc` | `P` | Abre tela de pausa ou retorna ao menu |
| **Confirmar / Avançar**| `Enter` | `Espaço` | Inicia prova ou avança diálogos de vitória/derrota |

---

## 7. Documentos Relacionados

- Visão das 4 Pistas: [[Cenas do Jogo]]
- Enredo Oficial: [[História do Jogo]]
- Telas de Vitória e Derrota: [[Telas do Jogo]]
- Game Design Geral: [[GDD - Enduro National Rally]]
- Sprites e Paletas: [[Arte e Sprites]]
- Hub do Projeto: [[Inicio]]
