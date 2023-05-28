# Template_Matching
Ödevde izlenecek adımlar :
1.	Görselleri yükleyip: Belirtilen linkteki 150 adet görseli bilgisayar indirin ve bir klasöre kaydedin.
2.	Görselleri parçalara bölün: Her görseli 20x20 piksel boyutunda parçalara bölebilirsiniz. Bu, görselinizi daha küçük bölgelerini analiz etmenize ve benzerlikleri bulmanıza yardımcı olur.
3.	Template Matching yöntemini uygulayın: OpenCV veya benzer bir kütüphane kullanarak, her parçayı diğer parçalarla karşılaştırın ve benzerlik oranlarını hesaplayın. Template Matching yöntemi, bir görüntüdeki bir şablona en iyi eşleşen bölgeyi bulmanıza yardımcı olabilir.
4.	En çok benzeyenleri belirleyin: Benzerlik oranlarına göre parçaları sıralayın ve en yüksek benzerlik oranına sahip olanları bulun. Bu şekilde, birbirine en çok benzeyen parçaları belirleyebilirsiniz.
Algoritmanın karmaşıklık sınırları, kullanılan yöntemlere, görsel boyutuna ve analiz edilen parçaların sayısına bağlı olarak değişebilir. Özellikle büyük bir görsel veri seti üzerinde çalışılıyorsa, işlem süresi artabilir. Bu nedenle, verilerinizin boyutuna ve hesaplama kaynaklarına göre karmaşıklığı göz önünde bulundurmanız önemlidir.
Template Matching ne işe yarar nasıl bir yöntemdir:
Template Matching, bir görüntü işleme yöntemidir ve bir görüntü içinde belirli bir desenin veya şablonun varlığını bulmak için kullanılır. Bu yöntem, görüntü içinde şablonun piksel değerlerinin benzer olduğu bölgeleri bulmak için bir şablon deseniyle karşılaştırma yapar.
Template Matching'in temel adımları şunlardır:
1.	Giriş Verilerinin Hazırlanması: Template Matching için öncelikle giriş görüntüsü ve şablon deseni hazırlanır. Giriş görüntüsü, aranan nesnenin bulunduğu büyük bir görüntü olabilirken, şablon deseni aranan nesnenin küçük bir kısmını temsil eder.
2.	Karşılaştırma Yöntemi Seçimi: Template Matching için farklı karşılaştırma yöntemleri kullanılabilir. Örnek olarak, piksel değerlerinin farkı, korelasyon katsayısı veya kesişim over union (IoU) gibi metrikler kullanılabilir. Karşılaştırma yöntemi seçimi, belirli bir uygulamaya ve veri setine bağlı olarak değişebilir.
3.	Şablon Karşılaştırması: Giriş görüntüsü üzerinde, şablon deseni ile karşılaştırma yapılır. Bu işlem, şablon deseninin piksel değerlerini, giriş görüntüsünün her bir bölgesiyle karşılaştırarak benzerlik skorunu hesaplar.
4.	Benzerlik Skorunun Hesaplanması: Karşılaştırma sonucunda, her bir bölge için bir benzerlik skoru elde edilir. Benzerlik skoru, şablon deseniyle giriş görüntüsü bölgesi arasındaki benzerliği ölçer. Yüksek bir benzerlik skoru, şablonun o bölgeyle iyi bir eşleştiğini gösterir.
5.	Eşleşen Bölgelerin Belirlenmesi: Benzerlik skorları analiz edilerek, şablon deseniyle en iyi eşleşen bölgeler belirlenir. Bu bölgeler, şablonun giriş görüntüsündeki konumunu ve varlığını gösterir.
Template Matching, basit bir görüntü işleme yöntemi olmasına rağmen, bazı zorlukları da beraberinde getirir. Özellikle, ışıklandırma değişiklikleri, ölçekleme, dönme gibi deformasyonlar, arka plan gürültüsü gibi faktörler doğru eşleştirmeyi etkileyebilir. Bu nedenle, Template Matching genellikle daha karmaşık yöntemlerle birlikte kullanılan bir başlangıç noktası olarak tercih edilir.

