---
title: WHERE (Entity SQL)
ms.date: 03/30/2017
ms.assetid: a8e1061e-0028-4a6f-8f19-b9f48e96c4b8
ms.openlocfilehash: 939d4c0ec2c30bc71b22fb65ab36644e063f97de
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2019
ms.locfileid: "66489849"
---
# <a name="where-entity-sql"></a><span data-ttu-id="ef2d2-102">WHERE (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="ef2d2-102">WHERE (Entity SQL)</span></span>
<span data-ttu-id="ef2d2-103">Die WHERE-Klausel direkt nach dem gilt die [FROM](../../../../../../docs/framework/data/adonet/ef/language-reference/from-entity-sql.md) Klausel.</span><span class="sxs-lookup"><span data-stu-id="ef2d2-103">The WHERE clause is applied directly after the [FROM](../../../../../../docs/framework/data/adonet/ef/language-reference/from-entity-sql.md) clause.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef2d2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ef2d2-104">Syntax</span></span>  
  
```  
[ WHERE expression ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="ef2d2-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="ef2d2-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="ef2d2-106">Ein boolescher Typ.</span><span class="sxs-lookup"><span data-stu-id="ef2d2-106">A Boolean type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ef2d2-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ef2d2-107">Remarks</span></span>  
 <span data-ttu-id="ef2d2-108">Die WHERE-Klausel weist dieselbe Semantik wie für Transact-SQL beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ef2d2-108">The WHERE clause has the same semantics as described for Transact-SQL.</span></span> <span data-ttu-id="ef2d2-109">Sie beschränkt die vom Abfrageausdruck zurückgegebenen Objekte, indem die Elemente der Quellauflistung auf diejenigen Elemente eingeschränkt werden, die die Bedingung erfüllen.</span><span class="sxs-lookup"><span data-stu-id="ef2d2-109">It restricts the objects produced by the query expression by limiting the elements of the source collections to those that pass the condition.</span></span>  
  
```  
select c from cs as c where e  
```  
  
 <span data-ttu-id="ef2d2-110">Der Ausdruck `e` muss einen booleschen Wert haben.</span><span class="sxs-lookup"><span data-stu-id="ef2d2-110">The expression `e` must have the type Boolean.</span></span>  
  
 <span data-ttu-id="ef2d2-111">Die WHERE-Klausel wird direkt nach der FROM-Klausel und vor der Ausführung von Gruppierungs-, Sortierungs- oder Projektionsvorgängen angewendet.</span><span class="sxs-lookup"><span data-stu-id="ef2d2-111">The WHERE clause is applied directly after the FROM clause and before any grouping, ordering, or projection takes place.</span></span> <span data-ttu-id="ef2d2-112">Alle in der FROM-Klausel definierten Elementnamen sind für den Ausdruck der WHERE-Klausel sichtbar.</span><span class="sxs-lookup"><span data-stu-id="ef2d2-112">All element names defined in the FROM clause are visible to the expression of the WHERE clause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef2d2-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ef2d2-113">See also</span></span>

- [<span data-ttu-id="ef2d2-114">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="ef2d2-114">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [<span data-ttu-id="ef2d2-115">Abfrageausdrücke</span><span class="sxs-lookup"><span data-stu-id="ef2d2-115">Query Expressions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expressions-entity-sql.md)
