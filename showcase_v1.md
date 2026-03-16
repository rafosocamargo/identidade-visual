# BOLD IMPACT — Design System

> Inspirado na identidade visual Manychat: tipografia pesada, alto contraste, brutalismo editorial.

---

## 1. Filosofia de Design

| Principio | Regra |
|-----------|-------|
| **Tipografia e heroi** | O texto E a interface. Nao e decoracao — e estrutura. |
| **Contraste absoluto** | Preto no branco. Sem cinzas medios. Sem gradientes. |
| **Whitespace generoso** | O espaco vazio amplifica o impacto da tipografia. |
| **Imperfeicao intencional** | Letras cortadas, overlaps, masking — o "erro" e o estilo. |
| **Sem distracao** | Zero ornamentos. Zero sombras suaves. Zero bordas arredondadas. |
| **Impacto primeiro** | Cada tela deve ter UMA declaracao impossivel de ignorar. |

---

## 2. Paleta de Cores

### Core (Obrigatorio)

| Token | Hex | Uso |
|-------|-----|-----|
| `--color-primary` | `#000000` | Texto principal, CTAs, elementos de destaque |
| `--color-background` | `#FFFFFF` | Fundo principal |
| `--color-foreground` | `#000000` | Texto sobre fundo branco |
| `--color-on-primary` | `#FFFFFF` | Texto sobre elementos pretos |

### Neutros (Suporte minimo)

| Token | Hex | Uso |
|-------|-----|-----|
| `--color-muted` | `#F5F5F5` | Fundo de secoes alternadas |
| `--color-muted-fg` | `#737373` | Texto secundario (subtitulos) |
| `--color-border` | `#000000` | Bordas visiveis (quando usadas) |
| `--color-border-subtle` | `#E5E5E5` | Separadores leves |

### Acento (Opcional — uso cirurgico)

| Token | Hex | Uso |
|-------|-----|-----|
| `--color-accent` | `#FF0000` | Alerta, destaque pontual, badge de urgencia |
| `--color-on-accent` | `#FFFFFF` | Texto sobre acento vermelho |

### Regras de Cor

- **Padrao**: Preto + Branco. Ponto.
- **Acento vermelho**: maximo 5% da area visual. Reservado para CTAs criticos ou dados de impacto.
- **Cinza**: apenas `--color-muted-fg` para texto secundario. Nunca para elementos estruturais.
- **Proibido**: gradientes, sombras coloridas, backgrounds coloridos, opacidades intermediarias.

```css
:root {
  --color-primary: #000000;
  --color-background: #FFFFFF;
  --color-foreground: #000000;
  --color-on-primary: #FFFFFF;
  --color-muted: #F5F5F5;
  --color-muted-fg: #737373;
  --color-border: #000000;
  --color-border-subtle: #E5E5E5;
  --color-accent: #FF0000;
  --color-on-accent: #FFFFFF;
  --color-destructive: #FF0000;
}
```

---

## 3. Tipografia

### Font Stack

| Papel | Fonte | Peso | Fallback |
|-------|-------|------|----------|
| **Display / Hero** | **Archivo Black** | 400 (ja e black) | `Impact, Arial Black, sans-serif` |
| **Headings** | **Barlow Condensed** | 700–900 | `Arial Narrow, sans-serif` |
| **Body** | **Inter** | 400–600 | `system-ui, sans-serif` |
| **Labels / Data** | **Inter** | 700 | `system-ui, sans-serif` |
| **Mono / Stats** | **JetBrains Mono** | 400–700 | `monospace` |

### Google Fonts Import

```css
@import url('https://fonts.googleapis.com/css2?family=Archivo+Black&family=Barlow+Condensed:wght@700;800;900&family=Inter:wght@400;500;600;700;800&family=JetBrains+Mono:wght@400;700&display=swap');
```

### Escala Tipografica

