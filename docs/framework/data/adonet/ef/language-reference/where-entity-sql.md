---
title: WHERE (Entity SQL)
ms.date: 03/30/2017
ms.assetid: a8e1061e-0028-4a6f-8f19-b9f48e96c4b8
ms.openlocfilehash: 02eeaeb8cfa335e5545b26d3d52b91c4e1614629
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61879436"
---
# <a name="where-entity-sql"></a><span data-ttu-id="ae331-102">WHERE (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="ae331-102">WHERE (Entity SQL)</span></span>
<span data-ttu-id="ae331-103">Die WHERE-Klausel direkt nach dem gilt die [FROM](../../../../../../docs/framework/data/adonet/ef/language-reference/from-entity-sql.md) Klausel.</span><span class="sxs-lookup"><span data-stu-id="ae331-103">The WHERE clause is applied directly after the [FROM](../../../../../../docs/framework/data/adonet/ef/language-reference/from-entity-sql.md) clause.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae331-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ae331-104">Syntax</span></span>  
  
```  
[ WHERE expression ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="ae331-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="ae331-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="ae331-106">Ein boolescher Typ.</span><span class="sxs-lookup"><span data-stu-id="ae331-106">A Boolean type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ae331-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ae331-107">Remarks</span></span>  
 <span data-ttu-id="ae331-108">Die WHERE[!INCLUDE[tsql](../../../../../../includes/tsql-md.md)]-Klausel hat die für  beschriebene Semantik.</span><span class="sxs-lookup"><span data-stu-id="ae331-108">The WHERE clause has the same semantics as described for [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="ae331-109">Sie beschränkt die vom Abfrageausdruck zurückgegebenen Objekte, indem die Elemente der Quellauflistung auf diejenigen Elemente eingeschränkt werden, die die Bedingung erfüllen.</span><span class="sxs-lookup"><span data-stu-id="ae331-109">It restricts the objects produced by the query expression by limiting the elements of the source collections to those that pass the condition.</span></span>  
  
```  
select c from cs as c where e  
```  
  
 <span data-ttu-id="ae331-110">Der Ausdruck `e` muss einen booleschen Wert haben.</span><span class="sxs-lookup"><span data-stu-id="ae331-110">The expression `e` must have the type Boolean.</span></span>  
  
 <span data-ttu-id="ae331-111">Die WHERE-Klausel wird direkt nach der FROM-Klausel und vor der Ausführung von Gruppierungs-, Sortierungs- oder Projektionsvorgängen angewendet.</span><span class="sxs-lookup"><span data-stu-id="ae331-111">The WHERE clause is applied directly after the FROM clause and before any grouping, ordering, or projection takes place.</span></span> <span data-ttu-id="ae331-112">Alle in der FROM-Klausel definierten Elementnamen sind für den Ausdruck der WHERE-Klausel sichtbar.</span><span class="sxs-lookup"><span data-stu-id="ae331-112">All element names defined in the FROM clause are visible to the expression of the WHERE clause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae331-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ae331-113">See also</span></span>

- [<span data-ttu-id="ae331-114">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="ae331-114">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [<span data-ttu-id="ae331-115">Abfrageausdrücke</span><span class="sxs-lookup"><span data-stu-id="ae331-115">Query Expressions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expressions-entity-sql.md)
