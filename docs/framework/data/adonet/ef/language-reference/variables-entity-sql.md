---
title: Variablen (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 3eed222a-f8f6-46b6-9cd5-220cc0e4e5d8
ms.openlocfilehash: bf6fa95e38d1eb5817fd67165b6993cbb0755fd1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59153581"
---
# <a name="variables-entity-sql"></a>Variablen (Entity SQL)
## <a name="variable"></a>Variable  
 Ein Variablenausdruck ist ein Verweis auf einen im aktuellen Bereich definierten benannten Ausdruck. Ein Variablenverweis muss ein gültiger [!INCLUDE[esql](../../../../../../includes/esql-md.md)] Bezeichner, die gemäß [Bezeichner](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md).  
  
 Im folgenden Beispiel wird die Verwendung einer Variablen im Ausdruck dargestellt. Der Buchstabe `c` in der FROM-Klausel ist die Definition der Variablen. Die Verwendung von `c` in der SELECT-Klausel stellt den Variablenverweis dar.  
  
```  
select c   
from LOB.customers as c  
```  
  
## <a name="see-also"></a>Siehe auch

- [Identifiers (Bezeichner)](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md)
- [Parameter](../../../../../../docs/framework/data/adonet/ef/language-reference/parameters-entity-sql.md)
- [Übersicht über Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
