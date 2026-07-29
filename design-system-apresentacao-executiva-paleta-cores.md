# Design System — Apresentações Executivas
### Setor: Tecnologia / Startup

Sistema visual derivado da identidade de produto existente, adaptado para o contexto de apresentações a board, investidores e liderança executiva. Mantém a linguagem "tech" (escura, precisa, confiante) com o rigor visual que decisões de alto nível exigem: hierarquia clara, baixo ruído, foco no dado.

---

## 1. Princípios

1. **Um dado, um destaque por slide.** Nunca competir por atenção.
2. **Escuro como padrão, claro como exceção.** O tema dark é a assinatura da marca — usar tema claro só quando o ambiente de projeção exigir (salas muito claras, impressão).
3. **Azul é ação, branco é informação, cinza é contexto.** A cor nunca é decorativa.
4. **Espaço em branco é hierarquia.** Preferir remover elementos a comprimi-los.
5. **Consistência de raio, sombra e espaçamento em 100% dos slides.**

---

## 2. Paleta de Cores

Paleta derivada da grade de swatches enviada: 4 famílias de cor (Azul, Verde, Ouro, Laranja), cada uma em 3 tons.

| Família | Escuro | Médio | Claro |
|---|---|---|---|
| Azul | `#071A4A` | `#0A2260` | `#0033FF` |
| Verde | `#0F3D0A` | `#0A9E1F` | `#AACC33` |
| Ouro | `#FFB800` | `#FF9E00` | `#FFD400` |
| Laranja | `#FF6A00` | `#FF8400` | `#FFA500` |

### Modo Escuro (padrão)

| Token | Hex | Uso |
|---|---|---|
| `bg/primary` | `#071A4A` | Fundo do slide (Azul escuro) |
| `bg/surface` | `#0A2260` | Cards, painéis, tabelas (Azul médio) |
| `bg/surface-hover` | `#103070` | Estado secundário / cards elevados |
| `border/subtle` | `rgba(255,255,255,0.08)` | Bordas de cards (1px) |
| `accent/primary` | `#0033FF` | Botões, links, destaques, barras de progresso (Azul claro) |
| `accent/primary-soft` | `#0033FF` a 15% de opacidade sobre o fundo | Fundo de badges/tags |
| `accent/gradient` | `#0033FF → #FF6A00` | Ícones em destaque, elementos hero (Azul → Laranja) |
| `text/primary` | `#FFFFFF` | Títulos, dados principais |
| `text/secondary` | `#B8C2DB` | Subtítulos, legendas, corpo de texto |
| `text/muted` | `#8996BE` | Notas de rodapé, fontes de dados |
| `success` | `#0A9E1F` | Indicadores positivos (↑ métricas) — Verde médio |
| `warning` | `#FFD400` | Alertas, riscos — Ouro claro |
| `danger` | `#FF6A00` | Indicadores negativos (↓ métricas) — Laranja escuro |

### Modo Claro (uso restrito)

| Token | Hex |
|---|---|
| `bg/primary` | `#FFFFFF` |
| `bg/surface` | `#F5F6F8` |
| `border/subtle` | `#E4E6EA` |
| `text/primary` | `#071A4A` (Azul escuro, mantém identidade mesmo no claro) |
| `text/secondary` | `#4A5578` |
| `accent/primary` | `#0033FF` (mesma cor, mantém identidade) |

**Regra de contraste:** texto primário sobre `bg/primary` deve manter razão de contraste ≥ 7:1 (AAA). Nunca usar `text/secondary` para números ou dados que sustentam uma decisão.

---

## 3. Tipografia

**Família:** Inter (ou Söhne / Geist como alternativas próximas). Sans-serif geométrica, mesma sensação da referência.

| Estilo | Peso | Tamanho (slide 16:9, 1920×1080) | Uso |
|---|---|---|---|
| Display | Bold (700) | 56px | Capa, número hero (ex: "$4.2M ARR") |
| H1 | Bold (700) | 36px | Título de slide |
| H2 | Semibold (600) | 24px | Subtítulo / título de seção dentro do slide |
| Body | Regular (400) | 18px | Texto corrido, bullets |
| Body Small | Regular (400) | 14px | Legendas de gráfico, labels |
| Caption | Medium (500) | 12px | Fonte de dados, notas de rodapé, badges |

- Entrelinha: 1.3–1.4× o tamanho da fonte.
- Bullets: máximo 3 níveis, nunca mais de 6 linhas por slide.
- Números grandes (Display) sempre em `text/primary`, nunca coloridos exceto para indicar variação (verde/vermelho).

---

## 4. Grid e Espaçamento

