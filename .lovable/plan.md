# Redesign Premium — Belleza

Transformar a interface num design premium moderno: tipografia refinada, paleta coesa, espaçamento consistente, animações suaves e microinterações — mantendo a identidade do projeto (logo serif "Belleza", conteúdo e funcionalidades intactos).

## Direção visual

- **Tipografia**: manter Noto Serif Display nos títulos (identidade). Introduzir **Manrope** como fonte de corpo — substitui a fonte do sistema em todo o app.
- **Paleta coesa (beleza premium)**: fundo creme quente, tinta profunda (quase-preto com matiz quente), **rosé** como cor de ação principal, detalhes dourados discretos. O verde WhatsApp fica reservado apenas aos botões WhatsApp. Remove-se o azul saturado + lilás atual, que lê-se "SaaS corporativo".
- **Tokens**: todas as cores passam a variáveis semânticas em `index.css` (sem cores hardcoded nos componentes).

## Fases

### 1. Sistema de design (base)
- `index.css`: novos tokens (cores, sombras, raios, gradientes) + utilitários de animação (reveal on scroll, hover elevation, microinterações de botão).
- `tailwind.config.js`: fontes Manrope (body) + Noto Serif Display (headings), cores semânticas.
- `index.html`: import das fontes.

### 2. Landing page (src/pages/LandingPage.tsx)
- Hero: hierarquia refinada, barra de pesquisa com elevação suave.
- Cards de serviço: reduzir ruído — imagem com zoom suave no hover, nome/profissional, preço e ação em destaque, horários compactados (linha única + detalhe), WhatsApp como botão secundário discreto (ícone), vagas como badge subtil.
- Cards de categoria: ícone + cor, hover elevado.
- Secções de profissionais, testemunhos e categorias com o novo estilo.
- Animações de entrada em cascata (fade/slide-up ao entrar na viewport, via utilitário CSS + IntersectionObserver).

### 3. Componentes partilhados
- Botões (classes `.btn-*` em index.css) com o novo estilo e microinterações (scale subtil, shine no hover).
- Cards, badges (CapacityBadge, InfoCard, ProfessionalCountBadge) e inputs (`.input-glow`) alinhados à nova paleta.

### 4. Páginas-chave da app
- Layout (nav/footer), Services, ServiceDetails, Dashboard, páginas de autenticação — aplicam os tokens; a estrutura e funcionalidades não mudam.

## Fora do âmbito
- Nenhuma alteração de base de dados, RLS ou lógica de negócio.
- Pendentes (separado deste trabalho): correr os SQL de correção de constraints no Supabase (service_variants e availability) e testar a conta da Catarina Domingues.

## Verificação
- Build sem erros; capturas (desktop + mobile) da landing e de uma página interna para confirmar o novo visual; sem erros de runtime no browser.
