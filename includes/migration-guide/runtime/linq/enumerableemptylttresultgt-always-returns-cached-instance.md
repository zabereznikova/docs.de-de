---
ms.openlocfilehash: c9efbefc2bce9e21f328680795e72b62bfcd5cbd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59804081"
---
### <a name="enumerableemptytresult-always-returns-cached-instance"></a>Enumerable.Empty\<TResult> gibt immer die zwischengespeicherte Instanz zurück

|   |   |
|---|---|
|Details|Ab .NET Framework 4.5 gibt <xref:System.Linq.Enumerable.Empty%60%601> eine zwischengespeicherte interne Instanz von <xref:System.Collections.Generic.IEnumerable%601> zurück. Zuvor zwischenspeicherte <xref:System.Linq.Enumerable.Empty%60%601> beim Aufruf der API eine leere <xref:System.Collections.Generic.IEnumerable%601>-Instanz, wodurch unter bestimmten Umständen, durch die <xref:System.Linq.Enumerable.Empty%60%601> schnell und gleichzeitig aufgerufen wurde, verschiedene Instanzen des Typs für unterschiedliche Aufrufe der API zurückgegeben werden konnten.|
|Vorschlag|Da das vorherige Verhalten nicht deterministisch war, ist es unwahrscheinlich, dass der Code davon abhängig ist. Jedoch für den unwahrscheinlichen Fall, dass leere Enumerables verglichen werden und dabei erwartet wird, dass diese gelegentlich ungleich sind, sollten explizite leere Arrays erstellt werden (<code>new T[0]</code>), anstatt <xref:System.Linq.Enumerable.Empty%60%601> zu verwenden.|
|Bereich|Microsoft Edge|
|Version|4.5|
|Typ|Laufzeit|
|Betroffene APIs|<ul><li><xref:System.Linq.Enumerable.Empty%60%601?displayProperty=nameWithType></li></ul>|
