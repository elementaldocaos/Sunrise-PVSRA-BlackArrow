# Guia Operacional — Como Ler o Gráfico e Tomar Decisões com PVSRA + Auction Market

> ⚠️ **Aviso Legal / Disclaimer**
> Este guia tem caráter **exclusivamente educacional e informativo**. Nenhuma explicação aqui constitui recomendação de compra/venda, sinal de operação ou consultoria financeira. Operações em mercados financeiros (Ouro/XAUUSD, Forex, Índices, Futuros e Criptomoedas) envolvem **alto risco de perda financeira**. Sempre teste em conta **simulada/demo** antes de operar capital real e respeite seu próprio gerenciamento de risco.

---

## 1. A Lógica por Trás do Setup (O Que Você Está Olhando)

O setup combina **três camadas de leitura** em um único gráfico:

1. **Tendência e Fluxo (`PVSRA_Main`):** 🟨 `EMA 200`, ⬜ `EMA 100`, 🟦 `Dragon (EMA 34)` e 🟪 `VWMA 25` mostram *para onde* o mercado está indo e onde ficam os pullbacks saudáveis.
2. **Atividade Institucional (`PVSRA_Coloracao` + `PVSRA_Volumes`):** mostra *quando* entrou volume acima do normal (🟩 🟥 **Clímax** e 🟦 🟪 **Rising**).
3. **Estrutura de Leilão e Volatilidade (`Sunrise_Price_Auction` + `Volume Profile` + `Force Numbers`):** mostra *onde* o mercado tende a travar, reverter ou acelerar (🟥 `VAH`, 🟩 `VAL`, 🟨 `POC`, nós de volume e `ATR(14)`).

> **Regra de ouro:** nenhum indicador sozinho manda comprar ou vender. A decisão nasce da **confluência** entre **Contexto (Médias) + Localização (VAH/VAL/POC/Níveis) + Gatilho de Volume (PVSRA) + Risco (`ATR`)**.

---

## 2. Entendendo Cada Elemento do Gráfico

### A. Candles e Volume PVSRA (`PVSRA_Coloracao` + `PVSRA_Volumes`)
Compara o volume do candle atual com a média dos **10 candles anteriores**:

* 🟩 **Verde / 🟥 Vermelho (Clímax):** Volume ≥ `200%` da média **ou** maior produto `Volume × Amplitude` dos últimos 10 candles.
  * **Quando aparece no início de um rompimento** (saindo de consolidação ou rompendo VAH/VAL/Dragon): indica **força/iniciativa** a favor do movimento.
  * **Quando aparece após um movimento longo/esticado**, batendo em resistência/suporte, 🟥 VAH, 🟩 VAL, 🟨 EMA 200 ou número redondo (`000/500`) e deixando **pavio**: indica possível **absorção, exaustão ou captura de liquidez (stop hunt)** — atenção para reversão!
* 🟦 **Azul / 🟪 Violeta (Rising — Volume em Ascensão):** Volume ≥ `150%` da média. Mostra aumento de interesse institucional ganhando tração.
* ⬜ **Cinza claro / ⬛ Cinza escuro (Normal):** Fluxo comum. Evite apostar em rompimentos importantes com candles cinzas sem volume.

---

### B. Médias de Tendência (`PVSRA_Main`)
* 🟨 **EMA 200 (Amarela tracejada grossa) — Viés Macro:**
  * Preço acima da EMA 200 → prioridade para **compras**.
  * Preço abaixo da EMA 200 → prioridade para **vendas**.
  * Também funciona como forte suporte/resistência dinâmica quando o preço volta até ela.
* ⬜ **EMA 100 (Branca tracejada) — Tendência Intermediária:**
  * Ajuda a filtrar pullbacks mais profundos e a ver quando a tendência está perdendo força (preço cruzando entre EMA 100 e 200).
* 🟦 **Dragon (`EMA 34` High / Low / Close) — Zona de Pullback:**
  * É a "coluna vertebral" do PVSRA. Em tendência forte, o preço tende a recuar até o canal do Dragon e voltar a andar na direção da tendência.
  * Dragon inclinado e separado das EMAs 100/200 = tendência saudável. Dragon horizontal e entrelaçado nas outras médias = **mercado lateral** (não opere tendência).
* 🟪 **VWMA 25 (Magenta contínua) — Média Ponderada por Volume:**
  * Reage mais rápido onde houve volume real. Quando a 🟪 VWMA 25 cruza o 🟦 Dragon na direção da 🟨 EMA 200, confirma alinhamento de fluxo de curto prazo.

---

### C. Áreas de Valor e Leilão (`Sunrise_Price_Auction` + `Volume Profile`)
* **Área de Valor (entre 🟩 `VAL` e 🟥 `VAH`):** faixa onde ocorreu **70%** do volume recente no Timeframe atual ("preço justo").
* 🟨 **`POC` (Point of Control):** preço de maior negociação. Em dias laterais funciona como **ímã**; em tendência, quando rompida com volume, vira suporte/resistência.
* **Volume Profile lateral:**
  * **HVN (barras longas / picos de volume):** zonas de aceitação — o preço costuma brigar e travar ali.
  * **LVN (vales / "buracos" com pouca barra):** zonas de rejeição — o preço costuma atravessar rápido até o próximo pico de volume.
