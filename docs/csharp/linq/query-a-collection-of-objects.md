---
title: Abfrage einer Auflistung von Objekten
description: Vorgehensweise zum Abfragen von Auflistungen
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 11/30/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.assetid: 87a76f8a-0b58-4791-90ea-2fe0a30416c9
ms.openlocfilehash: a62e5c6324d15376f1b42ad078eeb883b05ef14f
ms.sourcegitcommit: 935d5267c44f9bce801468ef95f44572f1417e8c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="query-a-collection-of-objects"></a><span data-ttu-id="c8ef5-104">Abfrage einer Auflistung von Objekten</span><span class="sxs-lookup"><span data-stu-id="c8ef5-104">Query a collection of objects</span></span>
<span data-ttu-id="c8ef5-105">In diesem Beispiel wird veranschaulicht, wie eine einfache Abfrage für eine Liste von `Student`-Objekten ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c8ef5-105">This example shows how to perform a simple query over a list of `Student` objects.</span></span> <span data-ttu-id="c8ef5-106">Jedes `Student`-Objekt enthält grundlegende Informationen über den Studenten und eine Liste, die die Ergebnisse des Studenten aus vier Prüfungen darstellt.</span><span class="sxs-lookup"><span data-stu-id="c8ef5-106">Each `Student` object contains some basic information about the student, and a list that represents the student's scores on four examinations.</span></span>  
  
 <span data-ttu-id="c8ef5-107">Diese Anwendung dient als Rahmen für viele andere Beispiele in diesem Bereich, bei denen dieselbe `students`-Datenquelle verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c8ef5-107">This application serves as the framework for many other examples in this section that use the same `students` data source.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c8ef5-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c8ef5-108">Example</span></span>  
 <span data-ttu-id="c8ef5-109">Die folgende Abfrage gibt die Studenten zurück, die ein Ergebnis von 90 oder höher in ihrer ersten Prüfung erzielt haben.</span><span class="sxs-lookup"><span data-stu-id="c8ef5-109">The following query returns the students who received a score of 90 or greater on their first exam.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#15](../../../samples/snippets/csharp/concepts/linq/how-to-query-a-collection-of-objects_1.cs)]  
  
 <span data-ttu-id="c8ef5-110">Diese Abfrage wurde absichtlich einfach gehalten, damit Sie damit experimentieren können.</span><span class="sxs-lookup"><span data-stu-id="c8ef5-110">This query is intentionally simple to enable you to experiment.</span></span> <span data-ttu-id="c8ef5-111">Sie können z.B. weitere Bedingungen in der `where`-Klausel ausprobieren oder eine `orderby`-Klausel verwenden, um die Ergebnisse zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="c8ef5-111">For example, you can try more conditions in the `where` clause, or use an `orderby` clause to sort the results.</span></span>  
  

## <a name="see-also"></a><span data-ttu-id="c8ef5-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c8ef5-112">See also</span></span>  
 [<span data-ttu-id="c8ef5-113">LINQ-Abfrageausdrücke</span><span class="sxs-lookup"><span data-stu-id="c8ef5-113">LINQ Query Expressions</span></span>](index.md)  
 [<span data-ttu-id="c8ef5-114">Zeichenfolgeninterpolation</span><span class="sxs-lookup"><span data-stu-id="c8ef5-114">String interpolation</span></span>](../language-reference/tokens/interpolated.md)
