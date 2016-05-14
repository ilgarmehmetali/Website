<!--
.. title: Gnome Bildirim Uyarıları
.. slug: gnome-bildirimleri-uyarilari
.. date: 2016-05-14 04:11:51 UTC+03:00
.. tags:
.. category:
.. link:
.. description:
.. type: text
-->

Gnome'un uygulamaların libnotify kütüphanesini kullanarak kullanıcıya bildirim göndermelerine olanak sağlayan, kabuk ile bütünleşik bir bildirim sistemi var. Gönderilen bildirimler ekranın üst kısımında baloncuk olarak gözüküyor, belli bir süre geçmesiylede takvim panelinin yanında yerini alıyor. Eğer gelen bildirimi, bildirim balonu açık iken kapatmazsanız daha sonra takvim panelinde okuyup kapatabiliyorsunuz. Okunmamış bildiriminiz olduğunuda ise takvimin yanında küçük bir beyaz nokta beliriyor. Ne yazıkki bu beyaz nokta her zaman dikkatimi çekmeye yeterli olmuyor.<!-- TEASER_END --> Acaba bildirim olduğu zaman daha dikkat çekici bir uyarı verebilecek bir gnome eklentisi varmı diye araştırırken [Notifications Alert] eklentisini buldum.

Notifications Alert eklentisi okunmamış bildirim olduğu zaman saat ve takvim'in renkli bir şekilde yanıp sönmesini sağlıyor. Normalde beyaz olarak kullandığım yazı renginin kırmızı yanıp sönmesi oldukça dikkat çekici oluyor.

Neden böyle bir eklentiye ihtiyaç duyduğuma gelirsek, bir süredir sistemime bir mail istemcisi yüklemeyi düşünüyordum ve sonunda Thunderbird yüklemeye karar verdim. Gelen mailleri haber vermek için kendi geliştirdikleri bir bildirim sistemleri var ama sistem ile bütünleşik çalışacak bir bildirim sisteminin daha çok hoşuma gideceğini düşünerek araştırma yaptığımda libnotify kullanan [Enhanced Desktop Notifications] isimli eklentiyi buldum.

Mail bildirimlerimi artık sorunsuz bir şekilde fark edebileceğim derken eklentinin her bildirim için uyarı veriyor olması benim için rahatsız edici bir olay olmaya başladı. Sisteminde aktif olarak spotify kullanan birisiyim ve spotify her müzik değiştiği zaman bir bildirim ile hangi parçanın çalınmaya başladğını size haber veriyor. 3-4 dakika arayla yanıp sönen uyarıdan kurtulmak için sürekli bildirimi okundu olarak işaretlemek çok can sıkıcı bir hal alıyordu.

Acaba eklentinin karaliste desteği varmı diye araştırdığımda olmadığını gördüm. Belki [github][gnome-shell-notifications-alert]'da geliştirilmekte olan bir özelliktir diyip projenin issues sayfasını incelemeye başladım. Bu konuyla ilgili açılmış 2 issue([\#23][23] [\#24][24]), 1 tanede whitelist isteği olan issue([\#9][9]) gördüm ama ne yazıkki geliştirilmeye başlanmamıştı.

İhtiyacım olan bu özelliği kendim ekleyebilirmiyim diye düşünmeye başladım. Projenin kaynak kodlarını inceledikten ve gnome eklentileri üzerine araştırma yaptıktan sonra çalışmalara başladım.

Araştırmalarım sırasında iki adet dökümantasyon([Gnome JavaScript Docs][doc2] ve [Giovanni Campagna'nın otomatik oluşturulmuş dökümantasyonu][doc1]) gözüme çarptı, yanlız GTK'nın javascript binding dökümantasyonun tahmin edemeyeceğim kadar zayıf durumda olduğunu gördüm. Bulduğum dökümantasyonlar metodların ve veri yapılarının kullanımı hakkında örnek içermiyordu, buda yeni bir api'ye alışmayı oldukca zor bir hale getirdi.

Belli bir uğraştan sonra bildirim uyarılarına filtre ayarı ekleyebildim ve değişiklilerimi eklentinin geliştiricisine pull-request olarak gönderdim. Eğer sizinde gelen bildiriler ile ilgili sürekli uyarı almaya ihtiyacınız varsa [Notifications Alert] eklentisini kullanmanızı öneririm.


[gnome-shell-notifications-alert]: https://github.com/hackedbellini/gnome-shell-notifications-alert
[Enhanced Desktop Notifications]: https://addons.mozilla.org/en-US/thunderbird/addon/enhanced-desktop-notifications/
[Notifications Alert]: https://extensions.gnome.org/extension/258/notifications-alert-on-user-menu/

[9]: https://github.com/hackedbellini/gnome-shell-notifications-alert/issues/9
[23]: https://github.com/hackedbellini/gnome-shell-notifications-alert/issues/23
[24]: https://github.com/hackedbellini/gnome-shell-notifications-alert/issues/24

[doc1]: https://people.gnome.org/~gcampagna/docs/
[doc2]: http://docs.ptomato.name:9292/
