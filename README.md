# tutorial
TUTORIAL 6.1: ARITHMETIC OPERATIONS

##Question 1 What are the maximum and minimum values of the original and the adjusted image? Explain your results.

I=imread('cameraman.tif') imshow(I)

J=imadd(I,75) figure

K=subplot(1,2,1),imshow(I),title('Original Image'); L=subplot(1,2,2),imshow(J),title('Brighter Image');

2

I = imread('cameraman.tif'); J = imread('cameraman2.tif'); figure subplot(1,2,1), imshow(I), title('Original Image'); subplot(1,2,2), imshow(J), title('Altered Image');

image

##Question 2 How many pixels had a value of 255 in the original image and how many have a value of 255 in the resulting image?

image

##Question 3 How did we scale the image output?

Verilenlere göre yapılan ölçeklendirme komutları..

subplot(2,2,3), imshow(diffim,[]), ...
title('Subtracted Image Scaled');
subplot(2,2,4), imshow(diffim2,[]), ...
title('Abs Diff Image Scaled');
Aynı zamanda;

B = imresize(A,scale) , komutu ile ölçeklendirme yapılır.Komut içerisindeki scale kısmında orijinal fotoğrafa göre küçültme veya büyültme işlemi yapılabilir. Örneğin aşağıda yazmış olduğum kod ile oriijinal fotoğrafa 0.5 kat küçültme işlemi uygulanmıştır.

I = imread('cicek.jpg'); J = imresize(I, 0.5); figure, imshow(I), figure, imshow(J)

##Question 6 When dynamically scaling the moon image, why did the dark regions around the moon not become brighter as in the normally adjusted image?

Z = imdivide(X,Y), X dizisindeki her öğeyi Y dizisindeki karşılık gelen öğeye böler ve sonucu Z çıktı dizisinin karşılık gelen öğesinde döndürür.

Bölüm, X ile aynı boyutta sayısal bir dizi olarak döndürülür. Z, X mantıksal olmadığı sürece X ile aynı sınıftır; bu durumda Z, veri türü double'dır. X bir tamsayı dizisiyse, tamsayı türünün aralığını aşan çıktı öğeleri kesilir ve kesirli değerler yuvarlanır.

image

##Question 7 Why did the multiplication procedure produce the same result as division?

Bölme Z çıktı dizisinin karşılık gelen öğesinde döndürür, çarpma da ürünü Z çıkış dizisinin karşılık gelen öğesinde döndürür.

##Question 8 Write a small script that will verify that the images produced from division and multiplication are equivalent.

I = imread('moon.tif'); J = immultiply(I,0.5); imshow(I) figure imshow(J)

I = imread('rice.png'); J = imdivide(I,2); imshow(I) figure imshow(J)

TUTORIAL 6.2: LOGIC OPERATIONS AND REGION OF INTEREST PROCESSING

##Question 1 How do we add points to the polygon? Yeni bir nokta eklemek için poligonun ilk noktasının üzerine işaretçiyi getirin ve tıklayın.

##Question 2 How do we delete points from the polygon?

İmleci ROI'ye getirin, sağ tıklayın ve içerik menüsünden Çokgeni Sil'i seçin. Ayrıca, deletenesne yöntemini kullanarak ROI'yi programlı olarak silebilirsiniz.

##Question 3 How do we end the process of creating a polygon?

Tepe noktası ve bitiş kısmını birleştirip çift tıklayın,ardından enter'a basın.

##Question 4 What class is the variable bw?

Giriş görüntüsü I uint8, uint16, int16, single veya double sınıfında olabilir. Çıktı görüntüsü BW mantıksal sınıftadır. Diğer tüm girdiler ve çıktılar double sınıfındadır.

##QQuestion 5 What does the variable bw represent?

roipoly, maskeli filtreleme için maske olarak kullanabileceğiniz ikili bir görüntü döndürür.

Question 6 In the above conversion step, what would happen if we used the im2uint8 function to convert the bw image as opposed to just using uint8(bw)? (Hint: after conversion, check what is the maximum value of the image bw2.)

