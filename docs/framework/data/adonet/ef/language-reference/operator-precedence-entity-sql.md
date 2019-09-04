---
title: Operatorrangfolge (Entity SQL)
ms.date: 03/30/2017
ms.assetid: e92e4ca5-2889-4266-9625-47f0eb01a948
ms.openlocfilehash: 2d8c78f410708fd1aa843ee8f14f7243a9f686c0
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70249785"
---
# <a name="operator-precedence-entity-sql"></a>Operatorrangfolge (Entity SQL)
Wenn eine [!INCLUDE[esql](../../../../../../includes/esql-md.md)] Abfrage über mehrere Operatoren verfügt, bestimmt die Operator Rangfolge die Reihenfolge, in der die Vorgänge ausgeführt werden. Die Ausführungsreihenfolge kann sich entscheidend auf das Abfrageergebnis auswirken.  
  
 Operatoren besitzen die in der folgenden Tabelle dargestellte Rangfolge. Ein Operator, der höher in der Rangfolge steht, wird vor einem Operator niedrigeren Ranges ausgewertet.  
  
|Ebene|Operationstyp|Operator|  
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
  
 Mit Klammern kann die definierte Rangfolge von Operatoren in einer Abfrage außer Kraft gesetzt werden. Die Operatoren innerhalb der Klammern werden zuerst ausgewertet, bevor das sich ergebende einzelne Ergebnis von den Operatoren außerhalb der Klammern verwendet werden kann. Beispiels `x+y*z` Weise `(x+y)*z` `z`multipliziert mit und`z` fügt `x`dann hinzu, fügt`x` jedoch zu`y` und multipliziert das Ergebnis mit. `y`  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über Entity SQL](entity-sql-overview.md)
