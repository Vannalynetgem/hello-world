# hello-world
//This a second repositary to test


PImage[] images = new PImage[3];//liste des images pouvant servir de noeud
int curveDeep = 300;//impacte la profondeur d'une courbe entre deux points 
int strokeWeight = 2;//epaisseur du trait des courbes de bezier
int nbNodes = 18;//nombre de noeuds
 
void setup(){
 taille (1024, 768);
 PImage red = loadImage ("red_maillon.png ");
 PImage yellow = loadImage ("yellow_ maillon.png"); 
 PImage blue=loadImage("blue_maillon.png");
 imageMode (CENTRE);
 images [0] = rouge;
 images [1] = jaune;
 images [2] = bleu;
 generatedMaillon();//génere le premier maillon
}


public void generatedMaillon () {
 arrière-plan (255);
 aucun remplissage();
 strokeWeight (strokeWeight);

 int x, y = 0;
 
 Node [] nodes = new Node [nbNodes];
 
 //definit une liste de points qui contient les debuts et fins de courbes
 pour (int i = 0; i <nbNodes; i ++) {
   x = (int) aléatoire (20, largeur);
   y = (int) aléatoire (20, hauteur);
   nodes[i] = (new Node(x,y));
 }
 
 //dessine les courbes de bezier 
  pour (int i = 0; i <nodes.length-1; i ++) {
   System.out.println ("ligne via les nœuds" + i);
   drawBezierCurve(curveDeep,nodes[i].x, nodes[i].y, nodes[i+1].x, nodes[i+1].y);//dessine une courbe de bezier entre deux points
  }
 
 //place les noeuds aux intersections des courbes, au dessus des courbes
 pushMatrix ();
 pour (int i = 0; i <nodes.length; i ++) {
   image (images [(int) random ( images.length)], noeuds [i] .x, noeuds [i] .y);
 }
 popMatrix ();
 
}

void draw () { 
}

void mousePressed () {
 generatedMaillon ();

}

Node de classe {
  int x;
  int et;
  
  public Node(int x, int y){
    this.x = x;
    this.y = y;
  }
    
}


void drawBezierCurve (int deepCurve, int x1, int y1, int x4, int y4) {
  
   int x2 = (int) aléatoire (x1-deepCurve, x1 + deepCurve);
   int y2 = (int) aléatoire (y1-deepCurve, y1 + deepCurve);
  
   int x3 = (int) aléatoire (x4-deepCurve, x4 + deepCurve);
   int y3 = (int) random (y4-deepCurve, y4 + deepCurve);
