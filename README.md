# mad012
basic fractal noise loop

![mad012](https://github.com/nicolasbaez/mad012/blob/master/mad012.gif)

```processing
float rr=0;
float gg=0;
float bb=0;
float dColor=1;
float dDots=1;
float j=0;
void setup() {
  size(512, 216);
  background(255);
}
void draw() {
  for (int i=0; i<=width; i+=dDots) {
    for (int j=0; j<=height; j+=dDots) {
      stroke(rr, gg, bb);
      point(i, j);
      rr+=random(-dColor, dColor);
      gg+=random(-dColor, dColor);
      bb+=random(-dColor, dColor);
      if (rr<0) {
        rr+=dColor*2;
      }
      if (gg<0) {
        gg+=dColor*2;
      }
      if (bb<0) {
        bb+=dColor*2;
      }
      if (rr>256) {
        rr-=dColor*2;
      }
      if (gg>256) {
        gg-=dColor*2;
      }
      if (bb>256) {
        bb-=dColor*2;
      }
    }
  }
  j++;
  if (j<=128) {
    saveFrame("gif/mad012-######.png");
  }
}
```
