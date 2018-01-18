---
title: Insert-, Update- und Delete-Operationen
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
ms.assetid: 26a43a4f-83c9-4732-806d-bb23aad0ff6b
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 51af1dad545f6ac948b17d1bdbd39bfc688c7f11
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="insert-update-and-delete-operations"></a><span data-ttu-id="69009-102">Insert-, Update- und Delete-Operationen</span><span class="sxs-lookup"><span data-stu-id="69009-102">Insert, Update, and Delete Operations</span></span>
<span data-ttu-id="69009-103">Sie führen die Operationen `Insert`, `Update` und `Delete` in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] aus, indem Sie Objekte dem Objektmodell hinzufügen, diese ändern oder entfernen.</span><span class="sxs-lookup"><span data-stu-id="69009-103">You perform `Insert`, `Update`, and `Delete` operations in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] by adding, changing, and removing objects in your object model.</span></span> <span data-ttu-id="69009-104">Standardmäßig übersetzt [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Ihre Aktionen in SQL und übergibt die Änderungen an die Datenbank.</span><span class="sxs-lookup"><span data-stu-id="69009-104">By default, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] translates your actions to SQL and submits the changes to the database.</span></span>  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="69009-105">bietet maximale Flexibilität beim Bearbeiten von und an Ihren Objekten vorgenommenen Änderungen beibehalten.</span><span class="sxs-lookup"><span data-stu-id="69009-105"> offers maximum flexibility in manipulating and persisting changes that you made to your objects.</span></span> <span data-ttu-id="69009-106">Sobald Entitätsobjekte zur Verfügung stehen (entweder durch Abrufen in einer Abfrage oder durch Neuzusammenstellung), können Sie diese wie typische Objekte in Ihrer Anwendung ändern.</span><span class="sxs-lookup"><span data-stu-id="69009-106">As soon as entity objects are available (either by retrieving them through a query or by constructing them anew), you can change them as typical objects in your application.</span></span> <span data-ttu-id="69009-107">D. h. Sie deren Werte ändern, Auflistungen hinzufügen und können sie aus Ihren Sammlungen entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="69009-107">That is, you can change their values, you can add them to your collections, and you can remove them from your collections.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="69009-108"> verfolgt Ihre Änderungen und kann diese zurück in die Datenbank übertragen, wenn Sie <xref:System.Data.Linq.DataContext.SubmitChanges%2A> aufrufen.</span><span class="sxs-lookup"><span data-stu-id="69009-108"> tracks your changes and is ready to transmit them back to the database when you call <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="69009-109">Kaskadierte Löschvorgänge werden von [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] nicht unterstützt bzw. erkannt.</span><span class="sxs-lookup"><span data-stu-id="69009-109">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] does not support or recognize cascade-delete operations.</span></span> <span data-ttu-id="69009-110">Wenn eine Zeile in einer Tabelle zu löschen, die Einschränkungen gelten sollen, müssen Sie entweder die `ON DELETE CASCADE` -Regel in der foreign Key-Einschränkung in der Datenbank, oder verwenden Sie eigenen Code zunächst die untergeordneten Objekte löschen, die verhindern, dass das übergeordnete Objekt gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="69009-110">If you want to delete a row in a table that has constraints against it, you must either set the `ON DELETE CASCADE` rule in the foreign-key constraint in the database, or use your own code to first delete the child objects that prevent the parent object from being deleted.</span></span> <span data-ttu-id="69009-111">Andernfalls wird eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="69009-111">Otherwise, an exception is thrown.</span></span> <span data-ttu-id="69009-112">Weitere Informationen finden Sie unter [Vorgehensweise: Löschen von Zeilen aus der Datenbank](../../../../../../docs/framework/data/adonet/sql/linq/how-to-delete-rows-from-the-database.md).</span><span class="sxs-lookup"><span data-stu-id="69009-112">For more information, see [How to: Delete Rows From the Database](../../../../../../docs/framework/data/adonet/sql/linq/how-to-delete-rows-from-the-database.md).</span></span>  
  
 <span data-ttu-id="69009-113">Die folgenden Auszüge verwenden die `Customer`-Klasse und die `Order`-Klasse aus der Beispieldatenbank Northwind.</span><span class="sxs-lookup"><span data-stu-id="69009-113">The following excerpts use the `Customer` and `Order` classes from the Northwind sample database.</span></span> <span data-ttu-id="69009-114">Klassendefinitionen werden zur besseren Übersicht nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="69009-114">Class definitions are not shown for brevity.</span></span>  
  
 [!code-csharp[DLinqCRUDOps#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCRUDOps/cs/Program.cs#1)]
 [!code-vb[DLinqCRUDOps#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCRUDOps/vb/Module1.vb#1)]  
  
 <span data-ttu-id="69009-115">Wenn Sie <xref:System.Data.Linq.DataContext.SubmitChanges%2A> aufrufen, übernimmt [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] automatisch die Erzeugung und Ausführung der SQL-Befehle, die zur Übertragung Ihrer Änderungen in die Datenbank erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="69009-115">When you call <xref:System.Data.Linq.DataContext.SubmitChanges%2A>, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] automatically generates and executes the SQL commands that it must have to transmit your changes back to the database.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="69009-116">Sie können dieses Verhalten überschreiben, indem Sie Ihre eigene Logik verwenden (typischerweise in Form einer gespeicherten Prozedur).</span><span class="sxs-lookup"><span data-stu-id="69009-116">You can override this behavior by using your own custom logic, typically by way of a stored procedure.</span></span> <span data-ttu-id="69009-117">Weitere Informationen finden Sie unter [Aufgaben der Entwickler beim Überschreiben von Standardverhalten](../../../../../../docs/framework/data/adonet/sql/linq/responsibilities-of-the-developer-in-overriding-default-behavior.md).</span><span class="sxs-lookup"><span data-stu-id="69009-117">For more information, see [Responsibilities of the Developer In Overriding Default Behavior](../../../../../../docs/framework/data/adonet/sql/linq/responsibilities-of-the-developer-in-overriding-default-behavior.md).</span></span>  
>   
>  <span data-ttu-id="69009-118">Entwickler, die mit [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] arbeiten, können mithilfe von [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] gespeicherte Prozeduren zu diesem Zweck entwickeln.</span><span class="sxs-lookup"><span data-stu-id="69009-118">Developers using [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] can use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to develop stored procedures for this purpose.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69009-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="69009-119">See Also</span></span>  
 [<span data-ttu-id="69009-120">Downloading Sample Databases (Herunterladen von Beispieldatenbanken)</span><span class="sxs-lookup"><span data-stu-id="69009-120">Downloading Sample Databases</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)  
 [<span data-ttu-id="69009-121">Anpassen von Insert-, Update- und Delete-Operationen</span><span class="sxs-lookup"><span data-stu-id="69009-121">Customizing Insert, Update, and Delete Operations</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md)
