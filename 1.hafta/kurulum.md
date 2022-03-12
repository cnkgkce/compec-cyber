# Kurulumları Gerçekleştirelim
> Cenk Gökçe - Cyber Security Researcher
> > [LinkedIn](https://www.linkedin.com/in/cenk-gokce-345b88190)  - [Medium](https://cnkgkce.medium.com/) - [Github](https://github.com/cnkgkce/)


## VirtualBox Kurulumu
Virtualbox,  Oracle tarafından geliştirilen ve sektörde sıklıkla kullanılan sanallaştırma araçlarından birtanesidir. Sektörde oldukça sık kullanılan ve daha çok kurumsal tarafta tercih edilen bir diğer sanallaştırma aracı ise VMWare'dir. Bizler bu eğitim boyunca bize hem bireysel kullanım kolaylığı hem de hızlı ve sorunsuz kurulum gerçekleştirme imkanı sağladığı için Virtualbox'ı tercih edeceğiz. Virtualbox'ın son sürümünü indirebileceğiniz bağlantıya [buradan erişebilirsiniz](https://www.virtualbox.org/wiki/Downloads).

![Ekran Görüntüsü 1](ss/Ekran%20G%C3%B6r%C3%BCnt%C3%BCs%C3%BC%20(85).png)

Yukarıdaki bölümden kullandığınız cihaza uygun dosyayı indirip kurabilirsiniz. İndirdiğiniz .exe dosyasını herhangi bir değişiklik yapmadan kurabilirsiniz. Yaşadığınız herhangi bir sorunda benimle iletişime geçebilirsiniz.

## Kali Linux Nedir ?
Kali Linux Offensive Security firmasının geliştirdiği ve özelleştirdiği linux dağıtımlarından birisidir. Sızma testleri spesifiğinde geliştirilmiş olan bu dağıtım içerisinde birçok güvenlik tool'u ya yüklü bir şekilde ya da yüklemeye hazır paketler halinde dağıtımın içerisinde gelmektedir.

## Kali Linux İndirelim
Kali linux'u çeşitli platformlarda kullanabilirsiniz. Kendi oluşturduğunuz bir sunucuya direkt bir şekilde kurulum gerçekleştirebilir, taşınabilir bilgisayarlarınıza veya mobil cihazlarınıza (Rasperry PI, Android, IOS), sanal makinelerinize, bulut sistemlerinize, Live Boot seçeneği ile ana cihazlarınıza, Docker container içerisinde veya WSL aracılğıyla Windows cihazlarınıza kurulum gerçekleştirebilirsiniz.<br>
Bizler  bu eğitim boyunca daha önceden kurulumunu gerçekleştirdiğimiz VirtualBox sanallaştırma aracının üzerine gerekli imajı indirip kurulumunu gerçekleştireceğiz.
Kali Linux  imajlarına [buradan erişebilirsiniz](https://www.kali.org/get-kali/)

![Ekran Görüntüsü 2](ss/Ekran%20G%C3%B6r%C3%BCnt%C3%BCs%C3%BC%20(87).png)<br>

İlgili bağlantıya tıkladıktan sonra gelen ekranda Virtual Machines bölümüne tıklayalım<br>

![Ekran Görüntüsü 3](ss/Ekran%20G%C3%B6r%C3%BCnt%C3%BCs%C3%BC%20(89).png)

Ardından işaretli bölüme tıklayarak bilgisayarımıza .ova uzantılı Kali Linux imajımızı indirelim. Open Virtual Applicance (OVA) imajları ile herhangi bir imajı VMWare veya VirtualBox üzerinde kurup kullanabilirsiniz.

## Kali Linux'u VirtualBox Aracımıza Kuralım
Öncelikle Virtualbox aracımızı açalım. 
![Ekran Görüntüsü 4](ss/Ekran%20G%C3%B6r%C3%BCnt%C3%BCs%C3%BC%20(91).png)
Yukarıda yer alan kali-2022 benim şuanda hali hazırda kullandığım kali imajıdır. Siz de orası da boş gelecektir. Şimdi ise 0 dan bu imajı kolayca nasıl bilgisayarımıza kuracağımızı görelim.

![aa](ss/Ekran%20G%C3%B6r%C3%BCnt%C3%BCs%C3%BC%20(97).png)
Yukarıdaki görselde de gösterildiği üzere üstte yer alan "Dosya" sekmesine tıkladıktan sonra "Cihazı İçe Aktar" seçeneğini seçelim.

![aa](ss/Ekran%20G%C3%B6r%C3%BCnt%C3%BCs%C3%BC%20(98).png)
Ardından işaretli yere tıklayarak dosya sihirbazını açalım.
Açılan pencerdeden Kali Linux imajını indirdiğimiz .ova uzantılı dosyamızı seçelim.

![aa](ss/Ekran%20G%C3%B6r%C3%BCnt%C3%BCs%C3%BC%20(99).png)
Ardından "İleri" sekmesine tıklayarak devam  edelim.

![aa](ss/Ekran%20G%C3%B6r%C3%BCnt%C3%BCs%C3%BC%20(100).png)

Açılan pencerde herhangi bir değişiklik yapmadan "İçe Aktar" butonuna tıklayarak devam edelim.

![aa](ss/Ekran%20G%C3%B6r%C3%BCnt%C3%BCs%C3%BC%20(101).png)

Gerekli kurulum başlayacaktır. VirtualBox aracımız indirdiğimiz Kali Linux  imajını hali hazırda kullandığımız diske yazdıracaktır. Bu örnekte C üzerine bu imaj kurulmaktadır.

Kurulum gerçekleştikten sonra tekrardan ana sayfaya dönüş yapabiliriz.

## Kali Linux Üzerinde Bazı Konfigürasyonlar
Kali Linux ana makinemiz üzerinden internete çıkacağı için bir takım network ayarları yapmamız gerekebilir. Kali Linux defaultta eth0 interface'i üzerinden ana makinenin Wireless bağlantısına sanal Ethernet üzerinden bağlantı gerçekleştirebilir. 

Kali Linux'u genelde Nat Network veya Bridge Adapter modlarında kullanmaktayız. Bridge adapter araya herhangi bir izolasyon sağlamadan Kali'yi  cihaza bağlamak olarak düşünebiliriz. Nat networkte ise ağ içerisinde Nat kullanımı ile izolasyon sağlanmakta ve bu bridge moda göre biraz daha güvenli varsayılmaktadır.

Nat Network eklemek için aşağıdaki adımları sırasıyla gerçekleştirelim. 

Virtualbox ana sayfası üzerinden sırasıyla;<br>

**Dosya > Tercihler > Ağ > Yeşil üstteki ikon(Yeni Nat Ağı Ekler)**

Tıkladıktan sonra virtualbox üzerinde yeni bir Nat Network tanımlamış  oluruz.

Ardından tekrar virtualbox ana arayüze döndükten sonra Kali Linuxu seçerek **"Ayarlar"** sekmesine tıklayalım. Açılan pencerde **"Ağ"** bölümüne tıkladıktan sonra "Ağ bağdaştırıcısını etkinleştir" sekmesini işaretleyerek "Şuna takıldı" bölümüne "Nat Ağı"  nı seçip, "Adı" bölümüne ise önceden oluşturduğumuz NatNetwork'ü seçip Tamam'a tıklayalım.

![ekk](ss/Ekran%20G%C3%B6r%C3%BCnt%C3%BCs%C3%BC%20(103).png)

Her şey tamam ! Şimdi ise ana sayfaya döndükten sonra sağ üst köşede bulunan yeşil "Başlat" ikonuna tıklayarak makinemizi başlatabiliriz. 

![ekk](ss/Ekran%20G%C3%B6r%C3%BCnt%C3%BCs%C3%BC%20(105).png)

Açılan pencerde kullanıcı adı ve parola değerlerini "kali:kali" kullanarak başlatabiliriz. Artık Kali Linuxumuz kullanıma hazır durumdadır :)




