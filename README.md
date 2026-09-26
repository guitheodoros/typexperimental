# Type FX

Ferramenta client-side (WebGL2, vanilla JS, arquivo único) de tipografia experimental — blur, halftone e hachura sobre o texto. Tudo roda no navegador; nada é enviado para fora.

## Modos

- **Blur / Grão** — borrão com granulado/dither, tipo spray atmosférico.
- **Halftone** — pontos paramétricos (tamanho mín./máx., raio do canto de quadrado a círculo, ângulo, ruído) em grade Regular, Benday ou Hex, com:
  - desenho do ponto: proporção 1:1 ou largura/altura aleatória, sobreposição geral e por eixo;
  - fusão de área forte (2×2 a 4×4) para regiões sólidas;
  - meios-tons: até 6 faixas de tom, cada uma com cor e forma própria (redondo, cruz, anel, losango, estrela), rampa automática fundo → tinta, modo de mesclagem e troca aleatória de tom.
- **Crosshatch** — hachura cruzada em camadas conforme o tom.

## Painéis globais

- **Texto** e **Fonte** — família (lista de fontes do sistema ou upload TTF/OTF/WOFF/WOFF2), tamanho, entrelinha, largura/altura do texto, kerning e blur prévio.
- **Tinta** — cor da tinta.
- **Fundo** — liso, degradê (ângulo + 4 cores com posição) ou imagem carregada.
- **Ajustes** — limiar (engorda/afina a tinta), inverter, brilho, contraste e gama.
- **Formato** — proporção (3:4, 2:3, quadrado, 4:3) e zoom.
- **Exportar** — PNG em até ~4200px no lado maior.

## Como usar

Abra `index.html` no navegador — não precisa de build. Para servir localmente:

```bash
python3 -m http.server 5178
```

## Estrutura

- `index.html` — tudo em um arquivo: HTML, CSS e JS/GLSL.
