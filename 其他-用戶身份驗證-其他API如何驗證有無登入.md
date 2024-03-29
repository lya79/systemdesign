# 帳號身份驗證(呼叫 API)

# 介紹 
在一般的情況下, 部份 API是需要用戶先登入後才可以使用, 因此在呼叫這些 API需要有一個機制來確保用戶已經有登入. 本章節說明如何達到 API驗證身份. 

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
        1. 檢查用戶的帳號是否可用
1. 呼叫 API Handler

# 方法
這裡只有說明中間件的 `檢查用戶權限`, 其餘部份請參考 `登入`與 `登出`流程.

## 2. 中間件(Middleware)處理
在呼叫登入API Handler之前, 會先經過中間件(Middleware), 中間件通常會由多組邏輯組合而成.

在登入時會用到的中間件, 處理順序由上至下, 參考下列:
1. Gzip壓縮
1. 檢查來源位址
1. 檢查語系
1. 檢查 Session
    1. 取出 Session
    1. 重新設定 Session  
    1. 檢查 Session
    1. Header寫入用戶資訊
1. 檢查用戶權限
    1. 取出 Header內的用戶資訊
    1. 取得用戶權限
    1. 檢查用戶權限是否可使用此 API
    1. 檢查用戶的帳號是否可用

> 備註: Gzip壓縮、檢查來源位址、檢查語系、檢查用戶權限參考 `登入`與 `登出`流程. 另外步驟 `檢查 Session`這一步驟每次執行時都會延長 Session的時效 1小時, 這樣子就可以達到 1小時內用戶沒有任何操作時, 就視為需要重新登入.

### 2.5. 檢查用戶權限
#### 2.5.2 取出 Header內的用戶資訊
這一步驟會用到的用戶資訊, 來自於步驟 `檢查 Session`.

#### 2.5.3 取得用戶權限
上一步驟取出用戶資訊後會將帳號ID、權限階層傳遞給 `RPC服務層`, 最後會在回傳帳號可用的功能給 `HTTP API層`.

#### 2.5.4 檢查用戶權限是否可使用此 API
檢查用戶權限是否允許執行當前要執行的 API.

#### 2.5.5 檢查用戶的帳號是否可用
檢查用戶的帳號是否被凍結或停用.