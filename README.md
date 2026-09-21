# 🔴 Red Team Saldırı Zinciri — LinkedIn Carousel Serisi

**Özgür Çakmak** tarafından hazırlanan, gerçek lab ortamında uçtan uca sızma testi senaryolarını adım adım anlatan 3 bölümlük bir sunum serisi.

> ⚠️ **Önemli Not:** Tüm içerikler yalnızca **eğitim ve farkındalık** amacıyla hazırlanmıştır. Paylaşılan teknikler yalnızca izinli ve kontrollü lab ortamlarında uygulanmıştır.

---

## 📁 Dosya Yapısı

```
attack-chain-labs/
├── 01-llmnr-poisoning/
│   └── LLMNR_Poisoning_LinkedIn_Carousel.pptx
├── 02-lateral-movement/
│   └── Lateral_Movement_LinkedIn_Carousel.pptx
└── 03-persistence/
    └── Ozgur_Cakmak_Persistence_Sunum.pptx
```

---

## 📚 Seri İçeriği

### Bölüm 1 — LLMNR Poisoning
**Active Directory Ortamında Kimlik Bilgisi Ele Geçirme**

Windows ağlarında DNS çözümlemesi başarısız olduğunda devreye giren LLMNR ve NBT-NS protokollerinin nasıl kötüye kullanılabileceğini gösterir.

**Konu Akışı:**
- Ağ keşfi (Nmap ile aktif host & port taraması)
- Responder ile LLMNR zehirleme
- NetNTLMv2 hash yakalama
- Hashcat ile sözlük saldırısı
- Ele geçirilen kimlik bilgileriyle Metasploit üzerinden sistem erişimi

**Kullanılan Araçlar:** `Nmap` · `Responder` · `Hashcat` · `Metasploit`

---

### Bölüm 2 — Lateral Movement
**"Erişilemez" Ağa Pivot Üzerinden Ulaşmak**

Farklı bir ağ segmentindeki sisteme, ele geçirilmiş dual-homed bir sunucu üzerinden tünel kurarak nasıl ulaşıldığını gösterir.

**Konu Akışı:**
- Meterpreter oturumu alma (payload + multi/handler)
- Autoroute ile ikinci ağa rota ekleme
- SOCKS Proxy kurulumu (127.0.0.1:1080)
- Proxychains ile araç trafiğini tünelleme
- Hydra ile kaba kuvvet saldırısı
- RDP üzerinden hedef sisteme erişim

**Kullanılan Araçlar:** `Metasploit` · `Autoroute` · `SOCKS Proxy` · `Proxychains` · `Hydra` · `RDP`

---

### Bölüm 3 — Persistence (Kalıcılık)
**Oturum Kapansa Bile Erişimi Sürdürmek**

Sisteme sızdıktan sonra, yeniden başlatma veya bağlantı kesilmesi durumunda erişimi otomatik olarak geri kazanmayı sağlayan iki farklı kalıcılık tekniğini gösterir.

**Konu Akışı:**

| | Yöntem 1 | Yöntem 2 |
|---|---|---|
| **Giriş** | PSExec ile Meterpreter | EternalBlue ile Meterpreter |
| **Yetki Yükseltme** | lsass.exe migrate → SYSTEM | — |
| **Teknik** | Yeni yerel kullanıcı oluşturma | Persistence/Service modülü |
| **Kalıcılık** | Kullanıcı hesabı | Windows servisi (otomatik başlar) |

**Kullanılan Araçlar:** `Metasploit` · `PSExec` · `EternalBlue` · `persistence/service`

---

## 🔗 Bağlantı

- **LinkedIn:** [linkedin.com/in/ozgur-cakmak](https://www.linkedin.com/in/ozgur-cakmak/)

---

*Bu seri, siber güvenlik farkındalığı ve mavi takım savunmacılarının saldırgan bakış açısını anlamasına katkı sağlamak amacıyla hazırlanmıştır.*
