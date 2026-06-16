### Veri Tabanı Normalizasyonu 

Normalizasyon, veri tabanı tablolarını belirli kurallara (normal formlar) göre düzenleyerek veri tekrarını azaltmayı ve veri tutarlılığını sağlamayı amaçlar.
Başlıca normal formlar: 1NF, 2NF, 3NF (ve BCNF), 4NF, 5NF.

---

#### 1. Normal Form (First Normal Form - 1NF)

1NF, bir tabloda:

Primary key (birincil anahtar) bulunmasını
Aynı tür verilerin tekrar eden sütunlar halinde olmamasını
Hücrelerde birden fazla değer bulunmamasını gerektirir

**Örnek:**
Bir tabloda child1, child2, child3 gibi sütunların olması tekrar eden grup oluşturur.

**Çözüm:**
Veri iki tabloya ayrılır:

Birinci tablo ebeveyn bilgilerini içerir
İkinci tablo çocuk bilgilerini içerir

Bu tablolar primary key ve foreign key ile ilişkilendirilir.
**Sonuç:**
Veri tekrarları tamamen ortadan kalkmasa da sorgular daha sade ve anlaşılır hale gelir.

---

#### 2. Normal Form (Second Normal Form - 2NF)

2NF, 1NF’i sağladıktan sonra şu kuralı ekler:

Non-key alanlar, primary key’in tamamına bağlı olmalıdır
Özellikle birleşik anahtar varsa kısmi bağımlılıklar olmamalıdır

**Örnek :**
Bir tabloda primary key (part, warehouse) iken
warehouse_address sadece warehouse kolonuna bağlıysa bu 2NF ihlalidir.
**Sorun:**

Veri tekrarı oluşur
Güncelleme ve silme hataları meydana gelebilir

**Çözüm:**
Tablo ikiye bölünür:

Parça, depo ve miktar bilgisi
Depo ve adres bilgisi

**Sonuç:**
Veri tekrarları azalır ve veri tutarlılığı artar.

---

#### 3. Normal Form (Third Normal Form - 3NF) ve BCNF

3NF, 2NF’i sağladıktan sonra ek olarak:

Non-key alanların başka non-key alanlara bağlı olmamasını ister
Bu tür bağımlılıklar transitive dependency olarak adlandırılır

**Örnek:**
dept_name, dept_num’a bağlıdır ama primary key emp_numdur.
Bu durumda dolaylı bağımlılık oluşur.

**Sorun:**
Aynı veri birden fazla satırda tekrarlanır
Güncelleme hataları ortaya çıkar

**Çözüm:**
Veri üç tabloya ayrılır:

EMPLOYEE
DEPARTMENT
EMPLOYEE_DEPARTMENT (ilişki tablosu)

BCNF (Boyce-Codd Normal Form):
3NF’in daha katı halidir. Her belirleyici alanın (determinant) bir super key olması gerekir.

---

#### 4. Normal Form (Fourth Normal Form - 4NF)
4NF, çok değerli bağımlılıkları (multi-valued dependency) ortadan kaldırır.

**Örnek:**
Bir çalışan birden fazla beceriye ve birden fazla dile sahip olabilir.
Bu iki ilişki birbirinden bağımsızdır ancak aynı tabloda tutuluyorsa sorun oluşur.
**Çözüm:**
İki ayrı tablo oluşturulur:

Employee-Skills
Employee-Languages

**Sonuç:**
Bağımsız veri kümeleri ayrılarak gereksiz veri kombinasyonları önlenir.

---

#### 5. Normal Form (Fifth Normal Form - 5NF)

5NF, join dependency kavramına dayanır.
Temel kural:
Bir tablo parçalara ayrıldıktan sonra bu parçalar tekrar birleştirildiğinde,
orijinal tablo eksiksiz ve hatasız şekilde elde edilmelidir.
Mantık:

Veri kaybı olmamalı
Fazladan (yanlış) veri oluşmamalı

Eğer parçalama sonrası birleştirme sırasında farklı veya hatalı sonuç oluşuyorsa,
o parçalama işlemi uygun değildir.

Normalizasyonun temel amaçları:

Veri tekrarını azaltmak
Veri tutarlılığını artırmak
Güncelleme, silme ve ekleme hatalarını önlemek

Her normal form veri yapısını daha düzenli hale getirir.
Ancak pratikte çoğu sistem genellikle 3NF veya BCNF seviyesine kadar normalize edilir.

---
