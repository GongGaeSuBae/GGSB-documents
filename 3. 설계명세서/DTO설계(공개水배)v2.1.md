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
  
  - **Double** phVal / **Double** tbVal / **Double** clVal
    
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
      "dates" : [2022111424, 2022111501, 2022111502, 2022111503, 2022111504, 2022111505, 2022111506 ...]
      "pHVals": [6.0, 5.8, 6.1, ...],
      "tbVals": [0.0589, 0.06, 0.055, ...],
      "clVals": [0.9987, 0.9898, 1.105, ...]
  }
  ```
  
  - **String** state / **String** city / **String** district
  
  - **WPurification** 객체

  - **List<String>** dates
  
  - **List<Double>** phVal / **List<Double>** tbVal / **List<Double>** clVal
    
    - 일정 기간에 따른 수치를 리스트화

    - dates => 실시간(1시간주기), 일일(날짜만)
    
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
      "datetime": "2022-11-02T09:00:00"
      "dt": "2022110209구미정수장"
  }
  ```
  
  - **String** fcltyMngNm
  
  - **String** phVal / **String** tbVal / **String** clVal
    
    - phVal => pH, tbVal => 탁도 (NTU), clVal => 잔류염소(mg/L)
  
  - **String** ocrrncDt

  - **Date** datetime 
     - pattern = yyyy-MM-dd'T'HH:mm:ss

  - **String** dt
    
