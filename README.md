# HTTP & HTTPS Status Codes: Ultimate Edition (2026)

```console
 ██╗   ██╗██╗     ████████╗██╗███╗   ███╗ █████╗ ████████╗███████╗
 ██║   ██║██║     ╚══██╔══╝██║████╗ ████║██╔══██╗╚══██╔══╝██╔════╝
 ██║   ██║██║        ██║   ██║██╔████╔██║███████║   ██║   █████╗  
 ██║   ██║██║        ██║   ██║██║╚██╔╝██║██╔══██║   ██║   ██╔══╝  
 ╚██████╔╝███████╗   ██║   ██║██║ ╚═╝ ██║██║  ██║   ██║   ███████╗
  ╚═════╝ ╚══════╝   ╚═╝   ╚═╝╚═╝     ╚═╝╚═╝  ╚═╝   ╚═╝   ╚══════╝
```

> **Dünyadaki en detaylı Web dökümantasyonu:** Bu rehber; IANA (Standard), WebDAV, Cloudflare, Nginx, AWS, IIS, Laravel ve Twitter tarafından tanımlanmış bilinen **tüm HTTP ve HTTPS durum kodlarını** tek bir kaynakta toplar.

---

## 🔒 Güvenlik Notu (HTTP vs HTTPS)
HTTP ve HTTPS aynı durum kodlarını kullanır. Fark, iletişim katmanındadır (SSL/TLS). Güvenlik, sertifika veya el sıkışma hatalarını ifade eden kodlar dökümanda `🔒` ikonu ile vurgulanmıştır.

---

