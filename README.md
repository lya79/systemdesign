# 系統架構學習

# 摘要

後續章節是依據自己實務經驗做的筆記. 

# 目錄

## 2. HTTP API層

### 2.1. 環境設定
- 設定 /etc/host

### 2.2. 系統架構
- 目錄規劃
- 優雅關閉服務(os/signal)
- 中間件設計(github.com/gin-gonic/gin)
- 錯誤代碼設計
- 多語系設計

### 2.2. 套件工具
- docker-compose
- vendor
- toml(github.com/naoina/toml)
- rpc(Protobuf-RPC)
- swagger
- rest api(github.com/gin-gonic/gin)
- cron(github.com/robfig/cron/tree/v3.0.0)

## 3. RPC服務層  

### 3.1. 系統架構
- 目錄規劃
- 優雅關閉服務(os/signal)
- 錯誤代碼設計
- 多語系設計
- DB連線池與讀寫分離設計

### 3.2. 套件工具
- docker-compose
- vendor
- toml(github.com/naoina/toml)
- rpc(Protobuf-RPC)
- gorm(github.com/jinzhu/gorm)
- redis(github.com/go-redis/redis)
- ip位置工具(github.com/ipipdotnet/ipdb-go)

## 4. 其他

- 用戶身份驗證(登入、登出、API使用權限)
    - [登入](https://github.com/lya79/systemdesign/blob/master/%E5%85%B6%E4%BB%96-%E7%94%A8%E6%88%B6%E8%BA%AB%E4%BB%BD%E9%A9%97%E8%AD%89-%E7%99%BB%E5%85%A5.md)
    - [登出](https://github.com/lya79/systemdesign/blob/master/%E5%85%B6%E4%BB%96-%E7%94%A8%E6%88%B6%E8%BA%AB%E4%BB%BD%E9%A9%97%E8%AD%89-%E7%99%BB%E5%87%BA.md)
    - [其他 API如何驗證有無登入](https://github.com/lya79/systemdesign/blob/master/%E5%85%B6%E4%BB%96-%E7%94%A8%E6%88%B6%E8%BA%AB%E4%BB%BD%E9%A9%97%E8%AD%89-%E5%85%B6%E4%BB%96API%E5%A6%82%E4%BD%95%E9%A9%97%E8%AD%89%E6%9C%89%E7%84%A1%E7%99%BB%E5%85%A5.md)
- HTTP API層與 RPC服務層分離的目的