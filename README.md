# 7_fark_bulma_oyunu
## Uygulama Hakkında:<br/>
Eğlenceli iki resim arasındaki farkları bulma ve yaratıcı beyin eğitimi oyunu…
İki görüntü arasındaki yedi farkı bulun! Herhangi bir fark bulduğunuzda, ekrandaki alt resimde fark olan alana dokunun. Fark bulma oyunu zihin alıştırmaları yapmak ve görsel yeteneklerinizi geliştirmek için harika bir uygulama! Zihninizi eğitmenin en eğlenceli yolu bu uygulamada.
Uygulamayı açın ve hemen iki resim arasındaki yedi farkı bulmaya başlayın. Eğlenceli resimlerle süslü eğitici bulmaca oyunumuz ile beyin jimnastiği yapın ve görsel yeteneklerinizi geliştirin. Fark bulma oyunları kişilerin dikkatli olmalarını ve daha iyi odaklanmalarını sağlamakla beraber zihninizi daha hızlı çalıştıran oyun grubudur. Neredeyse aynı olan iki fotoğrafı karşılaştırırken gözlem becerilerinizi test edin ve farklılıkları bulmaya çalışın! 7 farkı bul oyunu, görsel motor becerilerinin yanı sıra hem zeka geliştirici hem de hafıza geliştirici bir özelliğe sahiptir.
Eğlenceli bulmaca oyununda farklılıkları bulmaya hazır ol! Hedefin şu: resimlere bak, farkları bul, bulduğun her farkta alt resime dokun. Her seviyede, neredeyse birbirinin aynısı görünen iki güzel fotoğraf sunulacak. Bunlar arasında küçük farklılıklar var. Seviyelerde ilerledikçe seni daha da zorlayacak olan bu oyun sana eğlenme fırsatı sunuyor...
## Oyunda ki amaç:
Oyunumdaki amaç çocuklaar için  eğlenceli zaman geçirirken bir yandan da motor becerilerinizi geliştirmelerini sağlamak. Uygulama içerisindeki hem renk farklılıkları hem de varlık farklılıkları ile kendi dikkat becerinizi ölçebilirsiniz.
## Hitap ettiği kitle: 
Yaş aralığı olarak belirli bir sınıfa hitap etmezken iki resim arasındaki farkı ayırabilecek her birey için uygun tasarım ve anlaşılır uyarılarla her birey için uygundur. 

