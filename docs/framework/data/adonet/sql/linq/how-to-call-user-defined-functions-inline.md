---
title: 'Vorgehensweise: Inline-Aufrufen von benutzerdefinierten Funktionen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f80d4327-b6a5-4aa8-a743-e95d09a2a02e
ms.openlocfilehash: e9808856543e20b8904be812b15b32154eab56e2
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70782106"
---
# <a name="how-to-call-user-defined-functions-inline"></a><span data-ttu-id="7a9db-102">Vorgehensweise: Inline-Aufrufen von benutzerdefinierten Funktionen</span><span class="sxs-lookup"><span data-stu-id="7a9db-102">How to: Call User-Defined Functions Inline</span></span>
<span data-ttu-id="7a9db-103">Obwohl Sie benutzerdefinierte Funktionen inline aufrufen können, werden in einer Abfrage enthaltene Funktionen, deren Ausführung umgeleitet wird, bis zur Ausführung der Abfrage verzögert.</span><span class="sxs-lookup"><span data-stu-id="7a9db-103">Although you can call user-defined functions inline, functions that are included in a query whose execution is deferred are not executed until the query is executed.</span></span> <span data-ttu-id="7a9db-104">Weitere Informationen finden Sie unter [Introduction to LINQ queries (C#) (Einführung in LINQ-Abfragen (C#))](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span><span class="sxs-lookup"><span data-stu-id="7a9db-104">For more information, see [Introduction to LINQ Queries (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span></span>  
  
 <span data-ttu-id="7a9db-105">Wenn Sie die gleiche Funktion außerhalb einer Abfrage ausführen, erstellt [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] eine einfache Abfrage aus der call expression-Methode.</span><span class="sxs-lookup"><span data-stu-id="7a9db-105">When you call the same function outside a query, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] creates a simple query from the method call expression.</span></span> <span data-ttu-id="7a9db-106">Folgendes befindet sich in der SQL-Syntax (der `@p0`-Parameter ist an die übergebene Konstante gebunden):</span><span class="sxs-lookup"><span data-stu-id="7a9db-106">The following is the SQL syntax (the parameter `@p0` is bound to the constant passed in):</span></span>  
  
```  
SELECT dbo.ReverseCustName(@p0)  
```  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="7a9db-107">erstellt Folgendes:</span><span class="sxs-lookup"><span data-stu-id="7a9db-107">creates the following:</span></span>  
  
 [!code-csharp[DLinqUDFS#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqUDFS/cs/Program.cs#4)]
 [!code-vb[DLinqUDFS#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqUDFS/vb/Module1.vb#4)]  
  
## <a name="example"></a><span data-ttu-id="7a9db-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7a9db-108">Example</span></span>  
 <span data-ttu-id="7a9db-109">In der folgenden [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Abfrage können Sie einen Inline-Aufrufder generierten benutzerdefinierten Funktions Methode `ReverseCustName`sehen.</span><span class="sxs-lookup"><span data-stu-id="7a9db-109">In the following [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] query, you can see an inline call to the generated user-defined function method `ReverseCustName`.</span></span> <span data-ttu-id="7a9db-110">Die Funktion wird nicht sofort ausgeführt, da die Abfrageausführung verzögert wird.</span><span class="sxs-lookup"><span data-stu-id="7a9db-110">The function is not executed immediately because query execution is deferred.</span></span> <span data-ttu-id="7a9db-111">Die für diese Abfrage erstellte SQL-Anweisung wird in einen Aufruf der benutzerdefinierten Funktion in der Datenbank übersetzt (siehe SQL-Code nach der Abfrage).</span><span class="sxs-lookup"><span data-stu-id="7a9db-111">The SQL built for this query translates to a call to the user-defined function in the database (see the SQL code following the query).</span></span>  
  
 [!code-csharp[DLinqUDFS#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqUDFS/cs/Program.cs#5)]
 [!code-vb[DLinqUDFS#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqUDFS/vb/Module1.vb#5)]  
  
```  
SELECT [t0].[ContactName],  
    dbo.ReverseCustName([t0].[ContactTitle]) AS [Title]  
FROM [Customers] AS [t0]  
```  
  
## <a name="see-also"></a><span data-ttu-id="7a9db-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7a9db-112">See also</span></span>

- [<span data-ttu-id="7a9db-113">Benutzerdefinierte Funktionen</span><span class="sxs-lookup"><span data-stu-id="7a9db-113">User-Defined Functions</span></span>](user-defined-functions.md)
