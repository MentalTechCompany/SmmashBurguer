# Smmash Burger | Site e cardápio online

Site da hamburgueria **Smmash Burger** (Brasília, DF), feito pela **Mental Tech**: cardápio completo com preços e uma parte para conhecer a casa.

O cliente aponta a câmera para o QR code na mesa e o site abre no celular, com o botão **Ver cardápio** logo no topo.

🔗 **Site no ar:** https://smmashburguer.netlify.app

## O que tem no site

Uma página só, nesta ordem:

1. **Abertura:** letreiro SMMASH BURGER, ilustração do lanche montando na chapa, selo **Aberto agora / Fechado agora** e os botões **Ver cardápio** e **Conheça a casa**
2. **Cardápio:** combos, lanches Smmash, batatas, adicionais, bebidas e sobremesas, com preços. Menu de categorias fixo que acompanha a rolagem. Botão **+** em cada item: o cliente monta a lista do pedido, vê o total e mostra no balcão (ou envia pelo WhatsApp, quando o número estiver configurado)
3. **A casa:** texto sobre a hamburgueria e números em destaque (90g, 4 molhos...)
4. **Como fazemos:** os 4 passos do smash (bola, prensa, crosta, montagem), ilustrados e animados, e o quadro "Do seu jeito" (low carb, troca de blend, adicionais)
5. **Visite:** endereço com botão **Como chegar**, horário da semana, formas de pagamento, WhatsApp e Instagram
6. **Rodapé** com atalhos

Funciona em qualquer celular ou computador, sem instalar nada. A barra de cima some ao descer a página e volta ao subir, para sobrar mais espaço para o cardápio no celular. Quem prefere menos movimento (configuração do celular) vê o site sem animações.

**Dica para o QR code:** se quiser que o QR da mesa abra direto no cardápio, gere o QR com o link `https://smmashburguer.netlify.app/#cardapio`. Os QR codes que já estão impressos continuam funcionando e abrem no topo.

## Como atualizar

Todo o site está em um único arquivo: `index.html`. Tudo o que muda (preços, itens, telefone, horário, textos da casa) fica no bloco **`CONFIG`**, no começo do `<script>`, perto do fim do arquivo. Não precisa mexer em mais nada.

**Cardápio**

- **Mudar um preço:** ache o item no `CONFIG` e troque o número. Use ponto, sem `R$`: `preco: 21.90`.
- **Adicionar um item:** copie uma linha de item parecido e mude nome, preço e descrição.
- **Selo no item:** coloque `selo: "Mais pedido"` (ou "Promoção", "Veggie"...).
- **Foto no item:** coloque `foto: "https://link-da-foto.jpg"`. A foto aparece no alto do cartão do lanche.
- **Frase "à mão" ao lado do nome da categoria:** `rabisco: "turbine seu lanche"`. Para tirar, apague a linha.

**Informações da loja**

- **WhatsApp:** preencha `whatsapp: "5561999998888"` (só números, com 55 e o DDD). Enquanto estiver vazio, os botões de WhatsApp ficam escondidos.
- **Instagram:** preencha `instagram: "nomedoperfil"` (sem @). Aparece em "Visite" e no rodapé.
- **Horário:** troque `horarios: null` pelo modelo que está no comentário logo acima. Dia fechado = `null`. Pode fechar depois da meia-noite (ex.: `["18:00","00:30"]`).
- **Endereço e mapa:** `endereco` (texto que aparece) e `mapa` (link do Google Maps do botão **Como chegar**).

**Textos da página**

- **Selo redondo da abertura:** `adesivo`. O `\n` quebra a linha.
- **Faixa vermelha que passa:** `faixa`, uma frase por item da lista.
- **A casa:** em `sobre`, troque `titulo`, `paragrafos` e `numeros`. No título, a palavra entre `*asteriscos*` fica amarela e sublinhada.
- **Tirar a faixa de prévia:** deixe `previa: ""`.
- **Mudar as cores:** no começo do arquivo, troque os códigos em `:root`.

O título e a descrição que aparecem quando alguém compartilha o link ficam no `<head>`, no topo do arquivo.

Depois de editar, abra o `index.html` no navegador para conferir e suba de novo no Netlify, na aba **Deploys** do site (arraste o arquivo). O link e o QR code continuam os mesmos. Não use o Netlify Drop para atualizar, porque ele cria um site novo com outro link.

## Pendências (marcadas com `PROVISÓRIO` no arquivo)

- [ ] História real da casa para a seção "A casa" (quando abriu, quem está por trás, o que inspirou)
- [ ] Cardápio das batatas
- [ ] Horário de funcionamento
- [x] WhatsApp da loja: (61) 99374-4996
- [ ] Instagram da loja
- [ ] Endereço completo
- [ ] Confirmar como funciona o pedido (balcão, mesa ou WhatsApp)
- [ ] Tamanho das bebidas (lata, 600 ml, long neck...)
- [ ] Qual é o lanche mais pedido (para o selo "Mais pedido")
- [ ] Fotos dos lanches
- [ ] Imagem de compartilhamento (`og:image`, 1200x630)
- [ ] Confirmar preços com o dono
- [ ] Tirar a faixa de "Prévia" depois da aprovação

---

Feito por **Mental Tech**
