# Yayın Notları

## VPS (nginx)
1. `index.html` ve `assets/` klasörünü `/var/www/syraxen` altına kopyalayın.
2. `nginx/syraxen.conf` dosyasını `/etc/nginx/sites-available/` altına koyup etkinleştirin, `nginx -t && systemctl reload nginx`.
3. syraxen.tr alan adının A kaydını VPS IP adresine yönlendirin.
4. HTTPS: `sudo certbot --nginx -d syraxen.tr -d www.syraxen.tr`

## Yayından önce yapılacaklar
- Projeler ve Hakkımızda sayfalarındaki örnek içerikleri gerçekleriyle değiştirin.
- Paylaşım görseli ve açıklama (Open Graph) etiketlerini ekleyin.
- Google'da görünmek için her sayfaya ayrı adres (`/hizmetler` vb.), `sitemap.xml` ve `robots.txt` hazırlayın.
- Gizlilik (KVKK) sayfası ekleyin.
- `info@syraxen.tr` için posta kutusu (MX kaydı) açın.

## Formspree
- Form adresi `index.html` içinde `FID` değişkeninde: https://formspree.io/f/xljjdyzr
- Formspree > Settings: reCAPTCHA kapalı olmalı (ya da kendi anahtarınız eklenmeli), Authorized domains kısmına `syraxen.tr` eklenmeli.
- Mesajlar Formspree panelindeki Submissions sekmesinde ve alıcı e-postada görünür. Ücretsiz pakette aylık gönderim sınırı vardır.
- Gönderim başarısız olursa form, mesajı e-posta uygulamasıyla göndermek için yedek seçenekleri (varsayılan, Gmail, Outlook, Yahoo) gösterir.

## İletişim formu
Form mesajı düzenler ve ziyaretçinin seçtiği e-posta uygulamasında (varsayılan, Gmail, Outlook, Yahoo) açar; sunucu gerektirmez.
Yapay zekâ ile düzenleme ve yazım düzeltme yalnızca Claude üzerinde çalışır. Kendi sunucunuzda gerçek yapay zekâ için Claude API'yi sunucu tarafında bağlamanız gerekir (API anahtarını sayfaya koymayın).