| Token | Size | Weight | Line Height | Letter Spacing | Transform | Uso |
|-------|------|--------|-------------|----------------|-----------|-----|
| `--text-hero` | 80px / 5rem | Black | 0.85 | -3px | uppercase | Numero/frase de impacto |
| `--text-display` | 56px / 3.5rem | Black | 0.9 | -2px | uppercase | Titulo principal da secao |
| `--text-h1` | 40px / 2.5rem | 800 | 0.95 | -1.5px | uppercase | Heading nivel 1 |
| `--text-h2` | 32px / 2rem | 700 | 1.0 | -1px | uppercase | Heading nivel 2 |
| `--text-h3` | 24px / 1.5rem | 700 | 1.1 | -0.5px | uppercase | Heading nivel 3 |
| `--text-body` | 18px / 1.125rem | 400 | 1.6 | 0 | none | Texto corrido |
| `--text-body-bold` | 18px / 1.125rem | 600 | 1.6 | 0 | none | Texto enfatizado |
| `--text-caption` | 14px / 0.875rem | 500 | 1.4 | 0.5px | none | Legendas, meta |
| `--text-label` | 12px / 0.75rem | 700 | 1.2 | 2px | uppercase | Labels, tags, badges |
| `--text-stat` | 96px / 6rem | Black | 0.8 | -4px | none | Numeros de destaque (KPIs) |

### Regras Tipograficas

1. **Tudo que e titulo: UPPERCASE.** Sem excecao.
2. **Letter-spacing negativo** em tudo acima de `--text-h3`. Isso cria a densidade visual.
3. **Line-height < 1.0** para display/hero. As linhas devem quase se tocar.
4. **Arquivo Black** so para hero e stats. Nao usar para body.
5. **Nunca usar peso Regular para headings.** Minimo 700.

```css
:root {
  --font-display: 'Archivo Black', Impact, 'Arial Black', sans-serif;
  --font-heading: 'Barlow Condensed', 'Arial Narrow', sans-serif;
  --font-body: 'Inter', system-ui, -apple-system, sans-serif;
  --font-mono: 'JetBrains Mono', 'Fira Code', monospace;
}
```

---

## 4. Espacamento

### Sistema 8px

| Token | Value | Uso |
|-------|-------|-----|
| `--space-1` | 4px | Micro gaps |
| `--space-2` | 8px | Inline spacing |
| `--space-3` | 16px | Padding interno componentes |
| `--space-4` | 24px | Gap entre elementos |
| `--space-5` | 32px | Separacao de grupos |
| `--space-6` | 48px | Separacao de secoes |
| `--space-7` | 64px | Padding de secao |
| `--space-8` | 96px | Hero padding |
| `--space-9` | 128px | Mega spacing (topo de pagina) |

### Regras de Espacamento

- **Whitespace e proposital.** Secoes hero devem ter no minimo `--space-8` de padding vertical.
- **Densidade dentro, respiro fora.** Texto hero com line-height apertado, mas cercado de whitespace generoso.
- **Assimetria permitida.** Padding top pode ser diferente de bottom para criar tensao visual.

```css
:root {
  --space-1: 0.25rem;
  --space-2: 0.5rem;
  --space-3: 1rem;
  --space-4: 1.5rem;
  --space-5: 2rem;
  --space-6: 3rem;
  --space-7: 4rem;
  --space-8: 6rem;
  --space-9: 8rem;
}
```

---

## 5. Layout

### Grid

| Propriedade | Valor |
|-------------|-------|
| Colunas (desktop) | 12 |
| Colunas (tablet) | 8 |
| Colunas (mobile) | 4 |
| Gutter | 24px |
| Max-width | 1200px |
| Margem lateral (mobile) | 20px |
| Margem lateral (desktop) | 80px |

### Breakpoints

| Token | Value | Alvo |
|-------|-------|------|
| `--bp-sm` | 375px | Mobile pequeno |
| `--bp-md` | 768px | Tablet |
| `--bp-lg` | 1024px | Desktop |
| `--bp-xl` | 1440px | Desktop largo |

