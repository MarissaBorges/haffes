<!-- BADGES -->

[HTML_BADGE]: https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white
[CSS_BADGE]: https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white
[JS_BADGE]: https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black
[GSAP_BADGE]: https://img.shields.io/badge/GSAP-88CE02?style=for-the-badge&logo=greensock&logoColor=black
[WIP_BADGE]: https://img.shields.io/badge/Status-Em%20Desenvolvimento-blue?style=for-the-badge

<!-- PROJECT -->
<h1 align="center" style="font-weight: bold;">Haffe’s Design System 🔥 (Em Desenvolvimento)</h1>

<p align="center">
  <img src="https://img.shields.io/badge/Status-Em%20Desenvolvimento-blue?style=for-the-badge" alt="Status Em Desenvolvimento">
  <img src="https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white" alt="HTML5 Badge">
  <img src="https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white" alt="CSS3 Badge">
  <img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black" alt="JavaScript Badge">
  <img src="https://img.shields.io/badge/GSAP-88CE02?style=for-the-badge&logo=greensock&logoColor=black" alt="GSAP Badge">
</p>

<p align="center">
  <a href="#-descrição">Descrição</a> •
  <a href="#-funcionalidades">Funcionalidades</a> •
  <a href="#-destaques-técnicos">Destaques</a> •
  <a href="#-como-executar">Como Executar</a> •
  <a href="#-documentação">Documentação</a> •
  <a href="#-roadmap-futuro">Roadmap Futuro</a>
</p>

---

## 📌 Descrição

O **Haffe’s Design System — Matéria, Fogo e Movimento** é uma biblioteca viva de identidade visual, tokens, componentes de interface e sistema de motion criada para experiências gastronômicas digitais.

O projeto consolida e combina referências estruturais, cromáticas e cinéticas de múltiplos design systems de estudo (`kveld-design-system`, `bulls-design-system`, `lando-norris-design-system`, `pringles-design-system` e `follow-design-system`) em um sistema autoral localizado em `assets/design_system.html` e `assets/design-system/`, além da base original em `haffes-design-system/`.

---

## 🚀 Funcionalidades

### Biblioteca Viva de Design System (`assets/design_system.html`)

- **Hero Editorial Interativa:** Primeira dobra de alto impacto com tipografia gigante em `Bebas Neue`, composições assimétricas, efeitos cinéticos e pré-carregamento otimizado de fontes e mídia.
- **Sistema Tipográfico Completo:** Escala fluida (`--display-xl`, `--display-lg`, `h1` a `h6`, `body-lg`, `body`, `body-sm`, `label`, `caption`) combinando `Bebas Neue`, `Archivo` e `IBM Plex Mono`.
- **Sistema de Cores Semântico:** Tokens estruturados em `tokens.css` e `tokens.json` (`--primary`, `--dark`, `--light`, `--bone`, `--surface`, `--accent` e estados `success`, `warning`, `error`, `info`, `disabled`).
- **Catálogo de Componentes UI:** Especificações e demonstrações interativas de botões, inputs, cards, navegação, modais, badges, tooltips e ícones (`icons.json`).
- **Sistema de Motion e Acessibilidade:** Animações orquestradas com **GSAP**, **ScrollTrigger** e rolagem suave com **Lenis**, incluindo alternância manual de redução de movimento (`#motion-toggle`) e respeito automático a `prefers-reduced-motion`.

### Catálogo de Referências

- Diretórios isolados com os design systems usados como referência estrutural, cromática e de microinterações (`kveld-design-system/`, `bulls-design-system/`, `lando-norris-design-system/`, `pringles-design-system/`, `follow-design-system/` e `haffes-design-system/`).

---

## 🔒 Destaques Técnicos

- **Fonte Única de Verdade para Tokens:** Os valores de cor, tipografia, espaçamento, sombras e durações de animação definidos em `assets/design-system/tokens.css` e `tokens.json` alimentam dinamicamente o módulo de motion (`motion-config.js`) via `getComputedStyle`.
- **Zero Dependências de Build ou CDN Obrigatória:** As bibliotecas `gsap.min.js`, `ScrollTrigger.min.js` e `lenis.min.js` estão versionadas localmente em `assets/design-system/vendor/`, permitindo execução totalmente offline.
- **Acessibilidade em Movimento:** O controlador `window.HaffesDS` monitora `prefers-reduced-motion` do sistema operacional, persiste a escolha do usuário em `localStorage` (`haffes-reduced-motion`) e dispara eventos customizados (`haffes:motion`) para sincronizar todos os módulos.
- **Carregamento Otimizado:** Uso de `preload` para fontes `.woff2` e mídia principal da hero (`fetchpriority="high"`), além de scripts com atributo `defer`.

---

## 📍 Como Executar

Por ser um projeto estático em HTML, CSS e JavaScript puro com bibliotecas locais, não exige etapa de compilação.

### Pré-requisitos

- Navegador moderno (Chrome, Firefox, Zen, Edge ou Safari)
- [Python 3](https://www.python.org/downloads/) (opcional, recomendado para servir via HTTP local)
- [Git](https://git-scm.com/)

### Clonando o Repositório

```bash
# Clone o projeto para a sua máquina local
git clone https://github.com/MarissaBorges/haffes.git

# Entre no diretório do projeto
cd haffes
```

### Iniciando o Projeto

Recomenda-se servir a raiz do repositório via servidor HTTP local para garantir o carregamento correto de fontes, JSONs (`tokens.json`, `icons.json`) e caminhos relativos:

```bash
# Inicie um servidor HTTP local na porta 8080
python3 -m http.server 8080
```

Depois, abra no navegador:

- **Design System Principal:** `http://localhost:8080/assets/design_system.html`
- **Versão Base Haffe’s:** `http://localhost:8080/haffes-design-system/design-system.html`

---

## 📚 Documentação

- [Arquitetura e Estrutura do Design System](docs/ARCHITECTURE.md)
- [Diretrizes Criativas Originais (`prompt.md`)](prompt.md)
- [Tokens Estruturados (`tokens.json`)](assets/design-system/tokens.json)

---

## 🗺️ Roadmap Futuro

- [ ] Expandir documentação interativa de estados de erro, foco e acessibilidade (WCAG AA/AAA) dos componentes.
- [ ] Adicionar testes automatizados de regressão visual e contraste para os componentes principais.
- [ ] Empacotar os tokens (`tokens.css` e `tokens.json`) para reutilização direta em aplicações web de produção da marca.
- [ ] Consolidar páginas de exemplo (landing page e cardápio interativo) consumindo exclusivamente o design system.

---

## 🤝 Colaboradores

<table>
  <tr>
    <td align="center">
      <a href="https://github.com/MarissaBorges">
        <img src="https://github.com/MarissaBorges.png?size=100" width="100px;" alt="Foto de Marissa Borges"/><br>
        <sub>
          <b>Marissa Borges</b>
        </sub>
      </a>
    </td>
  </tr>
</table>

---

## 📫 Como Contribuir

Contribuições são muito bem-vindas!

1. Faça um **Fork** do projeto.
2. Crie uma nova branch para sua Feature (`git checkout -b feature/AmazingFeature`).
3. Faça o **Commit** de suas mudanças (`git commit -m 'Add some AmazingFeature'`).
4. Faça o **Push** da sua branch (`git push origin feature/AmazingFeature`).
5. Abra um **Pull Request**.
