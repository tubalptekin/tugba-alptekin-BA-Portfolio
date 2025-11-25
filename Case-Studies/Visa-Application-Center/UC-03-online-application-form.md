Use Case ID: UC-03

Use Case Name: Online Application Form Creation

Actor: Başvuru Sahibi (User)

Level: User Goal

Priority: High



1. Preconditions

Kullanıcı platforma giriş yapmış olmalıdır.

Kullanıcı ülke (UC-01) ve vize türü (UC-02) seçimini tamamlamış olmalıdır.

Sistem ilgili ülke/vize türüne ait başvuru formu şablonunu yükleyebilir durumda olmalıdır.




2. Postconditions

Success Postcondition

Kullanıcının başvuru formu oluşturulmuş, kaydedilmiş ve “Draft” veya “Submitted” statüsünde saklanmış olur.


Failure Postcondition

Form kaydedilememişse sistem kullanıcıya hata bildirir ve mevcut veriler kaybolmaz (autosave devrededir).




3. Main Flow

1. UA: Kullanıcı “Başvuru Oluştur” butonuna tıklar.


2. SA: Sistem seçilen ülke/vize türüne uygun form alanlarını dinamik olarak yükler.


3. SA: Form ekranda görüntülenir.


4. UA: Kullanıcı ad, soyad, pasaport bilgisi, seyahat tarihi, konaklama bilgileri vb. alanları doldurur.


5. SA: Sistem her alan için gerçek zamanlı doğrulama yapar (zorunlu alan, format kontrolü).


6. UA: Kullanıcı “Kaydet ve Devam Et” seçeneğine tıklar.


7. SA: Sistem formu taslak olarak kaydeder (Draft).


8. UA: Kullanıcı tüm alanları tamamlayıp “Başvuruyu Gönder” seçeneğine tıklar.


9. SA: Sistem final bir doğrulama yapar (tüm zorunlu alanlar + ülkeye özel kurallar).


10. SA: Sistem formu “Submitted” statüsünde kaydeder.


11. UA: Kullanıcı formun başarıyla oluşturulduğuna dair bir onay mesajı görür.





4. Alternate Flow

4A – Kullanıcı taslağı daha sonra doldurmak ister

1. UA: Kullanıcı sayfadan çıkmak ister.


2. SA: Sistem “Autosave” yapar.


3. SA: Kullanıcının taslağı “Draft” olarak saklanır.


4. UA: Kullanıcı daha sonra “Taslaklarım” bölümünden devam eder.





4B – Zorunlu alanlar boş bırakılırsa

1. SA: “Başvuruyu Gönder” tıklandığında gerekli alanları kontrol eder.


2. SA: Eksik alanların yanında uyarı mesajı gösterir.


3. UA: Kullanıcı eksikleri tamamlar.


4. Main Flow adım 8’e geri dönülür.





4C – Ülkeye özel kurallar sağlanamazsa

Ör: Seyahat süresi max 90 gün / Pasaportun 6 ay geçerlilik şartı

1. SA: Kontrol sırasında kural ihlali tespit eder.


2. SA: Kullanıcıya spesifik hata mesajı gösterir.


3. UA: Bilgileri düzeltir.


4. Main Flow 9’a geri dönülür.





4D – İnternet bağlantısı koparsa

1. SA: Sistem otomatik kaydı deneyemez.


2. UA: Kullanıcı “Bağlantı yok” uyarısını görür.


3. SA: Bağlantı geri geldiğinde form tekrar yüklenir ve en son yerel kayıt gösterilir.





5. Exception Flow

E1 – Sunucu hatası (500)

Sistem veritabanına kayıt yapamaz.

Kullanıcıya “Beklenmedik bir hata oluştu” bildirimi gösterilir.

Kullanıcının girilen verileri tarayıcı belleğinde geçici olarak tutulur.


E2 – Session Timeout

Uzun süre işlem yapılmazsa oturum süre aşımı gerçekleşir.

Kullanıcı form ekranına geri döndüğünde “Taslaklarım”dan devam etmesi sağlanır.




6. Business Rules

BR-01: Zorunlu alanlar eksiksiz doldurulmalıdır.

BR-02: Pasaport geçerlilik süresi minimum 6 ay olmalıdır.

BR-03: Seyahat başlangıç tarihi başvuru tarihinden en az 7 gün sonra olmalıdır.

BR-04: Ülkeye göre değişen alanlar sistem tarafından dinamik olarak yüklenmelidir.

BR-05: Kullanıcı taslakları 30 gün boyunca saklanır.




7. Functional Requirements Mapping

FR Code	Requirement Description

FR-03.01	Sistem form alanlarını dinamik yüklemelidir.
FR-03.02	Sistem kullanıcı girdilerini gerçek zamanlı doğrulamalıdır.
FR-03.03	Taslak kayıt desteklenmelidir (Autosave).
FR-03.04	Final doğrulama mandatory olmalıdır.
FR-03.05	Form statüsü değişiklikleri kayıt altına alınmalıdır.

