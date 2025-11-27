# Use Case: Continue Watching 🎬

Use Case ID: UC-VW-01

Module: Video Watching

Actor: Logged-in User

### Preconditions:

- Kullanıcı giriş yapmış olmalı.

- Sistemde ilgili video için kayıtlı bir izleme zaman damgası olabilir.

### Postconditions:

- Kullanıcının seçimine göre video 0:00’dan veya kayıtlı zaman damgasından başlatılır.

- Seçim loglanır (isteğe bağlı analytics).

## Main Flow

User selects a video from the platform.

System checks if the user has previously watched this video.

System identifies a saved timestamp (if any).

System displays a Continue Watching prompt.

User chooses either:

Resume → Video saved timestamp’ten oynar

Start Over → Video 0:00’dan başlar

## Alternative Flows

A1 – No saved timestamp exists
3a. Eğer önceki izleme kaydı yoksa:
→ System automatically starts playback from 0:00

A2 – User closes the modal
5a. Kullanıcı modalı kapatır veya karar vermez
→ Default: Playback starts from 0:00

A3 – Playback failed
6a. Video yüklenemez
→ System displays an error message

Exceptions

E01: Timestamp corrupted → Reset to 0:00

E02: Network error → Retry option is shown
