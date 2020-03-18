---
title: Zurückgeben einer Abfrage aus einer Methode
description: Vorgehensweise zum Zurückgeben einer Abfrage aus einer Methode.
ms.date: 11/30/2016
ms.assetid: db220f79-c35b-41f2-886c-cd068672d42d
ms.openlocfilehash: 1df533770f76301432b104d6f8398f1687750cce
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "73972513"
---
# <a name="how-to-return-a-query-from-a-method-c-programming-guide"></a><span data-ttu-id="33dc3-103">Gewusst wie: Zurückgeben einer Abfrage aus einer Methode (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="33dc3-103">How to return a query from a method (C# Programming Guide)</span></span>
<span data-ttu-id="33dc3-104">In diesem Beispiel wird gezeigt, wie Sie eine Abfrage aus einer Methode als Rückgabewert oder `out`-Parameter zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="33dc3-104">This example shows how to return a query from a method as the return value and as an `out` parameter.</span></span>  
  
 <span data-ttu-id="33dc3-105">Abfrageobjekte sind zusammensetzbar, das bedeutet, dass Sie eine Abfrage aus einer Methode zurückgeben können.</span><span class="sxs-lookup"><span data-stu-id="33dc3-105">Query objects are composable, meaning that you can return a query from a method.</span></span> <span data-ttu-id="33dc3-106">Objekte, die Abfragen darstellen, speichern nicht die resultierende Auflistung, sondern bei Bedarf die Schritte zum Erzeugen der Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="33dc3-106">Objects that represent queries do not store the resulting collection, but rather the steps to produce the results when needed.</span></span> <span data-ttu-id="33dc3-107">Der Vorteil des Zurückgebens von Abfrageobjekten aus Methoden ist, dass diese weiter zusammengesetzt oder geändert werden können.</span><span class="sxs-lookup"><span data-stu-id="33dc3-107">The advantage of returning query objects from methods is that they can be further composed or modified.</span></span> <span data-ttu-id="33dc3-108">Daher muss ein Rückgabewert oder ein `out`-Parameter einer Methode, die eine Abfrage zurückgibt, über diesen Typ verfügen.</span><span class="sxs-lookup"><span data-stu-id="33dc3-108">Therefore any return value or `out` parameter of a method that returns a query must also have that type.</span></span> <span data-ttu-id="33dc3-109">Wenn eine Methode eine Abfrage in einen konkreten <xref:System.Collections.Generic.List%601>- oder <xref:System.Array>-Typ materialisiert, wird sie als Methode betrachtet, die die Abfrageergebnisse zurückgibt, nicht die Abfrage selbst.</span><span class="sxs-lookup"><span data-stu-id="33dc3-109">If a method materializes a query into a concrete <xref:System.Collections.Generic.List%601> or <xref:System.Array> type, it is considered to be returning the query results instead of the query itself.</span></span> <span data-ttu-id="33dc3-110">Eine Abfragevariable, die aus einer Methode zurückgegeben wird, kann noch zusammengesetzt oder geändert werden.</span><span class="sxs-lookup"><span data-stu-id="33dc3-110">A query variable that is returned from a method can still be composed or modified.</span></span>  
  
## <a name="example"></a><span data-ttu-id="33dc3-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="33dc3-111">Example</span></span>  
 <span data-ttu-id="33dc3-112">Im folgenden Beispiel gibt die erste Methode eine Abfrage als Rückgabewert zurück. Die zweite Methode gibt eine Abfrage als `out`-Parameter zurück.</span><span class="sxs-lookup"><span data-stu-id="33dc3-112">In the following example, the first method returns a query as a return value, and the second method returns a query as an `out` parameter.</span></span> <span data-ttu-id="33dc3-113">Beachten Sie, dass es sich in beiden Fällen um eine Abfrage handelt, die zurückgegeben wird, nicht um Abfrageergebnisse.</span><span class="sxs-lookup"><span data-stu-id="33dc3-113">Note that in both cases it is a query that is  returned, not query results.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#80](~/samples/snippets/csharp/concepts/linq/how-to-return-a-query-from-a-method_1.cs)]  

## <a name="see-also"></a><span data-ttu-id="33dc3-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="33dc3-114">See also</span></span>

- [<span data-ttu-id="33dc3-115">Language-Integrated Query (LINQ)</span><span class="sxs-lookup"><span data-stu-id="33dc3-115">Language Integrated Query (LINQ)</span></span>](index.md)
