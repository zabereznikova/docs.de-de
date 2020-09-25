---
title: Vergleichssemantik (Entity SQL)
ms.date: 03/30/2017
ms.assetid: b36ce28a-2fe4-4236-b782-e5f7c054deae
ms.openlocfilehash: 9a36fcc4476c25d64fed670e857f339fb20043d8
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91197832"
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
  
|**Typ**|**=**<br /><br /> **!=**|**GROUP BY**<br /><br /> **DISTINCT**|**UNION**<br /><br /> **INTERSECT**<br /><br /> **EXCEPT**<br /><br /> **SET**<br /><br /> **OVERLAPS**|**IN**|**<   <=**<br /><br /> **>   >=**|**ORDER BY**|**IS NULL**<br /><br /> **ist nicht NULL**|  
|-|-|-|-|-|-|-|-|  
|Entitätstyp|Ref<sup>1</sup>|Alle Eigenschaften<sup>2</sup>|Alle Eigenschaften<sup>2</sup>|Alle Eigenschaften<sup>2</sup>|Throw<sup>3</sup>|Throw<sup>3</sup>|Ref<sup>1</sup>|  
|Komplexer Typ|Throw<sup>3</sup>|Throw<sup>3</sup>|Throw<sup>3</sup>|Throw<sup>3</sup>|Throw<sup>3</sup>|Throw<sup>3</sup>|Throw<sup>3</sup>|  
|Zeile|Alle Eigenschaften<sup>4</sup>|Alle Eigenschaften<sup>4</sup>|Alle Eigenschaften<sup>4</sup>|Throw<sup>3</sup>|Throw<sup>3</sup>|Alle Eigenschaften<sup>4</sup>|Throw<sup>3</sup>|  
|Primitiver Typ|Anbieterspezifisch|Anbieterspezifisch|Anbieterspezifisch|Anbieterspezifisch|Anbieterspezifisch|Anbieterspezifisch|Anbieterspezifisch|  
|Multiset|Throw<sup>3</sup>|Throw<sup>3</sup>|Throw<sup>3</sup>|Throw<sup>3</sup>|Throw<sup>3</sup>|Throw<sup>3</sup>|Throw<sup>3</sup>|  
|Ref|Ja<sup>5</sup>|Ja<sup>5</sup>|Ja<sup>5</sup>|Ja<sup>5</sup>|Throw|Throw|Ja<sup>5</sup>|  
|Zuordnung<br /><br /> Typ|Throw<sup>3</sup>|Throw|Throw|Throw|Throw<sup>3</sup>|Throw<sup>3</sup>|Throw<sup>3</sup>|  
  
 <sup>1</sup> Die Verweise der angegebenen Entitätstyp Instanzen werden implizit verglichen, wie im folgenden Beispiel gezeigt:  
  
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
  
 <sup>2</sup> Eigenschaften komplexer Typen werden vereinfacht, bevor Sie an den Speicher gesendet werden, sodass Sie vergleichbar sind (solange alle Eigenschaften vergleichbar sind). Siehe auch <sup>4.</sup>  
  
 <sup>3</sup> Die Entity Framework-Laufzeit erkennt den nicht unterstützten Fall und löst eine sinnvolle Ausnahme aus, ohne den Anbieter bzw. den Speicher einzubinden.  
  
 <sup>4</sup> Es wurde versucht, alle Eigenschaften zu vergleichen. Wenn eine Eigenschaft einen nicht vergleichbaren Typ hat, wie beispielsweise text, ntext oder image, kann eine Serverausnahme ausgelöst werden.  
  
 <sup>5</sup> Alle einzelnen Elemente der Verweise werden verglichen (Dies schließt den Namen der Entitätenmenge und alle Schlüsseleigenschaften des Entitäts Typs ein).  
  
## <a name="see-also"></a>Weitere Informationen

- [Übersicht über Entity SQL](entity-sql-overview.md)