uint8 ,veri tipindeki (sınıf) uint8değişkenler 1 bayt (8-bit) işaretsiz tamsayılar olarak saklanır im2uint8(I) gri tonlamayı, RGB'yi veya ikili görüntüyü I uint8'e dönüştürür, gerektiğinde verileri yeniden ölçeklendirir veya dengeler.

##Question 7 What happens when we logically AND the two images?

AND'nin en belirgin uygulaması, iki görüntünün kesişimini hesaplamaktır. Genel olarak, aralarındaki farklılıkları veya benzerlikleri tespit etmek için AND operatörünü (veya diğer mantıksal operatörleri) iki görüntüye uygulamak, ikili olmaları veya eşikleme kullanılarak ikili biçime dönüştürülmeleri durumunda en uygunudur.

##Question 8 What happened when we complemented the bw2 image?

Morfolojik işlemlerden sonra görüntü, 2 boyutlu mantıksal matris olarak döndürülür.

BW = imread( 'circles.png' ); imshow(BW); BW2 = bwmorph(BW, 'kaldır' ); figür göster(BW2) BW3 = bwmorf (BW, 'skel' , Inf); figür göster(BW3)

Yukarıdaki komut satırlarının sonucunda görüntünün iskeleti alınmıştır.

TUTORIAL 7.1: IMAGE CROPPING, RESIZING, FLIPPING, AND ROTATION

##Question 1 Which numbers did you record for the top left and bottom right co�ordinates and what do they mean? Sol üst için (31,35), sağ alt için (177,245) koordinatları.

##Question 2 Visually compare the three resized images. How do they differ?

image

Yukarıdaki görüntüde görüldüğü üzere ilk görüntü orijinal olan,diğerlerine göre ölçeklendirme olarak daha küçük. Ortadaki pikselli bir görüntüye sahip ve orijinal görüntüye göre ise ölçeklendirilmiştir.Son görüntü ise blur ve orijinal görüntüye göre ölçeklendirilmiştir.

##Question 3 How did we scale the image?

imresize() komutu ile ölçeklendirme yapılmıştırç

I_big2 = imresize(I,3,’nearest’); I_big3 = imresize(I,3,’bilinear’); figure, imshow(I_big2), ... title(’Resized w/ nearest-neighbor interpolation’); figure, imshow(I_big3), ... title(’Resized w/ bilinear interpolation’);

##Question 4 What are the limitations of this technique?

B = imresize(A,m,method), A'nın boyutunun m katı olan bir görüntü döndürür. m, 0 ile 1.0 arasındaysa, B, A'dan küçüktür. m, 1.0'dan büyükse, B, A'dan daha büyüktür.

##Question 5 Inspect the size (number of rows and columns) of I_rot and compare it with the size of I. Why are they different?

Ölçeklendirilme yapılmıştır.imresize() komutu ile.

##Question 6 The previous step rotated the image counterclockwise. How would you rotate the image 35◦ clockwise?

flipub() ve fliplr() komutları ile satır ve sütün olarak döndürülmüştür.

##Question 7 How did bilinear interpolation affect the output of the rotation?

Geometrik dönüşümdeN farklı bir kayma kullanıyormuş gibi görünmesidir.

##Question 8 How did the crop setting change the size of our output?

Aşağıdaki görüntüde görüldüğü üzere çıktıda görüntümüzün bir kısmı kırpılmıştır.

image

TUTORIAL 7.2: SPATIAL TRANSFORMATIONS AND IMAGE REGISTRATION

##Question 1 Compare the two resulting images (I2 and I3). Inspect size, gray�level range, and visual quality. How are they different? Why?

image

##Question 2 Compare the two resulting images (I4 and I5). Inspect size, gray�level range, and visual quality. How are they different? Why?

image

##Question 3 Compare the two images (I1 and I6). Inspect size, gray-level range, and visual quality. How are they different? Why?

image

TUTORIAL 8.1: GRAY-LEVEL TRANSFORMATIONS

##QQuestion 2 How can we show that the adjusted image and the original image are equivalent?

Grafik tablomuzdaki doğruya bakarak bunu anlayabiliriz.Aşağıdaki grafikte görüldüğü gibi x=0 grafiği eşdeğer olduğu anlamına gelmektedir.

image

##Question 3 How did we create the negative transformation function?

