---
title: Erste Schritte
description: Mit diesem Beispielcode können Sie LINQ to SQL verwenden, um die LINQ-Technologie für den Zugriff auf SQL-Datenbanken zu verwenden, so wie Sie auf eine in-Memory-Sammlung zugreifen würden.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: db8a557a-fef8-4f4f-bb91-8cff7250ee25
ms.openlocfilehash: b886518d4cff687a18f363c3e3ba43b40631a22f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91194374"
---
# <a name="getting-started"></a><span data-ttu-id="ffe22-103">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="ffe22-103">Getting Started</span></span>

<span data-ttu-id="ffe22-104">Mithilfe von [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] können Sie die LINQ-Technologie verwenden, um auf SQL-Datenbanken genauso zuzugreifen wie auf eine Auflistung im Arbeitsspeicher.</span><span class="sxs-lookup"><span data-stu-id="ffe22-104">By using [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], you can use the LINQ technology to access SQL databases just as you would access an in-memory collection.</span></span>  
  
 <span data-ttu-id="ffe22-105">Beispielsweise wird das `nw`-Objekt im folgenden Code zur Darstellung der `Northwind`-Datenbank erzeugt. Das Ziel ist die `Customers`-Tabelle, die Zeilen werden nach `Customers` (Kunden) aus `London`, gefiltert, und die `CompanyName`-Zeichenfolge wird zum Abrufen ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="ffe22-105">For example, the `nw` object in the following code is created to represent the `Northwind` database, the `Customers` table is targeted, the rows are filtered for `Customers` from `London`, and a string for `CompanyName` is selected for retrieval.</span></span>  
  
 <span data-ttu-id="ffe22-106">Bei Ausführung der Schleife wird die Auflistung von `CompanyName`-Werten abgerufen.</span><span class="sxs-lookup"><span data-stu-id="ffe22-106">When the loop is executed, the collection of `CompanyName` values is retrieved.</span></span>  
  
 [!code-csharp[DLinqGettingStarted#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqGettingStarted/cs/Program.cs#1)]
 [!code-vb[DLinqGettingStarted#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqGettingStarted/vb/Module1.vb#1)]  
  
## <a name="next-steps"></a><span data-ttu-id="ffe22-107">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="ffe22-107">Next Steps</span></span>  

 <span data-ttu-id="ffe22-108">Weitere Beispiele, einschließlich einfügen und aktualisieren, finden Sie unter [was Sie mit LINQ to SQL tun können](what-you-can-do-with-linq-to-sql.md).</span><span class="sxs-lookup"><span data-stu-id="ffe22-108">For some additional examples, including inserting and updating, see [What You Can Do With LINQ to SQL](what-you-can-do-with-linq-to-sql.md).</span></span>  
  
 <span data-ttu-id="ffe22-109">Versuchen Sie danach, anhand einiger exemplarischer Vorgehensweisen und Lernprogramme einen praktischen Eindruck der Verwendung von [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] zu gewinnen.</span><span class="sxs-lookup"><span data-stu-id="ffe22-109">Next, try some walkthroughs and tutorials to have a hands-on experience of using [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="ffe22-110">Weitere Informationen finden Sie [unter Learning by Walkthrough](learning-by-walkthroughs.md).</span><span class="sxs-lookup"><span data-stu-id="ffe22-110">See [Learning by Walkthroughs](learning-by-walkthroughs.md).</span></span>  
  
 <span data-ttu-id="ffe22-111">Schließlich erfahren Sie, wie Sie mit den ersten Schritten für Ihr eigenes Projekt beginnen, indem Sie die [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] [typischen Schritte zum Verwenden von LINQ to SQL](typical-steps-for-using-linq-to-sql.md)lesen.</span><span class="sxs-lookup"><span data-stu-id="ffe22-111">Finally, learn how to get started on your own [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] project by reading [Typical Steps for Using LINQ to SQL](typical-steps-for-using-linq-to-sql.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffe22-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ffe22-112">See also</span></span>

- [<span data-ttu-id="ffe22-113">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="ffe22-113">LINQ to SQL</span></span>](index.md)
- [<span data-ttu-id="ffe22-114">Einführung in LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="ffe22-114">Introduction to LINQ (C#)</span></span>](../../../../../csharp/programming-guide/concepts/linq/index.md)
- [<span data-ttu-id="ffe22-115">Introduction to LINQ (Visual Basic) (Einführung in LINQ (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="ffe22-115">Introduction to LINQ (Visual Basic)</span></span>](../../../../../visual-basic/programming-guide/concepts/linq/introduction-to-linq.md)
- [<span data-ttu-id="ffe22-116">Das LINQ to SQL-Objektmodell</span><span class="sxs-lookup"><span data-stu-id="ffe22-116">The LINQ to SQL Object Model</span></span>](the-linq-to-sql-object-model.md)
