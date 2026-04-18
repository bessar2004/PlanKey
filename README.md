# PlanKey

PlanKey, arka planda çalışan ve sistem genelinde `F8` tuşunu dinleyen yerel yapay zeka (Ollama) tabanlı bir çalışma asistanıdır. Herhangi bir uygulamada metin seçip klavye kısayoluna basarak, seçili bağlam üzerinden hızlıca planlar oluşturabilirsiniz.

## Özellikler

- **Sınav Çalışma Takvimi:** Seçilen metne göre gün/saat bazlı çalışma programı.
- **Pomodoro Planı:** 25dk odak / 5dk mola döngülerine dayalı saatlik görev listesi.
- **Konu Analizi:** İçeriği önem sırasına göre ayırıp strateji oluşturma.
- **Tamamen Yerel:** API servisine ihtiyaç duymaz.

## Akış

```mermaid
flowchart LR
    A([Metin Seç]) --> B[F8]
    B --> C[Uygulama Menüsü]
    C --> D[Ollama API]
    D --> E([Sonuç Penceresi])
```

## Kurulum

Sisteminizde [Ollama](https://ollama.com) ve Python 3.8+ kurulu olmalıdır.

```bash
# 1. Ollama modelini indirin ve servisi başlatın
ollama pull gemma3
ollama serve

# 2. Bağımlılıkları kurun
pip install -r requirements.txt
```
*(Not: `kurulum.bat` dosyasını çalıştırarak Python ortamını otomatik hazırlayabilirsiniz.)*

## Başlatma

Uygulamayı arka planda terminal penceresi olmadan başlatmak için:
```bash
pythonw main.pyw
```
*(Veya direkt olarak `BASLAT.bat` dosyasına tıklayın.)*

## Yapılandırma

Kısayol tuşunu veya model tercihlerini değiştirmek için `main.pyw` dosyasının üst kısmını düzenleyin:

```python
MODEL_ADI = "gemma4:31b-cloud"
KISAYOL_METIN = keyboard.Key.f8
```

## Lisans

MIT
