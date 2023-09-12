# Cat-chatter
World outside

![buh](https://github.com/nicolasbaez/Cat-chatter/blob/main/xp012.gif)
```javascript
(k = 0), (w = 500);
h = 255;
t = 150;
setup = (_) => createCanvas(w, w, WEBGL);
draw = (_) => {
  clear();
  rotateX(k);
  rotateY(k / 2);
  for (i = 0; i <= 3; i += 0.3) {
    for (j = 0; j < 6; j += 0.3) {
      x = t * sin(i) * cos(j);
      y = t * sin(i) * sin(j);
      z = t * cos(i);
      push();
      translate(x, y, z);
      fill(noise(x) * h);
      box(noise(x, y, z) * 64);
      pop();
    }
  }
  k += 0.05;
};

function keyPressed() {
  if (key === "s") {
    saveGif("xp012.gif", 251, { delay: 0, units: "frames" });
  }
}
