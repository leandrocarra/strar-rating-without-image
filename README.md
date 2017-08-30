# Star Rating without Image

Review em forma de estrelas que não utiliza nenhuma imagem.

### Prerequisites

Feito em Scss, vc precisatá de um processador scss para gerar o css. 

```
como o gulp ou grunt por exemplo.
```

### Getting Started

#### A porcentagem das estrelas está dividida da seguinte forma. 
* 100%/5 o que nos dá 5 estrelas de 20%. 
* Ou seja, cada estrela que tiver no *style inline* 20% será uma estrela full.

* Por exemplo esse codigo equivale a 2.7 de rating 5 
* ou poderia também equivaler a 47% de 100% e assim por diante.

```html
<div class="rating-percent__full-star" style="width: 20%">&#9733;</div>
<div class="rating-percent__full-star" style="width: 20%">&#9733;</div>
<div class="rating-percent__full-star" style="width: 7%">&#9733;</div>
<div class="rating-percent__full-star" style="width: 0%">&#9733;</div>
<div class="rating-percent__full-star" style="width: 0%">&#9733;</div>
````

## Exemplo
* [JSFiddle](https://jsfiddle.net/r2kk3553/1/)

Existem alguns mixins que vc pode utilizar, são eles: 

```
Parametros:
$fontSize       = tamanho das estrelas;
$widthContainer = Coloca uma largura para centralizar o container em relação a pagina;
```

### Para mostrar o review só estrelas
```scss
@mixin showRatingStars($fontSize: 13px, $widthContainer: 100px)
```
##### No html coloque
```html
<div class="qualquerClasse">
    <div class="rating-percent__empty">
        <div class="rating-percent__empty-star">&#9733;</div>
        <div class="rating-percent__empty-star">&#9733;</div>
        <div class="rating-percent__empty-star">&#9733;</div>
        <div class="rating-percent__empty-star">&#9733;</div>
        <div class="rating-percent__empty-star">&#9733;</div>
    </div>
    <div class="rating-percent__full">
        <div class="rating-percent__full-star">&#9733;</div>
        <div class="rating-percent__full-star">&#9733;</div>
        <div class="rating-percent__full-star">&#9733;</div>
        <div class="rating-percent__full-star">&#9733;</div>
        <div class="rating-percent__full-star">&#9733;</div>
    </div>
</div>
```
##### no css utlize
```css
.qualquerClasse {
    @include showRatingStars();
}
```

### Para dar a opção de voto
```scss
@mixin toVoteStars($fontSize: 13px, $widthContainer: 200px)
```
##### No html coloque
```html
<ul class="qualquerClasse">
    <li class="to-vote__option">
        <label for="one-star" class="to-vote__bind">
            <span class="to-vote__star-empty">&#9733;</span>
        </label>
        <input type="radio" id="one-star" name="to-vote" value="1" />
    </li>
    <li class="to-vote__option">
        <label for="two-star" class="to-vote__bind">
            <span class="to-vote__star-empty">&#9733;</span>
        </label>
        <input type="radio" id="two-star" name="to-vote" value="2" />
    </li>
    <li class="to-vote__option">
        <label for="three-star" class="to-vote__bind">
            <span class="to-vote__star-empty">&#9733;</span>
        </label>
        <input type="radio" id="three-star" name="to-vote" value="3" />
    </li>
    <li class="to-vote__option">
        <label for="four-star" class="to-vote__bind">
            <span class="to-vote__star-empty">&#9733;</span>
        </label>
        <input type="radio" id="four-star" name="to-vote" value="4" />
    </li>
    <li class="to-vote__option">
        <label for="five-star" class="to-vote__bind">
            <span class="to-vote__star-empty">&#9733;</span>
        </label>
        <input type="radio" id="five-star" name="to-vote" value="5" />
    </li>
</ul>
```
##### no css utlize
```css
.qualquerClasse {
   @include toVoteStars();
}
```
* O JavaScript controla o efeito do hover e click da votacao
* No ie 8 o efeito smooth não será aplicado



### Para mostrar apenas uma estrela
```scss
@mixin singleStar($fontSize: 13px)
```
##### No html coloque
```html
<div class="rating-percent__single-star">
    <div class="rating-percent__star">&#9733;</div>
</div>
```
##### no css utlize
```css
.qualquerClasse {
   @include singleStar();
}
```
