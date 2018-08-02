---
title: Abfragen einer Sammlung von Objekten (LINQ in C#)
description: In diesem Artikel erfahren Sie, wie Sie Abfragesammlungen mit LINQ in C# erstellen.
ms.date: 11/30/2016
ms.assetid: 87a76f8a-0b58-4791-90ea-2fe0a30416c9
ms.openlocfilehash: 87c7bbe789c165a6e189231df1979fc264a34dce
ms.sourcegitcommit: 4c158beee818c408d45a9609bfc06f209a523e22
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2018
ms.locfileid: "37403920"
---
# <a name="query-a-collection-of-objects"></a><span data-ttu-id="d7be1-103">Abfrage einer Auflistung von Objekten</span><span class="sxs-lookup"><span data-stu-id="d7be1-103">Query a collection of objects</span></span>

<span data-ttu-id="d7be1-104">In diesem Beispiel wird veranschaulicht, wie eine einfache Abfrage für eine Liste von `Student`-Objekten ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d7be1-104">This example shows how to perform a simple query over a list of `Student` objects.</span></span> <span data-ttu-id="d7be1-105">Jedes `Student`-Objekt enthält grundlegende Informationen über den Studenten und eine Liste, die die Ergebnisse des Studenten aus vier Prüfungen darstellt.</span><span class="sxs-lookup"><span data-stu-id="d7be1-105">Each `Student` object contains some basic information about the student, and a list that represents the student's scores on four examinations.</span></span>  
  
<span data-ttu-id="d7be1-106">Diese Anwendung dient als Rahmen für viele andere Beispiele in diesem Bereich, bei denen dieselbe `students`-Datenquelle verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d7be1-106">This application serves as the framework for many other examples in this section that use the same `students` data source.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d7be1-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d7be1-107">Example</span></span>

<span data-ttu-id="d7be1-108">Die folgende Abfrage gibt die Studenten zurück, die ein Ergebnis von 90 oder höher in ihrer ersten Prüfung erzielt haben.</span><span class="sxs-lookup"><span data-stu-id="d7be1-108">The following query returns the students who received a score of 90 or greater on their first exam.</span></span>  
  
[!code-csharp[csProgGuideLINQ#15](~/samples/snippets/csharp/concepts/linq/how-to-query-a-collection-of-objects_1.cs)]  
  
<span data-ttu-id="d7be1-109">Diese Abfrage wurde absichtlich einfach gehalten, damit Sie damit experimentieren können.</span><span class="sxs-lookup"><span data-stu-id="d7be1-109">This query is intentionally simple to enable you to experiment.</span></span> <span data-ttu-id="d7be1-110">Sie können z.B. weitere Bedingungen in der `where`-Klausel ausprobieren oder eine `orderby`-Klausel verwenden, um die Ergebnisse zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="d7be1-110">For example, you can try more conditions in the `where` clause, or use an `orderby` clause to sort the results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7be1-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d7be1-111">See also</span></span>

[<span data-ttu-id="d7be1-112">Language-Integrated Query (LINQ)</span><span class="sxs-lookup"><span data-stu-id="d7be1-112">Language Integrated Query (LINQ)</span></span>](index.md)  
[<span data-ttu-id="d7be1-113">Zeichenfolgeninterpolation</span><span class="sxs-lookup"><span data-stu-id="d7be1-113">String interpolation</span></span>](../language-reference/tokens/interpolated.md)