### Principios de Layout

1. **Single column e o padrao.** Multi-coluna so quando necessario.
2. **Full-bleed para impacto.** Hero sections podem quebrar o container.
3. **Alinhamento a esquerda** para texto. Centrado so para CTAs e dados de impacto.
4. **Z-index scale**: 0 / 10 / 20 / 50 / 100 / 1000.

---

## 6. Componentes

### Botoes

| Variante | Background | Text | Border | Radius | Padding |
|----------|------------|------|--------|--------|---------|
| **Primary** | `#000000` | `#FFFFFF` | none | 0px | 16px 32px |
| **Secondary** | `#FFFFFF` | `#000000` | 2px solid #000 | 0px | 16px 32px |
| **Ghost** | transparent | `#000000` | none | 0px | 16px 32px |
| **Danger** | `#FF0000` | `#FFFFFF` | none | 0px | 16px 32px |

**Regras de botao:**
- Altura minima: 48px (touch target)
- Texto: uppercase, font-weight 700, letter-spacing 1px
- Hover: inversao de cores (preto→branco, branco→preto) — transicao 0ms (instantanea, brutalista)
- Focus: outline 2px solid #000, offset 2px
- Sem border-radius. Nunca. Zero.

```css
.btn-primary {
  background: var(--color-primary);
  color: var(--color-on-primary);
  border: none;
  border-radius: 0;
  padding: 16px 32px;
  font-family: var(--font-heading);
  font-weight: 700;
  font-size: 14px;
  letter-spacing: 2px;
  text-transform: uppercase;
  cursor: pointer;
  transition: none;
  min-height: 48px;
}

.btn-primary:hover {
  background: var(--color-background);
  color: var(--color-primary);
  outline: 2px solid var(--color-primary);
  outline-offset: -2px;
}

.btn-primary:focus-visible {
  outline: 2px solid var(--color-primary);
  outline-offset: 2px;
}
```

### Cards

| Propriedade | Valor |
|-------------|-------|
| Background | `#FFFFFF` |
| Border | 2px solid `#000000` |
| Radius | 0px |
| Shadow | none |
| Padding | 24px |
| Hover | background inverte para `#000000`, texto para `#FFFFFF` |

### Badges / Tags

| Propriedade | Valor |
|-------------|-------|
| Background | `#000000` |
| Text | `#FFFFFF` |
| Font | 12px, uppercase, letter-spacing 2px, weight 700 |
| Padding | 4px 12px |
| Radius | 0px |

### Inputs

| Propriedade | Valor |
|-------------|-------|
| Border | 2px solid `#000000` |
| Radius | 0px |
| Height | 48px |
| Font | Inter, 16px, weight 500 |
| Focus | border 2px solid `#000000`, outline 2px solid `#000000` offset 2px |
| Placeholder | `#737373` |
| Error | border-color `#FF0000` |

### Dividers

| Tipo | CSS |
|------|-----|
| Thick | `border-top: 4px solid #000000` |
| Regular | `border-top: 2px solid #000000` |
| Subtle | `border-top: 1px solid #E5E5E5` |

---

## 7. Efeitos Especiais (Signature)

### Text Clipping / Overlap

O efeito mais marcante da referencia Manychat: letras que se sobrepoe e se "cortam" mutuamente.

```css
/* Efeito de texto com masking/overlap */
.text-overlap {
  font-family: var(--font-display);
  font-size: clamp(3rem, 10vw, 6rem);
  line-height: 0.85;
  letter-spacing: -3px;
  text-transform: uppercase;
  color: var(--color-primary);
  overflow: hidden;
}

/* Linha individual com clip */
.text-overlap-line {
  display: block;
  margin-top: -0.05em; /* linhas quase se tocam */
}

/* Efeito de masking com mix-blend-mode */
.text-mask-effect {
  position: relative;
}

.text-mask-effect::after {
  content: '';
  position: absolute;
  background: var(--color-background);
  /* Posicionar para "cortar" partes das letras */
}
```

