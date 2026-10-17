Crie o site de uma página do **Restaurante Careca**, um restaurante de comida chinesa no Sudoeste, em Brasília (DF). O restaurante não tem site hoje. O objetivo é simples: quem achar o restaurante no Google ou receber o link pelo WhatsApp/Instagram precisa entender em poucos segundos o que é, como pedir (delivery pelo iFood ou retirada no balcão), onde fica e se está aberto agora.

O site é da agência Mental Tech e vai ser mostrado ao dono como prévia. O dono não sabe programar, então todo o conteúdo precisa ser fácil de trocar depois.

## Dados reais (do Google Maps, use exatamente assim)

- Nome: Restaurante Careca
- Tipo: restaurante chinês
- Endereço: St. Sudoeste, Q. Res. Sudoeste 1, loja 08 · Sudoeste/Octogonal, Brasília - DF · CEP 70675-100
- Telefone: (61) 3877-0637 (link: `tel:+556138770637`)
- Funciona só com retirada no balcão e delivery pelo iFood. Não tem mesas para comer no local.
- Mais de 4.600 avaliações no Google
- Preço médio informado no Google: R$ 40 a R$ 60 por pessoa
- O Google mostrava "fecha às 21h45" num sábado. O horário de abertura e o dos outros dias ainda não são conhecidos.
- O que os clientes elogiam nas avaliações (use só para orientar o tom dos textos, nunca como depoimento): comida chinesa típica, muita variedade, porções bem servidas, preço justo e atendimento atencioso.

## Ainda não sabemos (deixe o campo pronto e vazio, marcado como PROVISÓRIO)

- Link da loja no iFood
- WhatsApp (o telefone acima é fixo; não assuma que ele tem WhatsApp)
- Instagram
- Horário completo da semana
- Formas de pagamento
- Cardápio, preços e fotos dos pratos
- Logo e cores oficiais

[Se tiver o cardápio, cole aqui: categorias, pratos, descrição e preço de cada um.]

## Estrutura da página (nesta ordem)

