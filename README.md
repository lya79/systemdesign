# 系統架構學習
後續章節是依據自己實務經驗做的筆記.

## 1. 使用的工具與設定
此章節會說明用到的套件工具與知識, 並且說明使用的方法.

- 設定 /etc/host
- vendor
- toml(github.com/naoina/toml)
- rpc(Protobuf-RPC)
- rest api(github.com/gin-gonic/gin)
- 中間件設計(github.com/gin-gonic/gin)
- swagger
- cron(github.com/robfig/cron/tree/v3.0.0)
- gorm(github.com/jinzhu/gorm)
- redis(github.com/go-redis/redis)
- ip位置工具(github.com/ipipdotnet/ipdb-go)
- 優雅關閉服務(os/signal)
- docker-compose

## 2. HTTP API層
此章節會說明用到哪些技術與知識, 以及為何使用.

- vendor
- toml(github.com/naoina/toml)
- rpc(Protobuf-RPC)
- swagger
- rest api(github.com/gin-gonic/gin)
- cron(github.com/robfig/cron/tree/v3.0.0)
- docker-compose
- 目錄規劃
- 優雅關閉服務(os/signal)
- 中間件設計(github.com/gin-gonic/gin)
- 錯誤代碼設計
- 多語系設計

## 3. RPC服務層  
此章節會說明用到哪些技術與知識, 以及為何使用.

- vendor
- toml(github.com/naoina/toml)
- rpc(Protobuf-RPC)
- gorm(github.com/jinzhu/gorm)
- redis(github.com/go-redis/redis)
- docker-compose
- 目錄規劃
- 優雅關閉服務(os/signal)
- 錯誤代碼設計
- 多語系設計
- ip位置工具(github.com/ipipdotnet/ipdb-go)

## 4. 應用
此章節會說明系統設計時比較常見的問題.

- HTTP API層與 RPC服務層分離的目的
- 用戶身份驗證(登入、登出、API使用權限)
- DB連線池與讀寫分離設計