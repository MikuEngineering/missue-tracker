# missue-tracker

初問題了嗎？快來用我吧！

## Requirements

- [Docker](https://www.docker.com/)
- [ngrok](https://ngrok.com/)

## Usage

> 適用 POSIX 相容之作業系統

1. 參考[這篇教學](https://yaoandy107.github.io/line-bot-tutorial/)建立一個 LINE bot，開啟 Web Hook 功能並記下他的 Cannel Access Token 和 Cannel Secret。
2. 透過 `git` 將此 repo 下載下來。
```bash
git clone https://github.com/MikuEngineering/missue-tracker.git --recursive
```
3. 將 Cannel Access Token 和 Cannel Secret 設定為環境變數。
```bash
export LINE_CHANNEL_ACCESS_TOKEN='xxx'
export LINE_CHANNEL_SECRET='xxxxxxxxx'
```
4. 透過 `docker-compose` 執行起來。
```bash
docker-compose build && docker-compose up
```
5. 使用 `ngrok` 反向代理 LINE bot 的 port。
```bash
ngrok http 8001
```
6. 將 `ngrok` 畫面中 `Forwarding` 的網址（https 開頭的）加上 `/callback` 後設定為 LINE bot 設定頁面的 Web Hook 網址（例如：https://3bbe94ae.ngrok.io/callback）。