uint8 veri dönüşümü ile bunu sağladık.Aynı zamanda bir önceki soruda eşdeğer olma durumu burada da kanıtlanmış oldu.Dönüşüm fonksiyonu artık x=0 değil.

image
TUTORIAL 9.1: IMAGE HISTOGRAMS

##Question 1 Explain the drastic change of the Y-axis values when the histogram is displayed with fewer bins.

Aşağıda görüldüğü gibi 64-bin grafiğinde y eksenindeki değerler 1000'er artarken , 32-bin grafiğindeki y eksenindeki deeğerler 2000'er artmaktadır.Bu da x eksenindeki görüntü aralıklarını etkilemektedir.

image

##Question 2 What does the function numel do?

image

c_norm=c/ numel(I); I dizisindeki öğe sayısını, c_norm'u, prod(size(I)'ya eşdeğer) döndürür.

##Question 4 How would we change the width of the bars in a bar chart?

barwidth() komut satırı ile mümkündür.

barWidth = handles.slider1.Value; //0 ile 1 arasında kaydırıcı değer alınır,sonrasında bar() komutu ile çağırılır. bar(x, y, 'BarWidth', barWidth);

##Question 5 Explore the properties of stem charts. How can we make the lines dotted instead of solid?

s = stem(1:10); s.Color = 'red';

image

##Question 6 Alter the axes limits and tick marks to reflect the data being displayed in the stem plot.

Eksen sınırlamaları değişimleri ve kendi yaptığım diğer değişiklikler aşağıdaki gibidir.Bunlar için axis manual,auto,ij ; subplot(2,2,1),subplot(2,2,2); color olarak green i seçtim.

image

image

image

TUTORIAL 9.2: HISTOGRAM EQUALIZATION AND SPECIFICATION

##Question 1 Why must we include the second parameter (256) in the histeq function call?

Histogramın yoğunluk görüntüsü,görüntü içindeki ayrık düzey sayısından çok daha küçük olduğunda daha iyi eşleşme sağlar.

##Question 2 What is the effect of histogram equalization on images with low con�trast?

Bu , daha düşük yerel kontrasta sahip alanların daha yüksek bir kontrast kazanmasına izin verir . Histogram eşitleme bunu, görüntü kontrastını azaltmak için kullanılan yüksek yoğunluktaki değerleri etkin bir şekilde yayarak gerçekleştirir.

##Question 3 Based on the tire image’s original histogram, what can be said about its overall brightness?

Equalized histogramda parlaklık görüntünün pixellerini 255 olarak değiştiğini veyahut yaklaştığını göstermektedir. göstermektedir.

image

##Question 4 How did histogram equalization affect the overall image brightness in this case?

Equalized histogramda 0-150 arası değer aralıkları artmış,150-250 arasın değer aralıkları sıklaşmıştır.

##Question 5 Why was there such a loss in image quality after histogram equaliza�tion?

Original ve Equalized histogramlarına bakacak olursak 0-75 arası gibi 255 pixel görüntüleri ,0 pixel görüntülere çevirmiştir.Yani teoride, eğer histogram eşitleme fonksiyonu biliniyorsa, orijinal histogram kurtarılabilir. Hesaplama, hesaplama açısından yoğun değildir. Yöntemin bir dezavantajı , gelişigüzel olmasıdır . Kullanılabilir sinyali azaltırken arka plan gürültüsünün kontrastını artırabilir.Aşağıdaki görüntünün sebebi de budur.

image

##Question 6 What does the cumsum function do in the previous step?

B = cumsum(A), boyutu 1'e eşit olmayan A'daki ilk dizi boyutunun başlangıcından başlayarak A'nın kümülatif toplamını döndürür.

A bir vektörse, cumsum(A), A'nın öğelerinin kümülatif toplamını içeren bir vektör döndürür.

A bir matrisse, cumsum(A), A'nın her sütunu için kümülatif toplamları içeren bir matris döndürür.

A çok boyutlu bir diziyse, cumsum(A) ilk tek olmayan boyut boyunca hareket eder.

##Question 8 How do the different interpolation methods change the shape of the desired histogram curve?

Aşağıdaki figürlerden ikinci grafik ,birinci grafiğe göre dalgalanmaları çok olan bir grafiktir.(0,0.5) değerini (0,0) değerlerine dönüştürmüştür.

