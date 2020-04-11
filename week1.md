# 目錄

- [熱鍵與 emmet](#q1)
- [英打速度](#q2)
- [VSCode Plugins - TabNine](#q3)
- [容器觀念](#q4)
- [box-model](#q5)
- [行距設定](#q6)
- [Reset VS Normalize](#q7)
- [父層滿版，子層置中，共用語法抽取術](#q8)
- [觀念分享](#q9)
- [額外知識](#q10)

<br>

<h2 id="q1">熱鍵與 emmet</h2>

[熱鍵中文表](https://github.com/hexschool/VSCode_Hotkey_Translation)

幾乎全程使用 [emmet](https://docs.emmet.io/cheat-sheet/) 來開發

<br>

<h2 id="q2">英打速度</h2>

透過 [keybr.com](http://keybr.com/) 練習英打 ( [教學影片](https://www.youtube.com/playlist?list=PLYrA-SsMvTPOxjOi9BvWLJcbGLULH-uQF) )

刻意練習 [emmet](https://www.youtube.com/watch?v=l6iWMjlK2YU&list=PLYrA-SsMvTPOxjOi9BvWLJcbGLULH-uQF&index=7&t=0s) 與常見英文命名鍵位 ( [程式碼片段](https://github.com/hexschool/EmmetPractice) )

<br>

<h2 id="q3">VSCode Plugins - TabNine</h2>

[官網](https://www.tabnine.com/)

[GitHub](https://github.com/zxqfl/TabNine)

[詳細介紹](https://mp.weixin.qq.com/s/y7MZijv44mVqEWtTzHg4nw)

<br>

<h2 id="q4">容器觀念</h2>

網頁可以切分為 **容器** 與 **元素**

<br>

### 區塊元素

- 會另起一行
- 會盡可能 **撐滿父元素**
- 可以設定 **寬高**
- `h1`、`p`、`ul`、`li`

<br>

### 行內元素 ( 文字內容 )

- 不滿版
- 並排
- 寬高不理你 ( 可設定 `display:block` 變區塊處理 )

<br>

<h2 id="q5">box-model</h2>

```css
.box {
  width: 50px;
  height: 50px;
  padding-right: 30px;
  background: #000;
  border: 3px solid #000;
}
```

區塊寬度為 `86px` 

( `width: 50px` + `padding-right: 30px` + `border 3px * 2` )

<br>

但是加上這行 css 設定

```css
* {
  box-sizing: border-box;
}
```

區塊寬度為 `50px`

<br>

加上這設定就不會去管你的 `padding`、`border`

而是看 `width` 設定多少就是多少

就不用再去加加減減算出寬度

<br>

<h2 id="q6">行距設定</h2>

請問這 p 段落高度多少呢？

```html
<p>Lorem, ipsum dolor.</p>
```

```css
p {
  font-size: 16px;
  line-height: 24px;
}
```

答案為： **24px**

<br>

請問這 p 段落與圖片的距離多少呢？

```html
<p>Lorem, ipsum dolor.</p>
<img src="./images/photo.png" alt="" />
```

```css
p {
  font-size: 16px;
  line-height: 24px;
  margin-bottom: 30px;
}
```

答案為：**34px**

30 + ( 24 - 16 ) / 2

<br>

請問當 p 段落為 **兩行** 整個 `.box` 高度為多少？ ( 請添加 css reset )

```html
<div class="box">
  <p>
    Lorem, ipsum dolor. Lorem ipsum dolor sit amet consectetur adipisicing
    elit. Fugiat, quos. Lorem ipsum dolor sit amet consectetur adipisicing
    elit. Sint, eveniet. Lorem ipsum dolor sit amet consectetur adipisicing
    elit. Perspiciatis, veniam.
  </p>
  <img src="./images/photo.png" alt="" />
</div>
```

```css
p {
  font-size: 16px;
  line-height: 24px;
  margin-bottom: 30px;
}

img {
   height: 30px;
}
```

答案為： **110px**

24 + 24 + 30 + 30 + 2 ( img 底部會自動留白 2 ~ 3px 出來 )

可以至 google 關鍵字： `css img 3px`

因為 `img` 是 `inline` 可以設定為 `block` 就可以解決留白問題

```css
img {
   height: 30px;
   display: block;
}
```

這樣答案就會變成 **108px**

<br>

<h2 id="q7">Reset VS Normalize</h2>

[https://hedgehogkucc.github.io/2020-03-30-%E5%89%8D%E7%AB%AF%E9%9D%A2%E8%A9%A6%E5%95%8F%E9%A1%8C%E9%9B%86-2/#css-q2](https://hedgehogkucc.github.io/2020-03-30-%E5%89%8D%E7%AB%AF%E9%9D%A2%E8%A9%A6%E5%95%8F%E9%A1%8C%E9%9B%86-2/#css-q2)

<br>

<h2 id="q8">父層滿版，子層置中，共用語法抽取術</h2>

[CodePen](https://codepen.io/hedgehogkucc/pen/eYpmQJx?editors=1100)

<br>

<h2 id="q9">觀念分享</h2>

- 推擠方向請盡量一致，以便維護，例如 `margin-bottom`
- 透過父層統一設定 `padding` 來留白
- `img` 底部會自動留白 2 ~ 3px 出來

<br>

<h2 id="q10">額外知識</h2>

> 設計多大的 size 較適合人的手指點擊呢？

- 44px  ( IOS APP Guidelines )

<br>

> 人的眼睛一行只能看 25 ~ 40 個字

<br>

> Adobe XD 設計文件，點擊一個元素後，按住 option ( alt ) 移到另一個元素，就可以知道相差距離多少

<br>

> command + enter ( 不管游標位置在哪直接跳下一行 )

<br>

> shift + option ( alt ) + 上下鍵 ( 可以複製 )