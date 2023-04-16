# 第5章 密碼小偷 (Password Thefts) ? 建議的一些帳號存取技巧 (Account Access Tricks)?

## 一個小回顧! 來自Google的一個小小的自我”資安健檢”, Let’s go!

https://phishingquiz.withgoogle.com/?hl=zh-TW

![image](https://user-images.githubusercontent.com/89304181/229337789-660e4066-e1bf-4763-877e-67181428bbe6.png)

## 實戰1: 在 Windows 10  中設置帳戶 + 新建一個”唯讀”的新資料夾

![image](https://user-images.githubusercontent.com/89304181/229337835-a56b106e-20d0-4c26-b9d4-2eeaaf04cf3e.png)

![image](https://user-images.githubusercontent.com/89304181/229337854-2b76b9d6-dae8-4f88-aaa3-e620225a4cb6.png)


## 實戰2: Python快速回顧，並應用於身份驗證的基本概念和實作

### A. Python快速回顧

![image](https://user-images.githubusercontent.com/89304181/229340188-27a98add-b5cf-419b-a98c-197ebf0bec1c.png)

### B. 身份驗證的基本概念和實作方式

![image](https://user-images.githubusercontent.com/89304181/229340228-53121709-3117-4a8a-90d0-79e7e24a35e8.png)

![image](https://user-images.githubusercontent.com/89304181/229340231-0276ea9a-f7cc-42cc-b69f-21c84a20d0b8.png)

## 實戰3: Python程式說明與實作 - 密碼管理, 權限控制, 檢測網路攻擊指標, 審計日誌, 資料加密

### A. 密碼管理: generate_password() 函數使用 string.ascii_letters、string.digits 和 string.punctuation 來生成隨機字元，然後使用 random.choice() 函數從這些字元中隨機選擇一定長度的字元，最後使用 join() 函數將它們連接在一起並返回。

![image](https://user-images.githubusercontent.com/89304181/232279752-9bcd17cb-27a4-4da5-bc57-b54c9b8e59ab.png)

![image](https://user-images.githubusercontent.com/89304181/232280005-1ea1dfb2-8bd4-407c-8504-69ebab375e05.png)

![image](https://user-images.githubusercontent.com/89304181/232280040-1d453de6-f175-4f77-923b-41cfcc6c7b90.png)

### B. 權限控制: 首先定義了一個 User 類別，這個類別包含了用戶的名稱和權限。在初始化 User 物件時，必須提供用戶的名稱和權限列表。權限是用一個字串列表表示的，每個字串代表一個資源。

![image](https://user-images.githubusercontent.com/89304181/232279831-8f2b10f2-b7db-494d-a577-169fe6716f47.png)

### C. 檢測網路攻擊指標： 這個範例定義了一個攻擊指標列表和一個網路活動日誌，然後檢查日誌中是否包含任何攻擊指標。
![image](https://user-images.githubusercontent.com/89304181/232280164-a608820b-431c-460a-88a2-143244653b53.png)

#### 正則表達式？

![image](https://user-images.githubusercontent.com/89304181/232280206-4011bfe0-28cf-4735-9293-644869e33e90.png)

### D. 審計日誌： 這個範例將演示如何使用 Python 創建一個簡單的審計日誌系統。我們將為每個用戶訪問的資源記錄日誌，並實現一個簡單的分析工具來幫助檢測潛在的安全漏洞。

![image](https://user-images.githubusercontent.com/89304181/232280327-5d55af82-8632-4eaf-ae49-fe8df23c3ea0.png)

### E. 資料加密： Cryptography模組是Python中一個用於加密和解密的模組，提供了各種加密和解密算法以及相關的工具函數。使用Cryptography模組可以輕鬆地將機密數據進行加密，以保護其安全性。在此範例中，我們將使用 Python 實現對數據的加密和解密。

![image](https://user-images.githubusercontent.com/89304181/232280471-e168cc08-c528-4c21-b66e-c82c9b94d8c9.png)

![image](https://user-images.githubusercontent.com/89304181/232280526-e963cc89-552d-4d28-b360-5265531eae29.png)





