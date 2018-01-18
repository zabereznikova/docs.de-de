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
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 11687b1218c61acde7a68bb8fc112e287e5e1c38
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="where-entity-sql"></a><span data-ttu-id="82a76-102">WHERE (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="82a76-102">WHERE (Entity SQL)</span></span>
<span data-ttu-id="82a76-103">Die WHERE-Klausel direkt nach dem gilt die [FROM](../../../../../../docs/framework/data/adonet/ef/language-reference/from-entity-sql.md) Klausel.</span><span class="sxs-lookup"><span data-stu-id="82a76-103">The WHERE clause is applied directly after the [FROM](../../../../../../docs/framework/data/adonet/ef/language-reference/from-entity-sql.md) clause.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82a76-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="82a76-104">Syntax</span></span>  
  
```  
[ WHERE expression ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="82a76-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="82a76-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="82a76-106">Ein boolescher Typ.</span><span class="sxs-lookup"><span data-stu-id="82a76-106">A Boolean type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="82a76-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="82a76-107">Remarks</span></span>  
 <span data-ttu-id="82a76-108">Die WHERE[!INCLUDE[tsql](../../../../../../includes/tsql-md.md)]-Klausel hat die für  beschriebene Semantik.</span><span class="sxs-lookup"><span data-stu-id="82a76-108">The WHERE clause has the same semantics as described for [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="82a76-109">Sie beschränkt die vom Abfrageausdruck zurückgegebenen Objekte, indem die Elemente der Quellauflistung auf diejenigen Elemente eingeschränkt werden, die die Bedingung erfüllen.</span><span class="sxs-lookup"><span data-stu-id="82a76-109">It restricts the objects produced by the query expression by limiting the elements of the source collections to those that pass the condition.</span></span>  
  
```  
select c from cs as c where e  
```  
  
 <span data-ttu-id="82a76-110">Der Ausdruck `e` muss einen booleschen Wert haben.</span><span class="sxs-lookup"><span data-stu-id="82a76-110">The expression `e` must have the type Boolean.</span></span>  
  
 <span data-ttu-id="82a76-111">Die WHERE-Klausel wird direkt nach der FROM-Klausel und vor der Ausführung von Gruppierungs-, Sortierungs- oder Projektionsvorgängen angewendet.</span><span class="sxs-lookup"><span data-stu-id="82a76-111">The WHERE clause is applied directly after the FROM clause and before any grouping, ordering, or projection takes place.</span></span> <span data-ttu-id="82a76-112">Alle in der FROM-Klausel definierten Elementnamen sind für den Ausdruck der WHERE-Klausel sichtbar.</span><span class="sxs-lookup"><span data-stu-id="82a76-112">All element names defined in the FROM clause are visible to the expression of the WHERE clause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82a76-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="82a76-113">See Also</span></span>  
 [<span data-ttu-id="82a76-114">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="82a76-114">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="82a76-115">Abfrageausdrücke</span><span class="sxs-lookup"><span data-stu-id="82a76-115">Query Expressions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expressions-entity-sql.md)
