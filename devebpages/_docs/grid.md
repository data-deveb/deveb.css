---
layout: doc
title: "Dinamik Grid Sistemi"
permalink: /docs/grid/
nav_order: 2
---

Bu dokümantasyon, projemizde harici bir CSS derleyicisine (Sass, PostCSS vb.) ihtiyaç duymadan, tamamen anlık çalışan **sıfır derleme maliyetli dinamik grid sisteminin** kullanımını açıklar.

## 🚀 Temel Mantık

Geleneksel CSS framework'lerinin aksine, bu sistemde sınıfları (class) önceden derlemek zorunda değilsiniz. HTML etiketleri içerisine doğrudan oran belirten ifadeler yazarsınız ve sistem bu oranları anında yüzdesel (`width`) değerlere dönüştürür. 

Herhangi bir build (derleme) işlemine gerek yoktur; HTML üzerinde yapılan değişiklik tarayıcıda anında aktif olur.

---

## 💻 Kullanım ve Örnekler

Grid yapısını oluşturmak için elementlere `xs`, `sm`, `md`, `lg` gibi ekran boyutu öznitelikleri ve `(pay/fayda)` formatında oranlar verebilirsiniz.

### 1. Temel Esnek Kolonlar
Aşağıdaki örnekte, mobil cihazlarda (`xs`) kolon tüm genişliği kaplarken (`1/1`), büyük ekranlarda (`lg`) ekranın üçte birini (`2/6`) kaplamaktadır.

```html
<div class="row">
    <div xs="1/1" lg="2/6">
        <p>Sol Panel İçeriği</p>
    </div>
    <div xs="1/1" lg="4/6">
        <p>Sağ Ana İçerik Alanı</p>
    </div>
</div>
```

### 2. İleri Düzey Oranlar
Sistem `1/1` ile `100/100` arasındaki tüm kesirli değerleri işleyebilir. Hassas grid yerleşimleri için esnek oranlar tanımlayabilirsiniz:

```html
<div class="row">
    <div md="30/100">Genislik: %30</div>
    <div md="70/100">Genislik: %70</div>
</div>
```

---

## 📱 Duyarlı (Responsive) Kırılma Noktaları

Sistem, ekran genişliklerine göre dinamik olarak şu breakpoint (kırılma noktası) özniteliklerini destekler:

| Öznitelik | Hedef Ekran Boyutu | Açıklama |
| :--- | :--- | :--- |
| `xs` | Tüm Ekranlar (Default) | Mobil öncelikli taban genişlik. |
| `sm` | Küçük Ekranlar | Tablet ve üzeri cihazlar. |
| `md` | Orta Ekranlar | Standart dizüstü bilgisayarlar. |
| `lg` | Büyük Ekranlar | Geniş masaüstü monitörler. |

> **İpucu:** İstediğiniz ekranda anında değişiklik görmek için tarayıcınızı yenilemeniz bile gerekmez; HTML elementindeki değeri değiştirip kaydetmeniz yeterlidir.