* **Como usar VAH / VAL:**
  * *Em consolidação:* buscar rejeição (Clímax + pavio) na 🟥 **VAH** visando 🟨 **POC** / 🟩 **VAL**, ou na 🟩 **VAL** visando 🟨 **POC** / 🟥 **VAH**.
  * *Em tendência:* rompimento com volume (🟦/🟩 na alta ou 🟪/🟥 na baixa) para fora da VAH/VAL, seguido de pullback que segura nela + Dragon, sinaliza continuação.

---

### D. Níveis Psicológicos (`PVSRA_Force_Numbers`) & `ADR 14d`
* **Force Numbers (`000 / 250 / 500 / 750`):** níveis inteiros e quartos onde se concentram muitas ordens limite e stops. Muito comum o mercado dar um "tiro" rápido com candle de Clímax logo além de um `000` ou `500` para capturar liquidez antes de virar.
* **ADR (Average Daily Range):** mostra o quanto o ativo costuma andar no dia. Se o preço já andou perto de `100%` do ADR diário, evite entrar atrasado na ponta esticada.

---

### E. Como Usar o `ATR(14)` (`Sunrise_Price_Auction`)
O `ATR(14)` exibido no candle atual mostra a **amplitude média por candle** no Timeframe em que você está olhando (ex.: se no `GOLD 5Min` aparece `ATR(14): 7,54`, cada candle de 5 minutos oscila em média ~7,54 dólares).

Uso prático em **3 decisões**:
1. **Tamanho do Stop Loss (anti-violinada):**
   * Nunca coloque um stop menor que o ruído normal do gráfico.
   * Referência educativa comum: posicione o stop **atrás da estrutura** (atrás do Dragon, topo/fundo do candle de gatilho ou VAH/VAL) garantindo uma folga mínima de **`1,0×` a `1,5× ATR`**.
   * *Exemplo:* se `ATR(14) = 7,54`, um stop de `2` ou `3` pontos provavelmente será pego pelo ruído normal; um stop técnico de `8` a `11` pontos respeita a volatilidade do momento.
2. **Tamanho da Posição (Gestão de Risco):**
   * Volatilidade alta (`ATR` alto) → **reduza o lote** para manter o mesmo risco financeiro em dólares/reais.
   * Volatilidade baixa (`ATR` baixo) → mercado lento/travado; evite esperar movimentos longos antes de expansão.
3. **Filtro de Risco-Retorno (Alvo vs Stop):**
   * Só entre se a distância livre até a próxima barreira importante (🟨 EMA 200, 🟥 VAH, 🟩 VAL, 🟨 POC ou HVN) for pelo menos **`1,5×` a `2×` maior** que o seu stop em ATR.

---

## 3. Checklist Rápido Antes de Clicar (4 Passos)

1. **Tendência (Médias):** O preço está acima ou abaixo da 🟨 `EMA 200` e ⬜ `EMA 100`? O 🟦 `Dragon` e a 🟪 `VWMA 25` estão inclinados ou embolados (lateral)?
2. **Região (Estrutura):** O preço está em uma zona relevante (pullback no 🟦 Dragon/🟪 VWMA 25, 🟥 VAH, 🟩 VAL, 🟨 POC ou nível `000/500`)? Não está esticado demais no ADR?
3. **Gatilho (PVSRA):** Apareceu volume relevante (**Clímax** 🟩/🟥 ou **Rising** 🟦/🟪) confirmando **força no rompimento** ou **rejeição/absorção com pavio** na região?
4. **Risco (`ATR`):** O stop técnico (`~1x a 1,5x ATR`) cabe no seu limite de perda por trade e há espaço livre até o próximo alvo para compensar o risco?

---

## 4. Erros Mais Comuns de Iniciantes

* **Comprar só porque o candle ficou verde (ou vender só porque ficou vermelho):** cor de Clímax mostra *esforço/volume*, não direção garantida. Candle verde gigante no topo de uma resistência depois de esticar muito costuma ser **exaustão/armadilha**, não compra!
* **Operar no meio do nada:** entrar longe do Dragon, longe da VWMA 25 e no meio da Área de Valor sem motivo estrutural.
* **Ignorar o `ATR`:** usar o mesmo tamanho de stop fixo em mercado calmo e em horário de notícia/abertura de sessão.
* **Trocar de timeframe sem ajustar leitura:** o `Sunrise_Price_Auction` (`VAH/VAL/ATR`) recalcula automaticamente para o TF aberto — use o TF maior (`H1`/`M15`) para contexto e o menor (`M5`/`M1`) apenas para refinar a entrada na mesma direção.
