# Unidade-II-LOP

//João Victor de Oliveira Santos
//Turma: 2D

//Definição de algumas variáveis para criação dos botões
var xBotao = 250;
var yBotao = 240;
var yBotao1 = 350;
var yBotao2 = 460;
var larguraBotao = 300;
var alturaBotao = 100;

//Botão voltar
var xVoltar = 640;
var yVoltar = 730;
var VolLargura = 100;
var VoltAltura = 50;

var tela = 0;

var img;
var prof;
var joy;

//Carregar as imagens utilizadas no menu
function preload() {
  img = loadImage("assets/5190595.png");
  prof = loadImage("foto/rosto_2.png");
  joy = loadImage("foto2/20240308_082852.jpg");
}

function setup() {
  createCanvas(800, 800);
}

function draw() {
  //Tela Menu
  if (tela == 0) {
    background(220);

    //Nome do jogo
    textSize(50);
    fill(0);
    textStyle(BOLDITALIC);
    textAlign(CENTER);
    text("Sudoku Challenge", 398, 150);
    strokeWeight(1);

    //Palavra jogar
    textSize(40);
    textStyle(NORMAL);
    fill(255);
    rect(xBotao, yBotao, larguraBotao, alturaBotao, 20);
    fill(0);
    stroke(0);
    text("Jogar", 395, 303);

    //Palavra Instruções
    fill(255);
    rect(xBotao, yBotao1, larguraBotao, alturaBotao, 20);
    fill(0);
    stroke(0);
    text("Instruções", 399, 415);

    //Palavra Créditos
    fill(255);
    rect(xBotao, yBotao2, larguraBotao, alturaBotao, 20);
    fill(0);
    stroke(0);
    text("Créditos", 399, 525);
    fill(255);
  }
  //Criação das telas
  //Tela do jogo
  if (tela == 1) {
    background(220);
    drawGrade();
    fill(255);
    strokeWeight(1);
    rect(xVoltar, yVoltar, VolLargura, VoltAltura, 20);
    textSize(20);
    fill(0);
    textAlign(CENTER);
    text("Voltar", 689, 762);
  }

  //Tela Instruções
  if (tela == 2) {
    background(220);
    image(img, 290, 480, 300, 300);

    textAlign(LEFT);
    fill(0);
    textStyle(BOLDITALIC);
    textSize(40);
    text("• Instruções e Regras", 50, 100);

    textStyle(NORMAL);
    textAlign(CENTER);
    textSize(25);
    text("• Sudoku é um jogo de raciocínio e lógica.", 295, 200);
    text(
      "• O objetivo do jogo é completar todos os quadrados utilizando números de 1 a 9.",
      50,
      230,
      470
    );
    text(
      "• Não pode haver a repetição de números nas linhas horizontais e verticais, assim como no quadrados delimitado por linhas em negrito.",
      50,
      310,
      490
    );

    fill(255);
    rect(xVoltar, yVoltar, VolLargura, VoltAltura, 20);
    textSize(20);
    fill(0);
    textAlign(CENTER);
    text("Voltar", 689, 762);
  }

  //Tela Créditos
  if (tela == 3) {
    background(220);
    image(prof, 110, 210, 145, 170);
    image(joy, 106, 450, 165, 200);
    fill(255);
    rect(xVoltar, yVoltar, VolLargura, VoltAltura, 20);

    textSize(17);
    fill(0);
    text(
      "• Doutor e mestre pelo Centro de Informática da UFPE. Graduado em Ciência da Computação pela Universidade Federal da Bahia. Professor Adjunto da ECT/UFRN e Professor do Programa de Pós-graduação em Ciência, Tecnologia e Inovação (PPgCTI) . Tem experiência na área de Ciência da Computação, com ênfase em Sistemas de Computação, atuando principalmente nos seguintes temas: Aprendizagem de Máquina, Ciência de Dados Educacionais, Robótica Educacional e Indústria 4.0.",
      270,
      250,
      500
    );
    text(
      "• Estudante de Ciências e Tecnologia da Universidade Federal do Rio Grande do Norte.",
      270,
      550,
      500
    );

    fill(0);
    textSize(40);
    text("• Créditos", 150, 100);

    fill(0);
    textSize(32);
    text("Orivaldo Vieira", 500, 170);
    text("João Victor de O.", 500, 500);

    fill(0);
    textSize(28);
    text("Função: ", 430, 220);
    text("Função: ", 390, 530);

    fill(0);
    textSize(23);
    text("Educador ", 545, 220);
    text("Estudante/Programador ", 575, 530);

    fill(0);
    textSize(25);
    textAlign(CENTER);
    text("Voltar", 689, 762);
  }
}

//Função de Clicar aos botões e ele mudar de tela
function mouseClicked() {
  if (tela == 0) {
    //botao jogar
    if (
      mouseX > xBotao &&
      mouseX < xBotao + larguraBotao &&
      mouseY > yBotao &&
      mouseY < alturaBotao + yBotao
    ) {
      tela = 1;
    }

    //botao instruções
    if (
      mouseX > xBotao &&
      mouseX < xBotao + larguraBotao &&
      mouseY > yBotao1 &&
      mouseY < alturaBotao + yBotao1
    ) {
      tela = 2;
    }

    //botao creditos//
    if (
      mouseX > xBotao &&
      mouseX < xBotao + larguraBotao &&
      mouseY > yBotao2 &&
      mouseY < alturaBotao + yBotao2
    ) {
      tela = 3;
    }
  }

  //botão para voltar
  if (
    mouseX > xVoltar &&
    mouseX < xVoltar + VolLargura &&
    mouseY > yVoltar &&
    mouseY < VoltAltura + yVoltar
  ) {
    tela = 0;
  }
}

//Criação da grade
var i;
function drawGrade() {
  strokeWeight(1);
  for (i = 0; i <= 10; i++) {
    line(70, i * 70, 700, i * 70);
    strokeWeight(1);
  }
  for (i = 0; i <= 10; i++) {
    line(i * 70, 70, i * 70, 700);
    strokeWeight(1);
  }
  for (i = 1; i <= 10; i += 3) {
    line(70, i * 70, 700, i * 70);
    line(i * 70, 70, i * 70, 700);
    line(70, 70, 700, 70);
    line(70, 70, 70, 700);
    strokeWeight(2);
  }
}
