---
title: Operatorrangfolge (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e92e4ca5-2889-4266-9625-47f0eb01a948
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 537c9ae7c92c6abcbe597970f2b0ec29e399bc62
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="operator-precedence-entity-sql"></a><span data-ttu-id="e684d-102">Operatorrangfolge (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="e684d-102">Operator Precedence (Entity SQL)</span></span>
<span data-ttu-id="e684d-103">Wenn ein [!INCLUDE[esql](../../../../../../includes/esql-md.md)] Abfrage besitzt mehrere Operatoren, bestimmt die Operatorrangfolge die Reihenfolge, in der die Vorgänge ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="e684d-103">When an [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query has multiple operators, operator precedence determines the sequence in which the operations are performed.</span></span> <span data-ttu-id="e684d-104">Die Ausführungsreihenfolge kann sich entscheidend auf das Abfrageergebnis auswirken.</span><span class="sxs-lookup"><span data-stu-id="e684d-104">The order of execution can significantly affect the query result.</span></span>  
  
 <span data-ttu-id="e684d-105">Operatoren besitzen die in der folgenden Tabelle dargestellte Rangfolge.</span><span class="sxs-lookup"><span data-stu-id="e684d-105">Operators have the precedence levels shown in the following table.</span></span> <span data-ttu-id="e684d-106">Ein Operator, der höher in der Rangfolge steht, wird vor einem Operator niedrigeren Ranges ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="e684d-106">An operator with a higher level is evaluated before an operator with a lower level.</span></span>  
  
|<span data-ttu-id="e684d-107">Ebene</span><span class="sxs-lookup"><span data-stu-id="e684d-107">Level</span></span>|<span data-ttu-id="e684d-108">Operationstyp</span><span class="sxs-lookup"><span data-stu-id="e684d-108">Operation type</span></span>|<span data-ttu-id="e684d-109">Operator</span><span class="sxs-lookup"><span data-stu-id="e684d-109">Operator</span></span>|  
|-----------|--------------------|--------------|  
|<span data-ttu-id="e684d-110">1</span><span class="sxs-lookup"><span data-stu-id="e684d-110">1</span></span>|<span data-ttu-id="e684d-111">Primär</span><span class="sxs-lookup"><span data-stu-id="e684d-111">Primary</span></span>|`. , [] ()`|  
|<span data-ttu-id="e684d-112">2</span><span class="sxs-lookup"><span data-stu-id="e684d-112">2</span></span>|<span data-ttu-id="e684d-113">Unär</span><span class="sxs-lookup"><span data-stu-id="e684d-113">Unary</span></span>|`! not`|  
|<span data-ttu-id="e684d-114">3</span><span class="sxs-lookup"><span data-stu-id="e684d-114">3</span></span>|<span data-ttu-id="e684d-115">Multiplikativ</span><span class="sxs-lookup"><span data-stu-id="e684d-115">Multiplicative</span></span>|`* / %`|  
|<span data-ttu-id="e684d-116">4</span><span class="sxs-lookup"><span data-stu-id="e684d-116">4</span></span>|<span data-ttu-id="e684d-117">Additiv</span><span class="sxs-lookup"><span data-stu-id="e684d-117">Additive</span></span>|`+ -`|  
|<span data-ttu-id="e684d-118">5</span><span class="sxs-lookup"><span data-stu-id="e684d-118">5</span></span>|<span data-ttu-id="e684d-119">Sortieren</span><span class="sxs-lookup"><span data-stu-id="e684d-119">Ordering</span></span>|`< > <= >=`|  
|<span data-ttu-id="e684d-120">6</span><span class="sxs-lookup"><span data-stu-id="e684d-120">6</span></span>|<span data-ttu-id="e684d-121">Gleichheit</span><span class="sxs-lookup"><span data-stu-id="e684d-121">Equality</span></span>|`= != <>`|  
|<span data-ttu-id="e684d-122">7</span><span class="sxs-lookup"><span data-stu-id="e684d-122">7</span></span>|<span data-ttu-id="e684d-123">Bedingtes AND</span><span class="sxs-lookup"><span data-stu-id="e684d-123">Conditional AND</span></span>|`and &&`|  
|<span data-ttu-id="e684d-124">8</span><span class="sxs-lookup"><span data-stu-id="e684d-124">8</span></span>|<span data-ttu-id="e684d-125">Bedingtes OR</span><span class="sxs-lookup"><span data-stu-id="e684d-125">Conditional OR</span></span>|`or &#124;&#124;`|  
  
 <span data-ttu-id="e684d-126">Verfügen zwei Operatoren in einem Ausdruck über die gleiche Rangstufe, werden sie von links nach rechts, ausgehend von ihrer Position innerhalb der Abfrage, ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="e684d-126">When two operators in an expression have the same operator precedence level, they are evaluated left to right, based on their position in the query.</span></span> <span data-ttu-id="e684d-127">`x+y-z` wird beispielsweise als `(x+y)-z` ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="e684d-127">For example, `x+y-z` is evaluated as `(x+y)-z`.</span></span>  
  
 <span data-ttu-id="e684d-128">Mit Klammern kann die definierte Rangfolge von Operatoren in einer Abfrage außer Kraft gesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="e684d-128">You can use parentheses to override the defined precedence of the operators in a query.</span></span> <span data-ttu-id="e684d-129">Die Operatoren innerhalb der Klammern werden zuerst ausgewertet, bevor das sich ergebende einzelne Ergebnis von den Operatoren außerhalb der Klammern verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="e684d-129">Everything within parentheses is evaluated first to yield a single result before that result can be used by any operator outside the parentheses.</span></span> <span data-ttu-id="e684d-130">Beispielsweise `x+y*z` multipliziert `y` von `z` und fügt dann `x`, aber `(x+y)*z` fügt `x` auf `y` und multipliziert dann das Ergebnis von `z`.</span><span class="sxs-lookup"><span data-stu-id="e684d-130">For example, `x+y*z` multiplies `y` by `z` and then adds `x`, but `(x+y)*z` adds `x` to `y` and then multiplies the result by `z`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e684d-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e684d-131">See Also</span></span>  
 [<span data-ttu-id="e684d-132">Übersicht über Entity SQL</span><span class="sxs-lookup"><span data-stu-id="e684d-132">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
