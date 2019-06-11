# JogoFinal-e-Etapas-Restantes

LÍDER : THIAGO SOUZA DE OLIVEIRA; MATRÍCULA: 20180134732
      : MOISES SIQUEIRA DE ALCANTARA; MATRÍCULA: 20180134877
     
     
     
ETAPA - 05 
////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////
var x = 100;
var y = 100;
var v = 15
var xd = 0;
var yd = 0;

var estadoDisparo = false

var vidas = 3
var pontos = 0
var dificuldade = 1


function setup() {
  createCanvas(513, 513);
}

function draw() {
  background(220);
  drawInterface();
  if(keyIsDown(LEFT_ARROW))
    x-=v;
  
  if(keyIsDown(RIGHT_ARROW))
    x+=v;

   if(keyIsDown(UP_ARROW))
    y-=v;
  
  if(keyIsDown(DOWN_ARROW))
    y+=v

  ellipse(x,y,50,50)
  if(keyIsDown( CONTROL ) && estadoDisparo == false ){
    xd = x
    yd = y
    estadoDisparo = true
}
  if (estadoDisparo == true){
  ellipse(xd, yd, 4, 4);
    yd = yd - 10;
    if (yd < 0){
    estadoDisparo = false
    }
    
}
  
}

   function drawInterface(){
    background(220);
     fill(0, 102, 153);
   textSize(18)
   text('Vidas:'+vidas, 10, 30)
    text('Pontos:'+pontos, 200, 30)
   text('Nível:'+dificuldade, 400, 30)
   
     
   }
   ////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////ETAPA - 06
////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////

var x = 250;
var y = 400;
var raioP = 25
var xo = 100;
var yo = 120;
var raioO = 30;


function setup() {
  createCanvas(500, 500);
}

function draw() {
  background(210);
  fill(225);
  ellipse(x, y, 2*raioP, 2*raioP)
  if(keyIsDown(LEFT_ARROW)){
    x = x - 5;
  }
  
  if(keyIsDown(RIGHT_ARROW)){
    x = x + 5;
  }

   if(keyIsDown(UP_ARROW)){
    y = y - 5;
   }
  
  if(keyIsDown(DOWN_ARROW)){
    y = y + 5;
  }

  
  fill(70);
  ellipse(xo, yo, 50, 50);
  if (dist(x, y, xo,yo) < raioP + raioO){
      x = 250;
      y = 400;
  
  
  }


function drawInterface(){
 
  
  rect(200,170,180,80)
}
}
////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////ETAPA - 07
////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////
var vxo = [];
var vyo = [];
var vtam = [];
var qtObjetos = 250

function setup() {
  createCanvas(500, 500);
  for (var i=0; i < qtObjetos; i++){
  vxo[i] = random(0,500);
  vyo[i] = random(0,500);
    vtam[i] = random(2,40);
  }
}

function draw() {
  background(220);
  
  for (var i=0; i < qtObjetos; i++){
    ellipse(vxo[i],vyo[i], vtam[i], vtam[i]);
}
}


////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////ETAPA - 08
////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////
var pontos = 0;
var nivel = 1;
var barreiraDePontos = 1000;

function setup() {
  createCanvas(400, 400);
  frameRate(30);
}


function draw() {
  background(0);
  textSize(24);
  fill(135, 206, 235);
  text("Nivel: "+nivel, 30,60);
  text("Pontos: "+pontos, 210,60);
  // incremento de pontos
  pontos = pontos + 10;
  
  if(pontos > barreiraDePontos){
     nivel++;
    barreiraDePontos = barreiraDePontos + 1000;
    // implementar a dinâmica de mudança de nível
    
  }
  
}
////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////
ETAPA - 09
////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////
var tempo = 0;
var tela = 1;

function setup() {
  createCanvas(400, 400);
  frameRate(30);
}

