# User Stories & Acceptance Criteria – Video Watching Module

## 1. 📌 Story: Continue Watching Automatically
**As a user**, I want the system to automatically save my last watched timestamp,
**so that** I can continue watching from where I left off without losing progress.

### ✔️ Acceptance Criteria
- **AC1:** Sistem videonun izlenme süresini arka planda otomatik olarak kaydetmelidir.
- **AC2:** Kullanıcı videoyu tekrar açtığında sistem otomatik olarak kaldığı süreye gitmelidir.
- **AC3:** İlerleme buluta kaydedilmeli ve cihazdan bağımsız olmalıdır.


## 2. 📌 Story: Manual Save
**As a user**, I want to manually save my current position,
**so that** önemli bir noktayı kaybetmeden sabitleyebilirim.

### ✔️ Acceptance Criteria
- **AC1:** Kullanıcı bir "Kaydet" butonuna basarak manuel olarak zaman bilgisini kaydedebilmelidir.
- **AC2:** Manuel kaydedilen süre otomatik kaydın üzerine yazılmalıdır.


## 3. 📌 Story: Adjust Video Speed
**As a viewer**, I want to change the video playback speed (0.5x, 1x, 1.5x, 2x),
**so that** videoyu öğrenme hızına göre özelleştirebilirim.

### ✔️ Acceptance Criteria
- **AC1:** Kullanıcı 0.5x, 1x, 1.5x, 2x hız seçeneklerinden birini seçebilmelidir.
- **AC2:** Video hız değişimi anında ve sorunsuz uygulanmalıdır.


## 4. 📌 Story: Enable/Disable Subtitles
**As a user**, I want to toggle subtitles on or off,
**so that** sessiz ortamda altyazıyla ya da normal şekilde izleyebilirim.

### ✔️ Acceptance Criteria
- **AC1:** Kullanıcı altyazıyı açıp kapatabilmelidir.
- **AC2:** Subtitles doğru ve senkron gösterilmelidir.
- **AC3:** Farklı dil seçenekleri kullanılabilir olmalıdır.


## 5. 📌 Story: Skip 10 Seconds
**As a viewer**, I want to skip forward or backward by 10 seconds,
**so that** istediğim bölüme hızlıca gidebilirim.

### ✔️ Acceptance Criteria
- **AC1:** Kullanıcı 10 sn geri ve ileri alma butonlarıyla videoyu kontrol edebilmelidir.
- **AC2:** Sağ tarafa çift tık → 10 saniye ileri.
- **AC3:** Sol tarafa çift tık → 10 saniye geri.


## 6. 📌 Story: View Watch Progress
**As a user**, I want to see my video completion percentage,
**so that** videonun ne kadarını tamamladığımı takip edebilirim.

### ✔️ Acceptance Criteria
- **AC1:** Kullanıcı ilerleme yüzdesini (%) görebilmelidir.
- **AC2:** Yüzde değeri izlenen sürenin toplam süreye oranı olarak hesaplanmalıdır.
