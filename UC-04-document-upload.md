✅ UC-04: Document Upload – Detailed Use Case Specification

Use Case ID: UC-04

Use Case Name: Document Upload

Actor: Başvuru Sahibi (User)

Level: User Goal

Priority: Critical


1. Preconditions

Kullanıcı giriş yapmış ve başvuru formunu (UC-03) oluşturmuş olmalıdır.

Kullanıcının başvuru kaydı Draft veya Submitted (pre-payment) statüsünde olmalıdır.

Sistem vize türüne uygun zorunlu belge listesini yüklemiş olmalıdır.


2. Postconditions

Success Postcondition

Kullanıcı belgelerini yüklemiş ve sistem tarafından doğrulanmış şekilde kaydedilir.

Belgeler “Pending Review” statüsü ile Operasyon Departmanına aktarılır.


Failure Postcondition

Hatalı yüklenen dosya sistemde tutulmaz, kullanıcıya hata gösterilir.

Diğer yüklenen belgeler kaybolmaz.


3. Main Flow

1. UA: Kullanıcı başvuru detayında “Evrak Yükle” bölümüne girer.


2. SA: Sistem ilgili ülke/vize kategorisine göre zorunlu ve opsiyonel belge listesini gösterir.


3. UA: Kullanıcı belge türünü seçer (Pasaport, Fotoğraf, Banka Dökümü vb.).


4. UA: Kullanıcı cihazından dosya seçer veya sürükle-bırak yapar.


5. SA: Sistem dosya formatını ve boyutunu kontrol eder (pdf/jpg/png + max 10 MB).


6. SA: Sistem dosyayı virüs taramasından geçirir.


7. SA: Sistem yüklenen belgeyi önizleme şeklinde gösterir.


8. UA: Kullanıcı “Yükle” butonuna tıklar.


9. SA: Sistem dosyayı başvuruya ait belge havuzuna kaydeder.


10. SA: Bir başarı mesajı gösterilir.


11. UA: Kullanıcı diğer belgeleri yüklemeye devam eder.



4. Alternate Flow

4A – Yanlış format yüklenirse

1. SA: Sistem dosya türünü kontrol eder.


2. SA: “Geçersiz dosya formatı” uyarısı verir.


3. UA: Kullanıcı uygun dosya türünü seçer.


4. Main Flow 4’e dönülür.


4B – Boyut limitini aşarsa

1. SA: “Dosya boyutu limit aşımı (max 10 MB)” uyarısı verir.


2. UA: Dosyayı küçültür veya yeni dosya seçer.


3. Main Flow 4’e dönülür.



4C – Zorunlu belge eksik kalırsa

1. UA: Kullanıcı “Devam Et” butonuna basar.


2. SA: Sistem eksik zorunlu belgeleri kırmızı şekilde listeler.


3. UA: Eksikleri tamamlar.


4. Main Flow 3’e dönülür.



4D – İnternet bağlantısı koparsa

1. SA: Yükleme işlemi yarıda kalır.


2. SA: Sistem “Bağlantı kesildi, yükleme tamamlanamadı” mesajı gösterir.


3. UA: Bağlantı geldikten sonra yeniden dener.



5. Exception Flow

E1 – Sunucu dosyayı kaydedemez (Storage Error)

Sistem hata gösterir:
“Belge yükleme sırasında bir sorun oluştu. Lütfen tekrar deneyin.”

Sistem kullanıcıya yükleme sırasında kaybolan dosyayı tekrar seçmesi için yönlendirme yapar.



E2 – Virüs tespit edilirse

Sistem dosyayı işlemden kaldırır.

Uyarı mesajı:
“Dosyada zararlı bir içerik tespit edildi. Farklı bir dosya yükleyin.”


6. Business Rules

BR-04.01: Belgeler pdf, jpg, png formatında olmalıdır.

BR-04.02: Dosya boyutu maksimum 10 MB olabilir.

BR-04.03: Kullanıcı zorunlu belgeleri tamamlamadan sonraki adıma geçemez.

BR-04.04: Yukarı yüklendikten sonra belge silinebilir ama değiştirilirse tekrar doğrulama başlar.

BR-04.05: Her belge türü için yalnızca 1 adet geçerli belge yüklenebilir (örn. pasaport).


7. Functional Requirements Mapping

FR Code	Requirement Description

FR-04.01	Sistem zorunlu/opsiyonel belge listesini göstermelidir.
FR-04.02	Dosya format doğrulaması yapılmalıdır.
FR-04.03	Dosya boyut doğrulaması yapılmalıdır.
FR-04.04	Virüs taraması yapılmalıdır.
FR-04.05	Kullanıcı yüklenen belgeyi silebilmelidir.
FR-04.06	Belgeler güvenli depolama alanına kaydedilmelidir.


8. Non-Functional Requirements

NFR-01: Belge yükleme süresi maksimum 5 saniye olmalıdır (10 MB dosya için).

NFR-02: Belgeler en az AES-256 şifreleme ile saklanmalıdır.

NFR-03: Sistem yüksek trafikte bile %99.5 uptime sağlamalıdır.

NFR-04: Virüs tarama motoru güncel olmalıdır.