---
title: Zurückgeben einer Abfrage aus einer Methode
description: Vorgehensweise zum Zurückgeben einer Abfrage aus einer Methode.
ms.date: 11/30/2016
ms.assetid: db220f79-c35b-41f2-886c-cd068672d42d
ms.openlocfilehash: 646e771d637aa242231e3fe216d4a856bb156649
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203331"
---
# <a name="how-to-return-a-query-from-a-method-c-programming-guide"></a><span data-ttu-id="208ec-103">Gewusst wie: Zurückgeben einer Abfrage aus einer Methode (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="208ec-103">How to return a query from a method (C# Programming Guide)</span></span>

<span data-ttu-id="208ec-104">In diesem Beispiel wird gezeigt, wie Sie eine Abfrage aus einer Methode als Rückgabewert oder `out`-Parameter zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="208ec-104">This example shows how to return a query from a method as the return value and as an `out` parameter.</span></span>  
  
 <span data-ttu-id="208ec-105">Abfrageobjekte sind zusammensetzbar, das bedeutet, dass Sie eine Abfrage aus einer Methode zurückgeben können.</span><span class="sxs-lookup"><span data-stu-id="208ec-105">Query objects are composable, meaning that you can return a query from a method.</span></span> <span data-ttu-id="208ec-106">Objekte, die Abfragen darstellen, speichern nicht die resultierende Auflistung, sondern bei Bedarf die Schritte zum Erzeugen der Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="208ec-106">Objects that represent queries do not store the resulting collection, but rather the steps to produce the results when needed.</span></span> <span data-ttu-id="208ec-107">Der Vorteil des Zurückgebens von Abfrageobjekten aus Methoden ist, dass diese weiter zusammengesetzt oder geändert werden können.</span><span class="sxs-lookup"><span data-stu-id="208ec-107">The advantage of returning query objects from methods is that they can be further composed or modified.</span></span> <span data-ttu-id="208ec-108">Daher muss ein Rückgabewert oder ein `out`-Parameter einer Methode, die eine Abfrage zurückgibt, über diesen Typ verfügen.</span><span class="sxs-lookup"><span data-stu-id="208ec-108">Therefore any return value or `out` parameter of a method that returns a query must also have that type.</span></span> <span data-ttu-id="208ec-109">Wenn eine Methode eine Abfrage in einen konkreten <xref:System.Collections.Generic.List%601>- oder <xref:System.Array>-Typ materialisiert, wird sie als Methode betrachtet, die die Abfrageergebnisse zurückgibt, nicht die Abfrage selbst.</span><span class="sxs-lookup"><span data-stu-id="208ec-109">If a method materializes a query into a concrete <xref:System.Collections.Generic.List%601> or <xref:System.Array> type, it is considered to be returning the query results instead of the query itself.</span></span> <span data-ttu-id="208ec-110">Eine Abfragevariable, die aus einer Methode zurückgegeben wird, kann noch zusammengesetzt oder geändert werden.</span><span class="sxs-lookup"><span data-stu-id="208ec-110">A query variable that is returned from a method can still be composed or modified.</span></span>  
  
## <a name="example"></a><span data-ttu-id="208ec-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="208ec-111">Example</span></span>  

 <span data-ttu-id="208ec-112">Im folgenden Beispiel gibt die erste Methode eine Abfrage als Rückgabewert zurück. Die zweite Methode gibt eine Abfrage als `out`-Parameter zurück.</span><span class="sxs-lookup"><span data-stu-id="208ec-112">In the following example, the first method returns a query as a return value, and the second method returns a query as an `out` parameter.</span></span> <span data-ttu-id="208ec-113">Beachten Sie, dass es sich in beiden Fällen um eine Abfrage handelt, die zurückgegeben wird, nicht um Abfrageergebnisse.</span><span class="sxs-lookup"><span data-stu-id="208ec-113">Note that in both cases it is a query that is  returned, not query results.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#80](~/samples/snippets/csharp/concepts/linq/how-to-return-a-query-from-a-method_1.cs)]  

## <a name="see-also"></a><span data-ttu-id="208ec-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="208ec-114">See also</span></span>

- [<span data-ttu-id="208ec-115">Language-Integrated Query (LINQ)</span><span class="sxs-lookup"><span data-stu-id="208ec-115">Language Integrated Query (LINQ)</span></span>](index.md)
