# Typexperimental

Ferramenta client-side (WebGL2, vanilla JS, arquivo único) de tipografia experimental — blur, halftone e hachura sobre o texto. Tudo roda no navegador; nada é enviado para fora.

## Modos

- **Blur / Grão** — borrão com granulado/dither, tipo spray atmosférico.
- **Halftone** — pontos paramétricos (tamanho mín./máx., raio do canto de quadrado a círculo, ângulo, ruído) em grade Regular, Benday ou Hex, com:
  - desenho do ponto: proporção 1:1 ou largura/altura aleatória, sobreposição geral e por eixo;
  - fusão de área forte (2×2 a 4×4) para regiões sólidas;
  - meios-tons: até 6 faixas de tom, cada uma com cor e forma própria (redondo, cruz, anel, losango, estrela), rampa automática fundo → tinta, modo de mesclagem e troca aleatória de tom.
- **Crosshatch** — hachura cruzada em camadas conforme o tom.

## Painéis globais

Os painéis abrem e fecham como um acordeão (abrir um fecha o anterior); Modo e Exportar ficam sempre visíveis. O botão de lua/sol no topo alterna entre o tema claro e o escuro — abre no escuro por padrão e depois lembra a escolha.

- **Texto** — alinhamento à esquerda, centro ou direita.
- **Fonte** — família (34 fontes do Google Fonts em sans, condensada, serif, mono, display, pixel e manuscrita, baixadas só quando escolhidas; fontes do sistema; ou upload TTF/OTF/WOFF/WOFF2), tamanho, entrelinha, largura/altura do texto, kerning e blur prévio.
- **Tinta** — cor da tinta.
- **Fundo** — liso, degradê (ângulo + 4 cores com posição), imagem carregada ou transparente.
- **Ajustes** — limiar (engorda/afina a tinta), inverter, brilho, contraste e gama.
- **Formato** — proporção e zoom. Retrato: 3:4, 4:5, 2:3, A4, 9:16, 1:2 · Quadrado: 1:1 · Paisagem: 5:4, 4:3, 3:2, A4, 16:9, 2:1.
- **Exportar** — PNG em preview (1400px), 2K ou 4K no lado maior, com opção de fundo transparente; o nome do arquivo leva tamanho, data e hora.

## Como usar

Abra `index.html` no navegador — não precisa de build. Para servir localmente:

```bash
python3 -m http.server 5178
```

## Estrutura

- `index.html` — tudo em um arquivo: HTML, CSS e JS/GLSL.
