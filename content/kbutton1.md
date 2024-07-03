# KButton1

## ボタンライブラリ
簡単にGUI部品を表示することができるようになります。

## 構文
KBSetup kbSetup = new KBSetup(papplet);<br />
KButton button = new KButton(object, callFunction, x, y, width, height, radius);<br />
<br />
- papplet : global(setup関数がある空間)のthis
- object : ボタンを使用する部分のthis(Object)
- callFunction : ボタンが押された際に呼ばれる関数名
- x : ボタンの左上のx座標
- y : ボタンの左上のy座標
- width : 横幅
- height : 縦幅
- radius : ボタンの角丸具合

## メソッド

- **座標の設定**<br />
Set button.set.position(x, y)<br />
ボタンの左上の角の座標を設定します。<br />

- **大きさの設定**<br />
Set button.set.size(width, height, radius)<br />
ボタンの縦幅、横幅、丸み具合を設定します。<br />

- **背景画像の設定**<br />
Set button.set.bgImage(image)<br />
ボタンの背景を単色から画像に変更します。<br />
image: PImage

- **ボタンの色設定**<br />
Set button.set.buttonColor(rectColor, rectEdgeColor)<br />
ボタンの背景色、輪郭線の色を設定します。<br />
rectColor: color<br />
rectEdgeColor: color<br />

- **ボタンのホバー時色設定**<br />
Set button.set.buttonHoverColor(rectHoverColor)<br />
ボタンのカーソルホバー時の背景色を設定します。<br />
rectHoverColor: color<br />

- **ボタンの文字の設定**<br />
Set button.set.label(text, labelSize)<br />
Set button.set.label(text, labelSize, font) ※overload<br />
ボタンに表示されるテキストを設定します。
text: String<br />
labelSize: float<br />
font: PFont<br />

- **ボタンの文字位置設定**<br />
Set button.set.align(horizontal, vertical)<br />
ボタンに表示されるテキストの位置を設定します。<br />
  - horizontal: int
    - LEFT
    - CENTER
    - RIGHT
  - vertical: int
    - TOP
    - CENTER
    - BOTTOM

- **ボタンの文字色設定**<br />
Set button.set.labelColor(textColor)<br />
ボタンに表示されるテキストの色を設定します。<br />
textColor: color<br />

- **ボタンの文字色設定**<br />
Set button.set.labelFont(font)<br />
ボタンに表示されるテキストのフォントを設定します。<br />
font: PFont<br />

## サンプルコード
```javascript
// kbSetup という変数名でなければならない
KBSetup kbSetup;
KButton buttonUp;
KButton buttonDown;
int counter = 0;

void setup() {
    size(500, 500);
    // mainのthis(papplet)を渡す、必ずsetup関数内で最初に記述
    kbSetup = new KBSetup(this);
    buttonUp = new KButton(this, "countUp", (width-150)/2 - 50, (height-60)/2 + 50, 100, 60, 0);
    buttonUp.set.buttonColor(color(110), color(50))
        .buttonHoverColor(color(170))
        .label("up", 15)
        .align(CENTER, CENTER)
        .labelColor(color(230, 230, 255));
    buttonDown = new KButton(this, "countDown", (width-150)/2 + 100 , (height-60)/2 + 50, 100, 60, 0);
    buttonDown.set.buttonColor(color(110), color(50))
        .buttonHoverColor(color(170))
        .label("down", 15)
        .align(CENTER, CENTER)
        .labelColor(color(230, 230, 255));
}

void draw() {
    background(255);
    fill(0);
    textAlign(CENTER, CENTER);
    textSize(30);
    text("counter: "+counter, width/2.0, height/2.0 - 50);
}

/*ボタン生成時に第2引数で設定した関数名*/
void countUp() {
    counter++;
    println("count up click", counter);
}

/*ボタン生成時に第2引数で設定した関数名*/
void countDown() {
    counter--;
    println("count down click", counter);
}
```
![](https://lh3.googleusercontent.com/u/0/drive-viewer/AKGpihaSVB1T4srcUnTVwR0SGc9rlfniZWqzgQ--W06De38JIZcfYJnJZl5-ZtRomfYluS81Y_t_ouq9EhGsOTyVMpWTsqnlyww6qR8=w1440-h765)