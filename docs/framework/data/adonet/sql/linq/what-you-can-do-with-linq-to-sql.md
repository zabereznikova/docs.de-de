---
title: Möglichkeiten von LINQ to SQL
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 061d98b2-baa7-4336-8ad2-c14de8134d91
ms.openlocfilehash: 1c589ddbc7276ca13fc82513effd3bcae3cd61fd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54718740"
---
# <a name="what-you-can-do-with-linq-to-sql"></a><span data-ttu-id="8a86d-102">Möglichkeiten von LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="8a86d-102">What You Can Do With LINQ to SQL</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="8a86d-103">unterstützt alle wichtigen Funktionen, die Sie als SQL-Entwickler erwarten würden.</span><span class="sxs-lookup"><span data-stu-id="8a86d-103">supports all the key capabilities you would expect as a SQL developer.</span></span> <span data-ttu-id="8a86d-104">Sie können Informationen abfragen und Informationen in Tabellen einfügen, aktualisieren und löschen.</span><span class="sxs-lookup"><span data-stu-id="8a86d-104">You can query for information, and insert, update, and delete information from tables.</span></span>  
  
## <a name="selecting"></a><span data-ttu-id="8a86d-105">Auswählen</span><span class="sxs-lookup"><span data-stu-id="8a86d-105">Selecting</span></span>  
 <span data-ttu-id="8a86d-106">Die Auswahl (*Projektion*) wird erreicht, indem eine [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] -Abfrage in einer beliebigen Programmiersprache verfasst und zum Abrufen der Ergebnisse ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="8a86d-106">Selecting (*projection*) is achieved by just writing a [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] query in your own programming language, and then executing that query to retrieve the results.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="8a86d-107">übersetzt die Operationen in die entsprechenden SQL-Operationen, die bekannt sind.</span><span class="sxs-lookup"><span data-stu-id="8a86d-107">itself translates all the necessary operations into the necessary SQL operations that you are familiar with.</span></span> <span data-ttu-id="8a86d-108">Weitere Informationen finden Sie unter [LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/index.md).</span><span class="sxs-lookup"><span data-stu-id="8a86d-108">For more information, see [LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/index.md).</span></span>  
  
 <span data-ttu-id="8a86d-109">Im folgenden Beispiel werden die Firmennamen von Kunden aus London abgerufen und im Konsolenfenster dargestellt.</span><span class="sxs-lookup"><span data-stu-id="8a86d-109">In the following example, the company names of customers from London are retrieved and displayed in the console window.</span></span>  
  
 [!code-csharp[DLinqGettingStarted#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqGettingStarted/cs/Program.cs#1)]
 [!code-vb[DLinqGettingStarted#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqGettingStarted/vb/Module1.vb#1)]  
  
## <a name="inserting"></a><span data-ttu-id="8a86d-110">Einfügen</span><span class="sxs-lookup"><span data-stu-id="8a86d-110">Inserting</span></span>  
 <span data-ttu-id="8a86d-111">Zum Ausführen eines SQL- `Insert`können Sie einfach dem erstellten Objektmodell Objekte hinzufügen und <xref:System.Data.Linq.DataContext.SubmitChanges%2A> im <xref:System.Data.Linq.DataContext>aufrufen.</span><span class="sxs-lookup"><span data-stu-id="8a86d-111">To execute a SQL `Insert`, just add objects to the object model you have created, and call <xref:System.Data.Linq.DataContext.SubmitChanges%2A> on the <xref:System.Data.Linq.DataContext>.</span></span>  
  
 <span data-ttu-id="8a86d-112">Im folgenden Beispiel werden ein Kunde und Informationen zu diesem in die `Customers` -Tabelle eingefügt (mithilfe von <xref:System.Data.Linq.Table%601.InsertOnSubmit%2A>).</span><span class="sxs-lookup"><span data-stu-id="8a86d-112">In the following example, a new customer and information about the customer is added to the `Customers` table by using <xref:System.Data.Linq.Table%601.InsertOnSubmit%2A>.</span></span>  
  
 [!code-csharp[DLinqGettingStarted#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqGettingStarted/cs/Program.cs#2)]
 [!code-vb[DLinqGettingStarted#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqGettingStarted/vb/Module1.vb#2)]  
  
## <a name="updating"></a><span data-ttu-id="8a86d-113">Wird aktualisiert</span><span class="sxs-lookup"><span data-stu-id="8a86d-113">Updating</span></span>  
 <span data-ttu-id="8a86d-114">Zum Aktualisieren eines Datenbankeintrags mit `Update` , rufen Sie zuerst das Element ab und bearbeiten es direkt im Objektmodell.</span><span class="sxs-lookup"><span data-stu-id="8a86d-114">To `Update` a database entry, first retrieve the item and edit it directly in the object model.</span></span> <span data-ttu-id="8a86d-115">Nachdem Sie das Objekt geändert haben, rufen Sie <xref:System.Data.Linq.DataContext.SubmitChanges%2A> im <xref:System.Data.Linq.DataContext> auf, um die Datenbank zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="8a86d-115">After you have modified the object, call <xref:System.Data.Linq.DataContext.SubmitChanges%2A> on the <xref:System.Data.Linq.DataContext> to update the database.</span></span>  
  
 <span data-ttu-id="8a86d-116">Im folgenden Beispiel werden alle Kunden aus London abgerufen.</span><span class="sxs-lookup"><span data-stu-id="8a86d-116">In the following example, all customers who are from London are retrieved.</span></span> <span data-ttu-id="8a86d-117">Dann wird der Name des Orts von „London“ in „London - Metro“ geändert.</span><span class="sxs-lookup"><span data-stu-id="8a86d-117">Then the name of the city is changed from "London" to "London - Metro".</span></span> <span data-ttu-id="8a86d-118">Schließlich wird <xref:System.Data.Linq.DataContext.SubmitChanges%2A> aufgerufen, um die Änderungen an die Datenbank zu senden.</span><span class="sxs-lookup"><span data-stu-id="8a86d-118">Finally, <xref:System.Data.Linq.DataContext.SubmitChanges%2A> is called to send the changes to the database.</span></span>  
  
 [!code-csharp[DLinqGettingStarted#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqGettingStarted/cs/Program.cs#3)]
 [!code-vb[DLinqGettingStarted#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqGettingStarted/vb/Module1.vb#3)]  
  
## <a name="deleting"></a><span data-ttu-id="8a86d-119">Wird gelöscht</span><span class="sxs-lookup"><span data-stu-id="8a86d-119">Deleting</span></span>  
 <span data-ttu-id="8a86d-120">Wenn Sie ein Element löschen möchten ( `Delete` ), entfernen Sie dieses aus der entsprechenden Auflistung, und rufen Sie dann <xref:System.Data.Linq.DataContext.SubmitChanges%2A> im <xref:System.Data.Linq.DataContext> auf, um die Änderung zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="8a86d-120">To `Delete` an item, remove the item from the collection to which it belongs, and then call <xref:System.Data.Linq.DataContext.SubmitChanges%2A> on the <xref:System.Data.Linq.DataContext> to commit the change.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8a86d-121">Kaskadierte Löschvorgänge werden von[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] nicht erkannt.</span><span class="sxs-lookup"><span data-stu-id="8a86d-121">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] does not recognize cascade-delete operations.</span></span> <span data-ttu-id="8a86d-122">Wenn Sie eine Zeile in einer Tabelle löschen möchten, Einschränkungen, finden Sie unter [Vorgehensweise: Löschen von Zeilen aus der Datenbank](../../../../../../docs/framework/data/adonet/sql/linq/how-to-delete-rows-from-the-database.md).</span><span class="sxs-lookup"><span data-stu-id="8a86d-122">If you want to delete a row in a table that has constraints against it, see [How to: Delete Rows From the Database](../../../../../../docs/framework/data/adonet/sql/linq/how-to-delete-rows-from-the-database.md).</span></span>  
  
 <span data-ttu-id="8a86d-123">Im folgenden Beispiel wird der Kunde mit der `CustomerID` `98128` aus der Datenbank abgerufen.</span><span class="sxs-lookup"><span data-stu-id="8a86d-123">In the following example, the customer who has `CustomerID` of `98128` is retrieved from the database.</span></span> <span data-ttu-id="8a86d-124">Nach dem Bestätigen des Abrufs wird <xref:System.Data.Linq.Table%601.DeleteOnSubmit%2A> aufgerufen, um das Objekt aus der Auflistung zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="8a86d-124">Then, after confirming that the customer row was retrieved, <xref:System.Data.Linq.Table%601.DeleteOnSubmit%2A> is called to remove that object from the collection.</span></span> <span data-ttu-id="8a86d-125">Schließlich wird <xref:System.Data.Linq.DataContext.SubmitChanges%2A> aufgerufen, um die Löschung an die Datenbank weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="8a86d-125">Finally, <xref:System.Data.Linq.DataContext.SubmitChanges%2A> is called to forward the deletion to the database.</span></span>  
  
 [!code-csharp[DLinqGettingStarted#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqGettingStarted/cs/Program.cs#4)]
 [!code-vb[DLinqGettingStarted#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqGettingStarted/vb/Module1.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="8a86d-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8a86d-126">See also</span></span>
- [<span data-ttu-id="8a86d-127">Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="8a86d-127">Programming Guide</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/programming-guide.md)
- [<span data-ttu-id="8a86d-128">Das LINQ to SQL-Objektmodell</span><span class="sxs-lookup"><span data-stu-id="8a86d-128">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
- [<span data-ttu-id="8a86d-129">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="8a86d-129">Getting Started</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/getting-started.md)
