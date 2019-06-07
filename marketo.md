# LANDING PAGES

Para criar um `Guided landing pages template` é preciso saber que ele tem uma sintaxe diferente. Essa sintaxe serve para especificar o que é personalizável. Apenas as regiões ou variáveis que forem especificadas como editáveis estarão disponiveis para a personalização no editor de páginas.

Existem duas maneiras como declaram algum elemento na página para marcá-lo como editável:

- Declare um objeto como um "elemento". O criador da página de destino poderá adicionar 
imagens, texto ou recursos do Marketo nessas regiões especificadas.

- Declare uma string como uma "variável". O criador da página de destino poderá substituir essa variável por uma string, cor ou estado booleano de true / false.

## TEXTOS

Atributos obrigatórios:

- `class="mktoText"`
- `Id` (Não são permitidos "-" nem "_")
- `mktoName` (Use um texto autoexplicativo)

```html
<div class="mktoText" id="exampleText" mktoName="Main Body Text">
    O texto acrescentado no editor aparecerá aqui na landing page.
</div>
```

## IMAGENS

Você tem duas opções para definir elementos de imagem editáveis. Você pode usar um `<div>`, que especifica um container no qual a imagem será inserida ou uma tag `<img>`.

### __Opção 1 - Usando `<div>`__

Atributos obrigatórios:

- `class="mktoImg"`
- `Id` (Não são permitidos "-" nem "_")
- `mktoName` (Use um texto autoexplicativo)

Exemplo:

```html
<div class="mktoImg" id="exampleImg" mktoName="Example Image">
    Imagem será adicionada aqui
</div>
```

### __Opção 2 - Usando `<img>`__

Atributos obrigatórios:

- `class="mktoImg"`
- `Id` (Não são permitidos "-" nem "_")
- `mktoName` (Use um texto autoexplicativo)

```html
<img class="mktoImg" id="exampleImg" mktoName="Example Image">
```

**OBS:** Ao usar a versão `<img>`, o HTML renderizado conterá um wrapper div gerado ao redor da tag `<img>`. Ele será configurado para classe. "MktoImg.mktoGen" e será exibido: inline-block.

## FORM

### __Snippet__

Atributos obrigatórios:

- `class="mktoSnippet"`
- `Id` (Não são permitidos "-" nem "_")
- `mktoName` (Use um texto autoexplicativo)

```html
<div class="mktoSnippet" id="exampleSnippet" mktoName="Example Snippet"></div>
```

### __Share Button__

Atributos obrigatórios:

- `class="mktoSnippet"`
- `Id` (Não são permitidos "-" nem "_")
- `mktoName` (Use um texto autoexplicativo)

```html
<div class="mktoShareButton" id="exampleShareButton" mktoName="Example Share Button"></div>
```

## VIDEO

**OBS:** Quando precisar usar o elemento de vídeo em uma landing page, a plataforma somente suporta videos do `Youtube`. Se precisar usar um video de outro serviço é recomendado usar um elemento `rich text box` e colocar o código `embed` do video.

Atributos obrigatórios:

- `class="mktoVideo"`
- `Id` (Não são permitidos "-" nem "_")
- `mktoName` (Use um texto autoexplicativo)

```html
<div class="mktoVideo" id="exampleVideo" mktoName="Example Video"></div>
```

## POLL (Votação)

Atributos obrigatórios:

- `class="mktoSnippet"`
- `Id` (Não são permitidos "-" nem "_")
- `mktoName` (Use um texto autoexplicativo)

```html
<div class="mktoPoll" id="examplePoll" mktoName="Example Poll"></div>
```

## REFERRAL (Referência)

Atributos obrigatórios:

- `class="mktoSnippet"`
- `Id` (Não são permitidos "-" nem "_")
- `mktoName` (Use um texto autoexplicativo)

```html
<div class="mktoReferral" id="exampleReferral" mktoName="Example Referral"></div>
```

## SWEEPTAKES (Sorteios)

Atributos obrigatórios:

- `class="mktoSnippet"`
- `Id` (Não são permitidos "-" nem "_")
- `mktoName` (Use um texto autoexplicativo)

```html
<div class="mktoSweepstakes" id="exampleSweepstakes" mktoName="Example Sweepstakes"></div>
```

---

# VARIÁVEIS EDITÁVEIS

Todos os tipos de variáveis ​​são usados ​​referenciando o valor de seu atributo id envolvido dentro de uma seqüência de caracteres `${}`. Eles podem ser usados ​​em qualquer parte do documento, exceto dentro de outras declarações de variáveis.

```javascript
${var1}
```

## __Declaração__

Variáveis ​​são declaradas como meta tags dentro do elemento `<head>` do template. Existem três tipos de variáveis ​​disponíveis para uso: String, Color e Boolean.

### __String__

Atributos obrigatórios

- `class="mktoString"`
- `Id` (Não são permitidos "-" nem "_")
- `mktoName` (Use um texto autoexplicativo)

Atributos opcionais:

- `default` (O valor desse atributo precisa ser String. Deixar vazio se não tiver nada)
- `allowHtml` (Valor booleano de `True` ou `False`. Controla se o valor será impresso sem ser HTML escapado. O padrão é "falso" se não for definido.)

Exemplo básico:
```html
<meta class="mktoString" id="var1" mktoName="My Variable">
```

Exemplo com todos os atributos:
```html
<meta class="mktoString" id="var1" mktoName="My Variable" default="This is my default value" allowHtml="true">
```

### __Color__

Atributos obrigatórios

- `class="mktoString"`
- `Id` (Não são permitidos "-" nem "_")
- `mktoName` (Use um texto autoexplicativo)

Atributo opcional:

- `default` (Utilizar o código hexadecimal com os 6 digitos)

Exemplo básico:
```html
<meta class="mktoColor" id="color1" mktoName="My Color Variable">
```

Exemplo com todos os atributos:
```html
<meta class="mktoColor" id="color" mktoName="My Color Variable" default="#336699">
```

### __Boolean__

Atributos obrigatórios

- `class="mktoString"`
- `Id` (Não são permitidos "-" nem "_")
- `mktoName` (Use um texto autoexplicativo)

Atributos opcionais:
- `default` (String booleana. Controles `true` ou `false` se o valor começar na posição ON ou OFF. `false` se não for fornecido.)
- `false_value` (String. O valor a ser inserido para a variável quando estiver na posição OFF. `falso` se não for fornecido.)
- `true_value` (String. O valor a ser inserido para a variável quando estiver na posição ON. `true` se não for fornecido.)
- `false_value_name` (O nome de exibição a ser mostrado no editor da landing page, quando o valor estiver OFF ele não será fornecido.)
- `true_value_name` (O nome de exibição a ser mostrado no editor da landing page, quando estivar na posição ON ele não será fornecido.)

Exemplo básico:
```html
<meta class="mktoBoolean" id="boolean1" mktoName="My Boolean Variable">
```

Exemplo com todos os atributos:
```html
<meta class="mktoBoolean" id="boolean1" mktoName="My Boolean Variable" default="true" true_value="block" false_value="none" false_value_name="Hide" true_value_name="Show">
<style>
  #myConditionalDisplayArea {
    display: ${boolean1};
  }
</style>
```

---

# CRIANDO UMA GUIDED LANDING PAGE

