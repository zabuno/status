# Zabuno durum sayfası

Hedef alan adı: status.zabuno.com. DNS hazır olana kadar yayın:
https://zabuno.github.io/status/

Gerekli DNS: status CNAME zabuno.github.io.
DNS doğrulanınca .upptimerc.yml içindeki baseUrl yerine cname: status.zabuno.com
yazılır ve GitHub Pages özel alan adı/HTTPS etkinleştirilir.

Beş genel HTTP GET ucu izlenir. Giriş sayfasının yanıt vermesi gerçek oturum
açmanın veya ödemenin kanıtı değildir. Ölçüm geçmişi sözleşmeli SLA değildir.
Misafir menüsü yayından kaldırılırsa hedef güncellenmelidir. GitHub
zamanlayıcısındaki beş dakikalık aralık bir garanti değildir.

Organizasyonun salt-okunur varsayılan izni korundu. status.yml, ölçüm için
içerik ve olay yazımı; derleme için içerik yazımı; yayın için Pages ve OIDC
izni kullanır. Her koşunun geçici GITHUB_TOKEN değeri Upptime'ın GH_PAT
isimli girdisine verilir; kişisel anahtar saklanmaz. Fork/PR tetikleyicisi yok.

Upptime motoru v1.44.0 sürümüne sabittir. Şablonun otomatik workflow
yeniden yazıcısı kullanılmaz; güncellemeler incelenmiş commit gerektirir.
Beş dakikalık koşular ölçüm/özet üretir; her gün 01:17 UTC, manuel veya
yapılandırma değişikliği koşusu grafikleri ve statik sayfayı de yeniler. Örnek api/graphs/history verileri
kurulum commit'inde kaldırıldı, gerçek olay geçmişi temizlenmez.

Başarı: beş gerçek ölçüm + başarılı Pages yayını + tarayıcıda beş servis.
Özel alan adı ayrı DNS kapısıdır. Rollback kurulum commit'inin revert'idir;
örnek veriler Git geçmişinde saklıdır.

Kaynaklar:
- https://upptime.js.org/docs/get-started/
- https://upptime.js.org/docs/configuration/
- https://docs.github.com/en/actions/tutorials/authenticate-with-github_token
