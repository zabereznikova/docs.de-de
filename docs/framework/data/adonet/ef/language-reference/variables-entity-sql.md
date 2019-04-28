---
title: Variablen (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 3eed222a-f8f6-46b6-9cd5-220cc0e4e5d8
ms.openlocfilehash: bf6fa95e38d1eb5817fd67165b6993cbb0755fd1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61879774"
---
# <a name="variables-entity-sql"></a><span data-ttu-id="841c8-102">Variablen (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="841c8-102">Variables (Entity SQL)</span></span>
## <a name="variable"></a><span data-ttu-id="841c8-103">Variable</span><span class="sxs-lookup"><span data-stu-id="841c8-103">Variable</span></span>  
 <span data-ttu-id="841c8-104">Ein Variablenausdruck ist ein Verweis auf einen im aktuellen Bereich definierten benannten Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="841c8-104">A variable expression is a reference to a named expression defined in the current scope.</span></span> <span data-ttu-id="841c8-105">Ein Variablenverweis muss ein gültiger [!INCLUDE[esql](../../../../../../includes/esql-md.md)] Bezeichner, die gemäß [Bezeichner](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="841c8-105">A variable reference must be a valid [!INCLUDE[esql](../../../../../../includes/esql-md.md)] identifier, as defined in [Identifiers](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md).</span></span>  
  
 <span data-ttu-id="841c8-106">Im folgenden Beispiel wird die Verwendung einer Variablen im Ausdruck dargestellt.</span><span class="sxs-lookup"><span data-stu-id="841c8-106">The following example shows the use of a variable in the expression.</span></span> <span data-ttu-id="841c8-107">Der Buchstabe `c` in der FROM-Klausel ist die Definition der Variablen.</span><span class="sxs-lookup"><span data-stu-id="841c8-107">The `c` in the FROM clause is the definition of the variable.</span></span> <span data-ttu-id="841c8-108">Die Verwendung von `c` in der SELECT-Klausel stellt den Variablenverweis dar.</span><span class="sxs-lookup"><span data-stu-id="841c8-108">The use of `c` in the SELECT clause represents the variable reference.</span></span>  
  
```  
select c   
from LOB.customers as c  
```  
  
## <a name="see-also"></a><span data-ttu-id="841c8-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="841c8-109">See also</span></span>

- [<span data-ttu-id="841c8-110">Identifiers (Bezeichner)</span><span class="sxs-lookup"><span data-stu-id="841c8-110">Identifiers</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md)
- [<span data-ttu-id="841c8-111">Parameter</span><span class="sxs-lookup"><span data-stu-id="841c8-111">Parameters</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/parameters-entity-sql.md)
- [<span data-ttu-id="841c8-112">Übersicht über Entity SQL</span><span class="sxs-lookup"><span data-stu-id="841c8-112">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
