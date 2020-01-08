---
title: 'Gewusst wie: Abfragen von Informationen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e538d288-2070-40ca-9da6-4fbc68cd6ad0
ms.openlocfilehash: 3380b486da33a5dc083ed51f6705e666978df197
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/03/2020
ms.locfileid: "75634650"
---
# <a name="how-to-query-for-information"></a><span data-ttu-id="b9acf-102">Gewusst wie: Abfragen von Informationen</span><span class="sxs-lookup"><span data-stu-id="b9acf-102">How to: Query for Information</span></span>
<span data-ttu-id="b9acf-103">Bei Abfragen in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] wird dieselbe Syntax wie bei Abfragen in LINQ verwendet.</span><span class="sxs-lookup"><span data-stu-id="b9acf-103">Queries in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] use the same syntax as queries in LINQ.</span></span> <span data-ttu-id="b9acf-104">Der einzige Unterschied besteht darin, dass die Objekte, auf die in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Abfragen verwiesen wird, Elementen in einer Datenbank zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="b9acf-104">The only difference is that the objects referenced in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] queries are mapped to elements in a database.</span></span> <span data-ttu-id="b9acf-105">Weitere Informationen finden Sie unter [Introduction to LINQ queries (C#) (Einführung in LINQ-Abfragen (C#))](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span><span class="sxs-lookup"><span data-stu-id="b9acf-105">For more information, see [Introduction to LINQ Queries (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span></span>  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="b9acf-106">übersetzt die Abfragen, die Sie in entsprechende SQL-Abfragen schreiben, und sendet diese zur Verarbeitung an den Server.</span><span class="sxs-lookup"><span data-stu-id="b9acf-106">translates the queries you write into equivalent SQL queries and sends them to the server for processing.</span></span>  
  
 <span data-ttu-id="b9acf-107">Einige Features von LINQ-Abfragen erfordern unter Umständen besondere Aufmerksamkeit in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="b9acf-107">Some features of LINQ queries might need special attention in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] applications.</span></span> <span data-ttu-id="b9acf-108">Weitere Informationen finden Sie unter [Abfrage Konzepte](query-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="b9acf-108">For more information, see [Query Concepts](query-concepts.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b9acf-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b9acf-109">Example</span></span>  
 <span data-ttu-id="b9acf-110">Die folgende Abfrage fordert eine Liste von Kunden aus London an.</span><span class="sxs-lookup"><span data-stu-id="b9acf-110">The following query asks for a list of customers from London.</span></span> <span data-ttu-id="b9acf-111">In diesem Beispiel ist `Customers` eine Tabelle in der Northwind-Beispieldatenbank.</span><span class="sxs-lookup"><span data-stu-id="b9acf-111">In this example, `Customers` is a table in the Northwind sample database.</span></span>  
  
 [!code-csharp[DLinqQuerying#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#1)]
 [!code-vb[DLinqQuerying#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="b9acf-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b9acf-112">See also</span></span>

- [<span data-ttu-id="b9acf-113">Erstellen des Objektmodells</span><span class="sxs-lookup"><span data-stu-id="b9acf-113">Creating the Object Model</span></span>](creating-the-object-model.md)
- [<span data-ttu-id="b9acf-114">Downloading Sample Databases (Herunterladen von Beispieldatenbanken)</span><span class="sxs-lookup"><span data-stu-id="b9acf-114">Downloading Sample Databases</span></span>](downloading-sample-databases.md)
- [<span data-ttu-id="b9acf-115">Abfragen der Datenbank</span><span class="sxs-lookup"><span data-stu-id="b9acf-115">Querying the Database</span></span>](querying-the-database.md)
