---
title: 'Gewusst wie: Abfragen von Informationen'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: e538d288-2070-40ca-9da6-4fbc68cd6ad0
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: f0722f83c19c1eff43606afceeda484d72691eb9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-query-for-information"></a><span data-ttu-id="8e192-102">Gewusst wie: Abfragen von Informationen</span><span class="sxs-lookup"><span data-stu-id="8e192-102">How to: Query for Information</span></span>
<span data-ttu-id="8e192-103">Abfragen in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] verwenden die gleiche Syntax wie Abfragen in [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8e192-103">Queries in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] use the same syntax as queries in [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)].</span></span> <span data-ttu-id="8e192-104">Der einzige Unterschied besteht darin, dass die Objekte in verwiesen [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Abfragen auf Elemente in einer Datenbank zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="8e192-104">The only difference is that the objects referenced in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] queries are mapped to elements in a database.</span></span> <span data-ttu-id="8e192-105">Weitere Informationen finden Sie unter [Introduction to LINQ queries (C#) (Einführung in LINQ-Abfragen (C#))](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span><span class="sxs-lookup"><span data-stu-id="8e192-105">For more information, see [Introduction to LINQ Queries (C#)](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span></span>  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="8e192-106"> übersetzt die Abfragen, die Sie in entsprechende SQL-Abfragen schreiben, und sendet diese zur Verarbeitung an den Server.</span><span class="sxs-lookup"><span data-stu-id="8e192-106"> translates the queries you write into equivalent SQL queries and sends them to the server for processing.</span></span>  
  
 <span data-ttu-id="8e192-107">Einige Funktionen von [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)]-Abfragen benötigen in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Anwendungen besondere Aufmerksamkeit.</span><span class="sxs-lookup"><span data-stu-id="8e192-107">Some features of [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] queries might need special attention in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] applications.</span></span> <span data-ttu-id="8e192-108">Weitere Informationen finden Sie unter [Abfragekonzepte](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="8e192-108">For more information, see [Query Concepts](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8e192-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8e192-109">Example</span></span>  
 <span data-ttu-id="8e192-110">Die folgende Abfrage fordert eine Liste von Kunden aus London an.</span><span class="sxs-lookup"><span data-stu-id="8e192-110">The following query asks for a list of customers from London.</span></span> <span data-ttu-id="8e192-111">In diesem Beispiel ist `Customers` eine Tabelle in der Northwind-Beispieldatenbank.</span><span class="sxs-lookup"><span data-stu-id="8e192-111">In this example, `Customers` is a table in the Northwind sample database.</span></span>  
  
 [!code-csharp[DLinqQuerying#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#1)]
 [!code-vb[DLinqQuerying#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="8e192-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8e192-112">See Also</span></span>  
 [<span data-ttu-id="8e192-113">Erstellen des Objektmodells</span><span class="sxs-lookup"><span data-stu-id="8e192-113">Creating the Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)  
 [<span data-ttu-id="8e192-114">Downloading Sample Databases (Herunterladen von Beispieldatenbanken)</span><span class="sxs-lookup"><span data-stu-id="8e192-114">Downloading Sample Databases</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)  
 [<span data-ttu-id="8e192-115">Abfragen der Datenbank</span><span class="sxs-lookup"><span data-stu-id="8e192-115">Querying the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)
