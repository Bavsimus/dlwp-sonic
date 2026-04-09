# 🎤 Derin Öğrenme Sunum Notları (Cheat Sheet)

Bu dosya, sunum esnasında gelebilecek sorulara karşı ve her slaytta ne anlatılacağını hatırlanaması için hazırlandı. Laptopundan bu dosyayı açıp çalışabilirsin.

---

## 🔡 Terminoloji Sözlüğü
*   **FashionMNIST:** (Feşın-em-nist) - Kıyafet veriseti.
*   **MLP (Multi-Layer Perceptron):** Çok katmanlı yapay sinir ağı.
*   **Epoch:** Verisetinin tamamının modelden bir kez geçmesi.
*   **Optimizer (Optimizasyoncu):** Hata payını düşürmek için ağırlıkları nasıl güncellediğimiz (Örn: Adam, SGD).

---

## 🖼️ Slayt Slayt Anlatım Tüyoları

### 1. Model Development Pipeline (Süreç)
*   **Neden NumPy?** Temel matematiksel mantığı bildiğimizi kanıtlamak için (manuel geri yayılım).
*   **Neden PyTorch?** Endüstri standardı olduğu ve karmaşık modelleri hızlı eğitebildiği için.

### 2. Training Process (Eğitim Süreci)
*   **Düşen Eğri:** Modelin hata payının azaldığını ve öğrendiğini gösterir.
*   **Başlangıç:** İlk başta çok hızlı öğrenir çünkü genel kalıpları (ayakkabı vs tişört farkı) ayırt etmek kolaydır.

### 3. Activation Functions (Sigmoid vs ReLU)
*   **KRİTİK:** ReLU kullanıyoruz çünkü "Vanishing Gradient" (Gradyan Kaybolması) sorununu çözüyor. Sigmoid, derin ağlarda öğrenmeyi "dondurur".

### 4. Overfitting & Regularization (Ezberleme Sorunu)
*   **Ezberleme:** Model eğitim verisini ezberleyip testi yapamazsa (Overfitting).
*   **Çözümler:**
    *   **L2:** Ağırlıkları küçük tutar.
    *   **Dropout:** Bazı nöronları rastgele kapatıp sistemi zorlaştırır (sağlamlaştırır).
    *   **Early Stopping:** Ezber başladığı an eğitimi durdurur.

### 5. Optimization (SGD vs Adam)
*   **Adam vs SGD:** Adam "akıllıdır", her parametre için öğrenme hızını ayarlar. SGD daha "kabadır", sabit hızla gider.

---

## 🏆 Sonuçlar ve Başarı
*   **NumPy:** %97.9 ✅
*   **PyTorch:** %97.6 ✅
*   **Mesaj:** "İki yöntemle de yüksek başarı aldık, bu da temel matematiğimizin ve model mimarimizin ne kadar tutarlı olduğunu gösteriyor."

---

## ❓ En Muhtemel 3 Soru ve Cevabı

1.  **Soru:** "Loss grafiği neden bir yerden sonra düzleşiyor?"
    *   **Cevap:** "Model artık verideki tüm ana özellikleri öğrendi (yakınsadı) ve bu kapasiteyle yapabileceği en düşük hataya ulaştı."
2.  **Soru:** "Neden Dropout oranı 0.5 seçildi?"
    *   **Cevap:** "Yarısını kapatmak, ağın her seferinde farklı bir alt grup oluşturup birbirinden farklı özellikler öğrenmeye zorlanmasını sağlar. En sağlam (robust) sonuç bu oranda alınmıştır."
3.  **Soru:** "FashionMNIST yerine neden normal MNIST (rakamlar) kullanmadınız?"
    *   **Cevap:** "MNIST artık yapay zekalar için çok kolay kaldı. FashionMNIST daha detaylı (texture) olduğu için modelimizi gerçekten zorlayıp kalitesini ölçmemize yaradı."
