---
title: WHERE (Entity SQL)
ms.date: 03/30/2017
ms.assetid: a8e1061e-0028-4a6f-8f19-b9f48e96c4b8
ms.openlocfilehash: 1907b8786622d3c8019c75916f997c830cc07cfb
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91180958"
---
# <a name="where-entity-sql"></a><span data-ttu-id="c65ae-102">WHERE (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="c65ae-102">WHERE (Entity SQL)</span></span>

<span data-ttu-id="c65ae-103">Die WHERE-Klausel wird direkt nach der [from](from-entity-sql.md) -Klausel angewendet.</span><span class="sxs-lookup"><span data-stu-id="c65ae-103">The WHERE clause is applied directly after the [FROM](from-entity-sql.md) clause.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c65ae-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c65ae-104">Syntax</span></span>  
  
```sql  
[ WHERE expression ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="c65ae-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="c65ae-105">Arguments</span></span>  

 `expression`  
 <span data-ttu-id="c65ae-106">Ein boolescher Typ.</span><span class="sxs-lookup"><span data-stu-id="c65ae-106">A Boolean type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c65ae-107">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="c65ae-107">Remarks</span></span>  

 <span data-ttu-id="c65ae-108">Die WHERE-Klausel verfügt über die gleiche Semantik wie für Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="c65ae-108">The WHERE clause has the same semantics as described for Transact-SQL.</span></span> <span data-ttu-id="c65ae-109">Sie beschränkt die vom Abfrageausdruck zurückgegebenen Objekte, indem die Elemente der Quellauflistung auf diejenigen Elemente eingeschränkt werden, die die Bedingung erfüllen.</span><span class="sxs-lookup"><span data-stu-id="c65ae-109">It restricts the objects produced by the query expression by limiting the elements of the source collections to those that pass the condition.</span></span>  
  
```sql  
select c from cs as c where e  
```  
  
 <span data-ttu-id="c65ae-110">Der Ausdruck `e` muss einen booleschen Wert haben.</span><span class="sxs-lookup"><span data-stu-id="c65ae-110">The expression `e` must have the type Boolean.</span></span>  
  
 <span data-ttu-id="c65ae-111">Die WHERE-Klausel wird direkt nach der FROM-Klausel und vor der Ausführung von Gruppierungs-, Sortierungs- oder Projektionsvorgängen angewendet.</span><span class="sxs-lookup"><span data-stu-id="c65ae-111">The WHERE clause is applied directly after the FROM clause and before any grouping, ordering, or projection takes place.</span></span> <span data-ttu-id="c65ae-112">Alle in der FROM-Klausel definierten Elementnamen sind für den Ausdruck der WHERE-Klausel sichtbar.</span><span class="sxs-lookup"><span data-stu-id="c65ae-112">All element names defined in the FROM clause are visible to the expression of the WHERE clause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c65ae-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c65ae-113">See also</span></span>

- [<span data-ttu-id="c65ae-114">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="c65ae-114">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="c65ae-115">Abfrageausdrücke</span><span class="sxs-lookup"><span data-stu-id="c65ae-115">Query Expressions</span></span>](query-expressions-entity-sql.md)
