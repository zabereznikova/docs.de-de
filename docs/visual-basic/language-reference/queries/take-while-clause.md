---
title: Take While-Klausel
ms.date: 07/20/2015
f1_keywords:
- vb.QueryTakeWhile
helpviewer_keywords:
- queries [Visual Basic], Take While
- Take While clause [Visual Basic]
- Take While statement [Visual Basic]
ms.assetid: db8f9f2f-fc9f-4a6c-b0b8-1bf048147e11
ms.openlocfilehash: 23b7c84a9f896161a66059fcb1f30753d3b863d5
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347108"
---
# <a name="take-while-clause-visual-basic"></a><span data-ttu-id="9f26f-102">Take While-Klausel (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9f26f-102">Take While Clause (Visual Basic)</span></span>
<span data-ttu-id="9f26f-103">Gibt Elemente in einer Auflistung zurück, solange eine angegebene Bedingung `true` ist, und überspringt dann die übrigen Elemente.</span><span class="sxs-lookup"><span data-stu-id="9f26f-103">Includes elements in a collection as long as a specified condition is `true` and bypasses the remaining elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f26f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9f26f-104">Syntax</span></span>  
  
```vb  
Take While expression  
```  
  
## <a name="parts"></a><span data-ttu-id="9f26f-105">-Komponenten</span><span class="sxs-lookup"><span data-stu-id="9f26f-105">Parts</span></span>  
  
|<span data-ttu-id="9f26f-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="9f26f-106">Term</span></span>|<span data-ttu-id="9f26f-107">Definition</span><span class="sxs-lookup"><span data-stu-id="9f26f-107">Definition</span></span>|  
|---|---|  
|`expression`|<span data-ttu-id="9f26f-108">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="9f26f-108">Required.</span></span> <span data-ttu-id="9f26f-109">Ein Ausdruck, der eine Bedingung darstellt, für die Elemente getestet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="9f26f-109">An expression that represents a condition to test elements for.</span></span> <span data-ttu-id="9f26f-110">Der Ausdruck muss einen `Boolean` Wert oder eine funktionale Entsprechung zurückgeben, z. b. eine `Integer`, die als `Boolean`ausgewertet werden soll.</span><span class="sxs-lookup"><span data-stu-id="9f26f-110">The expression must return a `Boolean` value or a functional equivalent, such as an `Integer` to be evaluated as a `Boolean`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9f26f-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9f26f-111">Remarks</span></span>  
 <span data-ttu-id="9f26f-112">Die `Take While`-Klausel schließt Elemente vom Anfang eines Abfrage Ergebnisses ein, bis die angegebene `expression` `false`zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="9f26f-112">The `Take While` clause includes elements from the start of a query result until the supplied `expression` returns `false`.</span></span> <span data-ttu-id="9f26f-113">Nachdem die `expression` `false`zurückgegeben hat, werden alle verbleibenden Elemente von der Abfrage umgangen.</span><span class="sxs-lookup"><span data-stu-id="9f26f-113">After the `expression` returns `false`, the query will bypass all remaining elements.</span></span> <span data-ttu-id="9f26f-114">Der `expression` wird für die restlichen Ergebnisse ignoriert.</span><span class="sxs-lookup"><span data-stu-id="9f26f-114">The `expression` is ignored for the remaining results.</span></span>  
  
 <span data-ttu-id="9f26f-115">Die `Take While`-Klausel unterscheidet sich von der `Where`-Klausel darin, dass die `Where`-Klausel verwendet werden kann, um alle Elemente aus einer Abfrage aufzunehmen, die eine bestimmte Bedingung erfüllen.</span><span class="sxs-lookup"><span data-stu-id="9f26f-115">The `Take While` clause differs from the `Where` clause in that the `Where` clause can be used to include all elements from a query that meet a particular condition.</span></span> <span data-ttu-id="9f26f-116">Die `Take While`-Klausel enthält Elemente nur bis zum ersten Mal, wenn die Bedingung nicht erfüllt wird.</span><span class="sxs-lookup"><span data-stu-id="9f26f-116">The `Take While` clause includes elements only until the first time that the condition is not satisfied.</span></span> <span data-ttu-id="9f26f-117">Die `Take While`-Klausel ist besonders nützlich, wenn Sie mit einem geordneten Abfrageergebnis arbeiten.</span><span class="sxs-lookup"><span data-stu-id="9f26f-117">The `Take While` clause is most useful when you are working with an ordered query result.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9f26f-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9f26f-118">Example</span></span>  
 <span data-ttu-id="9f26f-119">Im folgenden Codebeispiel wird die `Take While`-Klausel verwendet, um die Ergebnisse abzurufen, bis der erste Kunde ohne Bestellungen gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="9f26f-119">The following code example uses the `Take While` clause to retrieve results until the first customer without any orders is found.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="9f26f-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9f26f-120">See also</span></span>

- [<span data-ttu-id="9f26f-121">Einführung in LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9f26f-121">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="9f26f-122">Abfragen</span><span class="sxs-lookup"><span data-stu-id="9f26f-122">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="9f26f-123">Select-Klausel</span><span class="sxs-lookup"><span data-stu-id="9f26f-123">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="9f26f-124">From-Klausel</span><span class="sxs-lookup"><span data-stu-id="9f26f-124">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="9f26f-125">Take-Klausel</span><span class="sxs-lookup"><span data-stu-id="9f26f-125">Take Clause</span></span>](../../../visual-basic/language-reference/queries/take-clause.md)
- [<span data-ttu-id="9f26f-126">Skip While-Klausel</span><span class="sxs-lookup"><span data-stu-id="9f26f-126">Skip While Clause</span></span>](../../../visual-basic/language-reference/queries/skip-while-clause.md)
- [<span data-ttu-id="9f26f-127">Where-Klausel</span><span class="sxs-lookup"><span data-stu-id="9f26f-127">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
