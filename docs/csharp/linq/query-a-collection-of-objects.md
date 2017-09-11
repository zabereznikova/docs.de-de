---
title: Abfrage einer Auflistung von Objekten
description: Vorgehensweise zum Abfragen von Auflistungen
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 11/30/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 87a76f8a-0b58-4791-90ea-2fe0a30416c9
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 9e08f2e5877ffe24f5a238ab19abb9760cb442f2
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="query-a-collection-of-objects"></a><span data-ttu-id="34556-104">Abfrage einer Auflistung von Objekten</span><span class="sxs-lookup"><span data-stu-id="34556-104">Query a collection of objects</span></span>
<span data-ttu-id="34556-105">In diesem Beispiel wird veranschaulicht, wie eine einfache Abfrage für eine Liste von `Student`-Objekten ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="34556-105">This example shows how to perform a simple query over a list of `Student` objects.</span></span> <span data-ttu-id="34556-106">Jedes `Student`-Objekt enthält grundlegende Informationen über den Studenten und eine Liste, die die Ergebnisse des Studenten aus vier Prüfungen darstellt.</span><span class="sxs-lookup"><span data-stu-id="34556-106">Each `Student` object contains some basic information about the student, and a list that represents the student's scores on four examinations.</span></span>  
  
 <span data-ttu-id="34556-107">Diese Anwendung dient als Rahmen für viele andere Beispiele in diesem Bereich, bei denen dieselbe `students`-Datenquelle verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="34556-107">This application serves as the framework for many other examples in this section that use the same `students` data source.</span></span>  
  
## <a name="example"></a><span data-ttu-id="34556-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="34556-108">Example</span></span>  
 <span data-ttu-id="34556-109">Die folgende Abfrage gibt die Studenten zurück, die ein Ergebnis von 90 oder höher in ihrer ersten Prüfung erzielt haben.</span><span class="sxs-lookup"><span data-stu-id="34556-109">The following query returns the students who received a score of 90 or greater on their first exam.</span></span>  
  
 <span data-ttu-id="34556-110">[!code-cs[csProgGuideLINQ#15](../../../samples/snippets/csharp/concepts/linq/how-to-query-a-collection-of-objects_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="34556-110">[!code-cs[csProgGuideLINQ#15](../../../samples/snippets/csharp/concepts/linq/how-to-query-a-collection-of-objects_1.cs)]</span></span>  
  
 <span data-ttu-id="34556-111">Diese Abfrage wurde absichtlich einfach gehalten, damit Sie damit experimentieren können.</span><span class="sxs-lookup"><span data-stu-id="34556-111">This query is intentionally simple to enable you to experiment.</span></span> <span data-ttu-id="34556-112">Sie können z.B. weitere Bedingungen in der `where`-Klausel ausprobieren oder eine `orderby`-Klausel verwenden, um die Ergebnisse zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="34556-112">For example, you can try more conditions in the `where` clause, or use an `orderby` clause to sort the results.</span></span>  
  

## <a name="see-also"></a><span data-ttu-id="34556-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="34556-113">See also</span></span>  
 [<span data-ttu-id="34556-114">LINQ-Abfrageausdrücke</span><span class="sxs-lookup"><span data-stu-id="34556-114">LINQ Query Expressions</span></span>](index.md)

