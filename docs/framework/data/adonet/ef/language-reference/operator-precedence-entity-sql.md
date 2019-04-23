---
title: Operatorrangfolge (Entity SQL)
ms.date: 03/30/2017
ms.assetid: e92e4ca5-2889-4266-9625-47f0eb01a948
ms.openlocfilehash: 722ebe5f0ec530f8c7f86e9f9901451b060903f0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59159132"
---
# <a name="operator-precedence-entity-sql"></a>Operatorrangfolge (Entity SQL)
Wenn ein [!INCLUDE[esql](../../../../../../includes/esql-md.md)] Abfrage verfügt über mehrere Operatoren, bestimmt die Operatorrangfolge die Reihenfolge, in dem die Vorgänge ausgeführt werden. Die Ausführungsreihenfolge kann sich entscheidend auf das Abfrageergebnis auswirken.  
  
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
  
 Mit Klammern kann die definierte Rangfolge von Operatoren in einer Abfrage außer Kraft gesetzt werden. Die Operatoren innerhalb der Klammern werden zuerst ausgewertet, bevor das sich ergebende einzelne Ergebnis von den Operatoren außerhalb der Klammern verwendet werden kann. Z. B. `x+y*z` multipliziert `y` von `z` und fügt dann `x`, aber `(x+y)*z` fügt `x` zu `y` und multipliziert dann das Ergebnis durch `z`.  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
