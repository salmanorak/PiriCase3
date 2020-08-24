Piri Medya Case 3

# Reactjs veya Vuejs ile widget geliştirilmesi

İlk 4 hafta ve son 3 hafta haricindeki haftalar widgetın tam orta sırasına yani 5. sırada
gelecek şekilde focuslanacak. Widgetta 8 tane hafta görünecek.İlk 4 hafta ve son 3 hafta için
tasarımdaki hali gibi görünecek.Kendi içerisinde scroll olacak.(Yani scroll bulunduğumuz
haftaya focuslanacak örnek olarak yukarıdaki 12 hafta da belirtildi. Tasarımdaki gibi aktif olan
hafta geçmiş hafta ve gelecek haftalardaki gibi renklere uygun şekilde yapılmalıdır.)

# Çözüm
3 komponentten oluşan bir modül oluşturuldu.

1- Container: Dataların oluşturulması ve listenin başlık kısmını tutan componenttir.
2- Liste : Listenin oluşturulması ve doğru elemente focus olunmasını sağlamaktadır.
3- Liste Elemanları: Listedeki her bir elemanın bilgileri tutar. Görünümü ve içeriğini tutan componenttir.
