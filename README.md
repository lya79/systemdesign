# 系統架構學習

## Common
- 設定 /etc/host
- vendor

## HTTP API層
- vendor
- toml(github.com/naoina/toml)
- rpc(Protobuf-RPC)
- swagger
- rest api(github.com/gin-gonic/gin)
- cron(github.com/robfig/cron/tree/v3.0.0)
- docker-compose
- 目錄規劃
- 優雅關閉服務(os/signal)
- 中間件設計
- 錯誤代碼設計
- 多語系設計

## RPC服務層  
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

# 應用
- HTTP API層與 RPC服務層分離的目的
- 用戶身份驗證(登入、登出、API使用權限)
- DB連線池與讀寫分離設計