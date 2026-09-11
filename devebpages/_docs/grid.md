---
layout: doc
title: "Bölme Düzeni"
permalink: /docs/grid/
nav_order: 2
---

# Bölme Düzeni (Grid)

> Esnek, sezgisel ve tamamen bağımsız, derlemeksizin, JavaScript olmadan

**deveb.css Bölme Düzeni**, html tabanlı ağ sayfa tasarımlarını, karmaşık derleme adımlarına veya katı sütun kalıplarına bağlı kalmadan doğrudan HTML üzerinde yönetmenizi sağlar. Sezgisel pay pay oranlar sayesinde, tasarımın kendi matematiğine sadık kalan, duyarlı ve özgür bir genişlik denetimi sunar.

---

Geleneksel CSS frameworkleri, tasarımları kodlayanları sabit 12'lik grid kalıplarına hapseder, her ne kadar esnetme seçenekleri sunsalar da çok yetersizdir. Kimisi özel genişlikler için CSS derleme (JIT/Purge) süreçlerini zorunlu kılar. deveb.css, karmaşık araç zincirlerine ihtiyaç duymadan doğrudan HTML üzerinde sezgisel kesirli ifadelerle (1/1'den 100/100'e) genişlikler vermenizi sağlar. Yalnızca deveb.css'i html head arasına yazarak ekleyin ve hazır.

## Öne Çıkan Özellikler

* **Sezgisel Kesirli Mantık:** Genişlik değerlerini `(1/1)` ile `(100/100)` arasında istenen herhangi bir oranla ifade edebilirsiniz. `(6/12)`, `(3/6)` veya `(14/21)` gibi değerlerle yerleşimin yüzdesel alanını doğrudan belirlersiniz.

* **Tepkisel (Responsive) Esneklik:** Farklı ekran boyutlarındaki davranışları doğrudan kırılım öznitelikleriyle tanımlayarak temiz bir sözdizimi elde edersiniz:

```html
<!-- Varsayılan olarak %50, küçük ekranlarda ve daha büyüklerinde %33.3 genişlik -->
<div class="(6/12)" sm="(5/15)"></div>
```

* **Derlemesiz (Zero-Build) Mimari:** Herhangi bir derleyici, CLI aracı veya ön işleyiciye ihtiyaç duymaz. Ekstra yapılandırma dosyalarıyla uğraşmadan projeye doğrudan dahil edilip kullanılabilir.

* **Saf CSS Performansı (Zero-JS):** Tamamen CSS'in kendi dinamiklerinden faydalanır. Çalışma zamanında (runtime) JavaScript çalıştırmadığı için tarayıcıya ekstra iş yükü bindirmez ve bellek kullanımını minimumda tutar.

---

## Kullanım Senaryoları

* **Sıkı Güvenlik Politikaları (Strict CSP):** İstemci tarafında betik (JavaScript) yürütülmesinin engellendiği güvenli kurumsal paneller ve finans altyapıları.

* **Hafif ve Gömülü Düzenler:** POS cihazları, dijital panolar (kiosk) veya düşük donanımlı WebView ortamlarında maksimum çalışma hızı gerektiren arayüzler.

* **Kesintisiz Erişim ve Statik Dokümantasyon:** İstemci ortamından bağımsız olarak her koşulda tutarlı ve hızlı yüklenen web sayfaları.

---


## Temel Kullanım

Bölme düzeninde her eleman, kapsayıcısı içinde belirttiğiniz kesirli oran kadar genişlik kaplar:

```html
<!-- Yarı yarıya (%50 + %50) iki sütun -->
<div class="(6/12)">%50 Alan</div>
<div class="(6/12)">%50 Alan</div>

<!-- Üçe bölünmüş (%33.3) yerleşim -->
<div class="(1/3)">1/3 Alan</div>
<div class="(1/3)">1/3 Alan</div>
<div class="(1/3)">1/3 Alan</div>
```

---

## Tepkisel Kırılımlar (Responsive Breakpoints)

Ekran boyutuna göre farklı oranlar vermek için ilgili ekran özniteliğini eklemeniz yeterlidir:

| Kırılım | Öznitelik | Min Genişlik | Örnek Kullanım |
|---|---|---|---|
| **Ekstra Küçük** | `xs` | `0px` | `xs="(12/12)"` |
| **Küçük** | `sm` | `576px` | `sm="(6/12)"` |
| **Orta** | `md` | `768px` | `md="(4/12)"` |
| **Büyük** | `lg` | `992px` | `lg="(3/12)"` |
| **Ekstra Büyük** | `xl` | `1200px` | `xl="(2/12)"` |
| **Devasa** | `xxl` | `1400px` | `xxl="(1/12)"` |

### Tepkisel Örnek

```html
<!-- Mobilde tam genişlik (12/12), tablette yarı yarıya (6/12), masaüstünde dörtte bir (3/12) -->
<div class="(12/12)" md="(6/12)" lg="(3/12)">
  İçerik Kartı
</div>
```

---

## Gelişmiş Yerleşimler

Geleneksel 12'lik yapıların dışına çıkmak istediğinizde herhangi bir paydayı kullanabilirsiniz:

```html
<!-- 21'lik sistemde özel genişlikler -->
<div class="(14/21)">Sol Panel (%66.6)</div>
<div class="(7/21)">Sağ Panel (%33.3)</div>
```