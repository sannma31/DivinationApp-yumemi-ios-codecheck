# あなたと相性の良い都道府県アプリ

## 概要
株式会社ゆめみ インターン iOS提出課題

## 使用技術
- SwiftUI

## アプリの使用・動作・説明

- このアプリは、ユーザーが名前、誕生日、血液型を入力することで、相性の良い都道府県に関する情報が表示されるアプリです。
<table>
<tr>
<td><img src="https://private-user-images.githubusercontent.com/120109331/289011229-8b5b6206-502e-4a86-8ce2-4e801335163a.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTEiLCJleHAiOjE3MDIwMjUzNjIsIm5iZiI6MTcwMjAyNTA2MiwicGF0aCI6Ii8xMjAxMDkzMzEvMjg5MDExMjI5LThiNWI2MjA2LTUwMmUtNGE4Ni04Y2UyLTRlODAxMzM1MTYzYS5wbmc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBSVdOSllBWDRDU1ZFSDUzQSUyRjIwMjMxMjA4JTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDIzMTIwOFQwODQ0MjJaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT0xYTIxOGZiNGNhODg1YzNjMDQ1ZDE0YTk5ODU4OTllMjI5NjIyZGY0OTg5ZGI5NGE3YTA5MzhlOTI4NGQwYjFmJlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCZhY3Rvcl9pZD0wJmtleV9pZD0wJnJlcG9faWQ9MCJ9.d9t6mSJjPieJgOPxwvqHWQJIt8ZLntOQVNTDNS6hFIY" width="300"></td>

<td><img src="https://private-user-images.githubusercontent.com/120109331/289015165-9256c32d-7da5-4b3f-92a3-ff83ee5c6f8e.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTEiLCJleHAiOjE3MDIwMjU2NDgsIm5iZiI6MTcwMjAyNTM0OCwicGF0aCI6Ii8xMjAxMDkzMzEvMjg5MDE1MTY1LTkyNTZjMzJkLTdkYTUtNGIzZi05MmEzLWZmODNlZTVjNmY4ZS5wbmc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBSVdOSllBWDRDU1ZFSDUzQSUyRjIwMjMxMjA4JTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDIzMTIwOFQwODQ5MDhaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT1iN2ExNWRhZWYxZjAzMjc5MmNlMGVjM2U4OWY5ZWFkNWFjZGY1OWFmMmMwMTI4OWI4MWQyMmY5MzAwNzgwZTkzJlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCZhY3Rvcl9pZD0wJmtleV9pZD0wJnJlcG9faWQ9MCJ9.fm1B7oUKcfvvmbXJ-1CILhv7UiVzYKffl7mivi3z-4k" width="300"></td>
</tr>
</table>

## その他
- ダークモード対応
- 縦画面固定

<table>
<tr>
<td><img src="https://github.com/sannma31/DivinationApp-yumemi-ios-codecheck/assets/120109331/4ddb0eb7-77df-46d2-8076-05443f1410a1" width="300"></td>
<td><img src="https://github.com/sannma31/DivinationApp-yumemi-ios-codecheck/assets/120109331/f9c152b2-4b05-4bd5-a1c5-16cddcf5d31d" width="300"></td>
</tr>
</table>

## コード概要

### ContentView

- ユーザーが名前、誕生日、血液型を入力する画面を提供
- 入力情報を元に API にリクエストを送信

### DivinationApp

- API から受け取ったデータを表示する画面
- 画像データを非同期で取得して表示

## API 仕様

- End Point: "/my_fortune"
- HTTP Method: "POST"
- HTTP Request Headers:
  - Key: "API-Version", Value: "v1"
- HTTP Body:
  - "name": String - 占う人の名前
  - "birthday": YearMonthDay - 占う人の生年月日
  - "blood_type": String - 占う人の血液型
  - "today": YearMonthDay - 今日の日付
  - YearMonthDay 型の仕様:
  - "year": Int - 年
  - "month": Int - 月
  - "day": Int - 日
- Response Body:
  - "name": String - 都道府県の名前
  - "capital": String - 県庁所在地
  - "has_coast_line": Bool - 海岸線があるかどうか
  - "logo_url": String - ロゴの URL
  - "brief": String - 都道府県の概要
  - MonthDay 型の仕様:
    - "month": Int - 月
    - "day": Int - 日
### APIにリクエスト
```swift
        // APIのエンドポイント
        let url = URL(string: "https://yumemi-ios-junior-engineer-codecheck.app.swift.cloud/my_fortune")!
        
        // リクエストデータ
        let requestData: [String: Any] = [
            "name": name,
            "birthday": [
                "year": birthday.year,
                "month": birthday.month,
                "day": birthday.day
            ],
            "blood_type": bloodType.lowercased(),
            "today": [
                "year": today.year,
                "month": today.month,
                "day": today.day
            ]
        ]
        
        // ヘッダー
        var request = URLRequest(url: url)
        request.httpMethod = "POST"
        request.addValue("v1", forHTTPHeaderField: "API-Version")
        request.addValue("application/json", forHTTPHeaderField: "Content-Type")
```
### リクエストデータをJSONに変換
```swift
        // リクエストデータをJSONに変換
        do {
            let jsonData = try JSONSerialization.data(withJSONObject: requestData)
            request.httpBody = jsonData
        } catch {
            print("Error creating JSON data: \(error)")
            return ""  // エラーが発生した場合、空の文字列を返すか適切なエラー処理を行う
        }
```
### リクエストの送信
```swift 
        
        // URLSessionを使用してリクエストを送信
        do {
            let (data, _) = try await URLSession.shared.data(for: request)
            // Convert the response data to a Foundation object
            do {
                if let json = try JSONSerialization.jsonObject(with: data) as? [String: Any] {
                    // Now you can work with the JSON object if needed
                    Divinationname = json["name"] as! String
                    Divinationcapital = json["capital"] as! String
                    logo = json["logo_url"] as! String
                    Divinationbrief = json["brief"] as! String
                    Divinationhas_coast_line = json["has_coast_line"] as! Int
                    print(json)
                    // Assuming there's a key named "fortune" in the JSON response
                    if let fortune = json["fortune"] as? String {
                        return fortune
                    }else {
                        return ""  // Handle the case when the "fortune" key is not present in the response
                    }
                } else {
                    return ""  // Handle the case when JSONSerialization.jsonObject throws an error or the conversion is not successful
                }
            } catch {
                print("Error converting response data to JSON: \(error)")
                return ""  // Handle the error appropriately
            }
        } catch {
            print("Error: \(error)")
            return ""  // Handle the error appropriately
        }
    }
```