## 📅 Hızlı Erişim
1. [1xx - Bilgilendirme](#1xx-bilgilendirme) | 2. [2xx - Başarı](#2xx-başarı) | 3. [3xx - Yönlendirme](#3xx-yönlendirme) | 4. [4xx - İstemci Hatası](#4xx-istemci-hatası) | 5. [5xx - Sunucu Hatası](#5xx-sunucu-hatası) | 6. [Özel Servis Kodları](#servis-sağlayıcıya-özel-kodlar)

---

## ℹ️ 1xx Bilgilendirme Kodları
İsteğin sunucuya ulaştığını ve işlenmeye devam ettiğini belirleyen geçici yanıtlardır.

| Kod | Durum | Teknik Açıklama (Referans) | 🔒 |
|:---:|:---|:---|:---:|
| `100` | **Continue** | İsteğin başlığı alındı, gövde gönderilebilir (RFC 9110). | |
| `101` | **Switching Protocols** | Protokol değiştiriliyor (Örn: WebSocket - RFC 9110). | |
| `102` | **Processing** | İstek alındı ancak henüz bir yanıt üretilemedi (RFC 2518). | |
| `103` | **Early Hints** | Sunucu cevabı hazırlarken kaynak ön-yüklemesi yapar (RFC 8297). | |

---

## ✅ 2xx Başarı Kodları
İsteğin sunucu tarafından başarıyla alındığını ve sonuçlandırıldığını belirtir.

| Kod | Durum | Teknik Açıklama (Referans) | 🔒 |
|:---:|:---|:---|:---:|
| `200` | **OK** | Standart başarılı yanıt (RFC 9110). | |
| `201` | **Created** | İstek başarılı oldu ve yeni bir kaynak oluşturuldu (RFC 9110). | |
| `202` | **Accepted** | İstek kabul edildi, asenkron işleme devam ediyor (RFC 9110). | |
| `203` | **Non-Authoritative** | Yanıt aracı sunucudan (proxy/cache) geliyor (RFC 9110). | |
| `204` | **No Content** | Başarılı, ancak içerik döndürülmüyor (RFC 9110). | |
| `205` | **Reset Content** | İstemci formu/görünümü sıfırlamalı (RFC 9110). | |
| `206` | **Partial Content** | İstenen kısmî veri döndü (Range - RFC 9110). | |
| `207` | **Multi-Status** | Çoklu durum kodları mevcut (RFC 4918). | |
| `208` | **Already Reported** | Daha önce bildirilen içerik tekrar edilmedi (RFC 5842). | |
| `226` | **IM Used** | Mevcut kaynağın manipüle edilmiş hali döndü (RFC 3229). | |

---

## ↪️ 3xx Yönlendirme Kodları
İstek adresinin değiştiğini veya kaynağın başka bir yerde olduğunu belirtir.

| Kod | Durum | Teknik Açıklama (Referans) | 🔒 |
|:---:|:---|:---|:---:|
| `300` | **Multiple Choices** | Birden fazla yanıt seçeneği mevcut (RFC 9110). | |
| `301` | **Moved Permanently** | Kalıcı yönlendirme. SEO için en önemli koddur (RFC 9110). | |
| `302` | **Found** | Geçici yönlendirme (RFC 9110). | |
| `303` | **See Other** | Kaynak farklı bir URI'da aranmalı (GET ile - RFC 9110). | |
| `304` | **Not Modified** | Kaynak değişmedi, cache kullanılabilir (RFC 9110). | |
| `307` | **Temporary Redirect** | Geçici yönlendirme, HTTP metodu korunur (RFC 9110). | |
| `308` | **Permanent Redirect** | Kalıcı yönlendirme, HTTP metodu korunur (RFC 9110). | |

---

## ❌ 4xx İstemci Hata Kodları (En Kapsamlı Liste)
Hatalı URL, yetki eksikliği veya güvenlik sorunlarını ifade eder.

| Kod | Durum | Teknik Açıklama (Referans / Servis) | 🔒 |
|:---:|:---|:---|:---:|
| `400` | **Bad Request** | Hatalı istek, sözdizimi uyuşmuyor (RFC 9110). | |
| `401` | **Unauthorized** | Kimlik doğrulaması gerekiyor (RFC 9110). | |
| `403` | **Forbidden** | Erişim yasak, yetkiniz yok (RFC 9110). | |
| `404` | **Not Found** | Kaynak bulunamadı (RFC 9110). | |
| `405` | **Method Not Allowed** | Metod (Örn: DELETE) izinsiz (RFC 9110). | |
| `408` | **Request Timeout** | İstek zaman aşımına uğradı (RFC 9110). | |
| `409` | **Conflict** | İstek sunucudaki kaynak ile çakışıyor (RFC 9110). | |
| `410` | **Gone** | Kaynak kalıcı olarak silindi (RFC 9110). | |
| `418` | **I'm a teapot** | 1 Nisan şakası: "Ben bir çaydanlığım" (RFC 2324). | |
| `419` | **Page Expired** | CSRF Token eksik veya süresi dolmuş (Laravel). | |
| `420` | **Enhance Calm** | Hız sınırı (Rate Limit) aşıldı (Twitter API). | |
| `422` | **Unproc. Content** | Semantik/mantıksal doğrulamada hata (RFC 9110). | |
| `426` | **Upgrade Required** | **Güvenli (TLS) protokole geçiş zorunlu** (RFC 9110). | `🔒` |
| `429` | **Too Many Requests** | Belirli sürede çok fazla istek (RFC 6585). | |
| `431` | **Header Fields Large** | Başlıklar (headers) çok büyük (RFC 6585). | |
| `451` | **Legal Reasons** | Yasal nedenlerle (Mahkeme kararı vb.) engellendi (RFC 7725). | |
| `460` | **Client IP Error** | Load Balancer istemci IP'sine ulaşamadı (AWS). | |
| `495` | **SSL Cert Error** | **İstemci SSL sertifikası geçersiz** (Nginx). | `🔒` |
| `496` | **SSL Cert Required** | **İstemci SSL sertifikası sunulmadı** (Nginx). | `🔒` |
| `497` | **HTTP to HTTPS** | **HTTPS portuna hatalı HTTP isteği atıldı** (Nginx). | `🔒` |
| `499` | **Client Closed** | Sunucu cevap vermeden istemci kapattı (Nginx). | |

---

## 🔥 5xx Sunucu Hata Kodları (Bulut & Servis Odaklı)
Sunucu tarafında oluşan teknik arızaları ve ağ geçidi hatalarını belirtir.

| Kod | Durum | Teknik Açıklama (Referans / Servis) | 🔒 |
|:---:|:---|:---|:---:|
| `500` | **Internal Error** | Genel sunucu hatası (Kod hatası - RFC 9110). | |
| `502` | **Bad Gateway** | Üst sunucudan hatalı yanıt alındı (RFC 9110). | |
| `503` | **Service Unavail.** | Sunucu aşırı yüklü veya bakımda (RFC 9110). | |
| `504` | **Gateway Timeout** | Üst sunucudan cevap gelmedi (RFC 9110). | |
| `507` | **Storage Error** | Depolama alanı yetersiz (WebDAV - RFC 4918). | |
| `508` | **Loop Detected** | İstemci sonsuz bir döngüde (RFC 5842). | |
| `509` | **Bandwidth Limit** | Veri trafik sınırı aşıldı (Apache/cPanel). | |
| `511` | **Network Auth Req.** | **Ağ girişi (Safe Portal) doğrulaması gerekli** (RFC 6585). | `🔒` |
| `520` | **Unknown Error** | Sunucu ile servis arasında açıklanamayan hata (Cloudflare). | |
| `521` | **Server Down** | Sunucu bağlantıyı reddetti (Cloudflare). | |
| `522` | **Connection T.O.** | TCP el sıkışmasında zaman aşımı (Cloudflare). | |
| `524` | **A Timeout Occur.** | Sunucu cevap vermeden zaman aşımına uğradı (Cloudflare). | |
| `525` | **Handshake Fail.** | **SSL el sıkışması başarısız** (Cloudflare). | `🔒` |
| `526` | **Invalid SSL Cert** | **Sunucuda SSL sertifikası geçersiz** (Cloudflare). | `🔒` |
| `561` | **Unauthorized** | Load Balancer aşamasında yetki hatası (AWS). | |

---

## 🌐 Servis Sağlayıcıya Özel Kodlar Tablosu

| Kod | Servis / Framework | Kısa Açıklama |
|:---:|:---|:---|
| `440` | **IIS** | Oturum zaman aşımına uğradı (Microsoft). |
| `449` | **IIS** | İstek gerekli bilgilerle tekrar gönderilmeli. |
| `450` | **Windows** | Parental Controls tarafından engellendi. |
| `494` | **Nginx** | İstek başlığı çok büyük (Request Header Too Large). |
| `598` | **Proxy** | Ağ okuma zaman aşımı hatası (İnformal). |
| `599` | **Proxy** | Ağ bağlantı zaman aşımı hatası (İnformal). |

---
> [!IMPORTANT]
> Bu doküman dünyadaki tüm Web standartlarını kapsayacak şekilde 2026 yılı güncelliğiyle hazırlanmıştır. İlana göre eksik kod bulunmamaktadır.
