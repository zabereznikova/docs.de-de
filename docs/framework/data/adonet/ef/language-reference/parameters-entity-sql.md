---
title: Parameter (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 8d618edd-0988-4ff2-8263-ce59448af7a5
ms.openlocfilehash: 8fbca4f10a7c2c3dbaffff978a536b87d31a8df4
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319430"
---
# <a name="parameters-entity-sql"></a><span data-ttu-id="0b418-102">Parameter (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="0b418-102">Parameters (Entity SQL)</span></span>
<span data-ttu-id="0b418-103">Parameter sind Variablen, die außerhalb von [!INCLUDE[esql](../../../../../../includes/esql-md.md)] definiert werden, üblicherweise über eine Bindungs-API, die von einer Hostsprache verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="0b418-103">Parameters are variables that are defined outside [!INCLUDE[esql](../../../../../../includes/esql-md.md)], usually through a binding API that is used by a host language.</span></span> <span data-ttu-id="0b418-104">Jeder Parameter hat einen Namen und einen Typ.</span><span class="sxs-lookup"><span data-stu-id="0b418-104">Each parameter has a name and a type.</span></span> <span data-ttu-id="0b418-105">Parameternamen werden in Abfrageausdrücken mit einem "at" (@)-Symbol als Präfix definiert.</span><span class="sxs-lookup"><span data-stu-id="0b418-105">Parameter names are defined in query expressions with the at (@) symbol as a prefix.</span></span> <span data-ttu-id="0b418-106">Damit sind sie von den Namen von Eigenschaften oder anderen in der Abfrage definierten Namen unterscheidbar.</span><span class="sxs-lookup"><span data-stu-id="0b418-106">This disambiguates them from the names of properties or other names that are defined in the query.</span></span>  
  
 <span data-ttu-id="0b418-107">Die Bindungs-API der Hostsprache stellt APIs für die Parameterbindung zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="0b418-107">The host-language binding API provides APIs for binding parameters.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0b418-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0b418-108">Example</span></span>  
  
```sql  
SELECT c   
      FROM LOB.Customers AS c   
      WHERE c.Name = @name  
```  
  
## <a name="see-also"></a><span data-ttu-id="0b418-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0b418-109">See also</span></span>

- [<span data-ttu-id="0b418-110">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="0b418-110">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="0b418-111">Übersicht über Entity SQL</span><span class="sxs-lookup"><span data-stu-id="0b418-111">Entity SQL Overview</span></span>](entity-sql-overview.md)
