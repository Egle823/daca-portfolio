# Tooteanalüüsi projekt | Week_1

See projekt on valminud DACA andmeanalüüsi kursuse raames. Projekti eesmärk on uurida müügiandmeid, puhastada andmestikku SQL-i abil ning leida vastused äriküsimustele.

## 👤 Roll: Toomas Kask (Tooteanalüütik)
Töötan meeskonnas, mille ülesandeks on mõista poodide jõudlust ja klientide käitumist.

## 📊 Andmestik (Data Landscape)
Analüüsis kasutasin `sales` tabelit. Esialgne plaan oli kasutada `stores` tabelit, kuid kuna see andmebaasist puudus, keskendusin müügiandmete tabelis olevatele asukohaandmetele.

---

## 🛠️ Tehtud analüüsid

### 1. Kaupluste asukohad ja käibe jaotus
Uurisin, millistes linnades kauplused asuvad ning milline on nende tehingute arv ja kogukäive.

**SQL Päring:**
```sql
SELECT 
    store_location, 
    COUNT(*) AS tehingute_arv,
    SUM(total_price) AS kogukäive
FROM sales
WHERE store_location IS NOT NULL
GROUP BY store_location;