function draw() {
  if(tela == 1){
  
  // Inicio do jogo
  background(0);
  textSize(32);
  fill(235,106,15);
  text("Chuva larápia...", 50, 110);
    if (keyIsDown(ENTER)){
      tela = 2
    }
  }
  if(tela == 2){
  
  //Execução dojogo
  tempo++;
  background(0);
  textSize(32);
  fill(135,206,235);
  text("Seu popoti é meu amiegam", 50, 160);
  text("Segundos: "+(Math.floor(tempo/30)), 50, 260);
  // Situação que acaba o jogo
    if(tempo == 300){
       tela = 3;
    }
    
    if(tempo == 90){
    tela = 3;
    }
  }
  if(tela == 3){
  //Fim do jogo
  background(0);
  textSize(32);
  fill(135,206,235);
  text("The melo ru the melo bicha", 50, 210);
  // volta para a tela 1
    if(keyIsDown(32)){
      tela = 1;
      tempo = 0;
    }
}
}
////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////
ETAPA - 10
////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////
var anima;

var contFrame = 0;
var x = 0;
var paraFrames = 0;
var naveDoBem
function preload(){naveDoBem = loadImage("spiked ship 3. small.blue_.PNG"+i);
 
}
function setup() {
  
  frameRate(30);
  createCanvas(600, 400);
}

function draw() {
  background(200);
  x=x+2
  if(x>width){
    x=0;  
  }
  anima = imgsAndando[contFrame];
  //noFill
  noStroke();
  ellipse(x,50,40,40);
  imageMode(CENTER);
  image(anima, x, 50);
  
  contFrame++;
  
  if(contFrame > 3){
     contFrame = 0
  }
  
}
////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////
***JOGO - TATICAL SPACE***
----------------------------------------------------------------------------------------------------------------------------------------
var x = 200; 
var y = 250; 
var cont = 0; 
var vida = 20; 
var x1 = -100, y1 = 0; 
var naTela = true; 
var natelaVida = false; 
var nivel = 0; //FASES
var x2 = 150, y2 = 150; 
var gvida = 0;
var EllipseAleatoria = 0; 
var tempo = 100; 
var gameover = false; 
var estrelasX = [];
var estrelasY = [];
var estrelasVel = [];
var estrelasTam = []; 
var qtEstrelas = 80; 
var Img1DoBem;
var ImgRival1;
var ImgRival2;
var ImgRival3;
var ImgRival4;
var ImgRival5;
var inimigos = [];
var xo = [];
var yo = [];
var i;
var time = 0;
var sprite = 0;
var animeSpeed = 2;
var estaColidindo = false;
var song;



const NUM_IMAGES = 10;
function preload(){
     Img1DoBem = loadImage("spiked ship 3. small.blue_.PNG");
     ImgRival1 = loadImage("ship1.png");
     ImgRival2 = loadImage("large.ship_.1.PNG");
     ImgRival3 = loadImage("ship2b.png");
     ImgRival4 = loadImage("ship3.png");
     ImgRival5 = loadImage("cartoonship blue.png");
     inimigos[0] = ImgRival1;
     inimigos[1] = ImgRival2;
     inimigos[2] = ImgRival3;
     inimigos[3] = ImgRival4;
     inimigos[4] = ImgRival5;
     song = loadSound("musica_jogo.mp3");
     
}
	

function reiniciaJogo()
{
  x = 200;
  y = 250;
  naTela = true;
  cont = 0;
  vida = 3;
  estrelasX = [];
  estrelasY = [];
  estrelasVel = [];
  estrelasTam = [];    
  qtEstrelas = 80; 
  x1=-100; y1=0;
  natelaVida = false;
  nivel = 0; 
  x2 = 150; y2 = 150;
  gvida = 0;
  EllipseAleatoria = 0;
  tempo = 100;
  gameover = false;
  
  for (i = 0; i < qtEstrelas; i++)
  {
		estrelasX[i] = random(0,width);
		estrelasY[i] = random(0,height); 
		estrelasVel[i] = 2+random(0,10)/10; 
		estrelasTam[i] = random(2,4); 
  } 
		
}

