---
title: Skip While-Klausel (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.QuerySkipWhile
helpviewer_keywords:
- Skip While statement [Visual Basic]
- Skip While clause [Visual Basic]
- queries [Visual Basic], Skip While
ms.assetid: 5dee8350-7520-4f1a-b00d-590cacd572d6
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f447a6d9b2eb58fa546ced6c96b987caf68fb3e5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="skip-while-clause-visual-basic"></a><span data-ttu-id="b7a67-102">Skip While-Klausel (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b7a67-102">Skip While Clause (Visual Basic)</span></span>
<span data-ttu-id="b7a67-103">Überspringt Elemente in einer Auflistung, solange eine angegebene Bedingung `true` ist, und gibt anschließend die übrigen Elemente zurück.</span><span class="sxs-lookup"><span data-stu-id="b7a67-103">Bypasses elements in a collection as long as a specified condition is `true` and then returns the remaining elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7a67-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b7a67-104">Syntax</span></span>  
  
```  
Skip While expression  
```  
  
## <a name="parts"></a><span data-ttu-id="b7a67-105">Teile</span><span class="sxs-lookup"><span data-stu-id="b7a67-105">Parts</span></span>  
  
|<span data-ttu-id="b7a67-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="b7a67-106">Term</span></span>|<span data-ttu-id="b7a67-107">Definition</span><span class="sxs-lookup"><span data-stu-id="b7a67-107">Definition</span></span>|  
|---|---|  
|`expression`|<span data-ttu-id="b7a67-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b7a67-108">Required.</span></span> <span data-ttu-id="b7a67-109">Ein Ausdruck, der eine zu testende Bedingung an Elementen für darstellt.</span><span class="sxs-lookup"><span data-stu-id="b7a67-109">An expression that represents a condition to test elements for.</span></span> <span data-ttu-id="b7a67-110">Der Ausdruck muss zurückgeben eine `Boolean` Wert oder eine funktionell gleichwertig, wie z. B. ein `Integer` als ausgewertet werden eine `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="b7a67-110">The expression must return a `Boolean` value or a functional equivalent, such as an `Integer` to be evaluated as a `Boolean`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b7a67-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b7a67-111">Remarks</span></span>  
 <span data-ttu-id="b7a67-112">Die `Skip While` Klausel umgeht Elemente vom Anfang bis zum angegebenen eines Abfrageergebnisses `expression` gibt `false`.</span><span class="sxs-lookup"><span data-stu-id="b7a67-112">The `Skip While` clause bypasses elements from the beginning of a query result until the supplied `expression` returns `false`.</span></span> <span data-ttu-id="b7a67-113">Nach dem `expression` gibt `false`, die Abfrage gibt alle übrigen Elemente zurück.</span><span class="sxs-lookup"><span data-stu-id="b7a67-113">After `expression` returns `false`, the query returns all the remaining elements.</span></span> <span data-ttu-id="b7a67-114">Die `expression` wird für die restlichen Ergebnisse ignoriert.</span><span class="sxs-lookup"><span data-stu-id="b7a67-114">The `expression` is ignored for the remaining results.</span></span>  
  
 <span data-ttu-id="b7a67-115">Die `Skip While` Klausel unterscheidet sich von der `Where` -Klausel, die die `Where` -Klausel kann verwendet werden, sollen alle Elemente aus einer Abfrage, die nicht auf eine bestimmte Bedingung erfüllen.</span><span class="sxs-lookup"><span data-stu-id="b7a67-115">The `Skip While` clause differs from the `Where` clause in that the `Where` clause can be used to exclude all elements from a query that do not meet a particular condition.</span></span> <span data-ttu-id="b7a67-116">Die `Skip While` -Klausel schließt Elemente nur bis zum ersten Mal, die die Bedingung nicht erfüllt wird.</span><span class="sxs-lookup"><span data-stu-id="b7a67-116">The `Skip While` clause excludes elements only until the first time that the condition is not satisfied.</span></span> <span data-ttu-id="b7a67-117">Die `Skip While` -Klausel ist besonders hilfreich bei der Arbeit mit einer sortierten Abfrageergebnis.</span><span class="sxs-lookup"><span data-stu-id="b7a67-117">The `Skip While` clause is most useful when you are working with an ordered query result.</span></span>  
  
 <span data-ttu-id="b7a67-118">Sie können eine bestimmte Anzahl von Ergebnissen zu Beginn eines Abfrageergebnisses umgehen, indem Sie mit der `Skip` Klausel.</span><span class="sxs-lookup"><span data-stu-id="b7a67-118">You can bypass a specific number of results from the beginning of a query result by using the `Skip` clause.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b7a67-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b7a67-119">Example</span></span>  
 <span data-ttu-id="b7a67-120">Im folgenden Codebeispiel wird mit der `Skip While` -Klausel, um Ergebnisse zu umgehen, bis die erste Kunden aus den USA gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="b7a67-120">The following code example uses the `Skip While` clause to bypass results until the first customer from the United States is found.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#3](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/skip-while-clause_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="b7a67-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b7a67-121">See Also</span></span>  
 [<span data-ttu-id="b7a67-122">Einführung in LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b7a67-122">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [<span data-ttu-id="b7a67-123">Abfragen</span><span class="sxs-lookup"><span data-stu-id="b7a67-123">Queries</span></span>](../../../visual-basic/language-reference/queries/queries.md)  
 [<span data-ttu-id="b7a67-124">Select-Klausel</span><span class="sxs-lookup"><span data-stu-id="b7a67-124">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)  
 [<span data-ttu-id="b7a67-125">From-Klausel</span><span class="sxs-lookup"><span data-stu-id="b7a67-125">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)  
 [<span data-ttu-id="b7a67-126">Skip-Klausel</span><span class="sxs-lookup"><span data-stu-id="b7a67-126">Skip Clause</span></span>](../../../visual-basic/language-reference/queries/skip-clause.md)  
 [<span data-ttu-id="b7a67-127">Take While-Klausel</span><span class="sxs-lookup"><span data-stu-id="b7a67-127">Take While Clause</span></span>](../../../visual-basic/language-reference/queries/take-while-clause.md)  
 [<span data-ttu-id="b7a67-128">Where-Klausel</span><span class="sxs-lookup"><span data-stu-id="b7a67-128">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
