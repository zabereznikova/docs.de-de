---
title: 'Vorgehensweise: Löschen von Zeilen aus der Datenbank'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2144c99b-8055-4080-a5c6-1ea14335e2a3
ms.openlocfilehash: 421735567c527ac9a70cc5eefdbd7570599faac7
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70782001"
---
# <a name="how-to-delete-rows-from-the-database"></a><span data-ttu-id="58420-102">Vorgehensweise: Löschen von Zeilen aus der Datenbank</span><span class="sxs-lookup"><span data-stu-id="58420-102">How to: Delete Rows From the Database</span></span>

<span data-ttu-id="58420-103">Sie können Zeilen in einer Datenbank löschen, indem Sie die [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] entsprechenden Objekte aus der Tabellen bezogenen Auflistung entfernen.</span><span class="sxs-lookup"><span data-stu-id="58420-103">You can delete rows in a database by removing the corresponding [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] objects from their table-related collection.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="58420-104">übersetzt die Änderungen in die entsprechenden SQL `DELETE` -Befehle.</span><span class="sxs-lookup"><span data-stu-id="58420-104">translates your changes to the appropriate SQL `DELETE` commands.</span></span>

<span data-ttu-id="58420-105">Kaskadierte Löschvorgänge werden von [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] nicht unterstützt bzw. erkannt.</span><span class="sxs-lookup"><span data-stu-id="58420-105">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] does not support or recognize cascade-delete operations.</span></span> <span data-ttu-id="58420-106">Wenn Sie eine Zeile in einer Tabelle löschen möchten, für die Einschränkungen gelten, führen Sie eines der folgenden Verfahren aus:</span><span class="sxs-lookup"><span data-stu-id="58420-106">If you want to delete a row in a table that has constraints against it, you must complete either of the following tasks:</span></span>

- <span data-ttu-id="58420-107">Legen Sie die `ON DELETE CASCADE`-Regel in der Fremdschlüsseleinschränkung in der Datenbank fest.</span><span class="sxs-lookup"><span data-stu-id="58420-107">Set the `ON DELETE CASCADE` rule in the foreign-key constraint in the database.</span></span>

- <span data-ttu-id="58420-108">Verwenden Sie eigenen Code, um zunächst die untergeordneten Objekte zu löschen, die das Löschen des übergeordneten Objekts verhindern.</span><span class="sxs-lookup"><span data-stu-id="58420-108">Use your own code to first delete the child objects that prevent the parent object from being deleted.</span></span>

 <span data-ttu-id="58420-109">Andernfalls wird eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="58420-109">Otherwise, an exception is thrown.</span></span> <span data-ttu-id="58420-110">Siehe das zweite Codebeispiel weiter unten in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="58420-110">See the second code example later in this topic.</span></span>

