# 🎯 Jogo do Número Secreto

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)  
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)  
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)  
![ResponsiveVoice](https://img.shields.io/badge/ResponsiveVoice-TextToSpeech-blueviolet?style=for-the-badge)

---

## 📝 Descrição do Projeto

Este é um jogo simples em **JavaScript** onde o jogador tenta adivinhar um **número secreto entre 1 e 10**. A cada tentativa, o sistema informa se o número digitado é maior ou menor que o número secreto. O jogo também contabiliza as tentativas realizadas e, ao acertar, exibe uma mensagem de vitória com a opção de reiniciar o jogo.

🔊 O jogo utiliza a biblioteca **[ResponsiveVoice](https://responsivevoice.org/)** para fazer a leitura em voz alta das mensagens, com voz em **português brasileiro**.

---

## ✨ Funcionalidades

- ✅ Geração aleatória do número secreto entre 1 e 10.  
- 🔁 Evita repetição do mesmo número até que todos tenham sido utilizados.  
- 🧏 Feedback visual e por voz.  
- 📊 Contador de tentativas.  
- 🔄 Botão de reinício do jogo.  
- 📱 Interface responsiva para celulares e tablets.

---

## 🛠️ Tecnologias Utilizadas

- 📄 **HTML5**  
- 🎨 **CSS3**  
- 🧠 **JavaScript**  
- 🗣️ **ResponsiveVoice** (biblioteca para síntese de voz)

---

## 🧩 Estrutura do Código

### 📄 HTML

- Título, instruções, campo numérico, botões e imagem decorativa.  
- Utilização do Google Fonts para uma melhor tipografia.  
- Inclusão do script do ResponsiveVoice no final da página.

### 🎨 CSS

- Layout moderno com gradiente e imagens de fundo.  
- Design responsivo e compatível com dispositivos móveis.  
- Estilização personalizada para botões, campos de entrada e mensagens.

### ⚙️ JavaScript

- Lógica para controle do número secreto e validação de tentativas.  
- Função para gerar números aleatórios sem repetição.  
- Atualização dinâmica de elementos da tela.  
- Leitura das mensagens em voz alta usando a biblioteca ResponsiveVoice.

---

## ▶️ Como Executar

1. 📥 Clone ou baixe este repositório em sua máquina.
2. 🌐 Abra o arquivo `index.html` diretamente no navegador.
3. 🔢 Digite um número entre 1 e 10 no campo de entrada.
4. 🖱️ Clique em **Chutar** para tentar adivinhar.
5. 📣 O jogo fornecerá feedback visual e sonoro.
6. 🆕 Ao acertar o número, clique em **Novo jogo** para jogar novamente.

---

## 💻 Código Exemplo (JavaScript)

```javascript
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