### Stat Counter (Numero de Impacto)

```css
.stat-hero {
  font-family: var(--font-display);
  font-size: clamp(4rem, 15vw, 8rem);
  line-height: 0.8;
  letter-spacing: -4px;
  color: var(--color-primary);
}

.stat-hero .unit {
  font-size: 0.6em;
  vertical-align: super;
}
```

### Texto Quebrado (Stacked Headlines)

```css
/* Headline empilhado — cada palavra em sua propria linha */
.headline-stacked {
  font-family: var(--font-display);
  font-size: clamp(2.5rem, 8vw, 5rem);
  line-height: 0.9;
  letter-spacing: -2px;
  text-transform: uppercase;
  word-spacing: 100vw; /* forca quebra por palavra */
}
```

---

## 8. Motion / Animacao

| Propriedade | Valor |
|-------------|-------|
| **Padrao** | `transition: none` (brutalista — instantaneo) |
| **Excecao: scroll** | `transform` com `duration: 0ms` |
| **Page transitions** | Corte seco. Sem fade. |
| **Hover** | Estado muda instantaneamente |
| **Loading** | Barra de progresso preta, sem spinner |
| **Entrada de conteudo** | Elementos aparecem instantaneamente |

### Regra de ouro

> Se o usuario notar a animacao, e porque ela nao devia existir. Neste sistema, a falta de animacao E o estilo.

```css
/* Override global — remove transicoes */
* {
  transition-duration: 0s !important;
}

/* Excecao: loading bar */
.loading-bar {
  transition: width 300ms linear !important;
}

/* Respeitar reduced-motion (ja nao tem, mas por seguranca) */
@media (prefers-reduced-motion: reduce) {
  * { animation: none !important; }
}
```

---

## 9. Iconografia

| Regra | Detalhe |
|-------|---------|
| **Set** | Lucide Icons (stroke-based) |
| **Stroke width** | 2px (consistente) |
| **Tamanho padrao** | 24px |
| **Cor** | Sempre `#000000` (ou `#FFFFFF` em fundo preto) |
| **Estilo** | Outline only. Nunca filled. |
| **Proibido** | Emojis, icones coloridos, icones filled |

---

## 10. Dark Mode

| Token | Light | Dark |
|-------|-------|------|
| `--color-primary` | `#000000` | `#FFFFFF` |
| `--color-background` | `#FFFFFF` | `#000000` |
| `--color-foreground` | `#000000` | `#FFFFFF` |
| `--color-on-primary` | `#FFFFFF` | `#000000` |
| `--color-muted` | `#F5F5F5` | `#111111` |
| `--color-muted-fg` | `#737373` | `#A3A3A3` |
| `--color-border` | `#000000` | `#FFFFFF` |
| `--color-border-subtle` | `#E5E5E5` | `#262626` |

> Dark mode e literalmente a inversao total. Branco no preto. Mesma brutalidade.

```css
@media (prefers-color-scheme: dark) {
  :root {
    --color-primary: #FFFFFF;
    --color-background: #000000;
    --color-foreground: #FFFFFF;
    --color-on-primary: #000000;
    --color-muted: #111111;
    --color-muted-fg: #A3A3A3;
    --color-border: #FFFFFF;
    --color-border-subtle: #262626;
  }
}
```

---

## 11. Tailwind Config

