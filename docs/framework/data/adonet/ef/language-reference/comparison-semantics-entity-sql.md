---
title: "Vergleichssemantik (Entity SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
ms.assetid: b36ce28a-2fe4-4236-b782-e5f7c054deae
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Vergleichssemantik (Entity SQL)
Beim Ausführen aller folgenden [!INCLUDE[esql](../../../../../../includes/esql-md.md)]\-Operationen werden Typinstanzen verglichen:  
  
## Expliziter Vergleich  
 Gleichheitsoperationen:  
  
-   \=  
  
-   \!\=  
  
 Sortieroperationen:  
  
-   \<  
  
-   \<\=  
  
-   \>  
  
-   \>\=  
  
 NULL\-Zulässigkeitsoperationen:  
  
-   IS NULL  
  
-   IS NOT NULL  
  
## Explizite Unterscheidung  
 Gleichheitsunterscheidung:  
  
-   DISTINCT  
  
-   GROUP BY  
  
 Sortierunterscheidung:  
  
-   ORDER BY  
  
## Implizite Unterscheidung  
 Mengenoperationen und Prädikate \(Gleichheit\):  
  
-   UNION  
  
-   INTERSECT  
  
-   EXCEPT  
  
-   SET  
  
-   OVERLAPS  
  
 Elementprädikate \(Gleichheit\):  
  
-   IN  
  
## Unterstützte Kombinationen  
 In der folgenden Tabelle werden alle unterstützten Kombinationen von Vergleichsoperatoren für jede Art von Typ angezeigt:  
  
|||||||||  
|-|-|-|-|-|-|-|-|  
|**Typ**|**\=**<br /><br /> **\!\=**|**GROUP BY**<br /><br /> **DISTINCT**|**UNION**<br /><br /> **INTERSECT**<br /><br /> **EXCEPT**<br /><br /> **SET**<br /><br /> **OVERLAPS**|**IN**|**\<   \<\=**<br /><br /> **\>   \>\=**|**ORDER BY**|**IS NULL**<br /><br /> **IS NOT NULL**|  
|Entitätstyp|Ref<sup>1</sup>|Alle Eigenschaften<sup>2</sup>|Alle Eigenschaften<sup>2</sup>|Alle Eigenschaften<sup>2</sup>|Auslösen<sup>3</sup>|Auslösen<sup>3</sup>|Ref<sup>1</sup>|  
|Komplexer Typ|Auslösen<sup>3</sup>|Auslösen<sup>3</sup>|Auslösen<sup>3</sup>|Auslösen<sup>3</sup>|Auslösen<sup>3</sup>|Auslösen<sup>3</sup>|Auslösen<sup>3</sup>|  
|Zeile|Alle Eigenschaften<sup>4</sup>|Alle Eigenschaften<sup>4</sup>|Alle Eigenschaften<sup>4</sup>|Auslösen<sup>3</sup>|Auslösen<sup>3</sup>|Alle Eigenschaften<sup>4</sup>|Auslösen<sup>3</sup>|  
|Primitiver Typ|Anbieterspezifisch|Anbieterspezifisch|Anbieterspezifisch|Anbieterspezifisch|Anbieterspezifisch|Anbieterspezifisch|Anbieterspezifisch|  
|Multiset|Auslösen<sup>3</sup>|Auslösen<sup>3</sup>|Auslösen<sup>3</sup>|Auslösen<sup>3</sup>|Auslösen<sup>3</sup>|Auslösen<sup>3</sup>|Auslösen<sup>3</sup>|  
|Ref|ja <sup>5</sup>|ja <sup>5</sup>|ja <sup>5</sup>|ja <sup>5</sup>|Throw|Throw|ja <sup>5</sup>|  
|Zuordnung<br /><br /> Typ|Auslösen<sup>3</sup>|Throw|Throw|Throw|Auslösen<sup>3</sup>|Auslösen<sup>3</sup>|Auslösen<sup>3</sup>|  
  
 <sup>1</sup>Die Verweise der angegebenen Entitätstypinstanzen werden implizit verglichen, wie im folgenden Beispiel gezeigt:  
  
```  
SELECT p1, p2   
FROM AdventureWorksEntities.Product AS p1   
     JOIN AdventureWorksEntities.Product AS p2   
WHERE p1 != p2 OR p1 IS NULL  
```  
  
 Eine Entitätsinstanz kann nicht mit einem expliziten Verweis verglichen werden.  Eine Ausnahme wird ausgelöst, wenn dies versucht wird.  Folgende Abfrage löst beispielsweise eine Ausnahme aus:  
  
```  
SELECT p1, p2   
FROM AdventureWorksEntities.Product AS p1   
     JOIN AdventureWorksEntities.Product AS p2   
WHERE p1 != REF(p2)  
```  
  
 <sup>2</sup>Eigenschaften komplexer Typen werden vor dem Speichern vereinfacht, sodass sie vergleichbar werden \(sofern alle ihre Eigenschaften vergleichbar sind\).  Siehe auch <sup>4</sup>.  
  
 <sup>3</sup>Die Entity Framework\-Laufzeit erkennt den nicht unterstützten Fall und löst eine angemessene Ausnahme aus, ohne den Anbieter\/Speicher in Anspruch zu nehmen.  
  
 <sup>4</sup>Es wird versucht, alle Eigenschaften zu vergleichen.  Wenn eine Eigenschaft einen nicht vergleichbaren Typ hat, wie beispielsweise **text**, **ntext** oder **image**, kann eine Serverausnahme ausgelöst werden.  
  
 <sup>5</sup>Alle Einzelelemente der Verweise werden verglichen \(einschließlich des Namens der Entitätenmenge und aller Schlüsseleigenschaften des Entitätstyps\).  
  
## Siehe auch  
 [Übersicht über Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)