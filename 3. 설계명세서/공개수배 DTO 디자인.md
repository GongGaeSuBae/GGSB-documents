## 공개수배 DTO 디자인

- CityDTO
  
  ```
  {
      "state": "경상북도",
      "city": ["고령시", "구미시", "경산시", ...]
  }
  ```
  
  - **String** state
  
  - **List<String>** city

---

- DistrictDTO
  
  ```
  {
      "city": "구미시",
      "district": ["거의동", "옥계동", "황상동", ...]
  }
  ```
  
  - **String** city
  
  - **List<String>** district

---

* WPurification
  
  ```
  {
          "wName": "구미정수장",
          "type": 0 or 1 or 2
  }
  ```
  
  - **String** wName
  
  - **int** type
    
    - 0 => 실시간
    
    - 1 => 일일
    
    - 2 => 정보X

---

* WInfo
  
  ```
  {
          "state": "경상북도",
          "city": "구미시",
          "district": "거의동",
          "waterPurification": {
              "wName": "구미정수장",
              "type": 0 or 1 or 2
          },
          "phVal": 6.0,
          "tbVal": 0.0589,
          "clVal": 0.9987
  }
  ```
  
  - **String** state / **String** city / **String** district
  
  - **WPurification** 객체
  
  - **float** phVal / **float** tbVal / **float** clVal
    
    - phVal => pH
    
    - tbVal => 탁도 (NTU)
    
    - clVal => 잔류염소 (mg/L)

---

* WGraph
  
  ```
  {
      "state": "경상북도",
      "city": "구미시",
      "district": "거의동",
      "waterPurification": {
              "wName": "구미정수장",
              "type": 0 or 1 or 2
      },
      "pHVals": [6.0, 5.8, 6.1, ...],
      "tbVals": [0.0589, 0.06, 0.055, ...],
      "clVals": [0.9987, 0.9898, 1.105, ...]
  }
  ```
  
  - **String** state / **String** city / **String** district
  
  - **WPurification** 객체
  
  - **List<float>** phVal / **List<float>** tbVal / **List<float>** clVal
    
    - 일정 기간에 따른 수치를 리스트화
    
    - phVal => pH, tbVal => 탁도 (NTU), clVal => 잔류염소(mg/L)

---

* WQuality
  
  ```
  {
      "fcltyMngNm": "구미정수장"
      "phVal": 6.0,
      "tbVal": 0.0589,
      "clVal": 0.9987,
      "ocrrncDt": "2022110209"
  }
  ```
  
  - **String** fcltyMngNm
  
  - **Double** phVal / **Double** tbVal / **Double** clVal
    
    - phVal => pH, tbVal => 탁도 (NTU), clVal => 잔류염소(mg/L)
  
  - **String** ocrrncDt
    
    - 연/월/일/시
