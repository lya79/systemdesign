# 帳號身份驗證(呼叫 API)

# 介紹 

## 系統架構
前端 <---> HTTP API層 <---> RPC服務層 <---> DB(MySQL和 Redis)
- 前端與 HTTP API層是使用 HTTP協定溝通
- HTTP API層與 RPC服務層是使用 RPC協定溝通

## 呼叫 API流程
1. 前端呼叫 API
1. 中間件(Middleware)處理
    1. Gzip壓縮
    1. 檢查來源位址
    1. 檢查語系
    1. 檢查 session
        1. 取出 session
        1. 重新設定 Session
        1. 檢查 Session
        1. Header寫入用戶資訊
    1. 檢查用戶權限
        1. 取出 Header內的用戶資訊
        1. 取得用戶權限
        1. 檢查用戶權限是否可使用此 API
1. 呼叫 API Handler

# 方法

## 2. 中間件(Middleware)處理
### 2.5. 檢查用戶權限
#### 2.5.2 取出 Header內的用戶資訊
#### 2.5.3 取得用戶權限
#### 2.5.4 檢查用戶權限是否可使用此 API

# 結論

# 參考