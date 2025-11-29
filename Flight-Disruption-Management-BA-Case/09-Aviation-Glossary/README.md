# ✈️ Aviation Glossary

A practical glossary of operational and technical terms used throughout this case study.

## 🛫 Core Operational Terms
OCC — Operations Control Center

Merkezi operasyon yönetim birimi.

Tüm gecikme, uçak, ekip, gate ve rota kararlarını koordine eder.

ETD — Estimated Time of Departure

Uçağın tahmini kalkış zamanı. Gecikme sonrası OCC tarafından güncellenir.

ETA — Estimated Time of Arrival

Uçağın varış istasyonuna tahmini iniş zamanı.

OTP — On-Time Performance

Havayolunun zamanında kalkış/iniş oranı.

## 📦 Passenger & Airport Systems
PNR — Passenger Name Record

Yolcu rezervasyon kaydı. Gecikme sonrası bildirim ve rebooking için temel sistemdir.

PSS — Passenger Service System

Biletleme, check-in, uçuş yönetimi ve PNR işlemlerini içerir.

DCS — Departure Control System

Check-in, boarding, bagaj etiketi (bag tag) ve kapı işlemlerini yönetir.

FIDS — Flight Information Display System

Havalimanındaki uçuş bilgi ekranları. Gate, ETD, delay reason gibi bilgileri gösterir.

AODB — Airport Operational Database

FIDS, gate yönetimi, apron, bagaj sistemleri gibi tüm havalimanı operasyonlarının merkezi veritabanı.

## 🛄 Baggage & Ground Handling
BHS — Baggage Handling System

Bagajların otomatik taşındığı bant, sorter ve yönlendirme sisteminin tamamı.

BRS — Baggage Reconciliation System

Bagajın doğru uçağa yüklenip yüklenmediğini takip eden sistem.

Ramp / Apron Operations

Uçağın etrafındaki tüm yer hizmetleri (baggage loading, pushback, catering, fueling).

## 👨‍✈️ Crew & Fleet
Crew Legality / FTL — Flight Time Limitations

Ekiplerin yasal olarak uçabileceği maksimum süre. Gecikmeler bunu etkileyebilir.

Roster / Duty Roster

Ekiplerin görev çizelgesi.

Tail Assignment / Aircraft Rotation

Uçağın gün içerisindeki uçuş sırası:
TA: Aircraft → F1 → F2 → F3 → …

Bir uçuş gecikirse sonraki tüm ayaklar (legs) etkilenir.

## 🧭 Operational Scenarios
IRROPS — Irregular Operations

Gecikme, iptal, rota değişikliği gibi normal dışı operasyon.

MCT — Minimum Connecting Time

Yolcu bağlantı süresi. Gecikmeler transfer yolcularını yüksek risk altına sokar.

Diversion

Uçağın planlanan havalimanı yerine başka bir havalimanına yönlendirilmesi.

## 🔗 Technical Integration Terms
Event-Driven Architecture

ETD değişikliği gibi bir olayın (event) OCC tarafından yayınlanıp tüm bağlı sistemlere aktarılması.

Publish / Subscribe Model

Bir sistemin olay yayınlaması → diğerlerinin dinlemesi (subscribe).

Downstream Systems

Olayı OCC'den aldıktan sonra kendi kararını veren sistemler:
FIDS, PNR, BHS, Crew Ops, Fleet Ops.

Upstream System

Kararı başlatan sistem:
OCC (primary source of truth)
