---
title: Operatorrangfolge (Entity SQL)
ms.date: 03/30/2017
ms.assetid: e92e4ca5-2889-4266-9625-47f0eb01a948
ms.openlocfilehash: f8aa0f213a24d6431d8910af849571a67fbd9f57
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91175641"
---
# <a name="operator-precedence-entity-sql"></a>Operatorrangfolge (Entity SQL)

Wenn eine [!INCLUDE[esql](../../../../../../includes/esql-md.md)] Abfrage über mehrere Operatoren verfügt, bestimmt die Operator Rangfolge die Reihenfolge, in der die Vorgänge ausgeführt werden. Die Ausführungsreihenfolge kann sich entscheidend auf das Abfrageergebnis auswirken.  
  
 Operatoren besitzen die in der folgenden Tabelle dargestellte Rangfolge. Ein Operator, der höher in der Rangfolge steht, wird vor einem Operator niedrigeren Ranges ausgewertet.  
  
|Ebene|Vorgangsart|Operator|  
|-----------|--------------------|--------------|  
|1|Primär|`. , [] ()`|  
|2|Unär|`! not`|  
|3|Multiplikativ|`* / %`|  
|4|Additiv|`+ -`|  
|5|Sortieren|`< > <= >=`|  
|6|Gleichheit|`= != <>`|  
|7|Bedingtes AND|`and &&`|  
|8|Bedingtes OR|`or &#124;&#124;`|  
  
 Verfügen zwei Operatoren in einem Ausdruck über die gleiche Rangstufe, werden sie von links nach rechts, ausgehend von ihrer Position innerhalb der Abfrage, ausgewertet. `x+y-z` wird beispielsweise als `(x+y)-z` ausgewertet.  
  
 Mit Klammern kann die definierte Rangfolge von Operatoren in einer Abfrage außer Kraft gesetzt werden. Die Operatoren innerhalb der Klammern werden zuerst ausgewertet, bevor das sich ergebende einzelne Ergebnis von den Operatoren außerhalb der Klammern verwendet werden kann. Beispielsweise `x+y*z` multipliziert `y` mit `z` und fügt dann hinzu `x` , fügt jedoch `(x+y)*z` `x` zu `y` und multipliziert das Ergebnis mit `z` .  
  
## <a name="see-also"></a>Weitere Informationen

- [Übersicht über Entity SQL](entity-sql-overview.md)