image

##Question 10 What does the ClipLimit setting do in the adapthisteq func�tion?

'ClipLimit', özellikle homojen alanlarda görüntünün aşırı doygunluğunu önleyen bir kontrast faktörüdür. Bu alanlar, aynı gri seviye aralığına düşen birçok pikselden dolayı belirli görüntü döşemesinin histogramında yüksek bir tepe noktası ile karakterize edilir. Klip sınırı olmadan, uyarlanabilir histogram eşitleme tekniği, bazı durumlarda orijinal görüntüden daha kötü sonuçlar üretebilir.

TUTORIAL 9.3: OTHER HISTOGRAM MODIFICATION TECHNIQUES

##Question 1 How did the histogram change after the adjustment?

x ekseni 0.3 noktasından 0.4 noktasına kaymıştır.

image

##Question 2 What does the variable bad_values contain?

bad_values = find(I3 > 1); I3(bad_values) = 1;

Yukarıdaki komut satırına göre gama değeri doğrusal olarak seçilmiştir.

##Question 3 Why does the third plot show such an excessive number of pixels with a value of 1?

constrat değeri 0.5 seçilip fotoğrafa eklenerek pikseli arttırılmıştır.

image

##Question 4 How did the histogram change after the adjustment?

Değer aralığı x-ekseninde 0.3 ile 0.6 arasından , 0 ile 1 arasına çıkmış ve görüntüye netlik verilmiştir.

image

##Question 5 What is the purpose of using the stretchlim function?

LOW_HIGH = Stretchlim(I), kontrast gerdirme görüntüsü I için kullanılabilecek alt ve üst limitleri belirten iki elemanlı piksel değerleri vektörü olan LOW_HIGH değerini döndürür. Varsayılan olarak, LOW_HIGH içindeki değerler, tüm piksel değerlerinin en alttaki %1'ini ve en üstteki %1'ini belirtir. Döndürülen gri değerler, bir görüntünün kontrastını artırmak için imadjust işlevi tarafından kullanılabilir.

##Question 8 What do the above first two statements in the code do?

B = reshape(A,m,n) öğeleri A'dan sütun bazında alınan m'ye n matris B'yi döndürür. A'nın m*n öğesi yoksa bir hata oluşur.

B = reshape(A,m,n,p,...) veya B = reshape(A,[mnp ...]), A ile aynı öğelere sahip ancak m-by- boyutuna sahip olacak şekilde yeniden şekillendirilmiş bir ND dizisi döndürür n-by-p-by-... . Belirtilen boyutların ürünü, mnp*..., prod(beden(A)) ile aynı olmalıdır.

B = reshape(A,...,[],...) yer tutucu [] tarafından temsil edilen boyutun uzunluğunu hesaplar, öyle ki boyutların çarpımı prod(size(A)'ya eşittir). prod(size(A)) değeri, belirtilen boyutların çarpımı tarafından eşit olarak bölünebilir olmalıdır. [] öğesinin yalnızca bir oluşumunu kullanabilirsiniz.

B = reshape(A,siz), A ile aynı öğelere sahip ancak yeniden şekillendirilmiş dizinin boyutlarını temsil eden bir vektör olan boyuta yeniden şekillendirilmiş bir N-D dizisi döndürür. prod(siz) miktarı prod(size(A)) ile aynı olmalıdır.

##Question 9 What does the xlabel and ylabel functions do?

xlabel( txt ) geçerli eksenlerin veya bağımsız görselleştirmenin x eksenini etiketler. xlabel komutunun yeniden yayınlanması, eski etiketi yeni etiketle değiştirir. xlabel( target , txt ) etiketi belirtilen hedef nesneye ekler. ylabel( txt ) geçerli eksenlerin veya bağımsız görselleştirmenin y eksenini etiketler. ylabel komutunun yeniden yayınlanması, yeni etiketin eski etiketin yerini almasına neden olur. ylabel( target , txt ) etiketi belirtilen hedef nesneye ekler.

##Question 10 The transformation function plot displays a gap from 0 to 12 (on the X axis) where there are no points. Why is this so?

Görüntü daraltma işlemi uygulanmıştır.

image
