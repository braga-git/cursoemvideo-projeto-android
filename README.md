# Curso em Vídeo - Projeto Android

### E aí! :call_me_hand:	

Essa é a minha solução para o [desafio 10 do Curso de HTML5 e CSS3 do ***Curso em Vídeo***](https://github.com/gustavoguanabara/html-css/blob/master/desafios/modulo-02/d010/desafio-android.pdf). 

Poor english translation soon. 

## Índice :earth_americas:

- [Visão geral](#visão-geral-bookmark_tabs)
  - [Screenshot](#screenshot-framed_picture)
  - [Links](#links-link)
- [Meu processo](#meu-processo-footprints)
  - [Criado com](#criado-com-hammer_and_wrench)
  - [O que aprendi](#o-que-aprendi-brain)
  - [Recursos úteis](#recursos-úteis-mag_right)
- [Autor](#autor-raising_hand_man)
- [Reconhecimentos](#reconhecimentos-pray)

## Visão geral :bookmark_tabs:

### Screenshot :framed_picture:

![Minha solução](https://github.com/braga-git/cursoemvideo-projeto-android/blob/main/imagens/projeto-android.png)

### Links :link:

- [Arquivos da solução](https://github.com/braga-git/cursoemvideo-projeto-android)
- [Site](https://braga-git.github.io/cursoemvideo-projeto-android/)

## Meu processo :footprints: 

### Criado com :hammer_and_wrench:

- HTML5
- CSS3

### O que aprendi :brain:

No capítulo 17 do curso de HTML5 e CSS3 do Curso em Vídeo, o professor Gustavo Guanabara nos desafia a criar um site seguindo apenas o modelo visual que ele disponibiliza (fora alguns materiais, como fontes e imagens).

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

![CSS de ambos os projetos](https://github.com/braga-git/cursoemvideo-projeto-android/blob/main/imagens/screenshot-css.png)

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

Agora, podemos ver que não fui tão feliz quando falamos de responsividade. Algumas coisas do meu site quebraram, como o `<main>` que deixou uma margem do fundo aparecendo. O menu de navegação, as colunas na parte inferior do site e o rodapé acabaram quebrando linhas.

| Meu projeto                                                                                | Modelo do Guanabara |
| -----------                                                                                | -----------         |
|![header](https://github.com/braga-git/cursoemvideo-projeto-android/blob/main/imagens/header-braga.jpeg) |![header](https://github.com/braga-git/cursoemvideo-projeto-android/blob/main/imagens/header-guanabara.jpeg)|
|![footer](https://github.com/braga-git/cursoemvideo-projeto-android/blob/main/imagens/footer-braga.jpeg) |![footer](https://github.com/braga-git/cursoemvideo-projeto-android/blob/main/imagens/footer-guanabara.jpeg)|

Isso ocorreu por alguns motivos, dentre eles:
1. Não coloquei as medidas corretas em algumas margens e paddings;
2. Não defini uma largura máxima e mínima para o `<main>`, isso fez com que ele ocupasse (no meu caso) sempre 75% da tela.

### Para me aprofundar :books:

Acredito que a maioria dos erros que cometi, ocorreram por falta de experiência. Sendo assim, decidi seguir o conselho de um amigo da área e investir o meu tempo em algo próprio ou em desafios. Ainda não comecei a estruturar um projeto meu, mas já andei brincando com os [desafios do Frontend Mentor](https://www.frontendmentor.io/challenges). Eu criei um repositório em meu [GitHub](https://github.com/braga-git/frontendmentor-qrcode-component) com a minha solução para o primeiro desafio do site.

Um outro hábito que decidi adotar depois de ter concluído o desafio do Projeto Android, foi visualizar projetos de outros profissionais, para entender como eles criam e o que eu posso extrair de cada um.

### Recursos úteis :mag_right:

- [Adicione um ícone a um hyperlink](https://www.youtube.com/watch?v=YJ1XUEy3oHw) - Esse foi o vídeo que vi para adicionar os ícones de corrente ao lado dos hyperlinks externos, utilizando uma imagem em `.SVG`.

- [Modelo do Projeto](https://professorguanabara.github.io/projeto-android/) - Veja o modelo do projeto hospedado no GitHub do Guanabara 

## Autor :raising_hand_man:

Me siga para mais "soluções" :wink: 

- Frontend Mentor - [@braga-git](https://www.frontendmentor.io/profile/braga-git)
- Instagram - [@braga.jpeg](https://www.instagram.com/braga.jpeg/)
- LinkedIn - [Gabriel Braga Camara](https://www.linkedin.com/in/gabrielbragacamara/)

## Reconhecimentos :pray:

Toda minha resolução para o desafio foi feita com base nos conhecimentos adquiridos nos módulos [1](https://www.cursoemvideo.com/curso/html5-css3-modulo1/) e [2](https://www.cursoemvideo.com/curso/curso-html5-e-css3-modulo-2-de-5-40-horas/) do curso de HTML5 e CSS3 do [Curso em Vídeo](https://www.cursoemvideo.com/cursos/), ministrados pelo [@gustavoguanabara](https://github.com/gustavoguanabara). 
