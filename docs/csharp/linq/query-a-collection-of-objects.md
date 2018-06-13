---
title: Abfrage einer Auflistung von Objekten
description: Vorgehensweise zum Abfragen von Auflistungen
ms.date: 11/30/2016
ms.assetid: 87a76f8a-0b58-4791-90ea-2fe0a30416c9
ms.openlocfilehash: c690da2ae59d2a9b34a5bd403bc54797c4e95fa0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33282391"
---
# <a name="query-a-collection-of-objects"></a><span data-ttu-id="7cc3b-103">Abfrage einer Auflistung von Objekten</span><span class="sxs-lookup"><span data-stu-id="7cc3b-103">Query a collection of objects</span></span>
<span data-ttu-id="7cc3b-104">In diesem Beispiel wird veranschaulicht, wie eine einfache Abfrage für eine Liste von `Student`-Objekten ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="7cc3b-104">This example shows how to perform a simple query over a list of `Student` objects.</span></span> <span data-ttu-id="7cc3b-105">Jedes `Student`-Objekt enthält grundlegende Informationen über den Studenten und eine Liste, die die Ergebnisse des Studenten aus vier Prüfungen darstellt.</span><span class="sxs-lookup"><span data-stu-id="7cc3b-105">Each `Student` object contains some basic information about the student, and a list that represents the student's scores on four examinations.</span></span>  
  
 <span data-ttu-id="7cc3b-106">Diese Anwendung dient als Rahmen für viele andere Beispiele in diesem Bereich, bei denen dieselbe `students`-Datenquelle verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="7cc3b-106">This application serves as the framework for many other examples in this section that use the same `students` data source.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7cc3b-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7cc3b-107">Example</span></span>  
 <span data-ttu-id="7cc3b-108">Die folgende Abfrage gibt die Studenten zurück, die ein Ergebnis von 90 oder höher in ihrer ersten Prüfung erzielt haben.</span><span class="sxs-lookup"><span data-stu-id="7cc3b-108">The following query returns the students who received a score of 90 or greater on their first exam.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#15](../../../samples/snippets/csharp/concepts/linq/how-to-query-a-collection-of-objects_1.cs)]  
  
 <span data-ttu-id="7cc3b-109">Diese Abfrage wurde absichtlich einfach gehalten, damit Sie damit experimentieren können.</span><span class="sxs-lookup"><span data-stu-id="7cc3b-109">This query is intentionally simple to enable you to experiment.</span></span> <span data-ttu-id="7cc3b-110">Sie können z.B. weitere Bedingungen in der `where`-Klausel ausprobieren oder eine `orderby`-Klausel verwenden, um die Ergebnisse zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="7cc3b-110">For example, you can try more conditions in the `where` clause, or use an `orderby` clause to sort the results.</span></span>  
  

## <a name="see-also"></a><span data-ttu-id="7cc3b-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7cc3b-111">See also</span></span>  
 [<span data-ttu-id="7cc3b-112">LINQ-Abfrageausdrücke</span><span class="sxs-lookup"><span data-stu-id="7cc3b-112">LINQ Query Expressions</span></span>](index.md)  
 [<span data-ttu-id="7cc3b-113">Zeichenfolgeninterpolation</span><span class="sxs-lookup"><span data-stu-id="7cc3b-113">String interpolation</span></span>](../language-reference/tokens/interpolated.md)
