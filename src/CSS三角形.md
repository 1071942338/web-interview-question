## 1、原理
原理是利用设置 border 的颜色，通过设置各个方向的boder宽度来控制三角形，然后隐藏其他边的颜色。

## 2、准备

```css
    div {
    /*背景色方便对比显示*/
    background: #999999;
    /*必要条件*/
    box-sizing: border-box;
    /*宽高根据实际需要设置*/
    width: 100px;
    height: 100px;
    /*方便布局*/
    margin-bottom: 32px;
}
```

## 3、设置border


```css
    .border {
        border-top: 20px solid red;
        border-bottom: 20px solid green;
        border-left: 50px solid blue;
        border-right: 50px solid yellow;
    }
```

## 4、单个方向形成三角形

### 4.1、上

```css
    .border-top {
        border-top: 50px solid red;
        border-bottom: 50px solid transparent;
        border-left: 50px solid transparent;
        border-right: 50px solid transparent;
    }
```

### 4.2、下

```css
    .border-bottom {
        border-top: 50px solid transparent;
        border-bottom: 50px solid green;
        border-left: 50px solid transparent;
        border-right: 50px solid transparent;
    }
```
### 4.3、左

```css
    .border-left {
        border-top: 50px solid transparent;
        border-bottom: 50px solid transparent;
        border-left: 50px solid blue;
        border-right: 50px solid transparent;
    }
```
### 4.4、右

```css
    .border-right {
        border-top: 50px solid transparent;
        border-bottom: 50px solid transparent;
        border-left: 50px solid transparent;
        border-right: 50px solid yellow;
    }
```

## 5、组合方向形成三角形

### 5.1、左上

```css
    .border-left-top {
        border-top: 50px solid red;
        border-bottom: 50px solid transparent;
        border-left: 50px solid blue;
        border-right: 50px solid transparent;
    }
```

### 5.2、左下

```css
    .border-left-bottom {
        border-top: 50px solid transparent;
        border-bottom: 50px solid green;
        border-left: 50px solid blue;
        border-right: 50px solid transparent;
    }
```
### 5.3、右上

```css
    .border-right-top {
        border-top: 50px solid red;
        border-bottom: 50px solid transparent;
        border-left: 50px solid transparent;
        border-right: 50px solid yellow;
    }
```
### 5.4、右下

```css
    .border-right-bottom {
        border-top: 50px solid transparent;
        border-bottom: 50px solid green;
        border-left: 50px solid transparent;
        border-right: 50px solid yellow;
    }
```

> [代码链接](https://github.com/1071942338/web-interview-question/blob/main/src/CSS%E4%B8%89%E8%A7%92%E5%BD%A2.html)
