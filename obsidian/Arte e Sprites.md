# Arte e Sprites — Enduro: Corrida Adler (1983)

A direção de arte de *Enduro: Corrida Adler* adota a estética retrô de **GB Studio 4.3.2 (Game Boy Color)**, respeitando o limite de 192 tiles únicos por cena e paletas de 4 cores por tile/sprite.

---

## 1. Especificações Técnicas de Resolução

* **Telas de Menu, Vitória, Derrota e Easter Egg:** **160 × 144 pixels** (20 × 18 tiles de 8×8).
* **Pistas de Corrida (Etapas 1 a 4):** **1600 × 144 pixels** (200 × 18 tiles de 8×8).
* **Sprites do Jogo:** **16 × 16 pixels** (2 × 2 tiles de 8×8).

---

## 2. Catálogo de Sprites Utilizados no Jogo

Todos os sprites utilizados encontram-se organizados na pasta [`sprites/`](file:///c:/Users/fi%20de%20k9/Desktop/EMOLe/sprites) com a geometria e as paletas reais do jogo:

### 2.1. Carros (16 × 16 px)

| Arquivo | Dimensões | Descrição Visual | Cores da Paleta no Jogo (Hex) |
| :--- | :---: | :--- | :--- |
| `carro-jogador.png` | 16 × 16 px | Carro 80 visto de frente/trás (parado ou ao soltar o botão). | `#FFFFFF`, `#E82820`, `#101018` |
| `carro-perfil.png` | 16 × 16 px | Carro 80 visto de perfil indo para a direita. | `#FFFFFF`, `#E82820`, `#101018` |
| `carro-azul.png` | 16 × 16 px | Carro Rival Azul (Etapas de Corrida). | `#FFFFFF`, `#3080F8`, `#101018` |
| `carro-amarelo.png` | 16 × 16 px | Carro Rival Amarelo (Etapas de Corrida e Protótipo Dourado). | `#FFFFFF`, `#F8D820`, `#101018` |
| `carro-verde.png` | 16 × 16 px | Carro Rival Verde (Etapas de Corrida). | `#FFFFFF`, `#30C848`, `#101018` |
| `carro-neblina.png` | 16 × 16 px | Carro Rival Neblina (Etapa 3 - Neblina). | `#FF2838`, `#9098A0`, `#181C20` |
| `carro-gelo-claro.png` | 16 × 16 px | Carro Rival Gelo (Etapa 4 - Gelo Noturno). | `#FFFFFF`, `#78D0F8`, `#081020` |

### 2.2. Personagens, Troféu e Cenário

| Arquivo | Dimensões | Descrição Visual |
| :--- | :---: | :--- |
| `trofeu.png` | 16 × 16 px | Taça Adler dourada exibida na Tela de Vitória e na Garagem Secreta. |
| `piloto-vitoria.png` | 16 × 16 px | Piloto campeão com os braços erguidos no pódio. |
| `piloto-derrota.png` | 16 × 16 px | Piloto derrotado na Tela de Derrota. |
| `arvore-amanhecer.png` | 8 × 8 px | Pinheiro da margem da pista na Etapa 1 (Amanhecer). |
| `arvore-crepusculo.png` | 8 × 8 px | Pinheiro da margem da pista na Etapa 2 (Crepúsculo). |
| `arvore-gelo.png` | 8 × 8 px | Pinheiro congelado da margem da pista na Etapa 4 (Gelo Noturno). |
| `spritesheet-preview.png` | 320 × 224 px | Prancha de visualização (4×) com todos os sprites utilizados no jogo. |

---

## 3. Cenas Renderizadas do Jogo

As cenas reais do jogo encontram-se organizadas nas pastas [`cenas/`](file:///c:/Users/fi%20de%20k9/Desktop/EMOLe/cenas) e [`obsidian/imagens/`](file:///c:/Users/fi%20de%20k9/Desktop/EMOLe/obsidian/imagens):

* `tela_inicio.png` (160 × 144 px): Tela inicial **ENDURO - ADLER 1983** com pista da garagem.
* `cena_secreta_easter_egg.png` (160 × 144 px): **Segredo Adler — Garagem VIP 83** (Easter Egg ao dirigir até o final da tela inicial).
* `tela_vitoria.png` (160 × 144 px): Pódio de campeão da Corrida Adler.
* `tela_derrota.png` (160 × 144 px): Tela de fim de jogo / carro quebrado.
* `cena_1_amanhecer.png` (1600 × 144 px): Etapa 1 — Amanhecer (Ultrapassagens: 10).
* `cena_2_crepusculo.png` (1600 × 144 px): Etapa 2 — Crepúsculo (Ultrapassagens: 22).
* `cena_3_neblina.png` (1600 × 144 px): Etapa 3 — Neblina (Ultrapassagens: 36).
* `cena_4_gelo.png` (1600 × 144 px): Etapa 4 — Gelo Noite (Ultrapassagens: 52).
