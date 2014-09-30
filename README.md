import processing.pdf.*;

  //1. verticaal1: paars, oranje, lichtblauw 
  //2. horizontaal1: rood, donkerblauw, groen
  //3. verticaal2: rood, donkerblauw, groen 
  //4. horizontaal2: lila, beige, lichtblauw

void setup() {
 color paars, oranje, lichtblauw, rood, donkerblauw, groen, lila, beige;
   paars = color(173, 119, 245);      //codes toekennen aan de woorden
   oranje = color(255, 157, 8);       //is makkelijker en sneller voor later
   lichtblauw = color(149, 216, 242);
   rood = color(222, 4, 4);
   donkerblauw = color(45, 59, 134);
   groen = color(35, 196, 34);
   lila = color(211, 178, 255);
   beige = color(250, 214, 146);
   
   color[] colorsVert1 = {          //kleuren toekennen aan lagen
     paars, oranje, lichtblauw
   };
   
   color[] colorsVert2 = {
     rood, donkerblauw, groen
   };
   
   color[] colorsHor1 = {
     rood, donkerblauw, groen
   };
   
   color[] colorsHor2 = {
     lila, beige, lichtblauw
   };
        

 size(800, 600);
 beginRecord(PDF, "OpdrachtKleedje.pdf");
 background(255);
 strokeWeight(10);
 drawVertical1(colorsVert1);
 drawHorizontal1(colorsHor1);
 drawVertical2(colorsVert2);
 drawHorizontal2(colorsHor2);
 
}

void drawVertical1(color[] colors) {
 for (int i = 0; i <20; i++) { 
  stroke(colors[getCorrectColorIndex(i)]);
   line(i*40 + 30, 0, i*40 + 30, height); 
  }
 }
 
 void drawVertical2(color[] colors){
 for (int i = 0; i <20; i++) {
  stroke(colors[getCorrectColorIndex(i)]);
    line(i*40 + 10, 0, i*40 + 10, height);
 }
}

 void drawHorizontal1(color[] colors){
   for (int i = 0; i < 20; i++){
     stroke(colors[getCorrectColorIndex(i)]);
     line(0, i*40 + 10, width, i*40 + 10);
 }
 }
 
 void drawHorizontal2(color[] colors) {
   for(int i = 0; i<20; i++) {
     stroke(colors[getCorrectColorIndex(i)]);
     line(0, i*40 + 30 , width, i*40 + 30);
  
endRecord();
 }
 }
 
 int getCorrectColorIndex(int i) {
   return i % 3;  


 }
    

