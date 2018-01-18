---
title: "Nicht unterstützte Ausdrücke (Entity SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5e79da7e-e78a-413c-8fb0-f3f9cd84f579
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: a7dde3d88b5b21df99be64cedc92d6aa06b00d3b
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="unsupported-expressions-entity-sql"></a><span data-ttu-id="58d4e-102">Nicht unterstützte Ausdrücke (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="58d4e-102">Unsupported Expressions (Entity SQL)</span></span>
<span data-ttu-id="58d4e-103">In diesem Thema werden die [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)]-Ausdrücke beschrieben, die in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] nicht unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="58d4e-103">This topic describes [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] expressions that are not supported in [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span> <span data-ttu-id="58d4e-104">Weitere Informationen finden Sie unter [wie Entity SQL unterscheidet sich von Transact-SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/how-entity-sql-differs-from-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="58d4e-104">For more information, see [How Entity SQL Differs from Transact-SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/how-entity-sql-differs-from-transact-sql.md).</span></span>  
  
## <a name="quantified-predicates"></a><span data-ttu-id="58d4e-105">Quantifizierte Prädikate</span><span class="sxs-lookup"><span data-stu-id="58d4e-105">Quantified Predicates</span></span>  
 <span data-ttu-id="58d4e-106">In [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] sind Konstrukte der folgenden Form zulässig:</span><span class="sxs-lookup"><span data-stu-id="58d4e-106">[!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] allows constructs of the following form:</span></span>  
  
```  
sal > all (select salary from employees)  
sal > any (select salary from employees)  
```  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="58d4e-107"> unterstützt solche Konstrukte jedoch nicht.</span><span class="sxs-lookup"><span data-stu-id="58d4e-107">, however, does not support such constructs.</span></span> <span data-ttu-id="58d4e-108">In [!INCLUDE[esql](../../../../../../includes/esql-md.md)] können gleichwertige Ausdrücke wie folgt geschrieben werden:</span><span class="sxs-lookup"><span data-stu-id="58d4e-108">Equivalent expressions can be written in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] as follows:</span></span>  
  
```  
not exists(select 0 from employees as e where sal > e.salary)  
exists(select 0 from employees as e where sal > e.salary)  
```  
  
## <a name="-operator"></a><span data-ttu-id="58d4e-109">Operator \*</span><span class="sxs-lookup"><span data-stu-id="58d4e-109">\* Operator</span></span>  
 [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)]<span data-ttu-id="58d4e-110"> unterstützt die Verwendung des "\*"-Operators in der SELECT-Klausel, um anzugeben, dass alle Spalten herausprojiziert werden sollen. Dies wird in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="58d4e-110"> supports the use of the \* operator in the SELECT clause to indicate that all columns should be projected out. This is not supported in [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58d4e-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="58d4e-111">See Also</span></span>  
 [<span data-ttu-id="58d4e-112">Übersicht über Entity SQL</span><span class="sxs-lookup"><span data-stu-id="58d4e-112">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)  
 [<span data-ttu-id="58d4e-113">Unterschiede zwischen Entity SQL und Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="58d4e-113">How Entity SQL Differs from Transact-SQL</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/how-entity-sql-differs-from-transact-sql.md)
