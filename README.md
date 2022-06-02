# 1anoC-Jhefrey
O nome é uma lembrança de um passarinho muito querido. 
let xBolinha = 300;
let yBolinha = 200;
let diametro = 15;
let raio = diametro / 2;

let velocidadeXBolinha = 2;
let velocidadeYBolinha = 2;

//variáveis da raquete
let xRaquete = 5
let yRaquete = 150
let raqueteComprimento = 10
raqueteAltura = 90

function setup() {
  createCanvas(600, 400);
}

function draw() {
  background(0,200,0);
  mostraBolinha();
  movimentaBolinha();
  verificaColisaoBorda();
  mostraRaquete();
  movimentaMinhaRaquete();
  verificaColisaoRaquete();
  circle(xBolinha,yBolinha,diametro);
  rect (xRaquete, yRaquete, raqueteComprimento, raqueteAltura);
  xBolinha += velocidadeXBolinha;
  yBolinha += velocidadeYBolinha;

  if (xBolinha + raio > width || xBolinha - raio < 0) {
    velocidadeXBolinha *= -1;
  }
  if (yBolinha + raio > height || yBolinha - raio < 0) {
    velocidadeYBolinha *= -1; 
}  
}
function movimentaBolinha() {
  xBolinha += velocidadeXBolinha;
  yBolinha += velocidadeYBolinha;
}

function mostraBolinha() {
  circle(xBolinha,yBolinha,diametro);
}
function verificaColisaoBorda() {
  if (xBolinha + raio > width || xBolinha - raio < 0) {
    velocidadeXBolinha *= -1;
  }
  if (yBolinha + raio > height || yBolinha - raio < 0) {
    velocidadeYBolinha *= -1; 
}  
}
function mostraRaquete() {
  rect (xRaquete, yRaquete, raqueteComprimento, raqueteAltura);
}
function movimentaMinhaRaquete() {
  if (keyIsDown(UP_ARROW)) {
    yRaquete -= 10;
  }
  if (keyIsDown(DOWN_ARROW)) {
    yRaquete += 10;
  }
}
function verificaColisaoRaquete() {
  if (xBolinha - raio < xRaquete + raqueteComprimento
     && yBolinha - raio < yRaquete + raqueteAltura
     && yBolinha + raio > yRaquete) {
    velocidadeXBolinha *= -1;
  }
}

