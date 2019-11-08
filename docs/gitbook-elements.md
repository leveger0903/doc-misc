# 元素

## 字符元素

```
# 字符大小 H1
## 字符大小 H2
### 字符大小 H3
#### 字符大小 H4
##### 字符大小 H5
###### 字符大小 H6
```

# 字符大小 H1
## 字符大小 H2
### 字符大小 H3
#### 字符大小 H4
##### 字符大小 H5
###### 字符大小 H6

## 跳脫字符

```
\# Hello
```

\# Hello

以下字符需要透過跳脫字符處理

```
\  反斜線
`  反引號
*  星號
_  底線
{} 花括號
[] 方括號
() 括號
#  井字號
+  加號
-  減號
.  句號
!  驚嘆號
```

## 分隔線

```
---
```

<br>

---

<br>

## 換行

```
This is a book.<br>
That is a pencil.
```

This is a book.<br>
That is a pencil.

## 引言區塊

```
> This is a book.<br>
That is a book.
```

> This is a book.<br>
That is a book.

## 結構清單

```
- Color
  - White
  - Gray
  - Black
- Month
  - September
  - October
  - November
- Season
- Zodiac
- Sex
```

- Color
  - White
  - Gray
  - Black
- Month
  - September
  - October
  - November
- Season
- Zodiac
- Sex

## 數字型結構清單

```
1. Color
2. Month
3. Season
4. Zodiac
5. Sex
```

1. Color
2. Month
3. Season
4. Zodiac
5. Sex

## 程式碼區塊

使用 \`\`\` 包覆,<br>
包覆於該段的內容不會被做任何轉換.<br>

````
```
function saySomething (input)
{
  return input;
}
```
````

## 表格

以下為表格樣式,<br>
並可透過冒號變更置左, 置右.<br>
(不使用冒號或是雙邊使用冒號為置中)

```
|Brand|Price|Color|
|:---|---|---:|
|Ford|1000|Light Yellow|
|Toyota|800|Grey|
|Volkswagen|1200|Black|
```

|Brand|Price|Color|
|---|---|---|
|Ford|1000|Light Yellow|
|Toyota|800|Grey|
|Volkswagen|1200|Black|


## 連結

- 絕對網址

```
This is [an example](http://example.com/ "Title") inline link.
```

This is [an example](http://example.com/ "Title") inline link.

- 相對網址

```
See my [about](/about/) page for details.
```

See my [about](/about/) page for details.

## 自動連結

- 連結

```
<http://example.com>
```

<http://example.com>

- 電子信箱

```
<address@example.com>
```

<address@example.com>

## 強調文字

- 粗體

```
Hello, My name is **Kaoru**.
```

Hello, My name is **Kaoru**.

- 斜線

```
Hello, My name is *Kaoru*.
```

Hello, My name is *Kaoru*.

## 圖片

```
![圖片說明](images-markdown/elements-1.jpg)
```

![圖片說明](images-markdown/elements-1.jpg)