---
title: Variablen (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 3eed222a-f8f6-46b6-9cd5-220cc0e4e5d8
ms.openlocfilehash: 88ee41bc08711cf84b8b2e273c9ac0f4267d1d34
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79149816"
---
# <a name="variables-entity-sql"></a><span data-ttu-id="17018-102">Variablen (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="17018-102">Variables (Entity SQL)</span></span>
## <a name="variable"></a><span data-ttu-id="17018-103">Variable</span><span class="sxs-lookup"><span data-stu-id="17018-103">Variable</span></span>  
 <span data-ttu-id="17018-104">Ein Variablenausdruck ist ein Verweis auf einen im aktuellen Bereich definierten benannten Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="17018-104">A variable expression is a reference to a named expression defined in the current scope.</span></span> <span data-ttu-id="17018-105">Ein Variablenverweis muss [!INCLUDE[esql](../../../../../../includes/esql-md.md)] ein gültiger Bezeichner sein, wie in [Identifiers](identifiers-entity-sql.md)definiert.</span><span class="sxs-lookup"><span data-stu-id="17018-105">A variable reference must be a valid [!INCLUDE[esql](../../../../../../includes/esql-md.md)] identifier, as defined in [Identifiers](identifiers-entity-sql.md).</span></span>  
  
 <span data-ttu-id="17018-106">Im folgenden Beispiel wird die Verwendung einer Variablen im Ausdruck dargestellt.</span><span class="sxs-lookup"><span data-stu-id="17018-106">The following example shows the use of a variable in the expression.</span></span> <span data-ttu-id="17018-107">Der Buchstabe  in der FROM-Klausel ist die Definition der Variablen.</span><span class="sxs-lookup"><span data-stu-id="17018-107">The `c` in the FROM clause is the definition of the variable.</span></span> <span data-ttu-id="17018-108">Die Verwendung von  in der SELECT-Klausel stellt den Variablenverweis dar.</span><span class="sxs-lookup"><span data-stu-id="17018-108">The use of `c` in the SELECT clause represents the variable reference.</span></span>  
  
```sql  
select c
from LOB.customers as c  
```  
  
## <a name="see-also"></a><span data-ttu-id="17018-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="17018-109">See also</span></span>

- [<span data-ttu-id="17018-110">Identifiers (Bezeichner)</span><span class="sxs-lookup"><span data-stu-id="17018-110">Identifiers</span></span>](identifiers-entity-sql.md)
- [<span data-ttu-id="17018-111">Parameter</span><span class="sxs-lookup"><span data-stu-id="17018-111">Parameters</span></span>](parameters-entity-sql.md)
- [<span data-ttu-id="17018-112">Übersicht über Entity SQL</span><span class="sxs-lookup"><span data-stu-id="17018-112">Entity SQL Overview</span></span>](entity-sql-overview.md)
