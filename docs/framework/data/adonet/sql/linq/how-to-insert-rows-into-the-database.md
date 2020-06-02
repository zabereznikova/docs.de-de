---
title: 'Vorgehensweise: Einfügen von Zeilen in die Datenbank'
description: Erfahren Sie, wie Sie Zeilen in eine Datenbank einfügen, indem Sie LINQ to SQL Objekte zu einer Tabellen bezogenen Auflistung hinzufügen. LINQ to SQL übersetzt Ergänzungen in SQL INSERT-Befehle.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 44d99680-69c7-4879-a732-f6771b334211
ms.openlocfilehash: 39eee6edf59d2adb7de41efd88899050fbe69fd8
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286351"
---
# <a name="how-to-insert-rows-into-the-database"></a><span data-ttu-id="8b103-104">Vorgehensweise: Einfügen von Zeilen in die Datenbank</span><span class="sxs-lookup"><span data-stu-id="8b103-104">How to: Insert Rows Into the Database</span></span>

<span data-ttu-id="8b103-105">Sie fügen Zeilen in eine Datenbank ein, indem Sie der zugeordneten Auflistung Objekte hinzufügen [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Table%601> und dann die Änderungen an die Datenbank übermitteln.</span><span class="sxs-lookup"><span data-stu-id="8b103-105">You insert rows into a database by adding objects to the associated [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Table%601> collection and then submitting the changes to the database.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="8b103-106">übersetzt die Änderungen in die entsprechenden SQL- `INSERT` Befehle.</span><span class="sxs-lookup"><span data-stu-id="8b103-106">translates your changes into the appropriate SQL `INSERT` commands.</span></span>

> [!NOTE]
> <span data-ttu-id="8b103-107">Sie können [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Standardmethoden für die Datenbankoperationen `Insert`, `Update` und `Delete` überschreiben.</span><span class="sxs-lookup"><span data-stu-id="8b103-107">You can override [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] default methods for `Insert`, `Update`, and `Delete` database operations.</span></span> <span data-ttu-id="8b103-108">Weitere Informationen finden Sie unter [Anpassen von INSERT-, Update-und DELETE-Vorgängen](customizing-insert-update-and-delete-operations.md).</span><span class="sxs-lookup"><span data-stu-id="8b103-108">For more information, see [Customizing Insert, Update, and Delete Operations](customizing-insert-update-and-delete-operations.md).</span></span>
>
> <span data-ttu-id="8b103-109">Entwickler, die Visual Studio verwenden, können den objektrelationaler Designer verwenden, um gespeicherte Prozeduren für denselben Zweck zu entwickeln.</span><span class="sxs-lookup"><span data-stu-id="8b103-109">Developers using Visual Studio can use the Object Relational Designer to develop stored procedures for the same purpose.</span></span>

<span data-ttu-id="8b103-110">In den folgenden Schritten wird davon ausgegangen, dass Sie ein gültiger <xref:System.Data.Linq.DataContext> mit der Datenbank Northwind verbindet.</span><span class="sxs-lookup"><span data-stu-id="8b103-110">The following steps assume that a valid <xref:System.Data.Linq.DataContext> connects you to the Northwind database.</span></span> <span data-ttu-id="8b103-111">Weitere Informationen finden Sie unter Gewusst [wie: Herstellen einer Verbindung mit einer Datenbank](how-to-connect-to-a-database.md).</span><span class="sxs-lookup"><span data-stu-id="8b103-111">For more information, see [How to: Connect to a Database](how-to-connect-to-a-database.md).</span></span>

### <a name="to-insert-a-row-into-the-database"></a><span data-ttu-id="8b103-112">So fügen Sie eine Zeile in die Datenbank ein</span><span class="sxs-lookup"><span data-stu-id="8b103-112">To insert a row into the database</span></span>

1. <span data-ttu-id="8b103-113">Erstellen Sie ein neues Objekt, das die zu übermittelnden Spaltendaten enthält.</span><span class="sxs-lookup"><span data-stu-id="8b103-113">Create a new object that includes the column data to be submitted.</span></span>

2. <span data-ttu-id="8b103-114">Fügen Sie das neue-Objekt der-Auflistung hinzu, die [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] `Table` der Ziel Tabelle in der-Datenbank zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="8b103-114">Add the new object to the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] `Table` collection associated with the target table in the database.</span></span>

3. <span data-ttu-id="8b103-115">Übergeben Sie die Änderung an die Datenbank.</span><span class="sxs-lookup"><span data-stu-id="8b103-115">Submit the change to the database.</span></span>

## <a name="example"></a><span data-ttu-id="8b103-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8b103-116">Example</span></span>

<span data-ttu-id="8b103-117">Im folgenden Codebeispiel wird ein neues Objekt des Typs `Order` erstellt und mit entsprechenden Werten aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="8b103-117">The following code example creates a new object of type `Order` and populates it with appropriate values.</span></span> <span data-ttu-id="8b103-118">Anschließend wird das neue Objekt der `Order`-Auflistung hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="8b103-118">It then adds the new object to the `Order` collection.</span></span> <span data-ttu-id="8b103-119">Schließlich wird die Änderung an der Datenbank als neue Zeile in der `Orders`-Tabelle übergeben.</span><span class="sxs-lookup"><span data-stu-id="8b103-119">Finally, it submits the change to the database as a new row in the `Orders` table.</span></span>

[!code-csharp[System.Data.Linq.Table#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.table/cs/program.cs#1)]
[!code-vb[System.Data.Linq.Table#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.table/vb/module1.vb#1)]

## <a name="see-also"></a><span data-ttu-id="8b103-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8b103-120">See also</span></span>

- [<span data-ttu-id="8b103-121">Vorgehensweise: Verwalten von Änderungskonflikten</span><span class="sxs-lookup"><span data-stu-id="8b103-121">How to: Manage Change Conflicts</span></span>](how-to-manage-change-conflicts.md)
- [<span data-ttu-id="8b103-122">DataContext-Methoden (O/R-Designer)</span><span class="sxs-lookup"><span data-stu-id="8b103-122">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
- [<span data-ttu-id="8b103-123">Vorgehensweise: Zuweisen von gespeicherten Prozeduren zum Durchführen von Aktionen zum Aktualisieren, Einfügen und Löschen (O/R-Designer)</span><span class="sxs-lookup"><span data-stu-id="8b103-123">How to: Assign stored procedures to perform updates, inserts, and deletes (O/R Designer)</span></span>](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)
- [<span data-ttu-id="8b103-124">Vornehmen und Übergeben von Datenänderungen</span><span class="sxs-lookup"><span data-stu-id="8b103-124">Making and Submitting Data Changes</span></span>](making-and-submitting-data-changes.md)
