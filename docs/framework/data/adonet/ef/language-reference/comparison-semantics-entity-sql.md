---
title: Vergleichssemantik (Entity SQL)
ms.date: 03/30/2017
ms.assetid: b36ce28a-2fe4-4236-b782-e5f7c054deae
ms.openlocfilehash: 57d81d4b581df76a4382ad5e1d72fe8250b10d43
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150453"
---
# <a name="comparison-semantics-entity-sql"></a>Vergleichssemantik (Entity SQL)
Beim Ausführen aller folgenden [!INCLUDE[esql](../../../../../../includes/esql-md.md)]-Operationen werden Typinstanzen verglichen:  
  
## <a name="explicit-comparison"></a>Expliziter Vergleich  
 Gleichheitsoperationen:  
  
- =  
  
- !=  
  
 Sortieroperationen:  
  
- <  
  
- \<=  
  
- \>  
  
- \>=  
  
 NULL-Zulässigkeitsoperationen:  
  
- IS NULL  
  
- IS NOT NULL  
  
## <a name="explicit-distinction"></a>Explizite Unterscheidung  
 Gleichheitsunterscheidung:  
  
- DISTINCT  
  
- GROUP BY  
  
 Sortierunterscheidung:  
  
- ORDER BY  
  
## <a name="implicit-distinction"></a>Implizite Unterscheidung  
 Mengenoperationen und Prädikate (Gleichheit):  
  
- UNION  
  
- INTERSECT  
  
- EXCEPT  
  
- SET  
  
- OVERLAPS  
  
 Elementprädikate (Gleichheit):  
  
- IN  
  
## <a name="supported-combinations"></a>Unterstützte Kombinationen  
 In der folgenden Tabelle werden alle unterstützten Kombinationen von Vergleichsoperatoren für jede Art von Typ angezeigt:  
  
|**Typ**|**=**<br /><br /> **!=**|**GROUP BY**<br /><br /> **Unterschiedliche**|**Union**<br /><br /> **Schneiden**<br /><br /> **Außer**<br /><br /> **Festgelegt**<br /><br /> **Überschneidungen**|**In**|**< <=**<br /><br /> **> >=**|**ORDER BY**|**IST NULL**<br /><br /> **IST NICHT NULL**|  
|-|-|-|-|-|-|-|-|  
|Entitätstyp|Ref<sup>1</sup>|Alle Eigenschaften<sup>2</sup>|Alle Eigenschaften<sup>2</sup>|Alle Eigenschaften<sup>2</sup>|Wurf<sup>3</sup>|Wurf<sup>3</sup>|Ref<sup>1</sup>|  
|Komplexer Typ|Wurf<sup>3</sup>|Wurf<sup>3</sup>|Wurf<sup>3</sup>|Wurf<sup>3</sup>|Wurf<sup>3</sup>|Wurf<sup>3</sup>|Wurf<sup>3</sup>|  
|Zeile|Alle Eigenschaften<sup>4</sup>|Alle Eigenschaften<sup>4</sup>|Alle Eigenschaften<sup>4</sup>|Wurf<sup>3</sup>|Wurf<sup>3</sup>|Alle Eigenschaften<sup>4</sup>|Wurf<sup>3</sup>|  
|Primitiver Typ|Anbieterspezifisch|Anbieterspezifisch|Anbieterspezifisch|Anbieterspezifisch|Anbieterspezifisch|Anbieterspezifisch|Anbieterspezifisch|  
|Multiset|Wurf<sup>3</sup>|Wurf<sup>3</sup>|Wurf<sup>3</sup>|Wurf<sup>3</sup>|Wurf<sup>3</sup>|Wurf<sup>3</sup>|Wurf<sup>3</sup>|  
|Ref|Ja<sup>5</sup>|Ja<sup>5</sup>|Ja<sup>5</sup>|Ja<sup>5</sup>|Throw|Throw|Ja<sup>5</sup>|  
|Zuordnung<br /><br /> type|Wurf<sup>3</sup>|Throw|Throw|Throw|Wurf<sup>3</sup>|Wurf<sup>3</sup>|Wurf<sup>3</sup>|  
  
 <sup>1</sup> Die Verweise der angegebenen Entitätstypinstanzen werden implizit verglichen, wie im folgenden Beispiel gezeigt:  
  
```sql  
SELECT p1, p2
FROM AdventureWorksEntities.Product AS p1
     JOIN AdventureWorksEntities.Product AS p2
WHERE p1 != p2 OR p1 IS NULL  
```  
  
 Eine Entitätsinstanz kann nicht mit einem expliziten Verweis verglichen werden. Eine Ausnahme wird ausgelöst, wenn dies versucht wird. Folgende Abfrage löst beispielsweise eine Ausnahme aus:  
  
```sql  
SELECT p1, p2
FROM AdventureWorksEntities.Product AS p1
     JOIN AdventureWorksEntities.Product AS p2
WHERE p1 != REF(p2)  
```  
  
 <sup>2</sup> Eigenschaften komplexer Typen werden abgeflacht, bevor sie an den Speicher gesendet werden, so dass sie vergleichbar werden (solange alle ihre Eigenschaften vergleichbar sind). Siehe auch <sup>4.</sup>  
  
 <sup>3</sup> Die Entity Framework-Laufzeit erkennt den nicht unterstützten Fall und löst eine sinnvolle Ausnahme aus, ohne den Anbieter/Speicher einzubinden.  
  
 <sup>4</sup> Es wird versucht, alle Eigenschaften zu vergleichen. Wenn eine Eigenschaft einen nicht vergleichbaren Typ hat, wie beispielsweise text, ntext oder image, kann eine Serverausnahme ausgelöst werden.  
  
 <sup>5</sup> Alle einzelnen Elemente der Referenzen werden verglichen (dies schließt den Entitätssatznamen und alle Schlüsseleigenschaften des Entitätstyps ein).  
  
## <a name="see-also"></a>Weitere Informationen

- [Übersicht über Entity SQL](entity-sql-overview.md)
