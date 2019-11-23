---
title: MULTISET (Entity SQL)
ms.date: 03/30/2017
ms.assetid: eb90a377-e47a-43a5-b308-e993b6d611e6
ms.openlocfilehash: 222be86db434b5d41c7b0536d271a3750b6afbe8
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319584"
---
# <a name="multiset-entity-sql"></a><span data-ttu-id="8585a-102">MULTISET (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="8585a-102">MULTISET (Entity SQL)</span></span>
<span data-ttu-id="8585a-103">Erstellt eine Instanz einer Multimenge aus einer Liste von Werten.</span><span class="sxs-lookup"><span data-stu-id="8585a-103">Creates an instance of a multiset from a list of values.</span></span> <span data-ttu-id="8585a-104">Alle Werte im MULTISET-Konstruktor müssen von einem kompatiblen `T`-Typ sein.</span><span class="sxs-lookup"><span data-stu-id="8585a-104">All the values in the MULTISET constructor must be of a compatible type `T`.</span></span> <span data-ttu-id="8585a-105">Leere Multimengenkonstruktoren sind nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="8585a-105">Empty multiset constructors are not allowed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8585a-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="8585a-106">Syntax</span></span>  
  
```sql  
MULTISET ( expression [{, expression }] )  
-- or  
{ expression [{, expression }] }  
```  
  
## <a name="arguments"></a><span data-ttu-id="8585a-107">Argumente</span><span class="sxs-lookup"><span data-stu-id="8585a-107">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="8585a-108">Eine beliebige Liste gültiger Werte.</span><span class="sxs-lookup"><span data-stu-id="8585a-108">Any valid list of values.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8585a-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="8585a-109">Return Value</span></span>  
 <span data-ttu-id="8585a-110">Eine Auflistung vom Typ Multiset\<t >.</span><span class="sxs-lookup"><span data-stu-id="8585a-110">A collection of type MULTISET\<T>.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8585a-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8585a-111">Remarks</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="8585a-112">stellt drei Arten von Konstruktoren bereit: Zeilenkonstruktoren, Objektkonstruktoren und Multimengenkonstruktoren (oder Auflistungen).</span><span class="sxs-lookup"><span data-stu-id="8585a-112">provides three kinds of constructors: row constructors, object constructors, and multiset (or collection) constructors.</span></span> <span data-ttu-id="8585a-113">Weitere Informationen finden Sie unter [Konstruieren von Typen](constructing-types-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="8585a-113">For more information, see [Constructing Types](constructing-types-entity-sql.md).</span></span>  
  
 <span data-ttu-id="8585a-114">Der Multimengenkonstruktor erstellt eine Instanz einer Multimenge aus einer Liste von Werten.</span><span class="sxs-lookup"><span data-stu-id="8585a-114">The multiset constructor creates an instance of a multiset from a list of values.</span></span> <span data-ttu-id="8585a-115">Alle Werte im Konstruktor müssen von einem kompatiblen Typ sein.</span><span class="sxs-lookup"><span data-stu-id="8585a-115">All the values in the constructor must be of a compatible type.</span></span>  
  
 <span data-ttu-id="8585a-116">Zum Beispiel erstellt der folgende Ausdruck eine Multimenge von ganzen Zahlen.</span><span class="sxs-lookup"><span data-stu-id="8585a-116">For example, the following expression creates a multiset of integers.</span></span>  
  
 `MULTISET(1, 2, 3)`  
  
 `{1, 2, 3}`  
  
> [!NOTE]
> <span data-ttu-id="8585a-117">Unterstützte Multiset-Literale werden nur unterstützt, wenn eine Wrapping-Multimenge über ein einzelnes Multiset-Element verfügt. beispielsweise `{{1, 2, 3}}`.</span><span class="sxs-lookup"><span data-stu-id="8585a-117">Nested multiset literals are only supported when a wrapping multiset has a single multiset element; for example, `{{1, 2, 3}}`.</span></span> <span data-ttu-id="8585a-118">Wenn die Wrapping-Multimenge über mehrere Multimengenelemente verfügt, werden geschachtelte (z. B. `{{1, 2}, {3, 4}}`) Multimengenliterale nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="8585a-118">When the wrapping multiset has multiple multiset elements (for example, `{{1, 2}, {3, 4}}`), nested multiset literals are not supported.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8585a-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8585a-119">Example</span></span>  
 <span data-ttu-id="8585a-120">Die Folgende Entity SQL-Abfrage verwendet den MULTISET-Operator, um eine Instanz einer Multimenge aus einer Liste mit Werten zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="8585a-120">The following Entity SQL query uses the MULTISET operator to create an instance of a multiset from a list of values.</span></span> <span data-ttu-id="8585a-121">Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell.</span><span class="sxs-lookup"><span data-stu-id="8585a-121">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="8585a-122">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="8585a-122">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="8585a-123">Verwenden Sie das Verfahren unter [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="8585a-123">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="8585a-124">Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="8585a-124">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#MULTISET](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#multiset)]  
  
## <a name="see-also"></a><span data-ttu-id="8585a-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8585a-125">See also</span></span>

- [<span data-ttu-id="8585a-126">Konstruktionstypen</span><span class="sxs-lookup"><span data-stu-id="8585a-126">Constructing Types</span></span>](constructing-types-entity-sql.md)
- [<span data-ttu-id="8585a-127">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="8585a-127">Entity SQL Reference</span></span>](entity-sql-reference.md)
