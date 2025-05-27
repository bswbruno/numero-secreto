# Jogo do Número Secreto

## Descrição do Projeto
Este é um jogo simples em JavaScript onde o usuário tenta adivinhar um número secreto entre 1 e 10. O jogo informa se o chute é maior ou menor que o número secreto, contando as tentativas feitas. Quando o usuário acerta, o jogo exibe uma mensagem de vitória e permite reiniciar a partida.

O projeto inclui também a funcionalidade de leitura em voz alta das mensagens exibidas, usando a biblioteca **ResponsiveVoice** com voz em português brasileiro.

---

## Funcionalidades
- Geração aleatória do número secreto entre 1 e 10.
- Evita repetição do mesmo número secreto até que todos os números possíveis sejam usados.
- Feedback textual e em áudio para o jogador.
- Controle de tentativas.
- Botão para reiniciar o jogo.
- Interface responsiva para dispositivos móveis.

---

## Tecnologias Utilizadas
- HTML5
- CSS3
- JavaScript
- Biblioteca [ResponsiveVoice](https://responsivevoice.org/) para síntese de voz.

---

## Estrutura do Código

### HTML
- Título, instruções, campo numérico, botões e imagem decorativa.
- Uso de fontes Google Fonts.
- Inclusão do script ResponsiveVoice.

### CSS
- Layout moderno com gradiente e imagens de fundo.
- Design responsivo.
- Estilos para botões, texto e campos.

### JavaScript
- Controle do número secreto e tentativas.
- Função para gerar números aleatórios sem repetição.
- Atualização dinâmica do conteúdo da página.
- Leitura das mensagens em voz alta via ResponsiveVoice.

---

## Como Executar
1. Clone ou baixe este repositório.
2. Abra o arquivo `index.html` no navegador.
3. Digite um número entre 1 e 10 no campo.
4. Clique no botão **Chutar** para tentar adivinhar.
5. O feedback será exibido na tela e falado.
6. Quando acertar, clique em **Novo jogo** para reiniciar.

---

## Código Exemplo (JavaScript)

```js
let listaDeNumerosSorteados = [];
let numeroLimite = 10;
let numeroSecreto = gerarNumeroAleatorio();
let tentativas = 1;

function exibirTextoNaTela(tag, texto) {
   let campo = document.querySelector(tag);
   campo.innerHTML = texto;
   responsiveVoice.speak(texto, 'Brazilian Portuguese Female', { rate: 1 });
}

function gerarNumeroAleatorio() {
   if (listaDeNumerosSorteados.length === numeroLimite) {
      listaDeNumerosSorteados = [];
   }

   let numeroEscolhido = Math.floor(Math.random() * numeroLimite) + 1;

   if (listaDeNumerosSorteados.includes(numeroEscolhido)) {
      return gerarNumeroAleatorio();
   } else {
      listaDeNumerosSorteados.push(numeroEscolhido);
      return numeroEscolhido;
   }
}
