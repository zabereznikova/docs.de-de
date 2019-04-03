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
ms.openlocfilehash: 080a106fc1deeb54165511ed03d7c7c5d2060f21
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58818748"
---
# <a name="take-while-clause-visual-basic"></a><span data-ttu-id="376cd-102">Take While-Klausel (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="376cd-102">Take While Clause (Visual Basic)</span></span>
<span data-ttu-id="376cd-103">Gibt Elemente in einer Auflistung zurück, solange eine angegebene Bedingung `true` ist, und überspringt dann die übrigen Elemente.</span><span class="sxs-lookup"><span data-stu-id="376cd-103">Includes elements in a collection as long as a specified condition is `true` and bypasses the remaining elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="376cd-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="376cd-104">Syntax</span></span>  
  
```  
Take While expression  
```  
  
## <a name="parts"></a><span data-ttu-id="376cd-105">Teile</span><span class="sxs-lookup"><span data-stu-id="376cd-105">Parts</span></span>  
  
|<span data-ttu-id="376cd-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="376cd-106">Term</span></span>|<span data-ttu-id="376cd-107">Definition</span><span class="sxs-lookup"><span data-stu-id="376cd-107">Definition</span></span>|  
|---|---|  
|`expression`|<span data-ttu-id="376cd-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="376cd-108">Required.</span></span> <span data-ttu-id="376cd-109">Ein Ausdruck, der eine Bedingung zum Testen von Elementen für darstellt.</span><span class="sxs-lookup"><span data-stu-id="376cd-109">An expression that represents a condition to test elements for.</span></span> <span data-ttu-id="376cd-110">Der Ausdruck muss Zurückgeben einer `Boolean` Wert oder eine funktionale Entsprechung wie z. B. eine `Integer` als ausgewertet werden soll eine `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="376cd-110">The expression must return a `Boolean` value or a functional equivalent, such as an `Integer` to be evaluated as a `Boolean`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="376cd-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="376cd-111">Remarks</span></span>  
 <span data-ttu-id="376cd-112">Die `Take While` -Klausel enthält Elementen ab dem Anfang eines Abfrageergebnisses, bis die angegebene `expression` gibt `false`.</span><span class="sxs-lookup"><span data-stu-id="376cd-112">The `Take While` clause includes elements from the start of a query result until the supplied `expression` returns `false`.</span></span> <span data-ttu-id="376cd-113">Nach der `expression` gibt `false`, die Abfrage werden alle verbleibenden Elemente zu umgehen.</span><span class="sxs-lookup"><span data-stu-id="376cd-113">After the `expression` returns `false`, the query will bypass all remaining elements.</span></span> <span data-ttu-id="376cd-114">Die `expression` wird für die verbleibenden Ergebnisse ignoriert.</span><span class="sxs-lookup"><span data-stu-id="376cd-114">The `expression` is ignored for the remaining results.</span></span>  
  
 <span data-ttu-id="376cd-115">Die `Take While` Klausel unterscheidet sich von der `Where` -Klausel in, das die `Where` -Klausel kann verwendet werden, um alle Elemente aus einer Abfrage enthalten, die eine bestimmte Bedingung erfüllen.</span><span class="sxs-lookup"><span data-stu-id="376cd-115">The `Take While` clause differs from the `Where` clause in that the `Where` clause can be used to include all elements from a query that meet a particular condition.</span></span> <span data-ttu-id="376cd-116">Die `Take While` -Klausel enthält Elemente nur bis zum ersten Mal, die die Bedingung nicht erfüllt ist.</span><span class="sxs-lookup"><span data-stu-id="376cd-116">The `Take While` clause includes elements only until the first time that the condition is not satisfied.</span></span> <span data-ttu-id="376cd-117">Die `Take While` -Klausel ist besonders hilfreich, wenn Sie mit einer sortierten Abfrageergebnis arbeiten.</span><span class="sxs-lookup"><span data-stu-id="376cd-117">The `Take While` clause is most useful when you are working with an ordered query result.</span></span>  
  
## <a name="example"></a><span data-ttu-id="376cd-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="376cd-118">Example</span></span>  
 <span data-ttu-id="376cd-119">Im folgenden Codebeispiel wird die `Take While` -Klausel, um die Ergebnisse abzurufen, bis die erste Kunden ohne Bestellungen gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="376cd-119">The following code example uses the `Take While` clause to retrieve results until the first customer without any orders is found.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="376cd-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="376cd-120">See also</span></span>

- [<span data-ttu-id="376cd-121">Einführung in LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="376cd-121">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="376cd-122">Abfragen</span><span class="sxs-lookup"><span data-stu-id="376cd-122">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="376cd-123">Select-Klausel</span><span class="sxs-lookup"><span data-stu-id="376cd-123">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="376cd-124">From-Klausel</span><span class="sxs-lookup"><span data-stu-id="376cd-124">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="376cd-125">Take-Klausel</span><span class="sxs-lookup"><span data-stu-id="376cd-125">Take Clause</span></span>](../../../visual-basic/language-reference/queries/take-clause.md)
- [<span data-ttu-id="376cd-126">Skip While-Klausel</span><span class="sxs-lookup"><span data-stu-id="376cd-126">Skip While Clause</span></span>](../../../visual-basic/language-reference/queries/skip-while-clause.md)
- [<span data-ttu-id="376cd-127">Where-Klausel</span><span class="sxs-lookup"><span data-stu-id="376cd-127">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