OpenCV nedir ne işe yarar:
OpenCV (Açık Kaynak Bilgisayarlı Görüntü İşleme Kütüphanesi), bilgisayarlı görüntü işleme ve makine görüşü uygulamaları geliştirmek için kullanılan popüler bir açık kaynaklı kütüphanedir. Python, C++, Java ve diğer birçok programlama dilinde kullanılabilen bir kütüphanedir. OpenCV, görüntüleri ve videoları işlemek, nesne algılamak, nesne takip etmek, yüz tanımak, kamera kalibrasyonu yapmak ve daha birçok görüntü işleme işlevini sağlar.
OpenCV'nin bazı temel özellikleri şunlardır:
1.	Görüntü ve Video İşleme: OpenCV, görüntülerin ve videoların okunması, yazılması, görüntü formatlarının dönüştürülmesi, yeniden boyutlandırılması, kesilmesi ve birleştirilmesi gibi işlemleri gerçekleştirebilir.
2.	Görüntü İşleme Algoritmaları: OpenCV, bir dizi temel görüntü işleme algoritmasını içerir. Bunlar arasında filtreleme, kenar tespiti, histogram eşitleme, morfolojik işlemler, piksel manipülasyonu ve renk dönüşümleri bulunur.
3.	Nesne Algılama ve Takibi: OpenCV, nesne algılama ve takibi için çeşitli yöntemler sağlar. Özellikle, önceden eğitilmiş modelleri kullanarak nesneleri tespit etmek için derin öğrenme tabanlı yöntemleri destekler.
4.	Yüz Algılama ve Tanıma: OpenCV, yüzleri tespit etmek, yüz özelliklerini belirlemek ve yüz tanıma gibi yüz işleme görevleri için özel işlevler sunar. Bunlar, yüz tabanlı kimlik doğrulama ve yüz izleme gibi uygulamalarda kullanılabilir.
5.	Kamera Kalibrasyonu ve 3B Görüntüleme: OpenCV, kamera kalibrasyonu işlemlerini gerçekleştirmek için araçlar sağlar. Bu, kamera parametrelerini belirlemek ve 3B dünyadaki nesneleri doğru bir şekilde yerleştirmek için kullanılır.
OpenCV, geniş bir kullanıcı ve geliştirici topluluğuna sahiptir ve hem akademik araştırmalarda hem de ticari uygulamalarda yaygın olarak kullanılmaktadır. Kütüphane, yüksek performanslı ve etkili algoritmalar sunarak görüntü işleme projelerinin hızlı bir şekilde geliştirilmesini sağlar. OpenCV, belgeleme ve örneklerle zengin bir kaynak sağlayarak kullanıcıların hızlı bir şekilde öğrenmelerine ve projeler

OpenCV ye benzeyen kütüphaneler:
OpenCV, bilgisayarlı görüntü işleme alanında en yaygın kullanılan açık kaynaklı kütüphanelerden biridir. Bununla birlikte, OpenCV dışında başka görüntü işleme kütüphaneleri de bulunmaktadır. İşte OpenCV'ye benzer bazı popüler görüntü işleme kütüphaneleri:
1.	Pillow: Python için bir görüntü işleme kütüphanesidir. Görüntüleri yüklemek, manipüle etmek, dönüştürmek, filtrelemek, yeniden boyutlandırmak ve kaydetmek gibi işlevleri destekler.
2.	scikit-image: Python tabanlı bir görüntü işleme kütüphanesidir. Görüntü işleme algoritmaları, özellik çıkarımı, filtreleme, dönüşümler, segmentasyon, morfolojik işlemler ve daha fazlasını içerir.
3.	NumPy: Python'da çok boyutlu dizi işlemleri için bir kütüphanedir. Görüntüler, NumPy dizileri olarak temsil edilebilir ve bu kütüphane, görüntü verilerinin işlenmesi, dönüşümü ve analizi için kullanılabilir.
4.	TensorFlow: Derin öğrenme uygulamaları için bir açık kaynaklı kütüphanedir. Görüntü sınıflandırması, nesne tespiti ve görüntü segmentasyonu gibi görevlerde kullanılır. TensorFlow modelleri, görüntü işleme uygulamalarında yaygın olarak kullanılan Convolutional Neural Networks (CNN) gibi derin öğrenme mimarilerini destekler.
5.	PyTorch: Yine derin öğrenme için kullanılan bir açık kaynaklı kütüphanedir. Görüntü sınıflandırması, nesne tespiti, segmentasyon ve stil transferi gibi görevlerde kullanılabilir. PyTorch, esneklik ve kullanım kolaylığı açısından popülerdir.
6.	MATLAB Image Processing Toolbox: MATLAB ortamında kullanılan bir görüntü işleme aracıdır. Görüntü işleme algoritmaları, filtreleme, segmentasyon, kenar tespiti, şekil tanıma ve görüntü iyileştirme gibi işlevleri içerir.
Bu listedeki kütüphaneler, OpenCV'ye benzer işlevlere sahip olup görüntü işleme uygulamalarında yaygın olarak kullanılmaktadır. Seçim, projenizin gereksinimlerine, programlama dilinize ve tercihlerinize bağlı olarak değişebilir.

