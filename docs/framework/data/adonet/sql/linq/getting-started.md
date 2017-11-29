---
title: Erste Schritte
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
ms.assetid: db8a557a-fef8-4f4f-bb91-8cff7250ee25
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 0c6db401f710c470ea890a7a7ac090fabef5d64c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="getting-started"></a><span data-ttu-id="021fd-102">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="021fd-102">Getting Started</span></span>
<span data-ttu-id="021fd-103">Mithilfe von [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], können Sie die [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] Technologie SQL den Zugriff auf Datenbanken, wie Sie eine Auflistung im Arbeitsspeicher zugreifen würden.</span><span class="sxs-lookup"><span data-stu-id="021fd-103">By using [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], you can use the [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] technology to access SQL databases just as you would access an in-memory collection.</span></span>  
  
 <span data-ttu-id="021fd-104">Beispielsweise wird das `nw`-Objekt im folgenden Code zur Darstellung der `Northwind`-Datenbank erzeugt. Das Ziel ist die `Customers`-Tabelle, die Zeilen werden nach `Customers` (Kunden) aus `London`, gefiltert, und die `CompanyName`-Zeichenfolge wird zum Abrufen ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="021fd-104">For example, the `nw` object in the following code is created to represent the `Northwind` database, the `Customers` table is targeted, the rows are filtered for `Customers` from `London`, and a string for `CompanyName` is selected for retrieval.</span></span>  
  
 <span data-ttu-id="021fd-105">Bei Ausführung der Schleife wird die Auflistung von `CompanyName`-Werten abgerufen.</span><span class="sxs-lookup"><span data-stu-id="021fd-105">When the loop is executed, the collection of `CompanyName` values is retrieved.</span></span>  
  
 [!code-csharp[DLinqGettingStarted#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqGettingStarted/cs/Program.cs#1)]
 [!code-vb[DLinqGettingStarted#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqGettingStarted/vb/Module1.vb#1)]  
  
## <a name="next-steps"></a><span data-ttu-id="021fd-106">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="021fd-106">Next Steps</span></span>  
 <span data-ttu-id="021fd-107">Einige weitere Beispiele, einschließlich eingefügt und aktualisiert werden, finden Sie unter [was Sie können führen Sie mit LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/what-you-can-do-with-linq-to-sql.md).</span><span class="sxs-lookup"><span data-stu-id="021fd-107">For some additional examples, including inserting and updating, see [What You Can Do With LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/what-you-can-do-with-linq-to-sql.md).</span></span>  
  
 <span data-ttu-id="021fd-108">Versuchen Sie danach, anhand einiger exemplarischer Vorgehensweisen und Lernprogramme einen praktischen Eindruck der Verwendung von [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] zu gewinnen.</span><span class="sxs-lookup"><span data-stu-id="021fd-108">Next, try some walkthroughs and tutorials to have a hands-on experience of using [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="021fd-109">Finden Sie unter [lernen durch Exemplarische Vorgehensweisen](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md).</span><span class="sxs-lookup"><span data-stu-id="021fd-109">See [Learning by Walkthroughs](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md).</span></span>  
  
 <span data-ttu-id="021fd-110">Abschließend erfahren Sie, wie bei der selbständigen beginnen [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Projekt durch Lesen [Typische Schritte bei der Verwendung von LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/typical-steps-for-using-linq-to-sql.md).</span><span class="sxs-lookup"><span data-stu-id="021fd-110">Finally, learn how to get started on your own [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] project by reading [Typical Steps for Using LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/typical-steps-for-using-linq-to-sql.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="021fd-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="021fd-111">See Also</span></span>  
 [<span data-ttu-id="021fd-112">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="021fd-112">LINQ to SQL</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/index.md)  
 [<span data-ttu-id="021fd-113">Einführung in LINQ</span><span class="sxs-lookup"><span data-stu-id="021fd-113">Introduction to LINQ</span></span>](http://msdn.microsoft.com/library/24dddf19-12a0-4707-a4bc-eba4fa7f219e)  
 [<span data-ttu-id="021fd-114">Die LINQ to SQL-Objektmodell</span><span class="sxs-lookup"><span data-stu-id="021fd-114">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
