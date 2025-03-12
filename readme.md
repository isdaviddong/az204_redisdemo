# Azure Cache for Redis 示範專案

此專案展示如何使用 C# 程式碼連接和操作 Azure Cache for Redis。

## 專案說明

本專案使用 StackExchange.Redis 套件來與 Azure Redis Cache 進行互動，展示基本的 Redis 操作。

## 主要功能

程式碼展示以下 Redis 操作：
- 連接到 Azure Redis Cache
- 設定字串值 (StringSet)
- 取得字串值 (StringGet)
- 執行 PING 命令
- 清空資料庫 (FLUSHDB)

## 程式碼解析

### 連接字串
```csharp
string connectionString = "____________.redis.cache.windows.net:6380,password=***,ssl=True,abortConnect=False";
```
此連接字串包含：
- Redis 主機名稱
- 連接埠 (6380)
- 存取密碼
- SSL 加密設定
- 連接中斷處理設定

### 主要操作流程
1. 建立 Redis 連接
2. 執行字串設定操作
3. 執行字串讀取操作
4. 執行 PING 指令測試連接
5. 執行資料庫清除操作

## 使用說明

1. 確保已安裝必要的 NuGet 套件：
   ```
   StackExchange.Redis
   ```

2. 更新連接字串為您的 Azure Redis Cache 實例資訊

3. 執行程式，將會看到以下操作結果：
   - SET 操作結果
   - GET 操作取得的值
   - PING 指令的回應
   - FLUSHDB 操作的結果

## 注意事項

- 請妥善保管您的 Redis 連接字串
- 在生產環境中執行 FLUSHDB 時需特別小心
- 建議實作適當的錯誤處理機制
