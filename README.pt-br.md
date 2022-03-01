# Curso em Vídeo - Projeto Android

E aí! :call_me_hand:	

Essa é a minha solução para o [desafio 10 do Curso de HTML5 e CSS3 do ***Curso em Vídeo***](https://github.com/gustavoguanabara/html-css/blob/master/desafios/modulo-02/d010/desafio-android.pdf). 

## Índice

- [Visão geral](#visão-geral)
  - [Screenshot](#screenshot)
  - [Links](#links)
- [Meu processo](#meu-processo)
  - [Criado com](#criado-com)
  - [O que aprendi](#o-que-aprendi)
  - [Recursos úteis](#recursos-úteis)
- [Autor](#autor)
- [Reconhecimentos](#reconhecimentos)

## Visão geral

### Screenshot

![Minha solução](https://github.com/braga-git/projeto-android/blob/main/imagens/projeto-android.png)

### Links

- [Arquivos da solução](https://github.com/braga-git/projeto-android)
- [Site](https://braga-git.github.io/projeto-android/)

## Meu processo

### Criado com

- HTML5
- CSS3

### O que aprendi

Uma das maiores diferenças que eu notei entre a minha solução para o desafio e o modelo feito pelo Guanabara, é a questão da organização. O código feito pelo Gustavo é muito mais simples, organizado e fácil de ser lido do que o que eu havia feito na época. O próprio fluxo de criação dele foi muito melhor! 

A outra questão é referente ao conhecimento e raciocínio em si. O código dele parece ser muito mais "direto". Parece que encaixa melhor! Mesmo que eu tenha obtido um resultado semelhante ao esperado, a forma como ele fez me pareceu ser muito mais simples. Podemos identificar a veracidade da minha observação neste exemplo:

Em uma seção do site, ele pede para inserir um vídeo e que ele seja responsívo, como todo o site. Na minha solução eu: 

1. Dividi o site inteiro em 3 elementos `<main>`; 
2. Atribui uma `id="video"` ao `<main>` do `<iframe>`;
3. Dentro dessa `<main>`, eu adicionei uma `<div>` com uma `class="video-container"`;
4. E finalmente, dentro dessa `<div>` eu adicionei o `<iframe>`.

```html
<main id="video">

  <div class="video-container">
    
      <iframe width="560" height="315" src="https://www.youtube.com/embed/l2UDgpLz20M" 
      title="YouTube video player" frameborder="0" 
      allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" 
      allowfullscreen></iframe>
  
  </div>

</main>
```

Simplesmente porquê eu não sabia como iria dividir o site e colorir aquela seção do vídeo com a cor verde.

O Guanabara apenas:

1. Criou uma `<div>` com o `<iframe>` dentro e atribuiu uma `class="video"`.

```html
<div class="video">
  
  <iframe width="560" height="315" src="https://www.youtube.com/embed/l2UDgpLz20M" 
  title="YouTube video player" frameborder="0" 
  allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" 
  allowfullscreen></iframe>

</div>
```

No CSS utilizamos uma solução bem parecida. 

![CSS de ambos os projetos](https://github.com/braga-git/projeto-android/blob/main/imagens/screenshot-css.png)

Ou seja, eu precisava dar toda essa "volta"? Eu só compliquei e aumentei o meu trabalho.

---

Até o momento do desafio, o curso não havia apresentado a pseudo-classe `:root`, utilizada para a criação de variáveis globais, nem o seletor universal `*`, que nesse caso foi usado para zerar a margem e o padding de todos os elementos:

```css
* {
  margin: 0px;
  padding: 0px;
}
```

Ambos facilitam e simplificam muita coisa dentro do código. Por exemplo, ao invés de decorar o código HEX de cada cor a ser usada no projeto, você simplesmente cria uma variável para chamar cada cor por um número:

```css
:root {
    --cor0: #c5ebd6;
    --cor1: #83e1ad;
    --cor2: #3ddc84;
    --cor3: #2fa866;
    --cor4: #1a5c37;
    --cor5: #063d1e;
}
```

---

Em relação aos emojis que o Gustavo havia solicitado ao lado dos links externos: De novo, eu dei uma volta desnecessária! Para adicionar o link de corrente ao lado dos links externos eu:

1. Atribui todos os links externos à classe `class="chain"`;
2. Fiz o download de um ícone em SVG;
3. Defini um `background-image: url(link.svg)` para todos os links atribuídos à `class="chain"`.

Meu código completo ficou dessa forma:

```css
a.chain {
  background-image: url(link.svg);
  background-repeat: no-repeat;
  background-position: top right;
  padding-right: 1.5em;
  background-size: 1em;
}
```

O Guanabara basicamente criou isso:

```css
a.externo::after {
  content: '\00A0\1F517';
}
```

A propriedade `content` é usada para adicionar conteúdo antes ou depois do elemento. Nesse caso, ela foi utilizada com o pseudoelemento `::after` para gerar o ícone depois dos links. E os valores utilizados `'\OOAO\1F517'` correspondem respectivamente aos números do padrão unicode para um *espaço sem quebra* e para um *ícone de corrente (link)*.

---

Agora, falando sobre responsividade, podemos ver que eu não fui tão feliz quando se trata do mobile. Algumas coisas do meu site quebraram, como o menu de navegação, as colunas da parte inferior do site e o rodapé.

| Meu projeto                                                                                | Modelo do Guanabara |
| -----------                                                                                | -----------         |
|![header](https://github.com/braga-git/projeto-android/blob/main/imagens/header-braga.jpeg) |![header](https://github.com/braga-git/projeto-android/blob/main/imagens/header-guanabara.jpeg)|
|![footer](https://github.com/braga-git/projeto-android/blob/main/imagens/footer-braga.jpeg) |![footer](https://github.com/braga-git/projeto-android/blob/main/imagens/footer-guanabara.jpeg)|

## Autor

Me siga para mais "soluções" :wink: 

- Frontend Mentor - [@braga-git](https://www.frontendmentor.io/profile/braga-git)
- Instagram - [@braga.jpeg](https://www.instagram.com/braga.jpeg/)
- LinkedIn - [Gabriel Braga Camara](https://www.linkedin.com/in/gabrielbragacamara/)
