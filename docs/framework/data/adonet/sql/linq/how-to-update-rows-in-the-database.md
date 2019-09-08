---
title: 'Vorgehensweise: Aktualisieren von Zeilen in der Datenbank'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a2b5c90f-6cc3-4128-bfab-1db488d5af26
ms.openlocfilehash: c2055e1dd988352b50a439531ab5533f34a4965e
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70793133"
---
# <a name="how-to-update-rows-in-the-database"></a><span data-ttu-id="054e3-102">Vorgehensweise: Aktualisieren von Zeilen in der Datenbank</span><span class="sxs-lookup"><span data-stu-id="054e3-102">How to: Update Rows in the Database</span></span>

<span data-ttu-id="054e3-103">Sie können Zeilen in einer Datenbank aktualisieren, indem Sie die Element Werte der der Auflistung zugeordneten [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Table%601> Objekte ändern und dann die Änderungen an die Datenbank übermitteln.</span><span class="sxs-lookup"><span data-stu-id="054e3-103">You can update rows in a database by modifying member values of the objects associated with the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Table%601> collection and then submitting the changes to the database.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="054e3-104">übersetzt die Änderungen in die entsprechenden SQL `UPDATE` -Befehle.</span><span class="sxs-lookup"><span data-stu-id="054e3-104">translates your changes into the appropriate SQL `UPDATE` commands.</span></span>

> [!NOTE]
> <span data-ttu-id="054e3-105">Sie können [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Standardmethoden für die Datenbankoperationen `Insert`, `Update` und `Delete` überschreiben.</span><span class="sxs-lookup"><span data-stu-id="054e3-105">You can override [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] default methods for `Insert`, `Update`, and `Delete` database operations.</span></span> <span data-ttu-id="054e3-106">Weitere Informationen finden Sie unter [Anpassen von INSERT-, Update-und DELETE-Vorgängen](customizing-insert-update-and-delete-operations.md).</span><span class="sxs-lookup"><span data-stu-id="054e3-106">For more information, see [Customizing Insert, Update, and Delete Operations](customizing-insert-update-and-delete-operations.md).</span></span>
>
> <span data-ttu-id="054e3-107">Entwickler, die Visual Studio verwenden, können den objektrelationaler Designer verwenden, um gespeicherte Prozeduren für denselben Zweck zu entwickeln.</span><span class="sxs-lookup"><span data-stu-id="054e3-107">Developers using Visual Studio can use the Object Relational Designer to develop stored procedures for the same purpose.</span></span>

<span data-ttu-id="054e3-108">In den folgenden Schritten wird davon ausgegangen, dass Sie ein gültiger <xref:System.Data.Linq.DataContext> mit der Datenbank Northwind verbindet.</span><span class="sxs-lookup"><span data-stu-id="054e3-108">The following steps assume that a valid <xref:System.Data.Linq.DataContext> connects you to the Northwind database.</span></span> <span data-ttu-id="054e3-109">Weitere Informationen finden Sie unter [Vorgehensweise: Verbindung mit einer Datenbank](how-to-connect-to-a-database.md)herstellen.</span><span class="sxs-lookup"><span data-stu-id="054e3-109">For more information, see [How to: Connect to a Database](how-to-connect-to-a-database.md).</span></span>

### <a name="to-update-a-row-in-the-database"></a><span data-ttu-id="054e3-110">So aktualisieren Sie eine Zeile in der Datenbank</span><span class="sxs-lookup"><span data-stu-id="054e3-110">To update a row in the database</span></span>

1. <span data-ttu-id="054e3-111">Rufen Sie die zu aktualisierende Zeile aus der Datenbank ab.</span><span class="sxs-lookup"><span data-stu-id="054e3-111">Query the database for the row to be updated.</span></span>

2. <span data-ttu-id="054e3-112">Nehmen Sie die gewünschten Änderungen an Memberwerten im resultierenden [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Objekt vor.</span><span class="sxs-lookup"><span data-stu-id="054e3-112">Make desired changes to member values in the resulting [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] object.</span></span>

3. <span data-ttu-id="054e3-113">Übergeben Sie die Änderungen an die Datenbank.</span><span class="sxs-lookup"><span data-stu-id="054e3-113">Submit the changes to the database.</span></span>

## <a name="example"></a><span data-ttu-id="054e3-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="054e3-114">Example</span></span>

<span data-ttu-id="054e3-115">Im folgenden Beispiel wird die Bestellung Nr. 11000 aus der Datenbank abgerufen. Anschließend werden die Werte für `ShipName` und `ShipVia` im resultierenden `Order`-Objekt geändert.</span><span class="sxs-lookup"><span data-stu-id="054e3-115">The following example queries the database for order #11000, and then changes the values of `ShipName` and `ShipVia` in the resulting `Order` object.</span></span> <span data-ttu-id="054e3-116">Schließlich werden die Änderungen an diesen Memberwerten als Änderungen in der `ShipName`-Spalte und der `ShipVia`-Spalte an die Datenbank übergeben.</span><span class="sxs-lookup"><span data-stu-id="054e3-116">Finally, the changes to these member values are submitted to the database as changes in the `ShipName` and `ShipVia` columns.</span></span>

[!code-csharp[System.Data.Linq.Table#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.table/cs/program.cs#2)]
[!code-vb[System.Data.Linq.Table#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.table/vb/module1.vb#2)]

## <a name="see-also"></a><span data-ttu-id="054e3-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="054e3-117">See also</span></span>

- [<span data-ttu-id="054e3-118">Vorgehensweise: Verwalten von Änderungs Konflikten</span><span class="sxs-lookup"><span data-stu-id="054e3-118">How to: Manage Change Conflicts</span></span>](how-to-manage-change-conflicts.md)
- [<span data-ttu-id="054e3-119">Vorgehensweise: Zuweisen von gespeicherten Prozeduren zum Durchführen von Aktionen zum Aktualisieren, Einfügen und Löschen (O/R-Designer)</span><span class="sxs-lookup"><span data-stu-id="054e3-119">How to: Assign stored procedures to perform updates, inserts, and deletes (O/R Designer)</span></span>](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)
- [<span data-ttu-id="054e3-120">Vornehmen und Übergeben von Datenänderungen</span><span class="sxs-lookup"><span data-stu-id="054e3-120">Making and Submitting Data Changes</span></span>](making-and-submitting-data-changes.md)
