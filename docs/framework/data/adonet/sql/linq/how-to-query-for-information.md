---
title: 'Vorgehensweise: Abfragen von Informationen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e538d288-2070-40ca-9da6-4fbc68cd6ad0
ms.openlocfilehash: d45fdfa8b8976e3cdc86b905443bf7bcea578714
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91166403"
---
# <a name="how-to-query-for-information"></a><span data-ttu-id="669f9-102">Vorgehensweise: Abfragen von Informationen</span><span class="sxs-lookup"><span data-stu-id="669f9-102">How to: Query for Information</span></span>

<span data-ttu-id="669f9-103">Bei Abfragen in wird [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] dieselbe Syntax verwendet wie bei Abfragen in LINQ.</span><span class="sxs-lookup"><span data-stu-id="669f9-103">Queries in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] use the same syntax as queries in LINQ.</span></span> <span data-ttu-id="669f9-104">Der einzige Unterschied besteht darin, dass die Objekte, auf die in Abfragen verwiesen wird [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] , Elementen in einer Datenbank zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="669f9-104">The only difference is that the objects referenced in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] queries are mapped to elements in a database.</span></span> <span data-ttu-id="669f9-105">Weitere Informationen finden Sie unter [Introduction to LINQ queries (C#) (Einführung in LINQ-Abfragen (C#))](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span><span class="sxs-lookup"><span data-stu-id="669f9-105">For more information, see [Introduction to LINQ Queries (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span></span>  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="669f9-106">übersetzt die Abfragen, die Sie in entsprechende SQL-Abfragen schreiben, und sendet diese zur Verarbeitung an den Server.</span><span class="sxs-lookup"><span data-stu-id="669f9-106">translates the queries you write into equivalent SQL queries and sends them to the server for processing.</span></span>  
  
 <span data-ttu-id="669f9-107">Einige Features von LINQ-Abfragen erfordern unter Umständen besondere Aufmerksamkeit bei [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="669f9-107">Some features of LINQ queries might need special attention in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] applications.</span></span> <span data-ttu-id="669f9-108">Weitere Informationen finden Sie unter [Abfrage Konzepte](query-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="669f9-108">For more information, see [Query Concepts](query-concepts.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="669f9-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="669f9-109">Example</span></span>  

 <span data-ttu-id="669f9-110">Die folgende Abfrage fordert eine Liste von Kunden aus London an.</span><span class="sxs-lookup"><span data-stu-id="669f9-110">The following query asks for a list of customers from London.</span></span> <span data-ttu-id="669f9-111">In diesem Beispiel ist `Customers` eine Tabelle in der Northwind-Beispieldatenbank.</span><span class="sxs-lookup"><span data-stu-id="669f9-111">In this example, `Customers` is a table in the Northwind sample database.</span></span>  
  
 [!code-csharp[DLinqQuerying#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#1)]
 [!code-vb[DLinqQuerying#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="669f9-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="669f9-112">See also</span></span>

- [<span data-ttu-id="669f9-113">Erstellen des Objektmodells</span><span class="sxs-lookup"><span data-stu-id="669f9-113">Creating the Object Model</span></span>](creating-the-object-model.md)
- [<span data-ttu-id="669f9-114">Herunterladen von Beispieldatenbanken</span><span class="sxs-lookup"><span data-stu-id="669f9-114">Downloading Sample Databases</span></span>](downloading-sample-databases.md)
- [<span data-ttu-id="669f9-115">Abfragen der Datenbank</span><span class="sxs-lookup"><span data-stu-id="669f9-115">Querying the Database</span></span>](querying-the-database.md)
