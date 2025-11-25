Requirements – Personnel Performance & Training Tracking System
1. Project Overview

Bu sistem, kurum içi personel eğitim süreçlerini takip etmek, çalışan performanslarını ölçmek ve yöneticilere karar desteği sağlayacak bir yapıyı oluşturmak amacıyla tasarlanmıştır.

Ana hedef:

Eğitim süreçlerini uçtan uca kontrol etmek

Personelin performans metriklerini izlemek

Eğitim ihtiyaçlarını otomatik önermek

Yöneticilere raporlar sağlamak

2. Stakeholders

| Paydaş                | Rol                      | Beklentiler                                                              |
| --------------------- | ------------------------ | ------------------------------------------------------------------------ |
| **Personel**          | Sistemi kullanan çalışan | Eğitimleri görmek, katılım sağlamak, performans raporlarını görüntülemek |
| **Eğitim Departmanı** | Eğitim planlaması        | Eğitim oluşturmak, program takibi yapmak                                 |
| **Yönetici**          | Performans değerlendirme | Çalışan raporlarını görmek, eğitim önerilerini incelemek                 |
| **İK Departmanı**     | Genel sistem yönetimi    | Personel kayıtlarını yönetmek                                            |
| **Sistem Admin**      | Teknik yönetim           | Kullanıcı rolleri, sistem bakım                                          |


4. Functional Requirements (Fonksiyonel Gereksinimler)
3.1 Kullanıcı Yönetimi

FR-01: Sistem personel, yönetici ve İK için ayrı kullanıcı rolleri sunmalıdır.

FR-02: Kullanıcılar giriş yapabilmelidir.

FR-03: Kullanıcı şifreleri güvenli şekilde saklanmalıdır.

3.2 Eğitim Yönetimi

FR-10: Eğitim departmanı yeni eğitimler oluşturabilmelidir.

FR-11: Eğitimlere başlangıç-bitiş tarihleri atanmalıdır.

FR-12: Personel eğitimlere kayıt olabilmelidir.

FR-13: Eğitim sonunda kullanıcı başarı durumu işlenmelidir.

3.3 Performans Yönetimi

FR-20: Sistem, çalışan performansına dair metrikler tutmalıdır.

FR-21: Yönetici, çalışan performans değerlendirmesi ekleyebilmelidir.

FR-22: Sistem performans sonuçlarını grafiklerle göstermelidir.

3.4 Eğitim Öneri Sistemi

FR-30: Sistem düşük performans alan çalışanlara otomatik eğitim önerisi vermelidir.

FR-31: Öneriler geçmiş eğitimlere ve performans verilerine göre hesaplanmalıdır.

3.5 Raporlama

FR-40: Yönetici çalışan performans raporlarını görüntüleyebilmelidir.

FR-41: Eğitim katılım raporları oluşturulmalıdır.

FR-42: Sistem PDF/Excel formatında dışa aktarım sunmalıdır.

4. Non-functional Requirements (Fonksiyonel Olmayan Gereksinimler)
4.1 Güvenlik

NFR-01: Sistem çok faktörlü kimlik doğrulama desteklemelidir.

NFR-02: Şifreler SHA-256 ile hashlenmelidir.

4.2 Performans

NFR-10: Raporlama sayfaları maksimum 3 saniyede yüklenmelidir.

NFR-11: Sistem 10.000 eş zamanlı kullanıcıyı desteklemelidir.

4.3 Kullanılabilirlik

NFR-20: Tüm kullanıcı arayüzleri mobil uyumlu olmalıdır.

NFR-21: Menü yapısı UX prensiplerine uygun olmalıdır.

4.4 Ölçeklenebilirlik

NFR-30: Sistem eğitim sayısı arttıkça performansı korumalıdır.

5. Business Rules (İş Kuralları)

BR-01: Bir çalışan aynı eğitime yalnızca 1 kez kayıt olabilir.

BR-02: Eğitim tamamlanmadan yeni performans değerlendirmesi açılamaz.

BR-03: 70 puan altında kalan personele otomatik eğitim önerisi yapılır.

BR-04: Eğitim süresi 30 günden uzun olamaz.

6. Success Metrics

%90+ eğitim tamamlama oranı

Yönetici başına haftalık ortalama 2 saat zaman kazancı

Performans değerlendirme süresinde %50 iyileşme
