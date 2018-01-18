---
title: 'Gewusst wie: Aktualisieren von Zeilen in der Datenbank'
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
ms.assetid: a2b5c90f-6cc3-4128-bfab-1db488d5af26
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 62c1ac16ab2d8607c7dd505bf4cb68f475dc26a7
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-update-rows-in-the-database"></a><span data-ttu-id="18dfc-102">Gewusst wie: Aktualisieren von Zeilen in der Datenbank</span><span class="sxs-lookup"><span data-stu-id="18dfc-102">How to: Update Rows in the Database</span></span>
<span data-ttu-id="18dfc-103">Sie können Zeilen in einer Datenbank aktualisieren, indem Sie die Memberwerte der zugeordneten Objekte ändern die [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Table%601> Auflistung und anschließend übergeben Sie die Änderungen an der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="18dfc-103">You can update rows in a database by modifying member values of the objects associated with the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Table%601> collection and then submitting the changes to the database.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="18dfc-104">Ihre Änderungen in die entsprechenden SQL übersetzt `UPDATE` Befehle.</span><span class="sxs-lookup"><span data-stu-id="18dfc-104"> translates your changes into the appropriate SQL `UPDATE` commands.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="18dfc-105">Sie können [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Standardmethoden für die Datenbankoperationen `Insert`, `Update` und `Delete` überschreiben.</span><span class="sxs-lookup"><span data-stu-id="18dfc-105">You can override [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] default methods for `Insert`, `Update`, and `Delete` database operations.</span></span> <span data-ttu-id="18dfc-106">Weitere Informationen finden Sie unter [Anpassen von INSERT-, Update- und Delete-Operationen](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).</span><span class="sxs-lookup"><span data-stu-id="18dfc-106">For more information, see [Customizing Insert, Update, and Delete Operations](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).</span></span>  
>   
>  <span data-ttu-id="18dfc-107">Entwickler, die mit [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] arbeiten, können mithilfe von [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] gespeicherte Prozeduren für denselben Zweck entwickeln.</span><span class="sxs-lookup"><span data-stu-id="18dfc-107">Developers using [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] can use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to develop stored procedures for the same purpose.</span></span>  
  
 <span data-ttu-id="18dfc-108">In den folgenden Schritten wird davon ausgegangen, dass Sie ein gültiger <xref:System.Data.Linq.DataContext> mit der Datenbank Northwind verbindet.</span><span class="sxs-lookup"><span data-stu-id="18dfc-108">The following steps assume that a valid <xref:System.Data.Linq.DataContext> connects you to the Northwind database.</span></span> <span data-ttu-id="18dfc-109">Weitere Informationen finden Sie unter [Vorgehensweise: Herstellen einer Verbindung mit einer Datenbank](../../../../../../docs/framework/data/adonet/sql/linq/how-to-connect-to-a-database.md).</span><span class="sxs-lookup"><span data-stu-id="18dfc-109">For more information, see [How to: Connect to a Database](../../../../../../docs/framework/data/adonet/sql/linq/how-to-connect-to-a-database.md).</span></span>  
  
### <a name="to-update-a-row-in-the-database"></a><span data-ttu-id="18dfc-110">So aktualisieren Sie eine Zeile in der Datenbank</span><span class="sxs-lookup"><span data-stu-id="18dfc-110">To update a row in the database</span></span>  
  
1.  <span data-ttu-id="18dfc-111">Rufen Sie die zu aktualisierende Zeile aus der Datenbank ab.</span><span class="sxs-lookup"><span data-stu-id="18dfc-111">Query the database for the row to be updated.</span></span>  
  
2.  <span data-ttu-id="18dfc-112">Nehmen Sie die gewünschten Änderungen an Memberwerten im resultierenden [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Objekt vor.</span><span class="sxs-lookup"><span data-stu-id="18dfc-112">Make desired changes to member values in the resulting [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] object.</span></span>  
  
3.  <span data-ttu-id="18dfc-113">Übergeben Sie die Änderungen an die Datenbank.</span><span class="sxs-lookup"><span data-stu-id="18dfc-113">Submit the changes to the database.</span></span>  
  
## <a name="example"></a><span data-ttu-id="18dfc-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="18dfc-114">Example</span></span>  
 <span data-ttu-id="18dfc-115">Im folgenden Beispiel wird die Bestellung Nr. 11000 aus der Datenbank abgerufen. Anschließend werden die Werte für `ShipName` und `ShipVia` im resultierenden `Order`-Objekt geändert.</span><span class="sxs-lookup"><span data-stu-id="18dfc-115">The following example queries the database for order #11000, and then changes the values of `ShipName` and `ShipVia` in the resulting `Order` object.</span></span> <span data-ttu-id="18dfc-116">Schließlich werden die Änderungen an diesen Memberwerten als Änderungen in der `ShipName`-Spalte und der `ShipVia`-Spalte an die Datenbank übergeben.</span><span class="sxs-lookup"><span data-stu-id="18dfc-116">Finally, the changes to these member values are submitted to the database as changes in the `ShipName` and `ShipVia` columns.</span></span>  
  
 [!code-csharp[System.Data.Linq.Table#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.table/cs/program.cs#2)]
 [!code-vb[System.Data.Linq.Table#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.table/vb/module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="18dfc-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="18dfc-117">See Also</span></span>  
 [<span data-ttu-id="18dfc-118">Vorgehensweise: Verwalten von Änderungskonflikten</span><span class="sxs-lookup"><span data-stu-id="18dfc-118">How to: Manage Change Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)  
 [<span data-ttu-id="18dfc-119">Vorgehensweise: Zuweisen von gespeicherten Prozeduren zum Ausführen von Updates, einfügungen und löschen (O/R-Designer)</span><span class="sxs-lookup"><span data-stu-id="18dfc-119">How to: Assign stored procedures to perform updates, inserts, and deletes (O/R Designer)</span></span>](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)  
 [<span data-ttu-id="18dfc-120">Vornehmen und Übergeben von Datenänderungen</span><span class="sxs-lookup"><span data-stu-id="18dfc-120">Making and Submitting Data Changes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)
