# EBABOT'a Hoş Geldiniz!

EBABOT ile başta harici canlı ders tanımlama olmak üzere; EBA ve E-okul'daki iş süreçlerini otomatikleştirmeyi hedefliyorum. Şimdilik sadece harici canlı dersler otomatik eklenip, silinebiliyor. Uygulama olarak Zoom kullanılıyor.

## Geliştirdiğim ve Geliştirmeyi Düşündüğüm Özellikler

 - [x] Otomatik harici canlı ders tanımlama ve silme
 - [ ] Öğrencilerin EBA'daki performanslarına göre otomatik e-okul karne bilgilerinin doldurulması (notlar)
 - [ ] Öğrenci e-okul bilgilerini otomatik güncelleme

## PERFORMANS

Karşılaştırma yapmak için öğretmenlere anket yaptım. 4000 kişinin üzerinde katılımın sağlandığı anketlerde bir dersin ortalama ~2 dakikada eklendiğini tespit ettim. Bu bir günlük derslerin ortalama ~12 dakikada eklendiğini gösteriyor. EBABOT harici canlı ders tanımlama işleminde aşağıdaki performansları göstermektedir.

 **1. Sabit linkle ders ekleme işlemi**

 - Bir günlük ders ekleme işlemi 59 saniyede.
 - 1 ders yaklaşık 10 saniyede eklenmiştir.
 - Ortalama verilere göre yaklaşık 10 dakika kazanılmıştır.

**2. Ayrı ayrı linkler ile ders ekleme işlemi**

 - Bir günlük ders ekleme işlemi 1 dakika 45 saniyede.
 - 1 ders yaklaşık 17 saniyede eklenmiştir.
 - Ortalama verilere göre yaklaşık 9,5 dakika kazanılmıştır.

> Bu veriler ışığında EBABOT bir öğretmene haftalık ortalama ~1 saat kazandıracaktır.

# Kurulum

Kurulum aşamaları gözünüzü korkutmasın lütfen. Tek sefer yapmanız gerekiyor. Aşağıdaki adımları sırasıyla yaptığınızda çalışan bir EBABOT'unuz olacak 😊

