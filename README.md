# 系統架構學習
後續章節是依據自己實務經驗做的筆記. 

# 目錄

## 2. HTTP API層
此章節會說明用到哪些技術與知識, 以及為何使用.

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
此章節會說明用到哪些技術與知識, 以及為何使用.

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
此章節會說明特定功能的設計.

- HTTP API層與 RPC服務層分離的目的
- 用戶身份驗證(登入、登出、API使用權限)