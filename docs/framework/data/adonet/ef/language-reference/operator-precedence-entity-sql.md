---
title: Operatorrangfolge (Entity SQL)
ms.date: 03/30/2017
ms.assetid: e92e4ca5-2889-4266-9625-47f0eb01a948
ms.openlocfilehash: f8aa0f213a24d6431d8910af849571a67fbd9f57
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91175641"
---
# <a name="operator-precedence-entity-sql"></a><span data-ttu-id="c0f04-102">Operatorrangfolge (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="c0f04-102">Operator Precedence (Entity SQL)</span></span>

<span data-ttu-id="c0f04-103">Wenn eine [!INCLUDE[esql](../../../../../../includes/esql-md.md)] Abfrage über mehrere Operatoren verfügt, bestimmt die Operator Rangfolge die Reihenfolge, in der die Vorgänge ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="c0f04-103">When an [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query has multiple operators, operator precedence determines the sequence in which the operations are performed.</span></span> <span data-ttu-id="c0f04-104">Die Ausführungsreihenfolge kann sich entscheidend auf das Abfrageergebnis auswirken.</span><span class="sxs-lookup"><span data-stu-id="c0f04-104">The order of execution can significantly affect the query result.</span></span>  
  
 <span data-ttu-id="c0f04-105">Operatoren besitzen die in der folgenden Tabelle dargestellte Rangfolge.</span><span class="sxs-lookup"><span data-stu-id="c0f04-105">Operators have the precedence levels shown in the following table.</span></span> <span data-ttu-id="c0f04-106">Ein Operator, der höher in der Rangfolge steht, wird vor einem Operator niedrigeren Ranges ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="c0f04-106">An operator with a higher level is evaluated before an operator with a lower level.</span></span>  
  
|<span data-ttu-id="c0f04-107">Ebene</span><span class="sxs-lookup"><span data-stu-id="c0f04-107">Level</span></span>|<span data-ttu-id="c0f04-108">Vorgangsart</span><span class="sxs-lookup"><span data-stu-id="c0f04-108">Operation type</span></span>|<span data-ttu-id="c0f04-109">Operator</span><span class="sxs-lookup"><span data-stu-id="c0f04-109">Operator</span></span>|  
|-----------|--------------------|--------------|  
|<span data-ttu-id="c0f04-110">1</span><span class="sxs-lookup"><span data-stu-id="c0f04-110">1</span></span>|<span data-ttu-id="c0f04-111">Primär</span><span class="sxs-lookup"><span data-stu-id="c0f04-111">Primary</span></span>|`. , [] ()`|  
|<span data-ttu-id="c0f04-112">2</span><span class="sxs-lookup"><span data-stu-id="c0f04-112">2</span></span>|<span data-ttu-id="c0f04-113">Unär</span><span class="sxs-lookup"><span data-stu-id="c0f04-113">Unary</span></span>|`! not`|  
|<span data-ttu-id="c0f04-114">3</span><span class="sxs-lookup"><span data-stu-id="c0f04-114">3</span></span>|<span data-ttu-id="c0f04-115">Multiplikativ</span><span class="sxs-lookup"><span data-stu-id="c0f04-115">Multiplicative</span></span>|`* / %`|  
|<span data-ttu-id="c0f04-116">4</span><span class="sxs-lookup"><span data-stu-id="c0f04-116">4</span></span>|<span data-ttu-id="c0f04-117">Additiv</span><span class="sxs-lookup"><span data-stu-id="c0f04-117">Additive</span></span>|`+ -`|  
|<span data-ttu-id="c0f04-118">5</span><span class="sxs-lookup"><span data-stu-id="c0f04-118">5</span></span>|<span data-ttu-id="c0f04-119">Sortieren</span><span class="sxs-lookup"><span data-stu-id="c0f04-119">Ordering</span></span>|`< > <= >=`|  
|<span data-ttu-id="c0f04-120">6</span><span class="sxs-lookup"><span data-stu-id="c0f04-120">6</span></span>|<span data-ttu-id="c0f04-121">Gleichheit</span><span class="sxs-lookup"><span data-stu-id="c0f04-121">Equality</span></span>|`= != <>`|  
|<span data-ttu-id="c0f04-122">7</span><span class="sxs-lookup"><span data-stu-id="c0f04-122">7</span></span>|<span data-ttu-id="c0f04-123">Bedingtes AND</span><span class="sxs-lookup"><span data-stu-id="c0f04-123">Conditional AND</span></span>|`and &&`|  
|<span data-ttu-id="c0f04-124">8</span><span class="sxs-lookup"><span data-stu-id="c0f04-124">8</span></span>|<span data-ttu-id="c0f04-125">Bedingtes OR</span><span class="sxs-lookup"><span data-stu-id="c0f04-125">Conditional OR</span></span>|`or &#124;&#124;`|  
  
 <span data-ttu-id="c0f04-126">Verfügen zwei Operatoren in einem Ausdruck über die gleiche Rangstufe, werden sie von links nach rechts, ausgehend von ihrer Position innerhalb der Abfrage, ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="c0f04-126">When two operators in an expression have the same operator precedence level, they are evaluated left to right, based on their position in the query.</span></span> <span data-ttu-id="c0f04-127">`x+y-z` wird beispielsweise als `(x+y)-z` ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="c0f04-127">For example, `x+y-z` is evaluated as `(x+y)-z`.</span></span>  
  
 <span data-ttu-id="c0f04-128">Mit Klammern kann die definierte Rangfolge von Operatoren in einer Abfrage außer Kraft gesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="c0f04-128">You can use parentheses to override the defined precedence of the operators in a query.</span></span> <span data-ttu-id="c0f04-129">Die Operatoren innerhalb der Klammern werden zuerst ausgewertet, bevor das sich ergebende einzelne Ergebnis von den Operatoren außerhalb der Klammern verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="c0f04-129">Everything within parentheses is evaluated first to yield a single result before that result can be used by any operator outside the parentheses.</span></span> <span data-ttu-id="c0f04-130">Beispielsweise `x+y*z` multipliziert `y` mit `z` und fügt dann hinzu `x` , fügt jedoch `(x+y)*z` `x` zu `y` und multipliziert das Ergebnis mit `z` .</span><span class="sxs-lookup"><span data-stu-id="c0f04-130">For example, `x+y*z` multiplies `y` by `z` and then adds `x`, but `(x+y)*z` adds `x` to `y` and then multiplies the result by `z`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0f04-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c0f04-131">See also</span></span>

- [<span data-ttu-id="c0f04-132">Übersicht über Entity SQL</span><span class="sxs-lookup"><span data-stu-id="c0f04-132">Entity SQL Overview</span></span>](entity-sql-overview.md)
