# Typexperimental

Ferramenta client-side (WebGL2, vanilla JS, arquivo único) de tipografia experimental — blur, halftone e hachura sobre o texto. Processamento 100% local no navegador: nenhuma imagem é enviada a servidor.

**Site:** https://guitheodoros.github.io/typexperimental/

## Modos

- **Blur / Grão** — borrão com granulado/dither, tipo spray atmosférico.
- **Halftone** — pontos paramétricos (tamanho mín./máx., raio do canto de quadrado a círculo, ângulo, ruído) em grade Regular, Benday ou Hex, com:
  - desenho do ponto: proporção 1:1 ou largura/altura aleatória, sobreposição geral e por eixo;
  - fusão de área forte (2×2 a 4×4) para regiões sólidas;
  - meios-tons: até 6 faixas de tom, cada uma com cor e forma própria (redondo, cruz, anel, losango, estrela), rampa automática fundo → tinta, modo de mesclagem e troca aleatória de tom.
- **Crosshatch** — hachura cruzada em camadas conforme o tom.

## Painéis

- **Texto** — começa vazio; alinhamento à esquerda, centro ou direita.
- **Fonte** — família (34 fontes do Google Fonts em sans, condensada, serif, mono, display, pixel e manuscrita, baixadas só quando escolhidas; fontes do sistema; ou upload TTF/OTF/WOFF/WOFF2), tamanho, entrelinha, largura/altura do texto, kerning e blur prévio.
- **Tinta** — cor da tinta.
- **Fundo** — liso, degradê (ângulo + 4 cores com posição), imagem ou transparente. Em **Imagem**, uma grade com texturas de papel prontas (branco dobrado, kraft e granulado) e o botão **+** para carregar a sua. As texturas giram sozinhas nos formatos paisagem para a folha caber inteira, e podem ser **tingidas** com qualquer cor (multiplicação: o papel branco vira papel colorido mantendo dobras e grão).
- **Ajustes** — limiar (engorda/afina a tinta), inverter, brilho, contraste e gama.
- **Formato** — proporção e zoom. Retrato: 3:4, 4:5, 2:3, A4, 9:16, 1:2 · Quadrado: 1:1 · Paisagem: 5:4, 4:3, 3:2, A4, 16:9, 2:1.
- **Exportar** — PNG em preview (1400px), 2K ou 4K no lado maior, com opção de fundo transparente; o nome do arquivo leva tamanho, data e hora. A escala dos pontos, da hachura e do grão acompanha a resolução, então o PNG fica igual ao preview.

## Interface

- **Painéis recolhíveis** — abrem e fecham como um acordeão (abrir um fecha o anterior); Modo e Exportar ficam sempre visíveis. Dá para clicar em qualquer ponto da faixa do título.
- **Tema claro/escuro** — botão de lua/sol no topo. Abre no escuro por padrão e lembra a escolha.
- **Seletor de cor** — próprio e igual em qualquer navegador: quadrado de saturação/brilho, matiz, código hex editável (aceita `#abc`, `abc` ou `#aabbcc`) e uma fileira com as cores usadas na arte e as últimas escolhidas.
- **Controles** — checkboxes animados, botões com relevo e spinner na exportação e no carregamento de fontes, inspirados no [Spell UI](https://spell.sh/) e recriados em CSS puro.
- **Celular** — preview fixo no topo enquanto os painéis rolam por baixo, uma coluna só e alvos de toque de ~40–44px (o visual com mouse não muda).

## Como usar

Abra `index.html` no navegador — não precisa de build. Para servir localmente:

```bash
python3 -m http.server 5178
```

Precisa de um navegador com WebGL2 (Chrome, Safari, Firefox ou Edge atuais). As fontes do Google só são baixadas quando escolhidas; sem internet, a ferramenta usa as fontes do sistema.

## Estrutura

- `index.html` — a ferramenta inteira: HTML, CSS e JS/GLSL.
- `texturas/web/` — as texturas de fundo em três tamanhos: `-200` (miniatura da grade), `-1400` (preview) e `-4096` (export 2K/4K). Cada tamanho só é baixado quando é usado.
