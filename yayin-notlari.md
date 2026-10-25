# Yayın Notları

## Vercel (kullanılan yöntem)
1. vercel.com > Add New > Project > GitHub reposunu seçip Import edin.
2. Framework Preset: Other. Build/Output alanlarını boş bırakıp Deploy'a basın.
3. Settings > Domains > `www.syraxen.tr` ekleyin; Vercel'in gösterdiği DNS kaydını (www için CNAME) alan adı sağlayıcısında girin.
4. `syraxen.tr` (www'siz) için de ekleyip www'ye yönlendirin.
5. GitHub'a her push otomatik yeniden yayınlanır. Bu yöntemde `nginx/` klasörü kullanılmaz.

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
- Formspree > Settings: reCAPTCHA kapalı olmalı (ya da kendi anahtarınız eklenmeli), Authorized domains kısmına `syraxen.tr`, `www.syraxen.tr` ve Vercel'in `.vercel.app` adresi eklenmeli.
- Mesajlar Formspree panelindeki Submissions sekmesinde ve alıcı e-postada görünür. Ücretsiz pakette aylık gönderim sınırı vardır.
- Gönderim başarısız olursa form, mesajı e-posta uygulamasıyla göndermek için yedek seçenekleri (varsayılan, Gmail, Outlook, Yahoo) gösterir.

## İletişim formu
"Mesaj gönder" düğmesi, doğrulamadan sonra mesajı olduğu gibi (düzenleme yapmadan) doğrudan Formspree'ye gönderir ve başarı penceresi gösterir.
Gönderim başarısız olursa ziyaretçiye mesajı e-posta uygulamasıyla (varsayılan, Gmail, Outlook, Yahoo) gönderme veya kopyalama seçenekleri sunulur.
