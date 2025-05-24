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

* **Varlıklar (Entities)**: `books`, `students`, `loans`
* **CRUD Endpoint'leri**:

  * `GET/POST/PUT/DELETE /books`
  * `GET/POST/PUT/DELETE /students`
  * `GET/POST /loans`, `PATCH /loans/{id}/return`
* **components/schemas**: Her varlık için nesne tanımları yapıldı (Book, Student, Loan).
* **parameters**: `page`, `size` (query), `id` (path) parametreleri kullanıldı.
* **responses**: Tüm endpointlerde 200, 201, 400, 404 gibi durum kodları tanımlandı.
* **Sayfalama**: `GET /books` için `page` ve `size` parametreleriyle desteklenmektedir.
* **Hata Durumları**: Eksik veri ya da hatalı isteklerde `400 Bad Request` gibi cevaplar tanımlandı.
* **Açıklamalar ve Tag'ler**: Tüm endpointler özet ve tag ile açıklandı.

---

## 🧪 Test Notları (Opsiyonel)

* `GET /books`: Kitaplar listesini döner.
* `POST /students`: Yeni öğrenci eklemek için doğru şemaya uygun JSON gönderilir.
* `PATCH /loans/{id}/return`: Ödünç kitap iade edilir.
* `400` hatası: Eksik alanlar için dönür (Swagger üzerinden test edilmiştir).

---

## 📌 Ek Açıklamalar

* Proje Swagger Editor ile doğruluktan geçirilmiştir.
* Şema, enum, format ve nullable gibi detaylara dikkat edilmiştir.
* örnek veri (“example”) kullanımına yer verilmiştir.
* API yapısal olarak OpenAPI 3.0.3 standardına uygundur.
