# Smmash Burger | Cardápio online

Cardápio digital da hamburgueria **Smmash Burger** (Brasília, DF), feito pela **Mental Tech**.

O cliente aponta a câmera para o QR code na mesa e o cardápio abre no celular.

🔗 **Site no ar:** https://smmashburguer.netlify.app

## O que tem no site

- Combos, lanches Smmash, batatas, adicionais, bebidas e sobremesas, com preços
- Menu de categorias que acompanha a rolagem da página
- Botão **+** em cada item: o cliente monta a lista do pedido, vê o total e mostra no balcão (ou envia pelo WhatsApp, quando o número estiver configurado)
- Selo **Aberto agora / Fechado agora**, calculado pelo horário de funcionamento
- Localização, horário, formas de pagamento, WhatsApp e Instagram
- Funciona em qualquer celular, sem precisar instalar nada

## Como atualizar

Todo o site está em um único arquivo: `index.html`. Tudo o que muda (preços, itens, telefone, horário) fica no bloco **`CONFIG`**, no começo do `<script>`, perto do fim do arquivo. Não precisa mexer em mais nada.

- **Mudar um preço:** ache o item no `CONFIG` e troque o número. Use ponto, sem `R$`: `preco: 21.90`.
- **Adicionar um item:** copie uma linha de item parecido e mude nome, preço e descrição.
- **Selo no item:** coloque `selo: "Mais pedido"` (ou "Promoção", "Veggie"...).
- **Foto no item:** coloque `foto: "https://link-da-foto.jpg"`.
- **WhatsApp:** preencha `whatsapp: "5561999998888"` (só números, com 55 e o DDD). Enquanto estiver vazio, os botões de WhatsApp ficam escondidos.
- **Instagram:** preencha `instagram: "nomedoperfil"` (sem @).
- **Horário:** troque `horarios: null` pelo modelo que está no comentário logo acima. Dia fechado = `null`. Pode fechar depois da meia-noite (ex.: `["18:00","00:30"]`).
- **Tirar a faixa de prévia:** deixe `previa: ""`.
- **Mudar as cores:** no começo do arquivo, troque os códigos em `:root`.

O título e a descrição que aparecem quando alguém compartilha o link ficam no `<head>`, no topo do arquivo.

Depois de editar, abra o `index.html` no navegador para conferir e suba de novo no Netlify, na aba **Deploys** do site (arraste o arquivo). O link e o QR code continuam os mesmos. Não use o Netlify Drop para atualizar, porque ele cria um site novo com outro link.

## Pendências (marcadas com `PROVISÓRIO` no arquivo)

- [ ] Cardápio das batatas
- [ ] Horário de funcionamento
- [ ] WhatsApp e Instagram da loja
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
