🟦 BPMN – Personnel Performance & Training Tracking System

Bu doküman, sistemin uçtan uca BPMN süreç akışını tanımlar.
_Aşağıdaki süreçler BPMN 2.0 standartlarına göre açıklanmıştır._


1️⃣ Süreç: Eğitim Oluşturma

Actors: Eğitim Departmanı, Sistem

Akış:

Eğitim Departmanı → “Yeni Eğitim Oluştur” işlemi başlatır

Sistem → Eğitim formunu gösterir

Eğitim Departmanı → Eğitim adı, açıklama, tarih, kontenjan bilgilerini doldurur

Sistem → Bilgileri doğrular

Sistem → Eğitimi başarıyla kaydeder

Sistem → Eğitim listesini günceller

Notlar:

Tarih seçimi zorunludur

Kontenjan 0 olamaz

2️⃣ Süreç: Personelin Eğitime Kayıt Olması

Actors: Personel, Sistem

Akış:

Personel → Sisteme giriş yapar

Personel → “Eğitim Listesini Görüntüle”

Sistem → Mevcut eğitimleri gösterir

Personel → “Kaydol” butonuna tıklar

Sistem → Kontenjan kontrolü yapar

Sistem →

Kontenjan varsa → Kayıt başarılı

Kontenjan yoksa → Uyarı mesajı

![BPMN Diagram](./Diagram-BPMN.png) 

3️⃣ Süreç: Performans Değerlendirmesi

Actors: Yönetici, Sistem

Akış:

Yönetici → Çalışan listesini açar

Sistem → Ekibini listeler

Yönetici → Çalışan seçer

Yönetici → Performans formunu doldurur (puan + yorum + hedef)

Sistem → Puanı işler

Sistem → Puan < 70 ise “Eğitim Öner” sürecini tetikler

4️⃣ Süreç: Otomatik Eğitim Önerisi

Actors: Sistem

Akış:

Sistem → Çalışanın geçmiş performans kayıtlarını inceler

Sistem → Çalışanın aldığı eğitimleri kontrol eder

Sistem → Eksik eğitimleri belirler

Sistem → Uygun eğitimleri önerir

Sistem → Yönetici paneline “Önerilen Eğitimler” kartını ekler

5️⃣ Süreç: Raporlama

Actors: Yönetici, Sistem

Akış:

Yönetici → “Performans Raporu” sekmesini açar

Sistem → Çalışan performans verilerini çeker

Sistem → Grafikleri oluşturur

Yönetici → Raporları PDF/Excel olarak indirir



