# Laravel 8 望遠鏡

引入 laravel 的 telescope 套件來擴增實作開發調試工具，可以觀察資料庫、也可以觀察任務工作等。

## 使用方式
- 把整個專案複製一份到你的電腦裡，這裡指的「內容」不是只有檔案，而是指所有整個專案的歷史紀錄、分支、標籤等內容都會複製一份下來。
```sh
$ git clone
```
- 將 __.env.example__ 檔案重新命名成 __.env__，如果應用程式金鑰沒有被設定的話，你的使用者 sessions 和其他加密的資料都是不安全的！
- 當你的專案中已經有 composer.lock，可以直接執行指令以讓 Composer 安裝 composer.lock 中指定的套件及版本。
```sh
$ composer install
```
- 產生 Laravel 要使用的一組 32 字元長度的隨機字串 APP_KEY 並存在 .env 內。
```sh
$ php artisan key:generate
```
- 執行 __Artisan__ 指令的 __migrate__ 來執行所有未完成的遷移，並執行資料庫填充（如果要測試的話）。
```sh
$ php artisan migrate --seed
```
- 在瀏覽器中輸入已定義的路由 URL 來訪問，例如：http://127.0.0.1:8000。
- 你可以經由 `/user/1` 來進行使用者配置瀏覽；只能在本地環境經由 `/telescope` 來進行開發調試儀表板瀏覽。

----

## 畫面截圖
![](https://i.imgur.com/sZdXuyj.png)
> 每一個請求都會轉成 Illuminate\Http\Request 類別物件

![](https://i.imgur.com/xTE9tIq.png)
> 對資料庫進行查詢、新增、修改、刪除資料等動作執行語法查詢