## Projede Kullanılan Materyaller  
### Linear Layout:<br/>
Kullanımı Android'de, tüm nesneleri tek bir yönde kullanmamızı sağlar. Linear layout sayesinde nesneleri Android:orientation  özelliğini kullanarak, tamamen yatay veya dikey olarak konumlandırabiliriz. Projemizde linear layout’u hem yatay hem de dikey için “match_parent” olarak kullandık.Bu ayarı yaparken kod ile değilde attributes’den özelleştirdik.
### Sayaç:  
Proje içerisinde 3 farklı sayaç kullandım. Kullandığım sayaçlarım;
#### Doğru Sayacı: 
Bu sayacımız bölümdeki tüm doğrular (7) işaretlendiğinde bir sonraki bölüme girişi yapacak olan butonun aktifliğini tetikliyor, toast mesajında bölüm tamamlandı uyarısı veriyor ve bölümü tamamladığımızda giriş ekranına dönmemiz için kullanılıyor.
sapka.setOnClickListener(new View.OnClickListener() {
            @Override
        public void onClick(View v) {
   MainActivity.arapSayac++;
          int ArapSayacMod = MainActivity.arapSayac%7;
          tvArapSayac.setText(String.valueOf(ArapSayacMod));
          sapka.setClickable(false);
          isSeven(MainActivity.arapSayac);
#### Yanlış Sayacı:
Yanlış sayacımız ise o bölümdeki her yanlış tıklamayı içerisinde tutuyor ve sayacımız 3 olduğunda bölüm tamamlanamadı uyarısıyla giriş ekranına dönüş sağlanıyor. Doğru sayacına benzer kod bloğu vardır.
#### Bölüm Sayacı
: Bölüm sayacı ilk açılış yapıldığında “0” olarak başlıyor ve ilk bölüme girme ile koşullandırma başlıyor. İlk bölüm içerisinden doğru sayacını çekerek doğru sayacı=7 butonu aktif et diyerek tıklanma olayını gerçekleştirilmesine izin veren sayacımızdır. 
Toast:  Toast sınıfı, mesaj oluşturmaya ve oluşturduğumuz mesajı kullanıcıya göstermeye yardımcı olur. Bizim proje içerisinde kullandığımız 2 tip toast mesajımız var 
->	Bölüm geçildiğinde 
-> Bölüm geçilemediğinde 
Kullanım şekli: Toast.makeText(getApplicationContext(), "Yazılacak Mesaj",			    Toast.LENGTH_LONG).show();
    //Toast.LENGTH_LONG yerine 2000 girersek 2 sn gösterecektir.
## FORM EKRANLARI
### GİRİŞ EKRANI
Alt tarafta “7 Fark Bulma” oyunumuzun giriş ekranı bulunmaktadır. Bu ekran üzerindeki rakamların da üzerinde transparan butonlar bulunmaktadır. 1 numaralı buton üzerindeki butona direk erişim sağlanabilirken 2 ve 3 numaralı butonlara ise koşullandırma ile aktif ediliyor.  Her bölüm içerisinde doğru ve yanlış sayacı olmak üzere 2 adet sayacımız bulunmaktadır. Bölüm içerisinde yanlış sayacımız ve doğru sayacımız için koşullar bulunmaktadır. Doğru sayacımız yediye eşit olduğunda ana menüye dönerek ekrana “bölüm başarıyla geçildi” mesajı veriliyor ve bir sonraki bölümün geçiş yapacak olan transparan butonunun tıklanabilir özelliğini aktif et komutunu çalıştırır. Yanlış sayacımız ise 3 e eşit olduğunda “3 Defa Yanlış Seçim Yaptınız” ile uyarı verip bölüm içerisindeki sayaçları sıfırlar ve giriş ekranımıza dönüş sağlanır.	 
![giris ekranı](https://github.com/onursonmez37/7_fark_bulma_oyunu/blob/main/android/giris.png)<br/>
### İLK BÖLÜM:
Giriş ekranında 1 numaralı transparan butona tıklanması ile gelecek olan ekrandır. Bölüm açılır açılmaz kullanıcıya alt resimde işaretleme yapınız mesajı verilir ve bulmaca çözülmeye başlatılır. Bölüm içerisinde 2 sayaç bulunur birincisi yanlış işaretlenme sayısını tutarken diğeri de doğru işaretlenme sayısını tutar. Yanlış işaretlenmede yanlış sayacı birer birer artar ve üç olduğunda bölümden çıkar ve ekrana uyarı verip giriş ekranına döner. Her doğru işaretlenmede de sayaç birer birer artar, doğru sayacı 7 ye eşit olduğunda ekrana bölüm tamamlandı mesajı verip giriş ekranındaki 2.bölümün transparan ve pasif olan butonunu aktife çekerek tıklanabilirlik özelliğini değiştirir.	 

![birinci ekranı](https://github.com/onursonmez37/7_fark_bulma_oyunu/blob/main/android/uzay.png)<br/>

### İKİNCİ BÖLÜM:
Giriş ekranında 2 numaralı transparan butona tıklanması ile gelecek olan ekrandır. Bölüm açılır açılmaz kullanıcıya alt resimde işaretleme yapınız mesajı verilir ve bulmaca çözülmeye başlatılır. Bölüm içerisinde 2 sayaç bulunur birincisi yanlış işaretlenme sayısını tutarken diğeri de doğru işaretlenme sayısını tutar. Yanlış işaretlenmede yanlış sayacı birer birer artar ve üç olduğunda bölümden çıkar ve ekrana uyarı verip giriş ekranına döner. Her doğru işaretlenmede de sayaç birer birer artar, doğru sayacı 7 ye eşit olduğunda ekrana bölüm tamamlandı mesajı verip giriş ekranındaki 3.bölümün transparan ve pasif olan butonunu aktife çekerek tıklanabilirlik özelliğini değiştirir.	 

![giris ekranı](https://github.com/onursonmez37/7_fark_bulma_oyunu/blob/main/android/arap.png)<br/>
### ÜÇÜNCÜ BÖLÜM:
Giriş ekranında 3 numaralı transparan butona tıklanması ile gelecek olan ekrandır. Bölüm açılır açılmaz kullanıcıya alt resimde işaretleme yapınız mesajı verilir ve bulmaca çözülmeye başlatılır. Bölüm içerisinde 2 sayaç bulunur birincisi yanlış işaretlenme sayısını tutarken diğeri de doğru işaretlenme sayısını tutar. Yanlış işaretlenmede yanlış sayacı birer birer artar ve üç olduğunda bölümden çıkar ve ekrana uyarı verip giriş ekranına döner. Her doğru işaretlenmede de sayaç birer birer artıp  doğru sayacı 7 ye eşit olduğunda ekrana bölüm tamamlandı mesajı verip giriş ekranındaki 3.bölümün transparan ve pasif olan butonunu aktife çekerek tıklanabilirlik özelliğini değiştirir.	 

![giris ekranı](https://github.com/onursonmez37/7_fark_bulma_oyunu/blob/main/android/nasa.png)<br/>


## KODLAMALAR
### JAVA KODLARI:

Activity Main kodu	
btnuc.setOnClickListener(new View.OnClickListener() {
@Override
public void onClick(View v) {
Intent c=new Intent(MainActivity.this, nasa.class);
startActivity(c);  / / giriş ekranında 3.butona basıldığında
}                     çalışıp sayfalar arası geçişi sağlayan kod                     
});           

### İmport tanımlamaları :
 import android.app.Activity;
 import android.content.Intent;
 import android.os.Bundle;    // Her farklı ekranda kullandığımız sisteme ekleme tanıtma
 import android.view.View;                        amaçlı importlarımız
 import android.widget.Button;
 import android.widget.TextView;
 import android.widget.Toast;
### Her yeni bir bölüm açıldığında ekrana mesaj verme: 
Toast.makeText(getApplicationContext(), "Lütfen Alt Resme İşaretleme Yapınız", Toast.LENGTH_LONG).show();  // Her yeni bölümde alt resimde işaretleme yapılmasını kullanıcıya yansıtan mesaj

### Yanlış tıklamada çalışan kod:
ly.setOnClickListener(new View.OnClickListener() {
@Override  // Sayfanın en arka planında resim üzerinde ekranı kaplayan loyout bulunmaktadır. Layout üzerine butonlar 
public void onClick(View v)    konumlandırıp tıklamayı ya buton ya da loyout üzerinde yapmamızı sağlar. Layout üzerinde 
MainActivity.nasaYanlis++;     tıklanma olursa yanlışı butona tıklanmada ise doğru sayacını arttırıyor. Burada layout içindeki 
 yanlisTiklama(MainActivity.nasaYanlis); kod bloğu yazılmıştır.
}});

### 3 defa yanlış seçim yapıldığında çalışan kod : 
public void yanlisTiklama(int nasaYanlis){     
if(nasaYanlis%3 == 0){ 
MainActivity.nasaSayac=0;                                                // sayacı sıfırlama
Toast.makeText(getApplicationContext(), "3 Defa Yanlış Seçim Yaptınız , Lütfen Tekrar Deneyiniz", Toast.LENGTH_SHORT).show();
Intent mainActivity =new Intent(this, MainActivity.class);
startActivity(mainActivity);                                        // Main Activitye dönüş
}}


### Butona tıklandığında doğru sayacını arttırma ve kontrol etme	
gezegen.setOnClickListener(new View.OnClickListener() {          // butona tıklandığı anda
@Override
public void onClick(View v) { 
MainActivity.nasaSayac++;                                                                    doğru sayacını bir arttır
int nasaSayacMod = MainActivity.nasaSayac%7;     doğru sayacı 7 ye tam bölünüyor mu diye kontrol et
tvNasaSayac.setText(String.valueOf(nasaSayacMod));                     sayacı tvNasaSayac’a aktar
gezegen.setClickable(false);                                           gezegen butonunun tıklanabilirlik özelliğini kapat
isFive(MainActivity.nasaSayac);
 } }); 


### Final tanımlamalarımız:	
final Button gunes = findViewById(R.id.yildiz);
final Button deve = findViewById(R.id.deve);
final Button cadir = findViewById(R.id.cadır);
final Button kaktus = findViewById(R.id.kaktus);
final Button sapka = findViewById(R.id.sapka);
final Button piramit = findViewById(R.id.piramit);
final Button gozluk = findViewById(R.id.btnGozluk);
final TextView tvArapSayac = findViewById(R.id.arapSayac);
final ConstraintLayout ly = findViewById(R.id.arapLayout);


## XML KODLARI
## Aktivity main xml’i
<Button
    android:id="@+id/btnIlk" –buton id’si
    android:layout_width="wrap_content"   -> genişliği ortala 
    android:layout_height="wrap_content" -> yüksekliği ortala
    android:background="@color/colorPrimary"-> rengi ayarlama
    android:visibility="invisible"         -> görünürlüğü gizli
/>

Birinci   bölüm
xml’i	<Button
    android:id="@+id/bayrak" –> bayrak üzerindeki buton id’si
    android:layout_marginLeft="120dp" -> Soldan 120dp kayması
    android:background="@color/colorPrimary" -> renk ayarı
    android:visibility="invisible" -> görünürlüğü gizli
  />

İkinci  bölüm
xml’i	<Button
 android:id="@+id/kaktus" –> kaktüs üzerindeki buton id’si
 android:layout_width="wrap_content"-> genişliği ortalama
 android:layout_height="wrap_content" -> yüksekliği ortalama
 android:layout_marginTop="318dp"-> kenardan 318dp boşluk bırak
/>


üçüncü  bölüm
xml’i	<Button
    android:id="@+id/topurcuk" -> buton id’si topurcuk
    android:layout_width="99dp" ->genişliği 99dp 
    android:layout_height="74dp" ->yüksekliği 99dp
    android:layout_marginEnd="4dp" ->sondan 4dp uzak
    android:layout_marginRight="4dp" ->sağdan 4dp uzak/>
# UYGULAMA SONUCU:
Uygulamam tüm android cihazlar için uyumludur. Zaman sıkıntısı olmadan görsel  hafızanızı geliştirebilir ve boş zamanlarınızı değerlendirirken eğlenceli oyun oynama zevki sunuyor. Eğlenceli resimlerle oyundan sıkılmadan dilediğiniz kadar oynayabileceksiniz.

 KARŞILAŞTIĞIM ZORLUKLAR: 
Sayfalar arası veri çekme ve kullanma: Giriş sayfasında ilk bölümü direk açılırken ikinci ve üçüncü bölümler için bir önceki bölümün doğru sayacını öğrenmemiz ve bunu karşılaştırmamız gerekiyordu. Giriş ekranı üzerinde ikinci butona bastığında kodda ilk bölümün doğru sayacı eşit mi yediye diye kontrol ettirip eğer eşit ise tıklanabilirlik özelliğini aktif ediyoruz ve bölüm içerisine girilmesine izin veriyoruz.
## EKSİK GÖRDÜĞÜM YERLER: 
	Doğru ve yanlış seçimlerde kullanıcıya doğruyu veya yanlışı işaretlediğini belli etme amaçlı işaret koyma.
	Bölüm ekranlarındaki alt ve üst resimlerde buton koyup bunları birbirine eşitleyerek kullanıcıya sadece alt resimde işaretlemeyi zorunlu bırakmama.
 ## GELİŞTİRME ÖNERİLERİ:
	Bölümlerdeki resimlerin zorluk seviyesi arttırabilir.
	Süre konulabilir.
	Kullanıcıdan fotoğraf alınıp bunu bölümlerde sunabilirim.
	Bölüm sonlarında yıldız ile ödüllendirip her 10 bölümde 30 yıldıza ulaştığında istediği bölümü direk geçebilme butonu eklenebilir.
