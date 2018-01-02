---
title: WHERE (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a8e1061e-0028-4a6f-8f19-b9f48e96c4b8
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 2ad170500770bc370eb67a04ab29d0c9f9dcaabd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="where-entity-sql"></a><span data-ttu-id="26371-102">WHERE (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="26371-102">WHERE (Entity SQL)</span></span>
<span data-ttu-id="26371-103">Die WHERE-Klausel direkt nach dem gilt die [FROM](../../../../../../docs/framework/data/adonet/ef/language-reference/from-entity-sql.md) Klausel.</span><span class="sxs-lookup"><span data-stu-id="26371-103">The WHERE clause is applied directly after the [FROM](../../../../../../docs/framework/data/adonet/ef/language-reference/from-entity-sql.md) clause.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26371-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="26371-104">Syntax</span></span>  
  
```  
[ WHERE expression ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="26371-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="26371-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="26371-106">Ein boolescher Typ.</span><span class="sxs-lookup"><span data-stu-id="26371-106">A Boolean type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="26371-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="26371-107">Remarks</span></span>  
 <span data-ttu-id="26371-108">Die WHERE[!INCLUDE[tsql](../../../../../../includes/tsql-md.md)]-Klausel hat die für  beschriebene Semantik.</span><span class="sxs-lookup"><span data-stu-id="26371-108">The WHERE clause has the same semantics as described for [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="26371-109">Sie beschränkt die vom Abfrageausdruck zurückgegebenen Objekte, indem die Elemente der Quellauflistung auf diejenigen Elemente eingeschränkt werden, die die Bedingung erfüllen.</span><span class="sxs-lookup"><span data-stu-id="26371-109">It restricts the objects produced by the query expression by limiting the elements of the source collections to those that pass the condition.</span></span>  
  
```  
select c from cs as c where e  
```  
  
 <span data-ttu-id="26371-110">Der Ausdruck `e` muss einen booleschen Wert haben.</span><span class="sxs-lookup"><span data-stu-id="26371-110">The expression `e` must have the type Boolean.</span></span>  
  
 <span data-ttu-id="26371-111">Die WHERE-Klausel wird direkt nach der FROM-Klausel und vor der Ausführung von Gruppierungs-, Sortierungs- oder Projektionsvorgängen angewendet.</span><span class="sxs-lookup"><span data-stu-id="26371-111">The WHERE clause is applied directly after the FROM clause and before any grouping, ordering, or projection takes place.</span></span> <span data-ttu-id="26371-112">Alle in der FROM-Klausel definierten Elementnamen sind für den Ausdruck der WHERE-Klausel sichtbar.</span><span class="sxs-lookup"><span data-stu-id="26371-112">All element names defined in the FROM clause are visible to the expression of the WHERE clause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26371-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="26371-113">See Also</span></span>  
 [<span data-ttu-id="26371-114">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="26371-114">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="26371-115">Abfrageausdrücke</span><span class="sxs-lookup"><span data-stu-id="26371-115">Query Expressions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expressions-entity-sql.md)
