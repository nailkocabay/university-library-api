# OpenAPI Tasarımı Ödevi Teslim Raporu

## 👤 Öğrenci Bilgileri

* **Ad Soyad**: Nail Koçabay
* **Öğrenci Numarası**: 170422036

---

## 📂 OpenAPI YAML Dosyası

* **openapi.yaml** dosyası GitHub reposuna yüklenmiştir.
* Swagger Editor ile test edilmiştir.

### 🔗 GitHub Repo Linki

[https://github.com/nailkocabay/university-library-api](https://github.com/nailkocabay/university-library-api)

---


## 📝 API Açıklaması

### Genel Yapı

Bu API, bir üniversite kütüphane sistemini temsil etmektedir. Aşağıdaki varlıklar yer almaktadır:

- **Book**: Kitaplar (id, title, author, year)
- **User**: Kitap alan kullanıcılar (id, name, email)
- **Loan**: Ödünç alma işlemleri (userId, bookId, loanDate, returnDate)

### CRUD İşlemleri

- `GET /books` – Tüm kitapları listeler  
- `GET /books/{bookId}` – Belirli bir kitabı getirir  
- `POST /books` – Yeni kitap ekler  
- `PUT /books/{bookId}` – Kitap günceller  
- `DELETE /books/{bookId}` – Kitap siler

Benzer şekilde:
- `GET /users`, `POST /users`, `PUT /users/{userId}`, `DELETE /users/{userId}`
- `GET /loans`, `POST /loans`, `DELETE /loans/{loanId}` uç noktaları yer alır

### Components Kullanımı

- `schemas` altında `Book`, `User`, `Loan`, `Error` tanımları yer almakta.
- `responses` bölümünde başarılı ve hatalı yanıtlar şemalara bağlanmıştır.
- Parametre tanımlamaları doğrudan path üzerinde yapılmıştır (`{bookId}`, `{userId}`, `{loanId}`).

### Sayfalama ve Hata Durumları

- Sayfalama desteği `limit` ve `offset` parametreleriyle `GET /books` ve `GET /users` için tanımlanmış.
- Hata durumları `Error` nesnesi ile yönetilmekte. Tüm endpoint’lerde `400`, `404` ve `500` gibi olası durumlar tanımlanmış.

---

## 🧪 Test Notları

* `GET /books`: Kitaplar listesini döner.
* `POST /students`: Yeni öğrenci eklemek için doğru şemaya uygun JSON gönderilir.
* `PATCH /loans/{id}/return`: Ödünç kitap iade edilir.
* `400` hatası: Eksik alanlar için dönür (Swagger üzerinden test edilmiştir).

Swagger Editor'da aşağıdaki senaryolar test edilmiştir:

### ✅ `GET /books`

- Yanıt:
  ```json
  [
    {
      "id": 1,
      "title": "Introduction to AI",
      "author": "John McCarthy",
      "year": 2020
    }
  ]

---

## 📌 Ek Açıklamalar

* Proje Swagger Editor ile doğruluktan geçirilmiştir.
* Şema, enum, format ve nullable gibi detaylara dikkat edilmiştir.
* örnek veri (“example”) kullanımına yer verilmiştir.
* API yapısal olarak OpenAPI 3.0.3 standardına uygundur.