> [!NOTE]
> <span data-ttu-id="58420-111">Sie können [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Standardmethoden für die Datenbankoperationen `Insert`, `Update` und `Delete` überschreiben.</span><span class="sxs-lookup"><span data-stu-id="58420-111">You can override [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] default methods for `Insert`, `Update`, and `Delete` database operations.</span></span> <span data-ttu-id="58420-112">Weitere Informationen finden Sie unter [Anpassen von INSERT-, Update-und DELETE-Vorgängen](customizing-insert-update-and-delete-operations.md).</span><span class="sxs-lookup"><span data-stu-id="58420-112">For more information, see [Customizing Insert, Update, and Delete Operations](customizing-insert-update-and-delete-operations.md).</span></span>
>
> <span data-ttu-id="58420-113">Entwickler, die Visual Studio verwenden, können den objektrelationaler Designer verwenden, um gespeicherte Prozeduren für denselben Zweck zu entwickeln.</span><span class="sxs-lookup"><span data-stu-id="58420-113">Developers using Visual Studio can use the Object Relational Designer to develop stored procedures for the same purpose.</span></span>

<span data-ttu-id="58420-114">In den folgenden Schritten wird davon ausgegangen, dass Sie ein gültiger <xref:System.Data.Linq.DataContext> mit der Datenbank Northwind verbindet.</span><span class="sxs-lookup"><span data-stu-id="58420-114">The following steps assume that a valid <xref:System.Data.Linq.DataContext> connects you to the Northwind database.</span></span> <span data-ttu-id="58420-115">Weitere Informationen finden Sie unter [Vorgehensweise: Verbindung mit einer Datenbank](how-to-connect-to-a-database.md)herstellen.</span><span class="sxs-lookup"><span data-stu-id="58420-115">For more information, see [How to: Connect to a Database](how-to-connect-to-a-database.md).</span></span>

### <a name="to-delete-a-row-in-the-database"></a><span data-ttu-id="58420-116">So löschen Sie eine Zeile aus der Datenbank</span><span class="sxs-lookup"><span data-stu-id="58420-116">To delete a row in the database</span></span>

1. <span data-ttu-id="58420-117">Rufen Sie die zu löschende Zeile aus der Datenbank ab.</span><span class="sxs-lookup"><span data-stu-id="58420-117">Query the database for the row to be deleted.</span></span>

2. <span data-ttu-id="58420-118">Rufen Sie die <xref:System.Data.Linq.Table%601.DeleteOnSubmit%2A>-Methode auf.</span><span class="sxs-lookup"><span data-stu-id="58420-118">Call the <xref:System.Data.Linq.Table%601.DeleteOnSubmit%2A> method.</span></span>

3. <span data-ttu-id="58420-119">Übergeben Sie die Änderung an die Datenbank.</span><span class="sxs-lookup"><span data-stu-id="58420-119">Submit the change to the database.</span></span>

## <a name="example"></a><span data-ttu-id="58420-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="58420-120">Example</span></span>

<span data-ttu-id="58420-121">Im ersten Codebeispiel wird die Datenbank nach Bestelldetails durchsucht, die sich auf die Bestellung 11000 beziehen. Diese Bestelldetails werden dann zum Löschen markiert und diese Änderungen an die Datenbank übergeben.</span><span class="sxs-lookup"><span data-stu-id="58420-121">This first code example queries the database for order details that belong to Order #11000, marks these order details for deletion, and submits these changes to the database.</span></span>

[!code-csharp[System.Data.Linq.Table#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.table/cs/program.cs#3)]
[!code-vb[System.Data.Linq.Table#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.table/vb/module1.vb#3)]

## <a name="example"></a><span data-ttu-id="58420-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="58420-122">Example</span></span>

<span data-ttu-id="58420-123">In diesem zweiten Beispiel besteht das Ziel darin, eine Bestellung (10250) zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="58420-123">In this second example, the objective is to remove an order (#10250).</span></span> <span data-ttu-id="58420-124">Der Code durchsucht zunächst die `OrderDetails`-Tabelle, um zu prüfen, ob die zu entfernende Bestellung untergeordnete Elemente enthält.</span><span class="sxs-lookup"><span data-stu-id="58420-124">The code first examines the `OrderDetails` table to see whether the order to be removed has children there.</span></span> <span data-ttu-id="58420-125">Wenn die Bestellung untergeordnete Elemente enthält, werden zunächst die untergeordneten Elemente und dann die Bestellung zum Entfernen markiert.</span><span class="sxs-lookup"><span data-stu-id="58420-125">If the order has children, first the children and then the order are marked for removal.</span></span> <span data-ttu-id="58420-126"><xref:System.Data.Linq.DataContext> bringt die tatsächlichen Löschvorgänge in die richtige Reihenfolge, sodass die an die Datenbank übertragenen Löschbefehle die Datenbankbeschränkungen erfüllen.</span><span class="sxs-lookup"><span data-stu-id="58420-126">The <xref:System.Data.Linq.DataContext> puts the actual deletes in correct order so that delete commands sent to the database abide by the database constraints.</span></span>

[!code-csharp[DLinqCascadeWorkaround#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCascadeWorkaround/cs/Program.cs#1)]
[!code-vb[DLinqCascadeWorkaround#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCascadeWorkaround/vb/Module1.vb#1)]

## <a name="see-also"></a><span data-ttu-id="58420-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="58420-127">See also</span></span>

- [<span data-ttu-id="58420-128">Vorgehensweise: Verwalten von Änderungs Konflikten</span><span class="sxs-lookup"><span data-stu-id="58420-128">How to: Manage Change Conflicts</span></span>](how-to-manage-change-conflicts.md)
- [<span data-ttu-id="58420-129">Vorgehensweise: Zuweisen von gespeicherten Prozeduren zum Durchführen von Aktionen zum Aktualisieren, Einfügen und Löschen (O/R-Designer)</span><span class="sxs-lookup"><span data-stu-id="58420-129">How to: Assign stored procedures to perform updates, inserts, and deletes (O/R Designer)</span></span>](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)
- [<span data-ttu-id="58420-130">Vornehmen und Übergeben von Datenänderungen</span><span class="sxs-lookup"><span data-stu-id="58420-130">Making and Submitting Data Changes</span></span>](making-and-submitting-data-changes.md)
