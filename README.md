# app01_DevSamurai_Desenvolvimento_Web_Game-Ping-Pong
Pequeno jogo, que apesar de um clássico, é muito interessante - o Ping-Pong.

### Criando o Canvas
Para desenhar na tela, vamos usar o `canvas`, dentro do arquivo `index.html`.
E vamos pegar a largura e altura da tela:
```js
function setup() {
  canvasEl.width = canvasCtx.width = window.innerWidth
  canvasEl.height = canvasCtx.height = window.innerHeight
}

setup()
```
## 2 - Primeiros desenhos:

### Desenhando o campo
O `canvas` funciona com sobreposição de camadas. 
Sendo assim, o objeto que você desenha fica por cima dos anteriores.
```js
function draw() {
  canvasCtx.fillStyle = "#286047";
  canvasCtx.fillRect(0, 0, window.innerWidth, window.innerHeight);
}
draw();
```
Mas observe que ainda existe uma margem que vamos remover. 
Dentro da tag `<head>`, vamos definir um `<style>` para zerar as bordas.
```css
<style>
  * {
    overflow: hidden;
    margin: 0;
    padding: 0;
  }
</style>
```
Para melhorar a estética do código, vamos criar uma pasta dentro de `src` com o nome `style`, e dentro dela um arquivo CSS chamado `styleAll.css`.
No arquivo `index.html`, vamos adicionar o caminho do nosso arquivo CSS, como mostrado abaixo:
`<link rel="stylesheet" href="../src/style/styleAll.css" />`

### Desenhando a linha central.
Desenhe a linha branca que fica na metade do campo.
E para isso vamos usar a seguinte lógica:
x = larguraCampo / 2 - espessuraLinha.
y = 0.
L = espessuraLinha.
A = alturaCampo.
```js
const lineWidth = 15;
Criando os objetos com programação

canvasCtx.fillStyle = "#fff";
const x = window.innerWidth / 2 - lineWidth / 2;
const y = 0;
const w = lineWidth;
const h = window.innerHeight;
canvasCtx.fillRect(x, y, w, h);
```
Podendo fica tambem assim:
```js
const lineWidth = 15;

canvasCtx.fillStyle = "#fff";

canvasCtx.fillRect(
  window.innerWidth / 2 - lineWidth /2, 0, lineWidth, window.innerHeight
);
```

### Desenhando as raquetes:
Raquete esquerda:
```js
canvasCtx.fillRect(10, 400, lineWidth, 200);
```
aquete direita:
```js
canvasCtx.fillRect(window.innerWidth - lineWidth - 10, 120, lineWidth, 200);
```

### Desenhando a bola:
Para isso vamos entender oque o comando `arc`, pede:
0.5 * Math.PI = 1/4 do circulo.
1.0 * Math.PI = 2/4 ou 1/2 meio circulo.
1.5 * Math.PI = 3/4 do circulo.
2.0 * Math.PI = circulo.
<h1 align="center">
    <img src="../img/img_arc.png" />
</h1>

```js
canvasCtx.beginPath();
canvasCtx.arc(200, 300, 20, 0, 2 * Math.PI, false);
canvasCtx.fill();
```

### Desenhando o placar:
```js
canvasCtx.font = "bold 50px Arial";
canvasCtx.textAlign = "center";
canvasCtx.textBaseline = "top";
canvasCtx.fillStyle = "#01341D";
canvasCtx.fillText("3", window.innerWidth / 4, 50);
canvasCtx.fillText("1", window.innerWidth / 4 + window.innerWidth / 2, 50);
```

## 3 - Criando os objetos com programação