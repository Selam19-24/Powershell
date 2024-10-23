PowerShell için GitHub'da paylaşabileceğiniz kapsamlı ve akademik bir hızlı referans rehberi aşağıdaki gibidir. Bu rehber, Markdown formatında yazılmıştır ve `readme.md` dosyasına uygun bir tasarımda düzenlenmiştir.

```markdown
# PowerShell Hızlı Referans Rehberi

Bu rehber, PowerShell kullanımı için temel ve ileri düzey komutları kapsayan hızlı bir referans sunmaktadır. PowerShell, komut satırı arayüzü ve betik dili olarak Windows, macOS ve Linux sistemlerinde kullanılabilir. Rehberde temel kullanım örneklerinden, değişken yönetimine, komut dizilerine ve daha birçok konuya değinilecektir.

## İçindekiler
1. [PowerShell'e Giriş](#powershelle-giriş)
2. [Temel Komutlar](#temel-komutlar)
3. [Değişkenler](#değişkenler)
4. [Nesne Tabanlı Yapı](#nesne-tabanlı-yapı)
5. [Koşullu İfadeler](#koşullu-ifadeler)
6. [Döngüler](#döngüler)
7. [Fonksiyonlar](#fonksiyonlar)
8. [Modüller ve Cmdlet'ler](#modüller-ve-cmdletler)
9. [Hata Yönetimi](#hata-yonetimi)
10. [Gelişmiş Konular](#gelişmiş-konular)
11. [Kaynaklar](#kaynaklar)

---

## PowerShell'e Giriş

PowerShell, .NET framework üzerine inşa edilmiş nesne tabanlı bir komut satırı aracıdır. Hem sistem yöneticilerine hem de geliştiricilere esneklik sağlayarak, otomasyon işlemlerinde sıklıkla kullanılır.

PowerShell'i başlatmak için:
```bash
# Windows
powershell

# macOS / Linux
pwsh
```

## Temel Komutlar

PowerShell'de sık kullanılan temel komutlar:

```powershell
# Dosya Listesi
Get-ChildItem

# İçerik Okuma
Get-Content

# Yardım Almak
Get-Help <komut>

# Servisleri Görüntüleme
Get-Service

# Prosesleri Listeleme
Get-Process
```

Cmdlet'ler, PowerShell'in temel yapı taşlarıdır ve her cmdlet genellikle bir **fiil** ve bir **isim** formatında adlandırılır (`Verb-Noun`).

## Değişkenler

PowerShell'de değişkenler `$` işaretiyle tanımlanır. Bir değişkeni tanımlamak ve kullanmak oldukça basittir:

```powershell
# Değişken Tanımlama
$isim = "PowerShell"
$sayi = 10

# Değişkeni Kullanma
Write-Output $isim
Write-Output $sayi
```

## Nesne Tabanlı Yapı

PowerShell'de tüm veriler nesne tabanlıdır. Bu, çıktılarla daha fazla işlem yapılmasını sağlar. Bir komut çıktısını boru hattı (`|`) ile başka bir komuta yönlendirebilirsiniz.

```powershell
# Servislerin adlarını filtreleme
Get-Service | Select-Object -Property Name

# İşlem bilgilerini filtreleme
Get-Process | Where-Object {$_.CPU -gt 100}
```

## Koşullu İfadeler

Koşullu ifadeler, işlemleri belirli koşullara göre yürütmeye olanak tanır. PowerShell'de `if`, `else` ve `elseif` kullanılır.

```powershell
# If-Else Yapısı
$deger = 10
if ($deger -eq 10) {
    Write-Output "Değer 10'a eşit"
} elseif ($deger -gt 10) {
    Write-Output "Değer 10'dan büyük"
} else {
    Write-Output "Değer 10'dan küçük"
}
```

## Döngüler

Döngüler tekrarlı işlemler için kullanılır. PowerShell'de `for`, `foreach`, ve `while` döngüleri kullanılabilir.

```powershell
# For Döngüsü
for ($i = 0; $i -lt 5; $i++) {
    Write-Output "Sayı: $i"
}

# Foreach Döngüsü
$liste = 1..5
foreach ($sayi in $liste) {
    Write-Output "Sayı: $sayi"
}
```

## Fonksiyonlar

PowerShell'de kendi fonksiyonlarınızı tanımlayabilirsiniz. Fonksiyonlar, belirli görevleri yerine getiren kod bloklarıdır.

```powershell
# Fonksiyon Tanımlama
function Topla {
    param ($sayi1, $sayi2)
    return $sayi1 + $sayi2
}

# Fonksiyon Çağırma
Topla -sayi1 5 -sayi2 10
```

## Modüller ve Cmdlet'ler

Modüller, PowerShell'de bir grup komutu bir araya getiren bileşenlerdir. Mevcut modülleri görmek için:

```powershell
# Yüklü modülleri listele
Get-Module -ListAvailable

# Modül yükleme
Import-Module <modül_adı>
```

Örnek olarak, `Az` modülü ile Azure hizmetlerine erişebilirsiniz:

```powershell
# Azure modülünü yükleme
Install-Module -Name Az
```

## Hata Yönetimi

PowerShell'de hataları yakalamak ve yönetmek için `Try-Catch-Finally` yapısı kullanılır.

```powershell
# Hata Yönetimi
try {
    # Hata oluşabilecek işlem
    Get-Content "olmayan_dosya.txt"
}
catch {
    Write-Output "Hata: $_"
}
finally {
    Write-Output "İşlem tamamlandı"
}
```

## Gelişmiş Konular

### Pipeline (Boru Hattı)

PowerShell'de komutlar arasında veri aktarımı yapmak için boru hattı (`|`) kullanılır.

```powershell
# Bir işlemdeki sonuçları diğerine aktarma
Get-Process | Where-Object {$_.CPU -gt 100}
```

### Splatting

Birden çok parametreyi bir cmdlet'e aktarmak için splatting kullanılabilir.

```powershell
# Splatting kullanımı
$params = @{
    Path = "C:\Temp"
    Filter = "*.txt"
    Recurse = $true
}
Get-ChildItem @params
```

---

## Kaynaklar

- [Resmi PowerShell Belgeleri](https://docs.microsoft.com/powershell/)
- [PowerShell Gallery](https://www.powershellgallery.com/)
- [GitHub PowerShell Reposu](https://github.com/powershell/powershell)

---

Bu rehber, PowerShell kullanırken size yol gösterecek temel ve gelişmiş bilgileri sunar. Daha fazla bilgi ve derinlemesine eğitimler için yukarıdaki kaynakları inceleyebilirsiniz.
```

Bu rehberi Markdown formatında `readme.md` dosyasına ekleyerek GitHub projenizde kullanabilirsiniz.
