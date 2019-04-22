---
title: Skip While-Klausel (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QuerySkipWhile
helpviewer_keywords:
- Skip While statement [Visual Basic]
- Skip While clause [Visual Basic]
- queries [Visual Basic], Skip While
ms.assetid: 5dee8350-7520-4f1a-b00d-590cacd572d6
ms.openlocfilehash: 3d6caeb1938e8e53e8ec2575f740cd5e49496f62
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58839898"
---
# <a name="skip-while-clause-visual-basic"></a><span data-ttu-id="98785-102">Skip While-Klausel (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="98785-102">Skip While Clause (Visual Basic)</span></span>
<span data-ttu-id="98785-103">Überspringt Elemente in einer Auflistung, solange eine angegebene Bedingung `true` ist, und gibt anschließend die übrigen Elemente zurück.</span><span class="sxs-lookup"><span data-stu-id="98785-103">Bypasses elements in a collection as long as a specified condition is `true` and then returns the remaining elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98785-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="98785-104">Syntax</span></span>  
  
```  
Skip While expression  
```  
  
## <a name="parts"></a><span data-ttu-id="98785-105">Teile</span><span class="sxs-lookup"><span data-stu-id="98785-105">Parts</span></span>  
  
|<span data-ttu-id="98785-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="98785-106">Term</span></span>|<span data-ttu-id="98785-107">Definition</span><span class="sxs-lookup"><span data-stu-id="98785-107">Definition</span></span>|  
|---|---|  
|`expression`|<span data-ttu-id="98785-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="98785-108">Required.</span></span> <span data-ttu-id="98785-109">Ein Ausdruck, der eine Bedingung zum Testen von Elementen für darstellt.</span><span class="sxs-lookup"><span data-stu-id="98785-109">An expression that represents a condition to test elements for.</span></span> <span data-ttu-id="98785-110">Der Ausdruck muss Zurückgeben einer `Boolean` Wert oder eine funktionale Entsprechung wie z. B. eine `Integer` als ausgewertet werden soll eine `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="98785-110">The expression must return a `Boolean` value or a functional equivalent, such as an `Integer` to be evaluated as a `Boolean`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="98785-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="98785-111">Remarks</span></span>  
 <span data-ttu-id="98785-112">Die `Skip While` -Klausel werden die Elemente am Anfang eines Abfrageergebnisses, bis die angegebene `expression` gibt `false`.</span><span class="sxs-lookup"><span data-stu-id="98785-112">The `Skip While` clause bypasses elements from the beginning of a query result until the supplied `expression` returns `false`.</span></span> <span data-ttu-id="98785-113">Nach dem `expression` gibt `false`, die Abfrage gibt alle übrigen Elemente zurück.</span><span class="sxs-lookup"><span data-stu-id="98785-113">After `expression` returns `false`, the query returns all the remaining elements.</span></span> <span data-ttu-id="98785-114">Die `expression` wird für die verbleibenden Ergebnisse ignoriert.</span><span class="sxs-lookup"><span data-stu-id="98785-114">The `expression` is ignored for the remaining results.</span></span>  
  
 <span data-ttu-id="98785-115">Die `Skip While` Klausel unterscheidet sich von der `Where` -Klausel in, das die `Where` Klausel kann verwendet werden, um alle Elemente aus einer Abfrage, die eine bestimmte Bedingung nicht erfüllen ausgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="98785-115">The `Skip While` clause differs from the `Where` clause in that the `Where` clause can be used to exclude all elements from a query that do not meet a particular condition.</span></span> <span data-ttu-id="98785-116">Die `Skip While` -Klausel schließt Weitere Elemente nur bis zum ersten Mal, die die Bedingung nicht erfüllt ist.</span><span class="sxs-lookup"><span data-stu-id="98785-116">The `Skip While` clause excludes elements only until the first time that the condition is not satisfied.</span></span> <span data-ttu-id="98785-117">Die `Skip While` -Klausel ist besonders hilfreich, wenn Sie mit einer sortierten Abfrageergebnis arbeiten.</span><span class="sxs-lookup"><span data-stu-id="98785-117">The `Skip While` clause is most useful when you are working with an ordered query result.</span></span>  
  
 <span data-ttu-id="98785-118">Sie können eine bestimmte Anzahl von Ergebnissen zu Beginn eines Abfrageergebnisses umgehen, indem Sie mit der `Skip` Klausel.</span><span class="sxs-lookup"><span data-stu-id="98785-118">You can bypass a specific number of results from the beginning of a query result by using the `Skip` clause.</span></span>  
  
## <a name="example"></a><span data-ttu-id="98785-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="98785-119">Example</span></span>  
 <span data-ttu-id="98785-120">Im folgenden Codebeispiel wird die `Skip While` -Klausel, um Ergebnisse zu umgehen, bis der erste Kunde aus den Vereinigten Staaten gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="98785-120">The following code example uses the `Skip While` clause to bypass results until the first customer from the United States is found.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="98785-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="98785-121">See also</span></span>

- [<span data-ttu-id="98785-122">Einführung in LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="98785-122">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="98785-123">Abfragen</span><span class="sxs-lookup"><span data-stu-id="98785-123">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="98785-124">Select-Klausel</span><span class="sxs-lookup"><span data-stu-id="98785-124">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="98785-125">From-Klausel</span><span class="sxs-lookup"><span data-stu-id="98785-125">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="98785-126">Skip-Klausel</span><span class="sxs-lookup"><span data-stu-id="98785-126">Skip Clause</span></span>](../../../visual-basic/language-reference/queries/skip-clause.md)
- [<span data-ttu-id="98785-127">Take While-Klausel</span><span class="sxs-lookup"><span data-stu-id="98785-127">Take While Clause</span></span>](../../../visual-basic/language-reference/queries/take-while-clause.md)
- [<span data-ttu-id="98785-128">Where-Klausel</span><span class="sxs-lookup"><span data-stu-id="98785-128">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
