<p align="center">
  <img src="banner.svg" alt="Zendi, AI Engineer: veri etiketleme ve makine öğrenmesi" width="100%" />
</p>

<p align="center">
  <a href="https://github.com/zenndi">
    <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=20&duration=3500&pause=900&color=FFB547&center=true&vCenter=true&width=560&height=50&lines=Merhaba%2C+ben+Zendi+%F0%9F%91%8B;Veri+etiketleme+ve+veri+kalitesi;AI+pipeline%E2%80%99lar%C4%B1+kuruyorum;Makine+%C3%B6%C4%9Frenmesi+projeleri;Saf+JavaScript+ile+web+aray%C3%BCzleri" alt="Zendi" />
  </a>
</p>

<p align="center">
  <a href="https://github.com/zenndi?tab=followers"><img src="https://img.shields.io/github/followers/zenndi?style=for-the-badge&logo=github&logoColor=FFB547&labelColor=0F1B2D&color=22344F&label=Takip%C3%A7i" alt="Takipçi sayısı" /></a>
  <img src="https://hits.sh/github.com/zenndi/zenndi.svg?style=for-the-badge&label=Profil+G%C3%B6r%C3%BCnt%C3%BCleme&color=22344F&labelColor=0F1B2D&extraCount=1000000" alt="Profil görüntüleme sayısı" />
  <a href="https://discord.com/users/1235350793222361281"><img src="https://img.shields.io/badge/Discord-0F1B2D?style=for-the-badge&logo=discord&logoColor=5BA8FF" alt="Discord" /></a>
</p>

<p align="center"><img src="divider.svg" alt="" width="100%" /></p>

<h3 align="center">Hakkımda</h3>

<p align="center">
  <img src="about.svg" alt="Zendi hakkında özet" width="100%" />
</p>

Yapay zekâ ve makine öğrenmesi üzerine çalışıyorum. İyi bir modelin temeli temiz ve doğru etiketlenmiş veridir; bu yüzden veri hazırlamayı hızlandıran ve denetleyen araçlar yazmayı seviyorum. Arayüz tarafında framework kullanmadan, saf JavaScript ve Canvas ile çalışmayı tercih ediyorum.

> [!TIP]
> Bir proje fikrin ya da işbirliği teklifin varsa Discord’dan yazabilirsin.

<p align="center"><img src="divider.svg" alt="" width="100%" /></p>

<h3 align="center">Teknolojiler</h3>

<p align="center"><b>AI ve veri</b></p>
<p align="center">
  <img src="https://img.shields.io/badge/Python-0F1B2D?style=for-the-badge&logo=python&logoColor=3DDBC0" alt="Python" />
  <img src="https://img.shields.io/badge/TensorFlow-0F1B2D?style=for-the-badge&logo=tensorflow&logoColor=3DDBC0" alt="TensorFlow" />
  <img src="https://img.shields.io/badge/Redis-0F1B2D?style=for-the-badge&logo=redis&logoColor=3DDBC0" alt="Redis" />
</p>

<p align="center"><b>Web</b></p>
<p align="center">
  <img src="https://img.shields.io/badge/JavaScript-0F1B2D?style=for-the-badge&logo=javascript&logoColor=FFB547" alt="JavaScript" />
  <img src="https://img.shields.io/badge/TypeScript-0F1B2D?style=for-the-badge&logo=typescript&logoColor=FFB547" alt="TypeScript" />
  <img src="https://img.shields.io/badge/HTML5-0F1B2D?style=for-the-badge&logo=html5&logoColor=FFB547" alt="HTML5" />
  <img src="https://img.shields.io/badge/CSS3-0F1B2D?style=for-the-badge&logo=css3&logoColor=FFB547" alt="CSS3" />
</p>

<p align="center"><b>Araçlar</b></p>
<p align="center">
  <img src="https://img.shields.io/badge/Git-0F1B2D?style=for-the-badge&logo=git&logoColor=5BA8FF" alt="Git" />
  <img src="https://img.shields.io/badge/GitHub-0F1B2D?style=for-the-badge&logo=github&logoColor=5BA8FF" alt="GitHub" />
  <img src="https://img.shields.io/badge/VS%20Code-0F1B2D?style=for-the-badge&logo=visualstudiocode&logoColor=5BA8FF" alt="VS Code" />
</p>

<p align="center"><img src="divider.svg" alt="" width="100%" /></p>

