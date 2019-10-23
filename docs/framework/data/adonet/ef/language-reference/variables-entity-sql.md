---
title: Variablen (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 3eed222a-f8f6-46b6-9cd5-220cc0e4e5d8
ms.openlocfilehash: bb8e6ebe81dacc7ec0f45fdde65b9c18cfd76789
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319200"
---
# <a name="variables-entity-sql"></a><span data-ttu-id="e9d78-102">Variablen (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="e9d78-102">Variables (Entity SQL)</span></span>
## <a name="variable"></a><span data-ttu-id="e9d78-103">Variable</span><span class="sxs-lookup"><span data-stu-id="e9d78-103">Variable</span></span>  
 <span data-ttu-id="e9d78-104">Ein Variablenausdruck ist ein Verweis auf einen im aktuellen Bereich definierten benannten Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="e9d78-104">A variable expression is a reference to a named expression defined in the current scope.</span></span> <span data-ttu-id="e9d78-105">Ein Variablen Verweis muss ein gültiger [!INCLUDE[esql](../../../../../../includes/esql-md.md)] Bezeichner sein, wie [er in Bezeichnern](identifiers-entity-sql.md)definiert ist.</span><span class="sxs-lookup"><span data-stu-id="e9d78-105">A variable reference must be a valid [!INCLUDE[esql](../../../../../../includes/esql-md.md)] identifier, as defined in [Identifiers](identifiers-entity-sql.md).</span></span>  
  
 <span data-ttu-id="e9d78-106">Im folgenden Beispiel wird die Verwendung einer Variablen im Ausdruck dargestellt.</span><span class="sxs-lookup"><span data-stu-id="e9d78-106">The following example shows the use of a variable in the expression.</span></span> <span data-ttu-id="e9d78-107">Der Buchstabe `c` in der FROM-Klausel ist die Definition der Variablen.</span><span class="sxs-lookup"><span data-stu-id="e9d78-107">The `c` in the FROM clause is the definition of the variable.</span></span> <span data-ttu-id="e9d78-108">Die Verwendung von `c` in der SELECT-Klausel stellt den Variablenverweis dar.</span><span class="sxs-lookup"><span data-stu-id="e9d78-108">The use of `c` in the SELECT clause represents the variable reference.</span></span>  
  
```sql  
select c   
from LOB.customers as c  
```  
  
## <a name="see-also"></a><span data-ttu-id="e9d78-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e9d78-109">See also</span></span>

- [<span data-ttu-id="e9d78-110">Identifiers (Bezeichner)</span><span class="sxs-lookup"><span data-stu-id="e9d78-110">Identifiers</span></span>](identifiers-entity-sql.md)
- [<span data-ttu-id="e9d78-111">Parameter</span><span class="sxs-lookup"><span data-stu-id="e9d78-111">Parameters</span></span>](parameters-entity-sql.md)
- [<span data-ttu-id="e9d78-112">Übersicht über Entity SQL</span><span class="sxs-lookup"><span data-stu-id="e9d78-112">Entity SQL Overview</span></span>](entity-sql-overview.md)
