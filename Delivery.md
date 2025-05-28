# OpenAPI Tasarımı Ödevi Teslim Raporu

## 👤 Öğrenci Bilgileri

* **Ad Soyad**: Nail Kocabay
* **Öğrenci Numarası**: 170422036

---

## 📂 OpenAPI YAML Dosyası
```
openapi: 3.0.3
info:
  title: University Library API
  version: 1.0.0
  description: API for managing university library resources
paths:
  /books:
    get:
      summary: Get list of books
      responses:
        '200':
          description: Successful response
          content:
            application/json:
              schema:
                type: array
                items:
                  $ref: '#/components/schemas/Book'
    post:
      summary: Add a new book
      requestBody:
        required: true
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/Book'
      responses:
        '201':
          description: Book created
  /books/{bookId}:
    get:
      summary: Get a book by ID
      parameters:
        - in: path
          name: bookId
          required: true
          schema:
            type: integer
      responses:
        '200':
          description: Book details
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/Book'

components:
  schemas:
    Book:
      type: object
      properties:
        id:
          type: integer
        title:
          type: string
        author:
          type: string
        year:
          type: integer
    User:
      type: object
      properties:
        id:
          type: integer
        name:
          type: string
        email:
          type: string
    Loan:
      type: object
      properties:
        userId:
          type: integer
        bookId:
          type: integer
        loanDate:
          type: string
          format: date
        returnDate:
          type: string
          format: date
    Error:
      type: object
      properties:
        message:
          type: string
          example: An error occurred

  ```

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
