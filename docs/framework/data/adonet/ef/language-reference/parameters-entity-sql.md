---
title: Parameter (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 8d618edd-0988-4ff2-8263-ce59448af7a5
ms.openlocfilehash: 759452902461e1a460b69774bb33f92bbd532ed0
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177513"
---
# <a name="parameters-entity-sql"></a><span data-ttu-id="db395-102">Parameter (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="db395-102">Parameters (Entity SQL)</span></span>

<span data-ttu-id="db395-103">Parameter sind Variablen, die außerhalb von [!INCLUDE[esql](../../../../../../includes/esql-md.md)] definiert werden, üblicherweise über eine Bindungs-API, die von einer Hostsprache verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="db395-103">Parameters are variables that are defined outside [!INCLUDE[esql](../../../../../../includes/esql-md.md)], usually through a binding API that is used by a host language.</span></span> <span data-ttu-id="db395-104">Jeder Parameter hat einen Namen und einen Typ.</span><span class="sxs-lookup"><span data-stu-id="db395-104">Each parameter has a name and a type.</span></span> <span data-ttu-id="db395-105">Parameternamen werden in Abfrageausdrücken mit einem "at" (@)-Symbol als Präfix definiert.</span><span class="sxs-lookup"><span data-stu-id="db395-105">Parameter names are defined in query expressions with the at (@) symbol as a prefix.</span></span> <span data-ttu-id="db395-106">Damit sind sie von den Namen von Eigenschaften oder anderen in der Abfrage definierten Namen unterscheidbar.</span><span class="sxs-lookup"><span data-stu-id="db395-106">This disambiguates them from the names of properties or other names that are defined in the query.</span></span>  
  
 <span data-ttu-id="db395-107">Die Bindungs-API der Hostsprache stellt APIs für die Parameterbindung zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="db395-107">The host-language binding API provides APIs for binding parameters.</span></span>  
  
## <a name="example"></a><span data-ttu-id="db395-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="db395-108">Example</span></span>  
  
```sql  
SELECT c
      FROM LOB.Customers AS c
      WHERE c.Name = @name  
```  
  
## <a name="see-also"></a><span data-ttu-id="db395-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="db395-109">See also</span></span>

- [<span data-ttu-id="db395-110">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="db395-110">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="db395-111">Übersicht über Entity SQL</span><span class="sxs-lookup"><span data-stu-id="db395-111">Entity SQL Overview</span></span>](entity-sql-overview.md)
