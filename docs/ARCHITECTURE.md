# Arquitetura — Haffe’s Design System

Este documento descreve a organização de arquivos, módulos de estilo/motion e referências que compõem o **Haffe’s Design System — Matéria, Fogo e Movimento**.

---

## Estrutura de Diretórios

```text
haffes/
├── assets/
│   ├── design_system.html          # Página principal da biblioteca viva do Design System
│   └── design-system/
│       ├── tokens.css              # Fonte única de verdade em CSS Custom Properties
│       ├── tokens.json             # Espelho estruturado de tokens (cores, tipografia, escala, motion)
│       ├── styles.css              # Estilos dos componentes, layout editorial e estados
│       ├── icons.json              # Catálogo de ícones utilizados no sistema
│       ├── motion-config.js        # Controlador global `window.HaffesDS` e acessibilidade de motion
│       ├── motion.js               # Coreografias GSAP, ScrollTrigger e integração Lenis
│       ├── interactions.js         # Interações de UI (toasts, modais, tabs, tooltips e cópia de tokens)
│       ├── optional-media.js       # Carregamento sob demanda de mídia animada local (ex.: Rive)
│       ├── fonts/                  # Fontes locais `.woff2` (Bebas Neue, Archivo, IBM Plex Mono)
│       ├── media/                  # Imagens e ativos visuais locais otimizados (`.webp`)
│       └── vendor/                 # Dependências locais (`gsap.min.js`, `ScrollTrigger.min.js`, `lenis.min.js`)
├── haffes-design-system/           # Versão anterior/base do Design System Haffe's
├── kveld-design-system/            # Referência estrutural prioritária
├── bulls-design-system/            # Referência de paleta de cores e ícones
├── lando-norris-design-system/     # Referência de animações, motion e componentes
├── pringles-design-system/         # Referência de transições e microinterações
├── follow-design-system/           # Referência de ritmo visual e catálogo
└── prompt.md                       # Diretrizes criativas e especificações originais
```

---

## Camada de Tokens

Todos os fundamentos visuais ficam centralizados em `assets/design-system/tokens.css` e espelhados em `assets/design-system/tokens.json`:

- **Cores:** paleta principal (`--primary: #b72c39`, `--dark: #191a1c`, `--light: #f5f2ec`, `--bone: #e9e4db`, `--surface: #fcfaf6`), destaque (`--accent: #295bc5`) e estados semânticos (`--success`, `--warning`, `--error`, `--info`, `--disabled`).
- **Tipografia:** `--display` (`Bebas Neue`), `--sans` (`Archivo`) e `--mono` (`IBM Plex Mono`), com escala fluida via `clamp()`.
- **Espaçamento, Bordas e Elevação:** escala `--space-1` a `--space-24`, container máximo de `1600px`, raios `--radius-sm` a `--radius-pill` e sombras `--shadow-low`, `--shadow-high` e `--shadow-float`.
- **Motion:** durações (`--duration-instant` a `--duration-long`), curvas cúbicas (`--ease-standard`, `--ease-in`, `--ease-out`, `--ease-expressive`), `--reveal-distance`, `--stagger` e `--parallax`.

---

## Pipeline de Scripts (Ordem de Carregamento)

Os scripts em `assets/design_system.html` usam `defer` para manter a ordem determinística sem bloquear a renderização inicial:

1. `vendor/gsap.min.js`, `vendor/ScrollTrigger.min.js`, `vendor/lenis.min.js` — motores de animação e rolagem suave.
2. `motion-config.js` — inicializa `window.HaffesDS`, lê durações e distâncias diretamente dos tokens CSS, monitora `prefers-reduced-motion` e controla o botão `#motion-toggle` com persistência em `localStorage`.
3. `motion.js` — registra `ScrollTrigger` e aplica animações de entrada, parallax e rolagem suave respeitando `window.HaffesDS.reduced`.
4. `interactions.js` — ativa a classe `.js-ready` e gerencia interações dos componentes da página.
5. `optional-media.js` — carrega mídia interativa opcional sob demanda, mantendo todos os ativos locais.
