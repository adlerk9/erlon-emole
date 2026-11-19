# GDD — Enduro: National Rally

> **Documento de Game Design (Game Design Document)**  
> **Versão:** 1.2  
> **Status:** Produção / Assets Concluídos  
> **Inspiração:** *Enduro* (Activision, 1983 — Atari 2600)

---

## 1. Visão Geral do Projeto

* **Título Oficial:** Enduro — National Rally
* **Gênero:** Corrida Arcade de Resistência / Pseudo-3D Retro Racer
* **Plataforma:** PC (Navegador Web / HTML5) e Game Boy / GB Studio
* **Resolução Base:** **1600 × 900 pixels** (Widescreen 16:9 de Alta Definição) | Adaptação Retro: 160 × 144 pixels (GB Studio)
* **Público-Alvo:** Fãs de jogos retrô, arcade clássico e entusiastas de automobilismo nostálgico dos anos 80.

### Proposta de Valor
Recriar a essência viciante, tensa e atmosférica de *Enduro*, trazendo gráficos em pixel art vibrante e widescreen, preservando a identidade clássica de uma maratona contínua em estrada aberta através de quatro condições ambientais mutáveis.

---

## 2. Premissa e Objetivos

Diferente dos jogos de corrida de volta fechada, em *Enduro: National Rally* o jogador disputa uma maratona contínua por rodovias nacionais.

### Objetivo Principal
Ultrapassar no mínimo **200 carros adversários** ao longo de quatro etapas sucessivas antes que o tempo limite expire.

### Condições de Vitória e Derrota
* **Vitória:** Atingir a cota de 200 ultrapassagens antes do encerramento da Etapa 4, alcançando a [[Telas do Jogo#2-tela-de-vitória-consagração-e-pódio|Tela de Vitória]].
* **Derrota:** Deixar o cronômetro zerar antes de completar a cota de ultrapassagens em qualquer uma das quatro fases, ou danificar o veículo irreversivelmente por colisões sucessivas, acionando a [[Telas do Jogo#3-tela-de-derrota-tempo-esgotado|Tela de Derrota]].

---

## 3. As Quatro Etapas da Competição

A corrida não possui telas de carregamento intermediárias: o cenário e a iluminação se transformam continuamente durante o rali.

| Etapa | Cenário | Iluminação e Clima | Comportamento Especial | Referência |
| :---: | :--- | :--- | :--- | :---: |
| **1** | **Amanhecer Limpo** | Sol nascente, vales verdes e céu azul | Visibilidade total; fase de aprendizado e velocidade máxima | [[Cenas do Jogo#1-etapa-1-amanhecer-limpo]] |
| **2** | **Crepúsculo** | Pôr do sol roxo, magenta e laranja | Sombras compridas; contraste reduzido entre carros e pista | [[Cenas do Jogo#2-etapa-2-crepúsculo]] |
| **3** | **Neblina Implacável** | Névoa espessa em escala de cinzas | Visibilidade nula à distância; carros visíveis apenas pelas lanternas | [[Cenas do Jogo#3-etapa-3-neblina-implacável]] |
| **4** | **Pista de Gelo Noturna** | Meia-noite estrelada, montanhas de neve | **Aderência reduzida**; inércia lateral e derrapagens nas curvas | [[Cenas do Jogo#4-etapa-4-pista-de-gelo-noturna]] |

---

## 4. Mecânicas de Jogabilidade e Controles

### O Traçado de 3 Faixas
A pista possui 3 faixas de rodagem em perspectiva cônica (Esquerda, Centro e Direita). O jogador deve alternar rapidamente entre elas para encontrar brechas entre os veículos mais lentos.

### Tabela de Mapeamento de Comandos
| Ação | Teclado Principal | Alternativa | Função no Jogo |
| :--- | :---: | :---: | :--- |
| **Mover para Esquerda** | `←` | `A` | Desloca o carro para a faixa à esquerda |
| **Mover para Direita** | `→` | `D` | Desloca o carro para a faixa à direita |
| **Acelerar** | `↑` | `W` | Eleva a velocidade até 220 km/h; rivais aproximam-se mais rápido |
| **Frear** | `↓` | `S` | Reduz a velocidade para evitar batidas iminentes |
| **Alternar Faróis** | `L` | `F` | Melhora a leitura da pista nas etapas escuras |
| **Iniciar / Confirmar** | `Enter` | `Espaço` | Confirma menus e avança nas telas |
| **Voltar / Pausa** | `Esc` | `P` | Pausa a partida ou retorna ao menu |

Para a descrição aprofundada dos cálculos de aceleração e inércia de gelo, consulte [[Mecânicas e Controles]].

---

## 5. Interface do Usuário (UI / HUD)

A experiência é composta por:
1. **[[Telas do Jogo#1-tela-inicial-menu-principal|Tela Inicial]]:** Abertura retrô com logotipo em relevo e carro da equipe em exibição.
2. **[[Telas do Jogo#4-hud-head-up-display-durante-a-corrida|HUD Durante a Corrida]]:** Painel inferior fixo de instrumentos contendo Velocidade (km/h), Cota de Ultrapassagens, Tempo Restante e Nome da Etapa.
3. **[[Telas do Jogo#2-tela-de-vitória-consagração-e-pódio|Tela de Vitória]]:** Pódio com troféu dourado, torcida, confetes e relatório final da corrida.
4. **[[Telas do Jogo#3-tela-de-derrota-tempo-esgotado|Tela de Derrota]]:** Carro parado no acostamento, piloto desolado e opções de nova tentativa.

---

## 6. Direção de Arte e Áudio

### Arte Visual
* Estética baseada no pixel art arcade dos anos 80.
* Paletas de cores fiéis ao Atari 2600 e adaptadas com alto contraste para monitores modernos.
* Dimensões widescreen de 1600 × 900 pixels preservando a nitidez de pixel scaling 1:1.
* Catálogo completo de sprites disponível em [[Arte e Sprites]].

### Paisagem Sonora (Áudio)
* **Motor:** Ronco contínuo sintetizado que sobe de tom com a rotação por minuto (RPM).
* **Vento e Ultrapassagem:** Efeito de rajada em estéreo quando um adversário é superado.
* **Colisão:** Som metálico abafado acompanhado de queda brusca de RPM.
* **Pista de Gelo:** Ruído característico de atrito e pneus cantando na neve.
* **Vitória:** Fanfarra triunfal em chiptune com aplausos da torcida.

---

## 7. Sumário de Documentos do Cofre

- **Narrativa e Ambientação:** [[História do Jogo]]
- **Cenas de Corrida:** [[Cenas do Jogo]]
- **Telas do Jogo:** [[Telas do Jogo]]
- **Física e Dinâmica de Corrida:** [[Mecânicas e Controles]]
- **Sprites e Cores:** [[Arte e Sprites]]
- **Página Inicial:** [[Inicio]]
