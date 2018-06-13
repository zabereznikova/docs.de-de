---
title: Take While-Klausel (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryTakeWhile
helpviewer_keywords:
- queries [Visual Basic], Take While
- Take While clause [Visual Basic]
- Take While statement [Visual Basic]
ms.assetid: db8f9f2f-fc9f-4a6c-b0b8-1bf048147e11
ms.openlocfilehash: 7e0a6bd77ca2594e9d74e669fcd9cddf91ee1cad
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33600899"
---
# <a name="take-while-clause-visual-basic"></a><span data-ttu-id="c0a5a-102">Take While-Klausel (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c0a5a-102">Take While Clause (Visual Basic)</span></span>
<span data-ttu-id="c0a5a-103">Gibt Elemente in einer Auflistung zurück, solange eine angegebene Bedingung `true` ist, und überspringt dann die übrigen Elemente.</span><span class="sxs-lookup"><span data-stu-id="c0a5a-103">Includes elements in a collection as long as a specified condition is `true` and bypasses the remaining elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0a5a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c0a5a-104">Syntax</span></span>  
  
```  
Take While expression  
```  
  
## <a name="parts"></a><span data-ttu-id="c0a5a-105">Teile</span><span class="sxs-lookup"><span data-stu-id="c0a5a-105">Parts</span></span>  
  
|<span data-ttu-id="c0a5a-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="c0a5a-106">Term</span></span>|<span data-ttu-id="c0a5a-107">Definition</span><span class="sxs-lookup"><span data-stu-id="c0a5a-107">Definition</span></span>|  
|---|---|  
|`expression`|<span data-ttu-id="c0a5a-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c0a5a-108">Required.</span></span> <span data-ttu-id="c0a5a-109">Ein Ausdruck, der eine zu testende Bedingung an Elementen für darstellt.</span><span class="sxs-lookup"><span data-stu-id="c0a5a-109">An expression that represents a condition to test elements for.</span></span> <span data-ttu-id="c0a5a-110">Der Ausdruck muss zurückgeben eine `Boolean` Wert oder eine funktionell gleichwertig, wie z. B. ein `Integer` als ausgewertet werden eine `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="c0a5a-110">The expression must return a `Boolean` value or a functional equivalent, such as an `Integer` to be evaluated as a `Boolean`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c0a5a-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c0a5a-111">Remarks</span></span>  
 <span data-ttu-id="c0a5a-112">Die `Take While` -Klausel enthält Elemente vom Beginn eines Abfrageergebnisses, bis die angegebene `expression` gibt `false`.</span><span class="sxs-lookup"><span data-stu-id="c0a5a-112">The `Take While` clause includes elements from the start of a query result until the supplied `expression` returns `false`.</span></span> <span data-ttu-id="c0a5a-113">Nach der `expression` gibt `false`, die Abfrage werden alle verbleibenden Elemente zu umgehen.</span><span class="sxs-lookup"><span data-stu-id="c0a5a-113">After the `expression` returns `false`, the query will bypass all remaining elements.</span></span> <span data-ttu-id="c0a5a-114">Die `expression` wird für die restlichen Ergebnisse ignoriert.</span><span class="sxs-lookup"><span data-stu-id="c0a5a-114">The `expression` is ignored for the remaining results.</span></span>  
  
 <span data-ttu-id="c0a5a-115">Die `Take While` Klausel unterscheidet sich von der `Where` -Klausel, die die `Where` -Klausel kann verwendet werden, um alle Elemente aus einer Abfrage enthalten, die eine bestimmte Bedingung erfüllen.</span><span class="sxs-lookup"><span data-stu-id="c0a5a-115">The `Take While` clause differs from the `Where` clause in that the `Where` clause can be used to include all elements from a query that meet a particular condition.</span></span> <span data-ttu-id="c0a5a-116">Die `Take While` -Klausel enthält Elemente nur bis zum ersten Mal, die die Bedingung nicht erfüllt wird.</span><span class="sxs-lookup"><span data-stu-id="c0a5a-116">The `Take While` clause includes elements only until the first time that the condition is not satisfied.</span></span> <span data-ttu-id="c0a5a-117">Die `Take While` -Klausel ist besonders hilfreich bei der Arbeit mit einer sortierten Abfrageergebnis.</span><span class="sxs-lookup"><span data-stu-id="c0a5a-117">The `Take While` clause is most useful when you are working with an ordered query result.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c0a5a-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c0a5a-118">Example</span></span>  
 <span data-ttu-id="c0a5a-119">Im folgenden Codebeispiel wird mit der `Take While` -Klausel, um die Ergebnisse abzurufen, bis die erste Kunden ohne Bestellungen gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="c0a5a-119">The following code example uses the `Take While` clause to retrieve results until the first customer without any orders is found.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#2](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/take-while-clause_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="c0a5a-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c0a5a-120">See Also</span></span>  
 [<span data-ttu-id="c0a5a-121">Einführung in LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c0a5a-121">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [<span data-ttu-id="c0a5a-122">Abfragen</span><span class="sxs-lookup"><span data-stu-id="c0a5a-122">Queries</span></span>](../../../visual-basic/language-reference/queries/queries.md)  
 [<span data-ttu-id="c0a5a-123">Select-Klausel</span><span class="sxs-lookup"><span data-stu-id="c0a5a-123">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)  
 [<span data-ttu-id="c0a5a-124">From-Klausel</span><span class="sxs-lookup"><span data-stu-id="c0a5a-124">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)  
 [<span data-ttu-id="c0a5a-125">Take-Klausel</span><span class="sxs-lookup"><span data-stu-id="c0a5a-125">Take Clause</span></span>](../../../visual-basic/language-reference/queries/take-clause.md)  
 [<span data-ttu-id="c0a5a-126">Skip While-Klausel</span><span class="sxs-lookup"><span data-stu-id="c0a5a-126">Skip While Clause</span></span>](../../../visual-basic/language-reference/queries/skip-while-clause.md)  
 [<span data-ttu-id="c0a5a-127">Where-Klausel</span><span class="sxs-lookup"><span data-stu-id="c0a5a-127">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
