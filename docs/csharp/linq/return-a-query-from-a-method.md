---
title: "Zurückgeben einer Abfrage aus einer Methode"
description: "Vorgehensweise zum Zurückgeben einer Abfrage aus einer Methode."
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 11/30/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: db220f79-c35b-41f2-886c-cd068672d42d
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 747345f0a765bc6cbe947a2b0c7bc025eb599550
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-return-a-query-from-a-method-c-programming-guide"></a><span data-ttu-id="da4f2-104">Gewusst wie: Zurückgeben einer Abfrage aus einer Methode (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="da4f2-104">How to: Return a Query from a Method (C# Programming Guide)</span></span>
<span data-ttu-id="da4f2-105">In diesem Beispiel wird gezeigt, wie Sie eine Abfrage aus einer Methode als Rückgabewert oder `out`-Parameter zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="da4f2-105">This example shows how to return a query from a method as the return value and as an `out` parameter.</span></span>  
  
 <span data-ttu-id="da4f2-106">Abfrageobjekte sind zusammensetzbar, das bedeutet, dass Sie eine Abfrage aus einer Methode zurückgeben können.</span><span class="sxs-lookup"><span data-stu-id="da4f2-106">Query objects are composable, meaning that you can return a query from a method.</span></span> <span data-ttu-id="da4f2-107">Objekte, die Abfragen darstellen, speichern nicht die resultierende Auflistung, sondern bei Bedarf die Schritte zum Erzeugen der Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="da4f2-107">Objects that represent queries do not store the resulting collection, but rather the steps to produce the results when needed.</span></span> <span data-ttu-id="da4f2-108">Der Vorteil des Zurückgebens von Abfrageobjekten aus Methoden ist, dass diese weiter zusammengesetzt oder geändert werden können.</span><span class="sxs-lookup"><span data-stu-id="da4f2-108">The advantage of returning query objects from methods is that they can be further composed or modified.</span></span> <span data-ttu-id="da4f2-109">Daher muss ein Rückgabewert oder ein `out`-Parameter einer Methode, die eine Abfrage zurückgibt, über diesen Typ verfügen.</span><span class="sxs-lookup"><span data-stu-id="da4f2-109">Therefore any return value or `out` parameter of a method that returns a query must also have that type.</span></span> <span data-ttu-id="da4f2-110">Wenn eine Methode eine Abfrage in einen konkreten <xref:System.Collections.Generic.List%601>- oder <xref:System.Array>-Typ materialisiert, wird sie als Methode betrachtet, die die Abfrageergebnisse zurückgibt, nicht die Abfrage selbst.</span><span class="sxs-lookup"><span data-stu-id="da4f2-110">If a method materializes a query into a concrete <xref:System.Collections.Generic.List%601> or <xref:System.Array> type, it is considered to be returning the query results instead of the query itself.</span></span> <span data-ttu-id="da4f2-111">Eine Abfragevariable, die aus einer Methode zurückgegeben wird, kann noch zusammengesetzt oder geändert werden.</span><span class="sxs-lookup"><span data-stu-id="da4f2-111">A query variable that is returned from a method can still be composed or modified.</span></span>  
  
## <a name="example"></a><span data-ttu-id="da4f2-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="da4f2-112">Example</span></span>  
 <span data-ttu-id="da4f2-113">Im folgenden Beispiel gibt die erste Methode eine Abfrage als Rückgabewert zurück. Die zweite Methode gibt eine Abfrage als `out`-Parameter zurück.</span><span class="sxs-lookup"><span data-stu-id="da4f2-113">In the following example, the first method returns a query as a return value, and the second method returns a query as an `out` parameter.</span></span> <span data-ttu-id="da4f2-114">Beachten Sie, dass es sich in beiden Fällen um eine Abfrage handelt, die zurückgegeben wird, nicht um Abfrageergebnisse.</span><span class="sxs-lookup"><span data-stu-id="da4f2-114">Note that in both cases it is a query that is  returned, not query results.</span></span>  
  
 <span data-ttu-id="da4f2-115">[!code-cs[csProgGuideLINQ#80](../../../samples/snippets/csharp/concepts/linq/how-to-return-a-query-from-a-method_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="da4f2-115">[!code-cs[csProgGuideLINQ#80](../../../samples/snippets/csharp/concepts/linq/how-to-return-a-query-from-a-method_1.cs)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="da4f2-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="da4f2-116">See Also</span></span>  
 [<span data-ttu-id="da4f2-117">LINQ-Abfrageausdrücke</span><span class="sxs-lookup"><span data-stu-id="da4f2-117">LINQ Query Expressions</span></span>](index.md)