<h3 align="center">Çalışma akışım</h3>

<p align="center">
  <img src="pipeline.svg" alt="Ham veriden modele çalışma akışı" width="420" />
</p>

Ham veriden modele giden yolda her adımın kalitesi bir sonrakini belirler. Bu yüzden önce veriye, sonra modele bakarım.

<p align="center"><img src="divider.svg" alt="" width="100%" /></p>

<h3 align="center">Veri kalitesine bakışım</h3>

Etiket kalitesini sezgiyle değil ölçüyle değerlendirmeyi severim. İki etiketleyici arasındaki tutarlılığı, şansla beklenen uyumu çıkararak ölçen Cohen’s kappa buna iyi bir örnek:

```python
from collections import Counter


def cohen_kappa(a: list[str], b: list[str]) -> float:
    """İki etiketleyici arasındaki tutarlılığı, şansla beklenen uyumu çıkararak ölçer."""
    n = len(a)
    gozlenen = sum(x == y for x, y in zip(a, b)) / n
    ca, cb = Counter(a), Counter(b)
    beklenen = sum(ca[k] * cb[k] for k in ca.keys() | cb.keys()) / n**2
    return 1.0 if beklenen == 1 else (gozlenen - beklenen) / (1 - beklenen)


ali  = ["kedi", "köpek", "kedi", "kedi", "köpek", "kedi", "köpek", "kedi"]
veli = ["kedi", "köpek", "köpek", "kedi", "köpek", "kedi", "köpek", "kedi"]

print(round(cohen_kappa(ali, veli), 2))  # 0.75
```

Sekiz örnekten yedisinde iki etiketleyici aynı kararı vermiş, yani ham uyum %87,5. Şans payı çıkarılınca tutarlılık 0,75’e iniyor. Etiket kılavuzunun nerede netleşmesi gerektiğini böyle farklar gösterir.

<p align="center"><img src="divider.svg" alt="" width="100%" /></p>

<h3 align="center">Prensiplerim</h3>

| Prensip | Neden |
|---|---|
| **Çok veri değil, doğru veri.** | Yanlış etiket, modele yanlış bilgi öğretir. |
| **Otomatikleştir, ama sonucu doğrula.** | Betik hızlı çalışır; hatayı yakalamak yine de göz ister. |
| **Basit tut, sonra ölçekle.** | Küçük ve çalışan bir çözüm, büyük bir plandan iyidir. |

<p align="center"><img src="divider.svg" alt="" width="100%" /></p>

<h3 align="center">Projeler</h3>

> [!NOTE]
> Etiket verisindeki tutarsızlıkları yakalayan küçük bir Python aracı üzerinde çalışıyorum. Hazır olunca burada yer alacak.

<!-- Proje eklemek için bu satırı kullan:
- [**PROJE-ADI**](https://github.com/zenndi/PROJE-ADI): kısa açıklama

etiket-kontrol repo'su açılınca yukarıdaki notu silip bunu aç:
- [**etiket-kontrol**](https://github.com/zenndi/etiket-kontrol): Etiket verisindeki tutarsızlıkları bulan küçük Python aracı
-->

<p align="center"><img src="divider.svg" alt="" width="100%" /></p>

<h3 align="center">GitHub istatistikleri</h3>

<p align="center">
  <img src="https://streak-stats.demolab.com?user=zenndi&hide_border=true&background=0F1B2D&ring=FFB547&fire=FF6B8B&currStreakNum=EAF0F7&sideNums=EAF0F7&currStreakLabel=FFB547&sideLabels=8FA3BF&dates=8FA3BF" alt="GitHub katkı serisi" />
</p>

<p align="center"><img src="divider.svg" alt="" width="100%" /></p>

<h3 align="center">Bağlantılar</h3>

<p align="center">
  <a href="https://github.com/zenndi" target="_blank"><img src="https://img.shields.io/badge/GitHub-0F1B2D?style=for-the-badge&logo=github&logoColor=FFB547" alt="GitHub" /></a>
  <a href="https://discord.com/users/1235350793222361281" target="_blank"><img src="https://img.shields.io/badge/Discord-0F1B2D?style=for-the-badge&logo=discord&logoColor=5BA8FF" alt="Discord" /></a>
</p>

<p align="center">
  <img src="footer.svg" alt="Profilime uğradığın için teşekkürler" width="100%" />
</p>