### 1. EBABOT'u İndirin
[https://github.com/erenmustafaozdal/ebabot/releases](https://github.com/erenmustafaozdal/ebabot/releases) adresine giderek en son sürümü bilgisayarınıza indirin. İndirdikten sonra sıkıştırılmış dosyadan çıkartın. Bilgisayarınızda istediğiniz bir konuma taşıyın.

### 2. Bilgisayarınıza Python Kurun
[https://www.python.org/downloads](https://www.python.org/downloads) adresine gidip, Python'un en son `3.x` sürümünü indirin. Sistem türünüze göre kurulum dosyası indirmeniz gerekir. 32 bit işletim sistemleri **x86**, 64 bit işletim sistemleri **x86-64** yükleyicisini indirmeli. İşletim sistem türünüzü öğrenmek için **Bilgisayarım**'a sağ tıklayın ve **Özellikler**'i seçin.

> NOT: Eğer eski bir Windows versiyonu kullanıyorsanız Python'un `3.x`
> içinde eski sürümlerini tercih etmeniz gerekebilir. `3.9` versiyonu **Windows 7**'de desteklemiyor. `3.7` sürümü ile test edildi.

Ardından indirdiğiniz yükleyici ile Python'u bilgisayarınıza kurun. Yükleme esnasında aşağıdakilere dikkat edin.

 1. `Add Python 3.x to Path` seçeneğini işaretleyin.
 2. `Install Now` tuşu ile kurulumu başlatın.
 3. `Setup was successful` yazısını gördüğünüzde yükleyiciyi kapatabilirsiniz.
 4. Yükleyici dosyasını silmenizde herhangi bir sakınca yoktur.

Şimdi Python kurulumunu test edelim. Bilgisayarınızda komut satırını açın. Bunun için Windows tuşuna dokunun ve *cmd* yazın. **cmd.exe** uygulamasını çalıştırın. Bulunduğunuz satırda aşağıdaki kodu çalıştırın.

    python --version

Bu kodu çalıştırdığınızda aşağıdaki gibi bir çıktı alıyorsanız; her şey yolunda demektir. 😎👍

    Python 3.x.x

### 3. Chrome Driver İndirelim

Python ile kontrol edeceğimiz Chrome tarayıcı driver'ını indirmemiz gerekiyor. [https://chromedriver.storage.googleapis.com/index.html?path=2.35](https://chromedriver.storage.googleapis.com/index.html?path=2.35) adresine giderek sistemimiz için uygun olan `chromedriver_*.zip` dosyasını indirin. İndirdiğiniz dosyayı ZIP içinden çıkarın. Lütfen bu dosyayı bildiğiniz bir yere çıkarın. Çünkü içindeki **chromedriver.exe** dosyasının yolunu EBABOT'a bildirmeniz gerekecek.

> NOT: EBABOT çalıştırıldığında Chrome tarayıcısını açmadan versiyon
> hatası veriyorsa; yukarıdaki adresten bir üst dizine çıkın. Alt ve üst
> versiyonları indirerek tekrar deneyin. Windows 10 ve Windows 7'de 2.35
> versiyonu ile sorunsuz test edilmiştir.

### 4. EBABOT Bağımlılıklarını Yükleyelim
Her yazılımın bağımlı olduğu başka yazılımlar veya araçlar vardır. EBABOT da böyle. Öncelikle bu bağımlılıkları yüklemek gerekir.

EBABOT'u indirip, sıkıştırılmış dosyadan çıkardığınız `ebabot` klasörü içine girin. EBABOT'un olduğu bu klasörde komut satırını başlatmamız gerekiyor. Bunun için `ebabot` klasöründeyken, klasörün üstünde bulunan ve bulunduğunuz klasör yolunun (adresinin) olduğu kutucuğa dokunun. Bu kutucukta şuna benzer bir yol yazabilir: `C:\Users\Kullanıcı Adınız\Downloads\ebabot`. İşte bu kutucuktaki yolu silin. Ardından **cmd** yazın ve `enter` tuşuna basın. Bulunduğunuz klasörde çalışacak bir komut satırı açılmış olmalı.

Yukarıdaki örnek klasör yolumuzdan devam edecek olursak; komut satırında sizi şuna benzer yazılar karşılayacaktır.

    Microsoft Windows [Sürüm 6.1.7601]
    Telif Hakkı (c) 2009 Microsoft Corporation. Tüm hakları saklıdır.

    C:\Users\Kullanıcı Adınız\Downloads\ebabot>

Lütfen EBABOT'un bulunduğu klasör yolu ile komut satırındaki `C:\` ile başlayan yolun aynı olduğuna emin olun.

Şimdi bağımlıklıkları yüklemek için aşağıdaki kodu çalıştırın.

```
pip install -r requirements.txt
```

Python bağımlılıkları yükleyecektir. Eğer bir hata almadıysak işlemlerimiz başarılı bir şekilde sonuçlanmıştır. Artık EBABOT hazır. Şimdi örnek Excel dosyalarını kendimize göre düzenleyelim. Ardından EBABOT'u çalıştıralım.

# EXCEL Dosyaları

## `excel templates\örnek kullanıcılar.xls`

Bu dosyada EBABOT'u kullanacak kullanıcılar tutuluyor. *Dosyanın adını değiştirmekte özgürsünüz.* Birden fazla kullanıcı ekleyebilirsiniz. Örneğin eşinizin ve sizin bilgilerinizi bu dosyaya ekleyebilirsiniz. Ardından isterseniz bütün kullanıcılar, isterseniz de sadece belirli kullanıcılar için EBABOT'u çalıştırabilirsiniz.

Şimdi bu Excel dosyasına eklenecek verileri inceleyelim.

|Sütun Başlığı         |Açıklama                                                  |
|----------------------|----------------------------------------------------------|
|**name**              |Kullanıcının adını yazmalısınız. Bu veri sadece komut satırında bilgi vermek ve belirli kullanıcılar için EBABOT'u çalıştırmak amacıyla yazılır. Kullanıcı adlarını yazarken boşluk bırakabilirsiniz. Aynı isimler olmaması tavsiye edilir.|
|**zoom_email**        | Zoom hesabınıza giriş yaptığınız e-posta adresi. Zoom'a otomatik giriş sağlanamıyor. *Google Recaptcha* ile bot olmadığınızı kanıtlamak için çeşitli resimler seçmenizi istiyor. Fakat bu dosyaya bu bilgiyi eklerseniz; EBABOT kutucukları sizin için doldurur. Kolaylık olur.|
|**zoom_password**     |Zoom hesabınızın şifresi. Eğer doldurursanız EBABOT sizin için kutucuğu doldurur.|
|**edevlet_tc**        |E-devlet girişinde kullandığınız TC numaranız. EBABOT EBA'ya otomatik giriş yapabilmektedir. Eğer bilgileri verirseniz sizin yerinize giriş yapar. Bu dosyada bu bilgileri yazmazsanız; EBA'ya da kendiniz giriş yapmanız gerekecek.|
|**edevlet_password**  |E-devlet ile giriş yapmak için kullandığınız şifreniz.|
|**live_lessons_path** |Derslerinizin bulunduğu Excel dosyasının tam adresi. Dosya adı ve `.xls` uzantısı dahil tam yolu yazmalısınız. Örnek: `C:\Users\Kullanıcı Adınız\Downloads\ebabot\excel templates\örnek dersler.xls`|
|**pmi_link**          |Her ne kadar EBA önermese de; isteyenler için sabit link *(personal meeting id)* alanı. Eğer isterseniz bu alana sabit linkinizi ekleyin. Bu işlem süresini yarı yarıya azaltacaktır. **Ancak güvenli değildir. Bu sebeple ben de tavsiye etmiyorum.**|
|**pmi_passcode**      |Sabit linkiniz için oluşturduğunuz şifre|

Kullanıcıların bilgilerini yukarıdaki başlıklarda istenen bilgilere göre doldurmalısınız. **name**, **live_lessons_path** alanlarının doldurulması zorunludur.

> **NOT:** Zoom'a otomatik giriş yapılamıyor. İşlemin bu basamağında EBABOT
> sizi *5 dakikalığına beklemeye başlar*. Siz kendiniz giriş yaparsınız.
> Giriş yaptığınızı EBABOT anlar ve işlemlere devam eder. Zoom daha
> sonra sizi hatırlar. Sürekli giriş yapmanız gerekmez.

> **NOT:** EBA'da E-devlet bilgileri ile otomatik giriş yapılabiliyor. Ancak
> bu bilgileri dosyaya eklemeniz gerekir. Eğer kendiniz giriş yapmak
> isterseniz; Zoom'da olduğu gibi EBABOT sizi *5 dakikalığına bekler*. Siz istediğiniz
> yöntemle giriş yapabilirsiniz. Girişin yapıldığını EBABOT anlar ve
> işlemlerine devam eder.
>
>**EBA oturumunuzu Zoom gibi sürekli hatırlamaz. Bunu unutmayın.**
> Her seferinde tekrar giriş yapılması gerekiyor.
> Bu sebeple otomatik giriş yapma seçeneğini kullanabilirsiniz.

## `excel templates\örnek dersler.xls`

Bu dosyada EBABOT'un oluşturacağı dersler yer alıyor. *Dosyanın adını değiştirmekte özgürsünüz.* A-J sütunları EBA harici ders tanımlama sayfası form alanlarıdır. K-Q sütunlarında her ders için Zoom Meeting ayarlarını yapabilirsiniz.

Şimdi bu Excel dosyasına eklenecek verileri inceleyelim.

|Sütun Başlığı|Açıklama  |
|--|--|
|**Canlı Ders Başlığı** |EBA'daki `Canlı Ders Başlığı` alanına yazılacak bilgi|
|**Sınıf** |EBA'daki `Sınıf` alanında seçilecek bilgi. EBA'daki seçim kutusundaki bilgiyi birebir aynı yazmalısınız.|
|**Canlı Ders Tarihi** |EBA'daki `Canlı Ders Tarihi` alanında seçilecek tarih. Buraya bir tarih bilgisi yazmalısınız. Excel sizi buna zorlayacak. Yanlış yazarsanız uyaracak. Örnek: `07.12.2020` Yazdığınız farklı bir format görünebilir. Sorun yok 😊|
|**Ders Başlangıç**|EBA'daki `Ders Saat Aralığı` seçim kutusundaki dersin başlayacağı saati gösteren alan. Buraya bir saat bilgisi yazmalısınız. Excel sizi buna zorlayacak. Yanlış yazarsanız uyaracak. **EBA'daki ders başlangıç saatleriyle birebir aynı saati yazmalısınız.** Örnek: `09:10`|
|**Ders Bitiş**|EBA'daki `Ders Saat Aralığı` seçim kutusundaki dersin biteceği saati gösteren alan. Buraya bir saat bilgisi yazmalısınız. Excel sizi buna zorlayacak. Yanlış yazarsanız uyaracak. **EBA'daki ders bitiş saatleriyle birebir aynı saati yazmalısınız.** Örnek: `09:40`|
|**Açıklama** |EBA'daki `Açıklama` alanına yazılacak bilgi. Bu alan zorunlu değil. Ben Excel'de bir formül yazdım. **Ders**, **Ünite** ve **Konu** bilgilerini otomatik buraya ekliyor. Siz formülü silip istediğinizi buraya yazabilir veya boş bırakabilirsiniz.|
|**Ders** |EBA'daki `Ders` alanında seçilecek bilgi. EBA'daki seçim kutusundaki bilgiyi birebir aynı yazmalısınız.|
|**Ünite** |EBA'daki `Ünite` alanında seçilecek bilgi. EBA'daki seçim kutusundaki bilgiyi birebir aynı yazmalısınız. Zorunlu bir alan değil. Boş bırakırsanız EBABOT da seçim yapmaz.|
|**Konu** |EBA'daki `Konu` alanında seçilecek bilgi. EBA'daki seçim kutusundaki bilgiyi birebir aynı yazmalısınız. Zorunlu bir alan değil. Boş bırakırsanız EBABOT da seçim yapmaz.|
|**Şube/Grup** |EBA'daki `Şube/Grup` alanında seçilecek bilgi. EBA'daki seçim kutusundaki bilgiyi birebir aynı yazmalısınız. EBA'da bu alanda birden fazla seçim yapılabiliyor. Birden fazla şubeye aynı saatte ders yapacaksanız aralarına virgül `(,)` koyarak ilgili ilgili hücreye yazmalısınız. Her şubenin EBA'daki seçim kutusundaki bilgiyle birebir aynı olması gerektiğini unutmayın.|

> **NOT:** `Canlı Ders Tarihi` sütununda da kendi haftalık ders
> programıma göre ve size örnek olması için formül oluşturdum. Salı
> günleri İngilizce dersim olduğu için 4 dersim var. İlk satıra haftanın
> pazartesi tarihini yazdığımda diğer satırlar otomatik oluşturuluyor.
> İsterseniz kendinize uyarlayabilir veya hepsini kendiniz yazabilirsiniz.

Bu alanlar EBA'daki her ders için gereken bilgiler. **Ders Linki** ve **Ders Şifresi** alanlarını EBABOT Zoom'a kaydettiği dersten otomatik alır. Ya da sabit link kullanacaksanız; kullanıcılar Excel dosyasına eklediğiniz bilgiyi bu alanlara ekler.

Şimdi de Zoom'daki dersi ilgilendiren sütunları inceleyelim. Unutmayın EBABOT bu sütunları Zoom'a ders eklerken kullanacak. **Eğer sabit link seçimi yapıp, kullanıcılar Excel dosyasında link bilgisi tanımlarsanız; EBABOT Zoom'da ders oluşturmayacağı için bu ayarları kendiniz yapmanız gerekecektir.**

|Sütun Başlığı|Açıklama  |
|--|--|
|**Meeting ID** |Zoom'da tanımlanan dersin ayrı bir link mi, yoksa sabit bir link mi (personal meeting id) olacağını belirleyeceğiniz alan. Excel hücresine tıkladığınızda seçim kutusu belirir ve seçim yapabilirsiniz. Yazmak isterseniz de şu değerlerden birini yazmalısınız: `new` veya `pmi`. Eğer `new` seçeneğini seçerseniz ayrı ayrı link oluşturulur. `pmi` seçerseniz Zoom'da dersleri oluşturur ama hep sabit link ile... **Hem `pmi` seçer, hem de kullanıcılar Excel dosyasında sabit link tanımlarsanız; Zoom'da hiçbir ders oluşturmaz.**|
|**Passcode**|Zoom'da oluşturulacak her ders için kendiniz şifre belirleyebilirsiniz. Eğer boş bırakırsanız Zoom kendisi otomatik oluşturur. EBABOT da o şifreyi EBA'ya ekler.|
|**Waiting Room**|Derslerde bekleme odasını aktif edebilir veya kapatabilirsiniz. Excel hücresine tıkladığınızda seçim kutusu belirir ve seçim yapabilirsiniz. Yazmak isterseniz de şu değerlerden birini yazmalısınız: `on` veya `off`. `on` seçeneği ile açarsınız. `off` seçeneği ile kapatırsınız.|
|**Video Host**|Ders başlangıcında öğretmen kamerasını açabilir veya kapatabilirsiniz. Excel hücresine tıkladığınızda seçim kutusu belirir ve seçim yapabilirsiniz. Yazmak isterseniz de şu değerlerden birini yazmalısınız: `on` veya `off`. `on` seçeneği ile açarsınız. `off` seçeneği ile kapatırsınız.|
|**Video Participant**|Ders başlangıcında öğrencilerin kamerasını açabilir veya kapatabilirsiniz. Excel hücresine tıkladığınızda seçim kutusu belirir ve seçim yapabilirsiniz. Yazmak isterseniz de şu değerlerden birini yazmalısınız: `on` veya `off`. `on` seçeneği ile açarsınız. `off` seçeneği ile kapatırsınız.|
|**Request Unmute**|Ders başlangıcında öğrencilere tek seferlik mikrofon açma isteği gönderebilirsiniz. Eğer izin verirlerse ders içinde `Ask to unmute` yerine sadece `Unmute` tuşu ile hemen mikrofon açabilirsiniz. Excel hücresine tıkladığınızda seçim kutusu belirir ve seçim yapabilirsiniz. Yazmak isterseniz de şu değerlerden birini yazmalısınız: `on` veya `off`. `on` seçeneği ile açarsınız. `off` seçeneği ile kapatırsınız. **Bu ayar [https://zoom.us/profile/setting](https://zoom.us/profile/setting) adresinde kapalı bile olsa; eğer isterseniz EBABOT sizin yerinize açar.**|
|**Auto Record**|Dersleri bilgisayarınıza otomatik kaydetmeyi açabilir veya kapatabilirsiniz. Excel hücresine tıkladığınızda seçim kutusu belirir ve seçim yapabilirsiniz. Yazmak isterseniz de şu değerlerden birini yazmalısınız: `on` veya `off`. `on` seçeneği ile açarsınız. `off` seçeneği ile kapatırsınız. **Bu ayar [https://zoom.us/profile/setting](https://zoom.us/profile/setting) adresinde kapalı bile olsa; eğer isterseniz EBABOT sizin yerinize açar.**|

Bütün bu ayarlar ve sütunlar gözünüzü korkutmasın. Çünkü bir defa tanımladıktan sonra programınız değişmediği sürece sadece tarih değiştireceksiniz. 😊

# `.env_example` Dosyası ile Son Ayarlarımızı Yapalım

Kurulumu tamamladık. Excel dosyalarımızı hazırldık. Şimdi son adım olarak EBABOT'a tüm bunları gösterecek ayarları yapacağız.

`ebabot` klasörü içindeki `.env_example` dosyası size örnek olması için oluşturuldu. Sırasıyla aşağıdaki adımları yapalım.

### 1. `.env_example` dosyasını `.env` olarak kaydedelim ve ayarları tanımlayalım

`.env_example` dosyasının adını `.env` olarak değiştirelim. Windows buna izin vermeyebilir. **Notepad++** veya **Sublime Text** gibi bir metin editörü uygulaması ile dosyayı açıp; **Farklı Kaydet** seçeneği ile yapabilirsiniz. Hatta `.env` dosyasını da aynı uygulama ile düzenlemeniz gerekir. Çünkü Windows'ta bulunan **Not Defteri** uygulaması `.env` dosyasının tamamını tek satır gösterecektir. Bu ise dosyanın bozulmasına ve ayarların EBABOT tarafından düzgün okunmamasına sebep olur.

Eğer **Notepad++** veya **Sublime Text** gibi bir uygulama ile açamazsanız; online metin editörü servisi olan bir internet sitesinde düzenlemeyi tamamlayıp `.env` adıyla indirebilirsiniz.  İndirdiğiniz `.env` dosyasını ***ebabot klasörü içine taşımayı unutmayın***.

**Notepad++**, **Sublime Text** ya da online metin editörü ile `.env_example` dosyasını açtığınızda aşağıdaki gibi bir dosya içeriği göreceksiniz.

    DRIVER_PATH="Chromedriver dosyası Yolu Buraya Yazılacak"
    USERS_EXCEL="Kullanıcıların Listelendiği Excel Dosyası Yolu Buraya Yazılacak"

    WEB_HEADLESS=False
    WEB_IMPLICITLY_WAIT=3
    EBA_USER_LOGIN=False
    WEB_SIZE="max"
    # WEB_SIZE="1920,1080"

Şimdi .env dosyasının içindeki ayarları inceleyelim.

|Ayar|Açıklama  |
|--|--|
|**DRIVER_PATH** |İndirdiğiniz chromedriver.exe dosyasının tam adresi buraya yazılacak. Dosya adı ve `.exe` uzantısı dahil tam yolu yazmalısınız. Bu satır şuna benzer olacak: `DRIVER_PATH="C:\Users\Kullanıcı Adınız\Downloads\chromedriver_win32\chromedriver.exe"`|
|**USERS_EXCEL** |Kullanıcıların olduğu Excel dosyasının tam adresi buraya yazılacak. Dosya adı ve `.xls` uzantısı dahil tam yolu yazmalısınız. Bu satır şuna benzer olacak: `USERS_EXCEL="C:\Users\Sultan Özdal\Downloads\ebabot\excel templates\örnek kullanıcılar.xls"`|
|**WEB_HEADLESS**|Bu ayar işlemler sırasında tarayıcının görünmesini veya gizli çalışmasını belirler. Alabilecek değerler `True` veya `False` değeridir. `True` yazılırsa tarayıcı gizli çalışır. `False` yazılırsa tarayıcı işlemler sırasında izlenebilir. Olduğu gibi kalabilir. Örnek: `WEB_HEADLESS=False`|
|**WEB_IMPLICITLY_WAIT**|İşlemler sırasında beklenilecek en fazla saniye cinsinden süreyi buraya yazmalısınız. Benim bilgisayar donanımım, internet hızım ve EBA'nın çok yoğun olmadığı zamanlarda 3 saniye yeterli oluyor. Ancak sizlerin donanımınız ve internet performansınız düşük ise veya EBA'nın yoğun zamanlarında çalıştırıyorsanız; bekleme süresini arttırmanız gerekebilir. Öncelikle bu şekilde deneyin. Hata alırsanız arttırabilirsiniz. **Bu ayar çok önemli. Bazı hataların gelme sebebi olabilir.** Örnek: `WEB_IMPLICITLY_WAIT=3`|
|**EBA_USER_LOGIN**|Bu ayar EBA'ya kullanıcının kendisinin giriş yapmasını veya otomatik girilmesini ayarlar. Otomatik girilmesi için kullanıcıların olduğu Excel dosyasında E-devlet TC ve şifresinin yazılması gerektiğini unutmayın. Eğer `False` yazılırsa *EBABOT otomatik giriş yapar*. `True` yazılırsa **TC ve şifre yazılmış olsa bile kullanıcının kendisinin giriş yapmasını bekler**. Örnek: `EBA_USER_LOGIN=False`|
|**WEB_SIZE**|Tarayıcı boyutunu belirleyen ayar. Eğer `"max"` yazılırsa tarayıcı işlemler sırasında tam ekran çalışır. Ya da piksel cinsinden genişlik ve yükseklik değeri `"1920,1080"` şeklinde yazılabilir. Testlerin tamamı maksimum boyutta yapıldı. Diğerlerini de deneyebilirsiniz. Örnek: `WEB_SIZE="max"` Bir alt satırda bulunan ve başında **#** olan satır (`# WEB_SIZE="1920,1080"`) sadece örnek olması için var. Başında **#** olduğu için EBABOT yazılımı tarafından görünmüyor. **Küçük boyutlarda bazı hatalar alınabiliyor. Sayfa elemanları birbiri üzerine binebiliyor ve *EBABOT*'un tıklama işlemine engel oluyor. Bu sebeple olabildiğince büyük boyutlarda çalışın.**|

İşte EBABOT `.env` dosyası ayarlarını da bitirdik. Artık EBABOT çalışmaya hazır. `.env` dosyasını ebabot klasörü içine taşıdığınıza eminseniz bir sonraki aşamaya geçebiliriz.

> ✅ Buraya kadar yapılan her şey sadece tek seferlik. 😊 Ders programındaki tarih vb güncellemeleri yaparak sürekli kullanabilirsiniz.

# EBABOT'u çalıştırma

EBABOT'un olduğu klasörde komut satırını başlatmamız gerekiyor. Bunun için `ebabot` klasöründeyken, klasörün üstünde bulunan ve bulunduğunuz klasör yolunun (adresinin) olduğu kutucuğa dokunun. Bu kutucukta şuna benzer bir yol yazabilir: `C:\Users\Kullanıcı Adınız\Downloads\ebabot`. İşte bu kutucuktaki yolu silin. Ardından **cmd** yazın ve `enter` tuşuna basın. Bulunduğunuz klasörde çalışacak bir komut satırı açılmış olmalı.

Yukarıdaki örnek klasör yolumuzdan devam edecek olursak; komut satırında sizi şuna benzer yazılar karşılayacaktır.

    Microsoft Windows [Sürüm 6.1.7601]
    Telif Hakkı (c) 2009 Microsoft Corporation. Tüm hakları saklıdır.

    C:\Users\Kullanıcı Adınız\Downloads\ebabot>

Lütfen EBABOT'un bulunduğu klasör yolu ile komut satırındaki `C:\` ile başlayan yolun aynı olduğuna emin olun.

## Harici Canlı Dersleri Tanımlama
Aşağıdaki kod ile hiçbir parametre belirtmeden harici canlı ders tanımlama işlemlerini başlatmış olursunuz.

    python main.py

> **❗❗❗DİKKAT:** İlk defa çalıştırdığınızda bilgisayarındaki güvenlik duvarı
> size **"Python'ın işlem yapacağını ve izin verip vermediğinizi"**
> sorabilir. İzin verip devam edebilirsiniz.

Bu komut çalıştırıldığında EBABOT sizden kullanıcı seçmenizi isteyecektir. Şöyle bir ekran ile karşılaşacaksınız.

    ┌─────────────────────────────────────────────────────────────────────────┐
    │                                                                         │
    │  EBABOT - HARİCİ CANLI DERS                                             │
    │                                                                         │
    │  Lütfen işlem yapılacak kullanıcı seçimi yapın.                         │
    │                                                                         │
    │                                                                         │
    │    1 - Tüm Kullanıcılar                                                 │
    │    2 - Eren Mustafa Özdal                                               │
    │                                                                         │
    │                                                                         │
    └─────────────────────────────────────────────────────────────────────────┘
    >>
**1** numara yazılıp `enter` tuşuna basıldığında bütün kullanıcılar için işlem yapılır. Ya da işlem yapılmasını istediğiniz kullanıcının numarasını yazıp `enter` tuşuna basmanız yeterli.

Eğer Zoom'a daha önce giriş yapılmadı ise; EBABOT durup bekleyecek. Siz giriş yaptığınızda devam edecek. Giriş yaparken *Google Recaptcha* ile bot olmadığınızı kanıtlamak için resimleri seçmenizi isteyecektir.

### Belirli Kullanıcılar İçin Çalıştırma

Harici canlı ders oluşturma koduna `user` parametresi ekleyerek, seçim yapmamıza gerek kalmadan sadece bir kullanıcı için çalıştırabiliriz.

    python main.py user="Eren Mustafa Özdal"

`user` parametresinde, kullanıcıların tanımlandığı Excel dosyasında bulunan aşağıdaki alanlar ile kullanıcı seçilebilir.

 - **satır no :** Excel dosyasındaki satır numaraları. Burada başlık satırının sayılmadığını ve başlıktan sonraki satır olan 2. satırın 1  numaralı satır olduğuna dikkat edin. Yani yanındaki satır numarasını 1 eksik düşünün. Yukarıdaki seçicideki durumdan farklılık gösterir. Örnek:

    `python main.py user="1"`

 - **name :** Kullanıcı için yazdığınız isim. Birebir eşleşmesi gerektiğini unutmayın. Örnek:

    `python main.py user="Eren Mustafa Özdal"`

 - **zoom_email :** Kullanıcının Zoom'a girişte kullandığı ve Excel dosyasında yazılan e-posta adresi. Örnek:

    `python main.py user="zoom@email.com"`

 - **edevlet_tc :** Kullanıcının EBA'ya girişte kullandığı ve Excel dosyasında yazılan TC kimlik numarası. Örnek:

    `python main.py user="11111111111"`

## Oluşturulan ve Tanımlanan Harici Canlı Dersleri Silme

Bütün dersleri Zoom'dan ve EBA'dan tek bir komutla silebilirsiniz. Aşağıdaki kod ile hiçbir parametre belirtmeden harici canlı dersleri silme işlemlerini başlatmış olursunuz.

    python main.py delete="all"

Bu komut çalıştırıldığında EBABOT sizden kullanıcı seçmenizi isteyecektir. Şöyle bir ekran ile karşılaşacaksınız.

    ┌─────────────────────────────────────────────────────────────────────────┐
    │                                                                         │
    │  EBABOT - HARİCİ CANLI DERS                                             │
    │                                                                         │
    │  Lütfen işlem yapılacak kullanıcı seçimi yapın.                         │
    │                                                                         │
    │                                                                         │
    │    1 - Tüm Kullanıcılar                                                 │
    │    2 - Eren Mustafa Özdal                                               │
    │                                                                         │
    │                                                                         │
    └─────────────────────────────────────────────────────────────────────────┘
    >>

**1** numara yazılıp `enter` tuşuna basıldığında bütün kullanıcılar için işlem yapılır. Ya da işlem yapılmasını istediğiniz kullanıcının numarasını yazıp `enter` tuşuna basmanız yeterli.

### Belirli Kullanıcılar İçin Ders Silme İşlemini Çalıştırma

Harici canlı dersleri silme koduna `user` parametresi ekleyerek, seçim yapmamıza gerek kalmadan sadece bir kullanıcı için çalıştırabiliriz. `delete` ve `user` parametrelerinin hangi sırada eklendiği önemli değildir.

    python main.py user="Eren Mustafa Özdal" delete="all"

`user` parametresinde, kullanıcıların tanımlandığı Excel dosyasında bulunan aşağıdaki alanlar ile kullanıcı seçilebilir.

 - **satır no :** Excel dosyasındaki satır numaraları. Burada başlık satırının sayılmadığını ve başlıktan sonraki satır olan 2. satırın 1  numaralı satır olduğuna dikkat edin. Yani yanındaki satır numarasını 1 eksik düşünün. Yukarıdaki seçicideki durumdan farklılık gösterir. Örnek:

    `python main.py user="1"  delete="all"`

 - **name :** Kullanıcı için yazdığınız isim. Birebir eşleşmesi gerektiğini unutmayın. Örnek:

    `python main.py user="Eren Mustafa Özdal"  delete="all"`

 - **zoom_email :** Kullanıcının Zoom'a girişte kullandığı ve Excel dosyasında yazılan e-posta adresi. Örnek:

    `python main.py user="zoom@email.com"  delete="all"`

 - **edevlet_tc :** Kullanıcının EBA'ya girişte kullandığı ve Excel dosyasında yazılan TC kimlik numarası. Örnek:

    `python main.py user="11111111111"  delete="all"`

# SONUÇ

Hiçbir yazılım ilk çıkışını optimum seviyede yapamaz. Zaman içinde olgunlaşır. Performası artar. Hatalardan arınır. EBABOT bir öğretmen olarak bizzat benim de düzenli kullanacağım bir yazılım olacak. Bu sebeple zamanla gelişmeye devam edecektir.

## DİKKAT ❗❗❗

Lütfen EBABOT işlemlerinden sonra kontrollerinizi yapmayı unutmayın. EBABOT bir yazılım olduğu gibi; işlem yaptığı platformlar olan Zoom ve EBA da birer yazılımdır. Anlık sorunlar yaşanabilir. EBA'daki bir sorun aynı zamanda EBABOT'un da işlem yapmasını engelleyecektir. Bu sebeple her türlü kontrollerin sizin sorumluluğunuzda olduğunu belirtmek isterim.

## KATKI SAĞLAMAK

Python dili ile yazılım geliştirme yapabilen kişiler; isterlerse EBABOT'a GitHub üzerinden katkı sağlayabilirler. Yeni bir özellik ekleyebilecekleri gibi; varolan bir hatanın düzeltilmesini veya bir performans iyileştirmesini de sağlayabilirler.

GitHub üzerinden çekme isteği (Pull Request) hakkında bilgi almak için [tıklayın](https://docs.github.com/en/free-pro-team@latest/github/collaborating-with-issues-and-pull-requests/about-pull-requests).

## HATA BİLDİRİMİ

 - İşlem yaparken hatalarla karşılaşırsanız açılan tarayıcıyı kapatın ve tekrar deneyin.
 - Süre ile ilgili olabilecek hataları `.env` dosyasından saniyeyi arttırarak tekrar deneyin.
 - EBA'dan kaynaklanabilecek sorunlarla karşılaşmamak için yoğun olmayan saatleri tercih edin.

Tüm bunlara rağmen düzelmeyen hataları bana aşağıdaki bilgileri vererek bildirin.

 1. İşletim sistemi (Windows, Mac, Linux)
 2. İşletim sistemi türü (32-64 bit)
 3. Ekran çözünürlüğü. Hatayı aldığınız tarayıcı genişlik ve yükseklik boyutu. Maksimum seviyede kullandıysanız bilgisayarınızın ekran çözünürlüğü.
 4. Komut satırında ve tarayıcıda hatanın durumunu gösteren ekran görüntüsü
 5. Hangi ayarlarla EBABOT'u çalıştırdığınızı bilmem için .env dosyanızın bir örneği. Metin veya dosya şeklinde.

Yukarıdaki bilgileri okullutv.info@gmail.com adresine gönderebilirsiniz. Ayrıca [https://github.com/erenmustafaozdal/ebabot/issues](https://github.com/erenmustafaozdal/ebabot/issues) sayfasında konu (issue) açabilirsiniz.

## DİLEK ve TEMENNİ

Kendi tekrarlayan işlerimi, *"otomasyon haline getirmek"* isteği ile başladığım ve bizzat kullandığım projemi; meslektaşlarımla paylaşmanın mutluluğu içindeyim. Bu yazılım tamamen ücretsiz ve açık kaynaklıdır. Ticari amaçlı kullanımı mümkün değildir. Bunun dışında serbestçe kullanılabilir.