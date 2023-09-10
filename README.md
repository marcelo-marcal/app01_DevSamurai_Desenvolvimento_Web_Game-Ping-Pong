# app01_DevSamurai_Desenvolvimento_Web_Game-Ping-Pong
Pequeno jogo, que apesar de um clássico, é muito interessante - o Ping-Pong.

### Criando o Canvas
Para desenha na tela vamos usar o `canvas`, dentro do arquivo `index.html`.
E vamos pega a largura e altura da tela:
```js
function setup() {
  canvasEl.width = canvasCtx.width = window.innerWidth
  canvasEl.height = canvasCtx.height = window.innerHeight
}

setup()
```

### Desenhando o campo
O canvas funciona com sobre posição de camadas.
Sendo assim o objeto que você vai desenhando vai ficando um por cima do outro.
```js
function draw() {
  canvasCtx.fillStyle = "#286047";
  canvasCtx.fillRect(0, 0, window.innerWidth, window.innerHeight);
}
draw();
```
Mas observe que ainda existe uma margem que vamos remover.
Dentro da tag `<head>` vamos definir um `<style>`, para zera as bordas.
```css
<style>
  * {
    overflow: hidden;
    margin: 0;
    padding: 0;
  }
</style>
```
Para melhora a stetica do codigo vamos criar uma pasta dentro de `src`, com o nome `style` e dentro um arquivo css `styleAll.css`.
E no aquivo `index.html` vamos adicino o caminho do nosso arquivo `css`, como mostra a baixo:
`<link rel="stylesheet" href="../src/style/styleAll.css" />`

Agora vamos desenha os elementos na tela:
```

```