```js
// tailwind.config.js
module.exports = {
  theme: {
    extend: {
      colors: {
        primary: '#000000',
        background: '#FFFFFF',
        foreground: '#000000',
        'on-primary': '#FFFFFF',
        muted: { DEFAULT: '#F5F5F5', foreground: '#737373' },
        border: '#000000',
        'border-subtle': '#E5E5E5',
        accent: '#FF0000',
        'on-accent': '#FFFFFF',
        destructive: '#FF0000',
      },
      fontFamily: {
        display: ['"Archivo Black"', 'Impact', '"Arial Black"', 'sans-serif'],
        heading: ['"Barlow Condensed"', '"Arial Narrow"', 'sans-serif'],
        body: ['Inter', 'system-ui', 'sans-serif'],
        mono: ['"JetBrains Mono"', 'monospace'],
      },
      fontSize: {
        'hero': ['5rem', { lineHeight: '0.85', letterSpacing: '-3px' }],
        'display': ['3.5rem', { lineHeight: '0.9', letterSpacing: '-2px' }],
        'stat': ['6rem', { lineHeight: '0.8', letterSpacing: '-4px' }],
      },
      spacing: {
        '18': '4.5rem',
        '22': '5.5rem',
        '26': '6.5rem',
        '30': '7.5rem',
      },
      borderRadius: {
        'none': '0px',
        DEFAULT: '0px',
      },
      transitionDuration: {
        '0': '0ms',
      },
      letterSpacing: {
        'tightest': '-3px',
        'tighter-2': '-2px',
        'tighter-1': '-1px',
        'wide-2': '2px',
      },
      lineHeight: {
        'crush': '0.8',
        'tight-hero': '0.85',
        'tight-display': '0.9',
        'tight-heading': '0.95',
      },
    },
  },
}
```

---

## 12. Anti-Patterns (PROIBIDO)

| Nunca faca | Por que |
|------------|---------|
| Border-radius > 0 | Quebra a estetica brutalista |
| Sombras suaves (box-shadow com blur) | Contradiz alto contraste |
| Gradientes | O sistema e binario: preto ou branco |
| Transicoes suaves (ease-in-out) | Brutalismo = corte seco |
| Fontes finas (weight < 400) | Perde impacto |
| Emojis como icones | Inconsistente e nao profissional |
| Cinza medio como cor principal | Neutraliza a forca do contraste |
| Padding excessivo em texto hero | Line-height deve ser < 1.0 |
| Centralizar tudo | Alinhamento a esquerda para texto; centro so para stats/CTAs |
| Muitas cores | Maximo 2 cores + vermelho pontual |

---

## 13. Referencia Visual

### Anatomia da peca Manychat

```
┌─────────────────────────────────┐
│                                 │  ← whitespace generoso (top)
│  70% DOS                        │  ← Archivo Black, ~80px
│  NOVOS                          │  ← letras se sobrepoe
│  SEGUIDORES                     │  ← efeito de masking
│  NAO                            │  ← cada palavra = 1 linha
│  ENGAJAM                        │  ← line-height: 0.85
│                                 │  ← whitespace (separacao)
│  Chega de ignorar               │  ← Inter 400, ~16px
│  seus seguidores    Manychat    │  ← subtext + logo
│                                 │  ← whitespace (bottom)
└─────────────────────────────────┘
```

### Hierarquia

1. **Stat** (70%) — o numero que choca
2. **Statement** (DOS NOVOS SEGUIDORES NAO ENGAJAM) — contexto do choque
3. **CTA textual** (Chega de ignorar seus seguidores) — call to action emocional
4. **Brand** (Manychat) — assinatura discreta

---

## 14. Checklist Pre-Delivery

- [ ] Todas as fontes carregadas via Google Fonts
- [ ] Nenhum border-radius > 0 em todo o projeto
- [ ] Contraste texto/fundo >= 4.5:1 (AA)
- [ ] Todos os headings em uppercase
- [ ] Line-height < 1.0 em textos display/hero
- [ ] Letter-spacing negativo em headings
- [ ] Touch targets >= 44px
- [ ] Focus states visiveis em todos os interativos
- [ ] Dark mode testado (inversao completa)
- [ ] Sem transicoes suaves (0ms ou instantaneas)
- [ ] Sem emojis como icones
- [ ] Sem sombras suaves
- [ ] Whitespace generoso entre secoes
- [ ] `prefers-reduced-motion` respeitado
- [ ] Responsivo testado em 375px, 768px, 1024px, 1440px
