---
title: 'Vorgehensweise: Abfragen von Informationen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e538d288-2070-40ca-9da6-4fbc68cd6ad0
ms.openlocfilehash: ed32bbe7d27357cbed7d77dd235b698a65c0e29e
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70793539"
---
# <a name="how-to-query-for-information"></a><span data-ttu-id="cfa41-102">Vorgehensweise: Abfragen von Informationen</span><span class="sxs-lookup"><span data-stu-id="cfa41-102">How to: Query for Information</span></span>
<span data-ttu-id="cfa41-103">Abfragen in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] verwenden die gleiche Syntax wie Abfragen in [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cfa41-103">Queries in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] use the same syntax as queries in [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)].</span></span> <span data-ttu-id="cfa41-104">Der einzige Unterschied besteht darin, dass die [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Objekte, auf die in Abfragen verwiesen wird, Elementen in einer Datenbank zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="cfa41-104">The only difference is that the objects referenced in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] queries are mapped to elements in a database.</span></span> <span data-ttu-id="cfa41-105">Weitere Informationen finden Sie unter [Introduction to LINQ queries (C#) (Einführung in LINQ-Abfragen (C#))](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span><span class="sxs-lookup"><span data-stu-id="cfa41-105">For more information, see [Introduction to LINQ Queries (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span></span>  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="cfa41-106">übersetzt die Abfragen, die Sie in entsprechende SQL-Abfragen schreiben, und sendet diese zur Verarbeitung an den Server.</span><span class="sxs-lookup"><span data-stu-id="cfa41-106">translates the queries you write into equivalent SQL queries and sends them to the server for processing.</span></span>  
  
 <span data-ttu-id="cfa41-107">Einige Funktionen von [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)]-Abfragen benötigen in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Anwendungen besondere Aufmerksamkeit.</span><span class="sxs-lookup"><span data-stu-id="cfa41-107">Some features of [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] queries might need special attention in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] applications.</span></span> <span data-ttu-id="cfa41-108">Weitere Informationen finden Sie unter [Abfrage Konzepte](query-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="cfa41-108">For more information, see [Query Concepts](query-concepts.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="cfa41-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cfa41-109">Example</span></span>  
 <span data-ttu-id="cfa41-110">Die folgende Abfrage fordert eine Liste von Kunden aus London an.</span><span class="sxs-lookup"><span data-stu-id="cfa41-110">The following query asks for a list of customers from London.</span></span> <span data-ttu-id="cfa41-111">In diesem Beispiel ist `Customers` eine Tabelle in der Northwind-Beispieldatenbank.</span><span class="sxs-lookup"><span data-stu-id="cfa41-111">In this example, `Customers` is a table in the Northwind sample database.</span></span>  
  
 [!code-csharp[DLinqQuerying#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#1)]
 [!code-vb[DLinqQuerying#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="cfa41-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cfa41-112">See also</span></span>

- [<span data-ttu-id="cfa41-113">Erstellen des Objektmodells</span><span class="sxs-lookup"><span data-stu-id="cfa41-113">Creating the Object Model</span></span>](creating-the-object-model.md)
- [<span data-ttu-id="cfa41-114">Downloading Sample Databases (Herunterladen von Beispieldatenbanken)</span><span class="sxs-lookup"><span data-stu-id="cfa41-114">Downloading Sample Databases</span></span>](downloading-sample-databases.md)
- [<span data-ttu-id="cfa41-115">Abfragen der Datenbank</span><span class="sxs-lookup"><span data-stu-id="cfa41-115">Querying the Database</span></span>](querying-the-database.md)
