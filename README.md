# Sadede

> **Az söyle, öz söyle.**

AI asistanların cevaplarını dolgusuz, kısa ve öz hâle getiren Türkçe skill. Teknik içerik, kod ve hata mesajları aynen kalır; sadece laf kalabalığı gider.

## Önce / sonra

**Normal:**

> Tabii ki yardımcı olabilirim! Container'ınızın başlar başlamaz kapanmasının sebebi büyük ihtimalle, Docker'ın container içindeki ana process sona erdiğinde container'ı da durdurmasından kaynaklanıyor olabilir. Bu nedenle `CMD` satırınızda ön planda çalışmaya devam eden bir komut bulunması gerekmektedir. Sorunu daha detaylı incelemek için `docker logs` komutunu kullanmanızı öneririm. Umarım yardımcı olur!

**`/sadede`:**

> Ana process bitiyor -> container kapanıyor. `CMD` ön planda çalışan komut olmalı. Log: `docker logs <id>`.

## Neden Türkçe?

Türkçenin kendine has dolguları var: "gerçekleştirmek / sağlamak" fiil zincirleri, "-mektedir" ekleri, gereksiz "-dır/-dir", artikel gibi kullanılan "bir". Sadede bunları hedefler. Türkçe, ekli yapısı yüzünden İngilizceden daha çok token harcadığı için kısaltmanın getirisi de daha yüksek.

## Kurulum

### Tek komutla (Claude Code, Cursor, Codex ve diğerleri)

```bash
npx skills add tlh-k/sadede
```

### Claude Code (manuel)

```bash
git clone https://github.com/tlh-k/sadede.git
mkdir -p ~/.claude/skills
cp -r sadede/skills/sadede ~/.claude/skills/
```

Sadece bir projede kullanmak için `~/.claude/skills/` yerine projenin `.claude/skills/` klasörüne kopyala.

### Diğer asistanlar (ChatGPT, Gemini vb.)

`skills/sadede/SKILL.md` dosyasının içeriğini (en üstteki `---` arasındaki kısım hariç) asistanın özel talimat / sistem prompt alanına yapıştır.

## Kullanım

| | |
|---|---|
| Aç | `/sadede`, "sadede gel", "kısa kes" |
| Kapat | "normal mod", "sadede kapat" |

Güvenlik uyarıları, geri alınamaz işlemler ve sırası önemli talimatlarda geçici olarak açık Türkçeye döner, sonra kısa üsluba devam eder.

## Ne atar, ne korur

| Atar | Korur |
|---|---|
| "Tabii!", "Harika soru", "Umarım yardımcı olur" | Teknik terimler |
| aslında, yani, temelde, açıkçası | Kod blokları |
| "gerçekleştirmek", "-mektedir", gereksiz "-dır" | Birebir hata mesajları |
| Süs çekinceler, soruyu tekrar etme, kapanış özeti | Türkçe karakterler ve doğru yazım |

## Lisans

[MIT](LICENSE)
