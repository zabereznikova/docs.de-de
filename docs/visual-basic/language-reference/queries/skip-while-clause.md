---
title: SkipWhile-Klausel
ms.date: 07/20/2015
f1_keywords:
- vb.QuerySkipWhile
helpviewer_keywords:
- Skip While statement [Visual Basic]
- Skip While clause [Visual Basic]
- queries [Visual Basic], Skip While
ms.assetid: 5dee8350-7520-4f1a-b00d-590cacd572d6
ms.openlocfilehash: b357320a92ace1b7a261991737ed653d54d0eeab
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84359644"
---
# <a name="skip-while-clause-visual-basic"></a><span data-ttu-id="0eee1-102">Skip While-Klausel (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0eee1-102">Skip While Clause (Visual Basic)</span></span>
<span data-ttu-id="0eee1-103">Überspringt Elemente in einer Auflistung, solange eine angegebene Bedingung `true` ist, und gibt anschließend die übrigen Elemente zurück.</span><span class="sxs-lookup"><span data-stu-id="0eee1-103">Bypasses elements in a collection as long as a specified condition is `true` and then returns the remaining elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0eee1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0eee1-104">Syntax</span></span>  
  
```vb  
Skip While expression  
```  
  
## <a name="parts"></a><span data-ttu-id="0eee1-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="0eee1-105">Parts</span></span>  
  
|<span data-ttu-id="0eee1-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="0eee1-106">Term</span></span>|<span data-ttu-id="0eee1-107">Definition</span><span class="sxs-lookup"><span data-stu-id="0eee1-107">Definition</span></span>|  
|---|---|  
|`expression`|<span data-ttu-id="0eee1-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0eee1-108">Required.</span></span> <span data-ttu-id="0eee1-109">Ein Ausdruck, der eine Bedingung darstellt, für die Elemente getestet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="0eee1-109">An expression that represents a condition to test elements for.</span></span> <span data-ttu-id="0eee1-110">Der Ausdruck muss einen `Boolean` Wert oder eine funktionale Entsprechung zurückgeben, z. b. eine, die `Integer` als ausgewertet wird `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="0eee1-110">The expression must return a `Boolean` value or a functional equivalent, such as an `Integer` to be evaluated as a `Boolean`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0eee1-111">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="0eee1-111">Remarks</span></span>  
 <span data-ttu-id="0eee1-112">Die- `Skip While` Klausel umgeht Elemente vom Anfang eines Abfrage Ergebnisses, bis der angegebene `expression` zurückgibt `false` .</span><span class="sxs-lookup"><span data-stu-id="0eee1-112">The `Skip While` clause bypasses elements from the beginning of a query result until the supplied `expression` returns `false`.</span></span> <span data-ttu-id="0eee1-113">Nachdem `expression` zurückgegeben `false` wurde, gibt die Abfrage alle verbleibenden Elemente zurück.</span><span class="sxs-lookup"><span data-stu-id="0eee1-113">After `expression` returns `false`, the query returns all the remaining elements.</span></span> <span data-ttu-id="0eee1-114">Der `expression` wird für die restlichen Ergebnisse ignoriert.</span><span class="sxs-lookup"><span data-stu-id="0eee1-114">The `expression` is ignored for the remaining results.</span></span>  
  
 <span data-ttu-id="0eee1-115">Die- `Skip While` Klausel unterscheidet sich von der- `Where` Klausel darin, dass die- `Where` Klausel verwendet werden kann, um alle Elemente aus einer Abfrage auszuschließen, die eine bestimmte Bedingung nicht erfüllen.</span><span class="sxs-lookup"><span data-stu-id="0eee1-115">The `Skip While` clause differs from the `Where` clause in that the `Where` clause can be used to exclude all elements from a query that do not meet a particular condition.</span></span> <span data-ttu-id="0eee1-116">Die- `Skip While` Klausel schließt Elemente nur dann aus, wenn die Bedingung zum ersten Mal nicht erfüllt wird.</span><span class="sxs-lookup"><span data-stu-id="0eee1-116">The `Skip While` clause excludes elements only until the first time that the condition is not satisfied.</span></span> <span data-ttu-id="0eee1-117">Die- `Skip While` Klausel ist besonders nützlich, wenn Sie mit einem geordneten Abfrageergebnis arbeiten.</span><span class="sxs-lookup"><span data-stu-id="0eee1-117">The `Skip While` clause is most useful when you are working with an ordered query result.</span></span>  
  
 <span data-ttu-id="0eee1-118">Sie können eine bestimmte Anzahl von Ergebnissen ab dem Anfang eines Abfrage Ergebnisses umgehen, indem Sie die- `Skip` Klausel verwenden.</span><span class="sxs-lookup"><span data-stu-id="0eee1-118">You can bypass a specific number of results from the beginning of a query result by using the `Skip` clause.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0eee1-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0eee1-119">Example</span></span>  
 <span data-ttu-id="0eee1-120">Im folgenden Codebeispiel wird die- `Skip While` Klausel verwendet, um die Ergebnisse zu umgehen, bis der erste Kunde aus der USA gefunden wurde.</span><span class="sxs-lookup"><span data-stu-id="0eee1-120">The following code example uses the `Skip While` clause to bypass results until the first customer from the United States is found.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="0eee1-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0eee1-121">See also</span></span>

- [<span data-ttu-id="0eee1-122">Einführung in LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0eee1-122">Introduction to LINQ in Visual Basic</span></span>](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="0eee1-123">Abfragen</span><span class="sxs-lookup"><span data-stu-id="0eee1-123">Queries</span></span>](index.md)
- [<span data-ttu-id="0eee1-124">SELECT-Klausel</span><span class="sxs-lookup"><span data-stu-id="0eee1-124">Select Clause</span></span>](select-clause.md)
- [<span data-ttu-id="0eee1-125">From-Klausel</span><span class="sxs-lookup"><span data-stu-id="0eee1-125">From Clause</span></span>](from-clause.md)
- [<span data-ttu-id="0eee1-126">Skip-Klausel</span><span class="sxs-lookup"><span data-stu-id="0eee1-126">Skip Clause</span></span>](skip-clause.md)
- [<span data-ttu-id="0eee1-127">TakeWhile-Klausel</span><span class="sxs-lookup"><span data-stu-id="0eee1-127">Take While Clause</span></span>](take-while-clause.md)
- [<span data-ttu-id="0eee1-128">WHERE-Klausel</span><span class="sxs-lookup"><span data-stu-id="0eee1-128">Where Clause</span></span>](where-clause.md)
