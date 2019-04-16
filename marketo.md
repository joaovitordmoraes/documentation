# LANDING PAGES

Para criar um `Guided landing pages template` é preciso saber que ele tem uma sintaxe diferente. Essa sintaxe serve para especificar o que é personalizável. Apenas as regiões ou variáveis que forem especificadas como editáveis estarão disponiveis para a personalização no editor de páginas.

Existem duas maneiras como declaram algum elemento na página para marcá-lo como editável:

- Declare um objeto como um "elemento". O criador da página de destino poderá adicionar 
imagens, texto ou recursos do Marketo nessas regiões especificadas.

- Declare uma string como uma "variável". O criador da página de destino poderá substituir essa variável por uma string, cor ou estado booleano de true / false.

## TEXTOS

Atributos obrigatórios:

- `class="mktoText"`
- `Id`
- `mktoName` (Use um texto autoexplicativo)

```
<div class="mktoText" id="exampleText" mktoName="Main Body Text">
    O texto acrescentado no editor aparecerá aqui na landing page.
</div>
```

## IMAGENS

Você tem duas opções para definir elementos de imagem editáveis. Você pode usar um `<div>`, que especifica um container no qual a imagem será inserida ou uma tag `<img>`.

### __Opção 1 - Usando `<div>`__

Atributos obrigatórios:

- `class="mktoImg"`
- `Id`
- `mktoName`

Exemplo:

```
<div class="mktoImg" id="exampleImg" mktoName="Example Image">
    Imagem será adicionada aqui
</div>
```

### __Opção 2 - Usando `<img>`__

Atributos obrigatórios:

- `class="mktoImg"`
- `Id`
- `mktoName`

```
<img class="mktoImg" id="exampleImg" mktoName="Example Image">
```

**OBS:** Ao usar a versão `<img>`, o HTML renderizado conterá um wrapper div gerado ao redor da tag `<img>`. Ele será configurado para classe. "MktoImg.mktoGen" e será exibido: inline-block.

## FORM

