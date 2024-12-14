# React + TypeScript + Vite
# 學生管理系統
學生管理系統是一個基於前後端分離架構的應用程式，用於管理學生資料。系統支援新增、刪除、修改和查詢學生資訊，並提供篩選和統計功能。

---

## 功能簡介

1. **新增學生**：使用者可新增學生資料，包括帳號、姓名、院系等基本資訊。
2. **刪除學生**：通過學生 ID 刪除指定學生。
3. **修改資料**：更新學生的基本資訊，如姓名。
4. **查詢功能**：支持姓名搜索和按缺席次數篩選。
5. **統計分析**：計算各院系學生人數。

---

## 安裝與執行指引

### **環境需求**

- Node.js >= 16.0.0
- MongoDB >= 5.0
- npm >= 8.0.0

### **安裝步驟**

1. **clone專案**
   前端：
   ```bash
   git clone https://github.com/ETHCI-Lab/react-ts-mid.git
   ```
   後端：
   ```bash
   git clone https://github.com/ETHCI-Lab/mongoDemo.git
   ```
   

2. **安裝依賴**
   ```bash
   npm install
   ```

3. **配置環境變數**
   在專案根目錄下創建 `.env` 文件，並填寫以下內容：
   ```env
   MONGO_URI=mongodb://ceciliatest:0219test@127.0.0.1:27017/411630816
   PORT=2019
   ```

4. **啟動後端伺服器**
   使用以下命令啟動後端伺服器：
   ```bash
   npm run dev
   ```

5. **啟動前端應用**
   使用以下命令啟動前端應用：
   ```bash
   npm run dev
   ```

6. **打開應用**
   在瀏覽器中訪問 `http://localhost:5173` 開始使用。

---

## API 規格說明

### **1. 新增學生**

- **方法**：`POST /api/v1/insertOne`
- **描述**：新增學生資料。
- **請求 Body**：
  ```json
  {
    "userName": "user123",
    "name": "王小明",
    "sid": "12345",
    "department": "資訊工程",
    "grade": "3",
    "class": "資工一",
    "Email": "user123@example.com"
  }
  ```
- **回應 Body**：
  ```json
  {
    "code": 200,
    "message": "新增成功",
    "body": {
      "_id": "63b9ff2adf1c93e9a48e1234",
      "userName": "user123",
      "name": "王小明",
      "sid": "12345",
      "department": "資訊工程",
      "grade": "3",
      "class": "資工一",
      "Email": "user123@example.com"
    }
  }
  ```

---

### **2. 刪除學生**

- **方法**：`DELETE /api/v1/deleteById`
- **描述**：通過 ID 刪除學生。
- **請求參數**：
  ```
  ?id=63b9ff2adf1c93e9a48e1234
  ```
- **回應 Body**：
  ```json
  {
    "code": 200,
    "message": "刪除成功"
  }
  ```

---

### **3. 修改學生資料**

- **方法**：`PUT /api/v1/updateNameByID`
- **描述**：更新學生資料。
- **請求 Body**：
  ```json
  {
    "id": "63b9ff2adf1c93e9a48e1234",
    "name": "王大明"
  }
  ```
- **回應 Body**：
  ```json
  {
    "code": 200,
    "message": "修改成功",
    "body": {
      "_id": "63b9ff2adf1c93e9a48e1234",
      "name": "王大明",
      "sid": "12345",
      "department": "資訊工程",
      "grade": "3",
      "class": "資工一",
      "Email": "user123@example.com"
    }
  }
  ```

---

### **4. 查詢學生資料**

- **方法**：`GET /api/v1/findAll`
- **描述**：獲取所有學生資料。
- **回應 Body**：
  ```json
  [
    {
      "_id": "63b9ff2adf1c93e9a48e1234",
      "userName": "user123",
      "name": "王小明",
      "sid": "12345",
      "department": "資訊工程",
      "grade": "3",
      "class": "資工一",
      "Email": "user123@example.com",
      "absences": 2
    },
    {
      "_id": "67890ff2adf1c93e9a48e5678",
      "userName": "user456",
      "name": "李小華",
      "sid": "67890",
      "department": "商業管理",
      "grade": "2",
      "class": "商管一",
      "Email": "user456@example.com",
      "absences": 5
    }
  ]
  ```
## **架構圖**
![image](https://github.com/changwanlin/mongoDemo/blob/main/%E6%9E%B6%E6%A7%8B%E5%9C%96.drawio.png)
## **流程圖**
### **新增資料**
![image](https://github.com/changwanlin/mongoDemo/blob/main/%E6%96%B0%E5%A2%9E.drawio.png)
### **查詢資料**
![image](https://github.com/changwanlin/mongoDemo/blob/main/%E6%9B%B4%E6%96%B0.drawio.png)
### **修改資料**
![image](https://github.com/changwanlin/mongoDemo/blob/main/%E6%9B%B4%E6%96%B0.drawio.png)
### **刪除資料**
![image](https://github.com/changwanlin/mongoDemo/blob/main/%E5%88%AA%E9%99%A43.drawio.png)