- **Formato:** 16:9 (1920×1080px como base de trabalho)
- **Margem externa:** 96px em todos os lados
- **Colunas:** grid de 12 colunas, gutter de 24px
- **Escala de espaçamento** (base 8px): `4 · 8 · 16 · 24 · 32 · 48 · 64 · 96`
- **Raio de borda padrão:** 16px (cards grandes), 12px (badges/botões), 8px (chips pequenos)
- **Espessura de borda:** 1px, sempre `border/subtle`

---

## 5. Componentes

### 5.1 Card de Dado (KPI Card)
Réplica direta do padrão visto na referência (os três cards de feature).
- Fundo `bg/surface`, borda 1px `border/subtle`, raio 16px, padding 32px
- Ícone opcional no topo: 40×40px, fundo em gradiente `accent/gradient`, raio 10px
- Título do KPI: H2, `text/primary`
- Valor: Display, `text/primary`
- Variação: chip pequeno com seta (▲/▼) em `success`/`danger`
- Estado "destaque": borda em `accent/primary` + badge "PRIORIDADE" ou "RECOMENDADO" no canto superior, mesmo padrão do card "Diagnóstico de Carreira" da referência

### 5.2 Badge / Tag
- Padding 4px 12px, raio total (pill), fundo `accent/primary-soft`, texto `accent/primary`, Caption Medium
- Usar para status: "Em andamento", "Novo", "Risco", "Recomendado"

### 5.3 Barra de Progresso
- Trilho: `border/subtle`, altura 6px, raio total
- Preenchimento: `accent/primary`, mesma altura
- Label numérica à direita (ex: "72%"), Body Small, `text/secondary`

### 5.4 Callout / Destaque Contextual
Baseado na faixa "Recomendado começar pelo Diagnóstico" da referência.
- Fundo `bg/surface`, borda 1px `border/subtle`, raio 12px, padding 16px 24px
- Ícone contextual à esquerda (seta, lupa, alerta)
- Texto Body, com um trecho em destaque usando badge inline

### 5.5 Tabela / Comparativo
- Cabeçalho: `text/secondary`, Caption Medium, uppercase, letter-spacing 0.5px
- Linhas: separadas por `border/subtle` (sem grade completa)
- Linha em destaque (ex: opção recomendada): fundo `bg/surface` + borda `accent/primary`

### 5.6 Gráficos
- Paleta de séries: `accent/primary` (Azul) → `#0A9E1F` (Verde) → `#FFD400` (Ouro) → `#FF6A00` (Laranja), nessa ordem de prioridade
- Sem grid de fundo pesado — usar linhas guia finas em `border/subtle`, opacidade 40%
- Eixos e labels sempre `text/secondary`
- Data labels apenas no ponto/barra mais relevante, não em todos

### 5.7 Rodapé de Navegação (opcional, decks longos)
Inspirado na barra inferior da referência ("Modo Acessível / Suporte / Meu Perfil").
- Fina, `text/muted`, ícone + label, usado para indicar seção do deck (ex: "01 Contexto · 02 Estratégia · 03 Financeiro")

---

## 6. Estrutura de Slides Padrão

| Tipo de slide | Composição |
|---|---|
| **Capa** | Fundo `bg/primary`, logo/ícone centralizado com gradiente, título Display, subtítulo Body em `text/secondary` |
| **Divisor de seção** | Fundo `bg/primary`, número da seção grande (H1, `text/muted`) + título H1 |
| **Agenda** | Lista numerada, item ativo com badge `accent/primary`, demais em `text/secondary` |
| **KPI Overview** | Grid de 3–4 KPI Cards lado a lado |
| **Narrativa + Gráfico** | 40% texto (H2 + bullets) / 60% gráfico, divisão por coluna do grid |
| **Comparativo** | Tabela conforme 5.5, com uma coluna/linha destacada como recomendação |
| **Roadmap / Timeline** | Linha horizontal em `border/subtle`, marcos como pontos em `accent/primary`, cards de marco usando padrão 5.1 |
| **Encerramento / Ask** | Volta ao padrão da capa, com callout (5.4) contendo o pedido/decisão esperada |

---

## 7. Do's & Don'ts

**Fazer**
- Manter todo slide dentro do grid de 96px de margem
- Usar no máximo 1 cor de destaque (`accent/primary`) por slide, além de verde/vermelho para variação
- Repetir exatamente os mesmos raios, sombras e espaçamentos em todos os cards

**Evitar**
- Misturar tema claro e escuro no mesmo deck
- Usar mais de 3 pesos de fonte no mesmo slide
- Texto secundário (`text/secondary`) em números que sustentam a decisão principal
- Bordas de mais de 1px ou sombras pesadas (a referência é "flat com profundidade sutil", não skeuomórfico

---

## 8. Próximo passo

Este documento serve de base para o **template .pptx**, onde cada componente acima vira um layout mestre (slide master) editável. Quando quiser seguir para essa etapa, é só avisar.
