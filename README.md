# 🥛 Süt Sihirbazı (Milk Wizard)

**Süt Sihirbazı**, süt ve süt ürünleri üretimi, yönetimi ve süreçleri hakkında kullanıcılarına yapay zeka destekli rehberlik sağlayan kapsamlı bir mobil uygulama projesidir. Bu proje, üniversite bitirme tezi kapsamında geliştirilmiştir.

## 🚀 Proje Hakkında

Bu proje, kullanıcıların süt endüstrisi ile ilgili sorularını doğal dil işleme (NLP) teknolojileri kullanarak yanıtlayan ve RAG (Retrieval-Augmented Generation) mimarisi ile güçlendirilmiş bir yapay zeka asistanı içerir. Kullanıcılar mobil uygulama üzerinden sorularını sorabilir ve anlık, doğru bilgiler alabilirler.

### Öne Çıkan Özellikler
* **Yapay Zeka Destekli Sohbet:** Kullanıcı sorularını anlayan ve bağlamsal cevaplar veren akıllı asistan.
* **RAG Mimarisi:** Doğruluk payı yüksek, özel veri setleriyle eğitilmiş bilgi geri getirme sistemi.
* **Modern Mobil Arayüz:** Kullanıcı dostu ve hızlı React Native arayüzü.
* **Hızlı Backend:** Python ve FastAPI ile geliştirilmiş yüksek performanslı sunucu yapısı.

---

## 🛠️ Kullanılan Teknolojiler

### Backend (Sunucu Tarafı)
* **Dil:** Python 3.x
* **Framework:** FastAPI
* **AI & RAG:** LangChain, OpenAI (veya kullanılan diğer LLM), Vektör Veritabanı
* **Veri İşleme:** Pandas, NumPy

### Mobile App (İstemci Tarafı)
* **Framework:** React Native (Expo)
* **Dil:** TypeScript
* **Navigasyon:** Expo Router
* **HTTP İstekleri:** Axios / Fetch API

---

## 📂 Proje Yapısı

```text
Sut_Sihirbazi/
├── Backend/                # Python & FastAPI Kodları
│   ├── api.py              # API Endpoint tanımları
│   ├── main.py             # Uygulama giriş noktası
│   ├── rag.py              # RAG (AI) mantığı ve zincir yapıları
│   ├── data.py             # Veri işleme modülleri
│   └── requirements.txt    # Python kütüphane bağımlılıkları
│
├── mobileapp/              # React Native Mobil Uygulama
│   ├── app/                # Sayfalar ve Navigasyon (Expo Router)
│   ├── components/         # Tekrar kullanılabilir bileşenler (Chat.tsx vb.)
│   ├── assets/             # Görseller ve ikonlar
│   └── package.json        # JS bağımlılıkları
│
└── README.md               # Proje dökümantasyonu
````

⚙️ Kurulum ve Çalıştırma
Projeyi yerel makinenizde ve fiziksel Android cihazınızda çalıştırmak için aşağıdaki adımları takip edin.

1. Projeyi Klonlayın
Bash

git clone [https://github.com/KaanSezen1923/Sut_Sihirbazi.git](https://github.com/KaanSezen1923/Sut_Sihirbazi.git)
cd Sut_Sihirbazi
2. Backend Kurulumu
Backend klasörüne gidin ve sanal ortam oluşturup bağımlılıkları yükleyin:

Bash

cd Backend

# Sanal ortam oluşturma (Windows)
python -m venv venv
.\venv\Scripts\activate

# Bağımlılıkları yükleme
pip install -r requirements.txt

# Sunucuyu başlatma
uvicorn main:app --reload
Backend http://127.0.0.1:8000 adresinde çalışmaya başlayacaktır.

3. Mobil Uygulama ve Cihaz Bağlantısı (USB & ADB Reverse)
Bu proje fiziksel Android cihaz üzerinde USB bağlantısı ile test edilmek üzere yapılandırılmıştır.

Geliştirici Seçeneklerini Açın: Android telefonunuzda "Geliştirici Seçenekleri"ni ve "USB Hata Ayıklama"yı (USB Debugging) aktif hale getirin.

Cihazı Bağlayın: Telefonunuzu USB kablosu ile bilgisayara bağlayın.

Port Yönlendirme (Önemli): Bilgisayarınızdaki yerel sunucuyu (localhost) telefonunuza yönlendirmek için terminalde şu komutu çalıştırın:

Bash

adb reverse tcp:8000 tcp:8000
Bu komut sayesinde, telefonunuzdaki uygulama http://localhost:8000 veya http://127.0.0.1:8000 adresine istek attığında doğrudan bilgisayarınızdaki FastAPI sunucusuna erişebilir.

Uygulamayı Başlatın: Yeni bir terminal açın ve mobileapp klasörüne gidin:

Bash

cd mobileapp

# Bağımlılıkları yükleme
npm install

# Uygulamayı başlatma
npx expo start
Terminalde çıkan seçeneklerden "a" tuşuna basarak (Run on Android) uygulamayı bağlı olan telefonunuza yükleyip başlatabilirsiniz.

📝 Notlar
API URL: adb reverse kullanıldığı için kod içerisindeki (örneğin Chat.tsx) API isteklerinde IP adresi değiştirmeye gerek yoktur; http://127.0.0.1:8000 veya http://localhost:8000 olarak kalabilir.

API anahtarları (OpenAI API Key vb.) için .env dosyası oluşturmayı unutmayın.

👤 İletişim & Geliştirici
Geliştirici: Kaan Sezen

GitHub: KaanSezen1923

Bu proje Kaan Sezen tarafından Bitirme Tezi kapsamında geliştirilmiştir.