function setup()
{
  createCanvas(400, 600);
  y1 =  85+random(550);

  for(j=0; j<5; j++)
  {
    xo[j] = random(25,375);
    yo[j] = -random(10,160);
  }
  
  
  frameRate(50);   
  for (i = 0; i < qtEstrelas; i++) 
  {
		estrelasX[i] = random(0,width);
		estrelasY[i] = random(0,height); 
		estrelasVel[i] = 2+random(0,10)/10; 
		estrelasTam[i] = random(2,4); 
  } 

}

function draw () 
{
  if(nivel === 0)
  {
    textSize(23);
    background(0);
    fill(255, 255, 500);
    text("Tactical space ", 125, 125);
    fill(600,10,800);
    text("Devie dos inimigos", 95,250);
    text("o máximo que você poder!!!", 60, 300);
    fill(30, 105, 400);
    text("Pressione ENTER para começar", 35, 460);
		
   if(keyIsDown(ENTER))
    {
      nivel = 1;
    }	
  }
  else if(nivel === 1)
  {
    background(0);
    if(!song.isPlaying()){
      song.loop();
    
   }
    textSize(18); 
	fill(255, 242, 0);
	text("Vidas  x  " + vida + " : " + " ", 35, 30);
    fill(255, 255, 255);
    for(i = 0; i < qtEstrelas; i++) 
    {
	  rect(estrelasX[i],estrelasY[i],estrelasTam[i],estrelasTam[i])
    }
   
   if(keyIsDown(UP_ARROW) && y>25)
    {
       y-=6;
    }
    if (keyIsDown(DOWN_ARROW) && y<575)
    {
	   y+=6;  
    }
    if (keyIsDown(LEFT_ARROW) && x>25)
    {
       x-= 6.5;
    }
    if (keyIsDown(RIGHT_ARROW) && x<375)
    {
      x+= 6.5;
    }
    
   for(k=0; k<inimigos.length; k++)
    {
      image(inimigos[k],xo[k],yo[k],50,50);
      yo[k]+=5;
      if(yo[k] > 600)
      {
        yo[k] = -random(10,50);
        xo[k] = random(10,390);
      }
     
   d = dist(x+35, y+35, xo[k]+35, yo[k]+35);
     if(d < 70)
      {
        vida = vida - 1;
	    yo[k] = -random(10,60); 
        xo[k] = random(10,390);
        estaColidindo = true;     
      }  
    }
    
   fill(106, 90, 205);
   imageMode(CENTER)
   fill(0,0,0,0)
   ellipse(x, y, 70, 70);
   image(Img1DoBem, x, y, 50, 50);
   fill(255, 255, 255);
   ellipse(x1, y1, 70, 70);
   
  d1 = dist(x+35, y+35, x1+35, y1+35);
  if(d1 < 70)
  {
	vida = vida + 1;
	y1 = random(512);
	x1 = -100;
	natelaVida = false
  }
  if(cont === 20)
  {
	natelaVida = true;
  }
  if(natelaVida === true)
  {
	x1 = x1 +20;
  } 
  
  if(cont === 300)
  {
    nivel = 4;
  }
  if(vida<0)
  {
    nivel = 5;
  }    
  }
  if(nivel == 4)
  {	
    fill(255, 255, 0);
    background(0);
    text("Vencedor", 380, 325);
    fill(0, 255, 0);
    if(tempo < 0)
    {
		tempo = 10;
		reiniciaJogo();
		nivel= 0;
        song.stop();
	}
    else
    {
	    tempo --;
    }	
   }
  if(nivel == 5) {	
    fill(255, 255, 0);
    background(0);
    fill(0, 255, 0);
    text("''PARABÉNS VOCÊ PERDEU O JOGO''", 45, 325);
   
   if(tempo < 0){
  	tempo = 10;
	reiniciaJogo();
    nivel= 0;
    song.stop();
	}
    else
    {
     tempo --;
	}	
  }	    
}
