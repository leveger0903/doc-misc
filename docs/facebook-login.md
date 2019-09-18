# FACEBOOK 登入

## 事前準備

- 建立 composer.json, 範例如下:

```
{
  "require": {
    "google/apiclient": "^2.0"
  }
}
```

- 下載 [composer.phar](https://getcomposer.org/download/) 並放入該資料夾
- 進入該資料夾, 並下指令 `php composer.phar install` 安裝套件
- 分別建立 index.php 與 oauth2callback.php 檔案
  - index.php: 登入後取得個人資料
  - oauth2callback.php: 未登入預登入檔

## 申請 API 金鑰

