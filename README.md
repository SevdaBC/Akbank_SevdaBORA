# Akbank_SevdaBORAÇINAR
SevdaBoraÇınar_metro_simulate
# 🚇 Sürücüsüz Metro Simülasyonu (Rota Optimizasyonu)

Bu proje, bir metro ağı üzerinde **en hızlı** ve **en az aktarmalı** rotayı hesaplayan bir simülasyon oluşturur.  
Python’un **BFS (Breadth-First Search)** ve **A* (A-Star)** algoritmalarını kullanarak en uygun rotayı bulur.

## 📌 Proje Amacı
Bu projede aşağıdaki hedeflere ulaşmak amaçlanmıştır:
1. **Metro ağını bir grafik veri yapısıyla modelleme**
2. **BFS algoritmasıyla en az aktarmalı rotayı bulma**
3. **A* algoritmasıyla en hızlı rotayı hesaplama**
4. **Algoritmik düşünme yetisini geliştirme**

---

## 📂 Kullanılan Teknolojiler ve Kütüphaneler
| Kütüphane | Kullanım Amacı |
|-----------|---------------|
| `collections.deque` | BFS algoritması için kuyruk oluşturma |
| `heapq` | A* algoritması için öncelik kuyruğu yönetme |
| `typing` | Kodun daha anlaşılır olması için tip belirleme |

---

## 🛠️ Algoritmaların Çalışma Mantığı

### **🔍 BFS Algoritması (en_az_aktarma_bul)**
**Breadth-First Search (Genişlik Öncelikli Arama)** algoritması kullanılarak **en az aktarma gerektiren** rotayı bulur.  
**Çalışma mantığı:**
1. **Kuyruk (queue) oluşturulur:** İlk istasyon eklenir.
2. **Ziyaret edilen istasyonlar takip edilir.**
3. **Her adımda en yakın komşular keşfedilir.**
4. **İlk hedefe ulaşan rota en az aktarmalıdır.**

📌 **Zaman karmaşıklığı:**  
**O(N + E)** → N: Düğümler (istasyonlar), E: Kenarlar (bağlantılar)  

---

### **🚀 A* Algoritması (en_hizli_rota_bul)**
A* algoritması, **en hızlı rota** bulmak için kullanılır.  
Dijkstra’nın bir optimizasyonu olup, **tahmini kalan mesafeyi** de hesaba katar.

**Çalışma mantığı:**
1. **Öncelik kuyruğu (`heapq`) oluşturulur:** `(toplam_süre, istasyon, rota)` şeklinde tutulur.
2. **Her adımda en düşük süreye sahip istasyon seçilir.**
3. **Komşular eklenerek toplam süre hesaplanır.**
4. **En hızlı rota, toplam süre en az olan yoldur.**

📌 **Zaman karmaşıklığı:**  
**O((N + E) log N)** → N: Düğümler (istasyonlar), E: Kenarlar (bağlantılar)  

---

## 📊 Örnek Kullanım ve Test Sonuçları

### 📍 **Örnek Metro Ağı**
lua
Kopyala
Düzenle
(M1) AŞTİ --5dk-- Kızılay (M2)
              |  
 (K1) Kızılay --4dk-- Ulus (K2)
              |
 (M3) Sıhhiye --3dk-- Gar (M4)
markdown
Kopyala
Düzenle

### ✅ **Test Senaryoları**
Örnek testler çalıştırıldığında aşağıdaki sonuçlar alınmaktadır:

| Başlangıç | Hedef | En Az Aktarmalı Rota | En Hızlı Rota | Süre (dakika) |
|-----------|--------|---------------------|--------------|--------------|
| **AŞTİ (M1)** | **OSB (K4)** | AŞTİ → Kızılay → Ulus → Demetevler → OSB | AŞTİ → Kızılay → Ulus → Demetevler → OSB | **25** |
| **Batıkent (T1)** | **Keçiören (T4)** | Batıkent → Demetevler → Gar → Keçiören | Batıkent → Demetevler → Gar → Keçiören | **21** |
| **Keçiören (T4)** | **AŞTİ (M1)** | Keçiören → Gar → Sıhhiye → Kızılay → AŞTİ | Keçiören → Gar → Sıhhiye → Kızılay → AŞTİ | **19** |

✅ **Kod başarılı şekilde çalışıyor!**

---

## 💡 Projeyi Geliştirme Fikirleri
- **İstasyonlar için gerçek harita verileri kullanılarak mesafeleri dinamik hesaplama**
- **Görselleştirme ekleyerek metro hattını grafik üzerinde gösterme**
- **Farklı hat yoğunluklarını hesaba katan bir sistem geliştirme**
- **Hızlı tren hatlarını entegre etme**

---
