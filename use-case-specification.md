# Use Case Specification – Video Watching Module

## Use Case Name
**Continue Watching From Last Position**


## 1. Actor
**User** – Platforma giriş yapan ve video izleyen kişi.


## 2. Preconditions
- Kullanıcı platforma giriş yapmış olmalıdır.
- Kullanıcı videoyu daha önce başlatmış olmalı ve sistem en az bir kez zaman bilgisini kaydetmiş olmalıdır.
- Video içeriği platformda hâlâ mevcut olmalıdır.


## 3. Main Flow
1. **UA:** Kullanıcı "Geçmiş" bölümünü açar.
2. **SA:** Sistem kullanıcının geçmişte izlediği videoları listeler.
3. **UA:** Kullanıcı daha önce yarım bıraktığı videoya tıklar.
4. **SA:** Sistem video oynatma sayfasını yükler.
5. **SA:** Sistem kullanıcıya ait son izlenilen zaman bilgisini getirir.
6. **SA:** Sistem videoyu bu süreye otomatik olarak konumlandırır.
7. **UA:** Kullanıcı videoyu kaldığı yerden izlemeye devam eder.


## 4. Alternate Flow
### **4A – İnternet Bağlantısı Kesilirse**
1. **UA:** Kullanıcı videoyu açmak ister.
2. **SA:** Sistem video oynatma sayfasını yükleyemez.
3. **SA:** Sistem "İnternet bağlantısı yok" uyarısı verir.
4. **UA:** Kullanıcı bağlantıyı yeniler.
5. **SA:** Bağlantı sağlandıktan sonra video sayfası yeniden yüklenir.
6. **SA:** Sistem kaldığı süreyi getirir ve videoyu kaldığı yerden başlatır.

### **4B – Son İzlenilen Zaman Bilgisi Bulunamazsa**
1. **SA:** Sistem son izlenen süreyi bulamaz (veri silinmiş olabilir, cihaz değişimi yapılmış olabilir).
2. **SA:** Sistem videoyu başlangıç noktasından başlatır.
3. **SA (Opsiyonel):** Kullanıcıya “Bu videoyu daha önce izlediniz ancak kaldığınız nokta bulunamadı.” bildirimi gösterilir.


## 5. Postconditions
- Kullanıcı videoyu kaldığı noktadan veya veri yoksa videonun başından izlemeye devam eder.
- Sistem yeni izleme verisini güncelleyerek kullanıcının hesabına kaydeder.