1. **Faixa fina no topo:** "Prévia feita pela Mental Tech com base no Google Maps (out. 2026)." Controlada por um campo no config: vazio, ela some.
2. **Topo:** nome grande, uma frase curta (ex.: "Comida chinesa bem servida no Sudoeste, pra retirar no balcão ou receber em casa."), selo "Aberto agora · fecha às 21h45" / "Fechado agora · abre às ..." calculado pelo horário, e os botões "Pedir no iFood" (principal) e "Ligar (61) 3877-0637". Se o link do iFood estiver vazio, o botão de ligar vira o principal.
3. **Aviso visível e simpático:** "Aqui é só retirada e delivery: não temos mesas no local."
4. **Como pedir:** dois blocos, lado a lado no desktop e um embaixo do outro no celular: "Delivery pelo iFood" e "Retirada no balcão" (com endereço e telefone).
5. **Cardápio:** lido do config, separado por categorias, com um menu de categorias que gruda no topo ao rolar. Visual de painel de balcão de comida pra levar: cada prato com número (Nº 01, Nº 02...), nome, descrição curta e preço alinhado à direita. Enquanto o cardápio estiver vazio, mostre um estado bonito com "Veja o cardápio completo no iFood" (botão) ou "Ligue e pergunte as opções". Não invente pratos nem preços.
6. **Avaliações:** só um bloco com "Mais de 4.600 avaliações no Google" e o botão "Ver avaliações no Google". Sem estrelas, sem nota média e sem depoimentos.
7. **Onde estamos:** endereço, mapa do Google incorporado (iframe sem chave de API, buscando o endereço), botão "Como chegar", horário da semana com o dia de hoje em negrito ("Horário a confirmar" enquanto estiver vazio), telefone, faixa de preço e formas de pagamento (escondidas enquanto estiverem vazias).
8. **Rodapé:** "Site feito por Mental Tech".
9. **Botão flutuante** no canto inferior direito: WhatsApp (verde #25D366, com ícone) quando o número estiver preenchido; senão, botão de ligar.

## Identidade visual

Ainda não temos a marca real, então crie uma direção própria e forte, marcada como provisória:

- **Conceito:** balcão de comida chinesa pra levar do bairro. Painel de cardápio iluminado, pratos numerados, comanda, sacola de delivery.
- **Cores:** vermelho laca #B3121C (principal), tinta quase preta #1C1714 (textos), creme papel de arroz #FBF5EA (fundo), dourado gergelim #E2A320 (só detalhes, nunca texto sobre o creme), verde jade #1F6B57 (selo "aberto"). Contraste AA em todos os textos.
- **Tipografia:** Bricolage Grotesque (Google Fonts). Títulos bem pesados e condensados (largura 75, peso 800); corpo com largura e peso normais.
- **Logo provisório:** "CARECA" em letra grossa ao lado de um carimbo quadrado vermelho com a letra "C", como um selo de tinta. SVG simples.
- **Movimento:** pouca animação, só para dar vida (ex.: o ponto do selo "aberto" pulsando de leve). Respeite `prefers-reduced-motion`.

Evite: dragões, lanternas, leques, letras imitando pincel ou "estilo chop suey", ideogramas chineses decorativos, gradiente roxo, cards todos iguais, emojis no lugar de ícones e fotos de banco de imagem ou geradas por IA apresentadas como comida do restaurante.

**Fotos:** ainda não temos. Use espaços reservados neutros e bem marcados ("Foto do prato em breve"), fáceis de trocar por um link no config. Prato sem foto aparece sem foto, sem quebrar o layout.

## Regras técnicas

- Site estático de uma página. Não use Supabase, login, banco de dados nem formulários.
- **Todo o conteúdo editável fica em um único arquivo `src/config/site.ts`**, com comentários em português explicando cada campo: nome, frase do topo, telefone, WhatsApp, Instagram, link do iFood, endereço, link do Google Maps, horários por dia, formas de pagamento, faixa de preço, texto da faixa de prévia, cardápio (categorias → pratos com nome, descricao, preco, foto, selo) e cores principais. Os componentes só leem desse arquivo: nenhum telefone, preço ou horário repetido no código.
- Todo campo não confirmado pelo dono leva o comentário `// PROVISÓRIO` ao lado.
- **Horário:** formato simples por dia (`{ seg: ["11:00","21:45"], ..., dom: null }`), dia fechado = `null`, aceitando fechar depois da meia-noite. O "aberto agora" usa o fuso America/Sao_Paulo, não o do celular. Sem horário preenchido, o selo some.
- **WhatsApp:** link `https://wa.me/55DDDNUMERO?text=` + `encodeURIComponent` de uma mensagem educada em português ("Olá, Restaurante Careca! Vim pelo site e gostaria de fazer um pedido."). Campo vazio = todos os botões de WhatsApp escondidos.
- Preços em real, no formato R$ 32,90.
- **Mobile first:** perfeito em 375px de largura, sem rolagem horizontal, botões com pelo menos 44px de altura. Bonito também no desktop.
- **iPhone:** precisa funcionar bem dentro do navegador do Instagram e do WhatsApp. Não dependa só de `dvh`/`svh` (tenha alternativa), respeite `env(safe-area-inset-bottom)` no botão flutuante e não esconda informação atrás de hover.
- **SEO local:** `lang="pt-BR"`, título "Restaurante Careca | Comida chinesa no Sudoeste, Brasília", meta description, tags Open Graph em português e JSON-LD schema.org do tipo `Restaurant` com nome, endereço, telefone, `servesCuisine: "Chinesa"` e `priceRange`. Não coloque `aggregateRating` nem avaliações no JSON-LD.
- **Acessibilidade:** foco visível, textos alternativos e rótulos claros nos links de telefone, iFood e mapa.
- Crie um `README.md` curto em português, para quem não programa, explicando como trocar textos, preços, horário e telefone em `src/config/site.ts`, e listando tudo o que ainda está PROVISÓRIO.

## Honestidade (obrigatório)

Não invente nada: nem pratos, preços, depoimentos, nota em estrelas, número de pedidos, prêmios, anos de história, nome do dono ou de funcionários. O que não está nos dados reais acima fica vazio e marcado como PROVISÓRIO.
