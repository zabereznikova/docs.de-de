---
title: Bearbeiten von Daten in einer "DataTable"
ms.date: 03/30/2017
ms.assetid: 5cb86d48-a987-4af4-80e0-8cc2c8373d62
ms.openlocfilehash: 83b1a4b6c0e477ac918a2bb4e454718fc58ece0b
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/31/2019
ms.locfileid: "70203495"
---
# <a name="manipulating-data-in-a-datatable"></a><span data-ttu-id="b297e-102">Bearbeiten von Daten in einer "DataTable"</span><span class="sxs-lookup"><span data-stu-id="b297e-102">Manipulating Data in a DataTable</span></span>
<span data-ttu-id="b297e-103">Nach dem Erstellen einer <xref:System.Data.DataTable> in einem <xref:System.Data.DataSet> können Sie die gleichen Aktionen ausführen, die Sie auch bei der Verwendung einer Tabelle in einer Datenbank ausführen würden.</span><span class="sxs-lookup"><span data-stu-id="b297e-103">After creating a <xref:System.Data.DataTable> in a <xref:System.Data.DataSet>, you can perform the same activities that you would when using a table in a database.</span></span> <span data-ttu-id="b297e-104">Sie können Daten in der Tabelle hinzufügen, anzeigen, bearbeiten und löschen, Fehler und Ereignisse überwachen und die Abfragen über die Daten in der Tabelle ausführen.</span><span class="sxs-lookup"><span data-stu-id="b297e-104">You can add, view, edit, and delete data in the table; you can monitor errors and events; and you can query the data in the table.</span></span> <span data-ttu-id="b297e-105">Wenn Sie Daten in einerDatentabelle ändern, können Sie auch überprüfen, ob die Änderungen korrekt sind, und feststellen, ob die Änderungen Programm gesteuert akzeptiert oder abgelehnt werden.</span><span class="sxs-lookup"><span data-stu-id="b297e-105">When modifying data in a **DataTable**, you can also verify whether the changes are accurate, and determine whether to programmatically accept or reject the changes.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b297e-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="b297e-106">In This Section</span></span>  
 [<span data-ttu-id="b297e-107">Hinzufügen von Daten zu einer DataTable</span><span class="sxs-lookup"><span data-stu-id="b297e-107">Adding Data to a DataTable</span></span>](adding-data-to-a-datatable.md)  
 <span data-ttu-id="b297e-108">Erläutert das Erstellen von neuen Zeilen und das anschließende Hinzufügen zu einer Tabelle.</span><span class="sxs-lookup"><span data-stu-id="b297e-108">Explains how to create new rows and add them to a table.</span></span>  
  
 [<span data-ttu-id="b297e-109">Anzeigen von Daten in einer DataTable</span><span class="sxs-lookup"><span data-stu-id="b297e-109">Viewing Data in a DataTable</span></span>](viewing-data-in-a-datatable.md)  
 <span data-ttu-id="b297e-110">Beschreibt, wie Sie auf die Daten in einer Zeile zugreifen (sowohl auf die ursprünglichen als auch die aktuellen Versionen der Daten).</span><span class="sxs-lookup"><span data-stu-id="b297e-110">Describes how to access the data in a row, including original and current versions of the data.</span></span>  
  
 [<span data-ttu-id="b297e-111">Load-Methode</span><span class="sxs-lookup"><span data-stu-id="b297e-111">The Load Method</span></span>](the-load-method.md)  
 <span data-ttu-id="b297e-112">Beschreibt die Verwendung der **Load** -Methode, um eine **Daten** Tabelle mit Zeilen zu füllen.</span><span class="sxs-lookup"><span data-stu-id="b297e-112">Describes the use of the **Load** method to fill a **DataTable** with rows.</span></span>  
  
 [<span data-ttu-id="b297e-113">Bearbeitungen von DataTable</span><span class="sxs-lookup"><span data-stu-id="b297e-113">DataTable Edits</span></span>](datatable-edits.md)  
 <span data-ttu-id="b297e-114">Erläutert, wie Sie die Daten in einer Zeile bearbeiten und die Änderungen in einer Zeile beispielsweise aussetzen können, bis die angeforderten Änderungen überprüft und übernommen wurden.</span><span class="sxs-lookup"><span data-stu-id="b297e-114">Explains how to modify the data in a row, including suspending the changes to a row until the proposed changes are verified and accepted.</span></span>  
  
 [<span data-ttu-id="b297e-115">Zeilenstatus und Zeilenversionen</span><span class="sxs-lookup"><span data-stu-id="b297e-115">Row States and Row Versions</span></span>](row-states-and-row-versions.md)  
 <span data-ttu-id="b297e-116">Stellt Informationen zu den unterschiedlichen Statusangaben für eine Zeile bereit.</span><span class="sxs-lookup"><span data-stu-id="b297e-116">Provides information about the different states of a row.</span></span>  
  
 [<span data-ttu-id="b297e-117">DataRow-Löschung</span><span class="sxs-lookup"><span data-stu-id="b297e-117">DataRow Deletion</span></span>](datarow-deletion.md)  
 <span data-ttu-id="b297e-118">Beschreibt, wie Sie eine Zeile aus einer Tabelle löschen.</span><span class="sxs-lookup"><span data-stu-id="b297e-118">Describes how to remove a row from a table.</span></span>  
  
 [<span data-ttu-id="b297e-119">Zeilenfehlerinformationen</span><span class="sxs-lookup"><span data-stu-id="b297e-119">Row Error Information</span></span>](row-error-information.md)  
 <span data-ttu-id="b297e-120">Beschreibt, wie Sie Fehlerinformationen, die zur Behebung von Problemen mit den Daten in einer Anwendung verwendet werden können, zeilenweise einfügen.</span><span class="sxs-lookup"><span data-stu-id="b297e-120">Explains how to insert error information per row, to help resolve problems with the data within an application.</span></span>  
  
 [<span data-ttu-id="b297e-121">AcceptChanges und RejectChanges</span><span class="sxs-lookup"><span data-stu-id="b297e-121">AcceptChanges and RejectChanges</span></span>](acceptchanges-and-rejectchanges.md)  
 <span data-ttu-id="b297e-122">Beschreibt, wie Änderungen in einer Zeile angenommen oder abgelehnt werden.</span><span class="sxs-lookup"><span data-stu-id="b297e-122">Explains how to accept or reject the changes made to a row.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b297e-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b297e-123">See also</span></span>

- [<span data-ttu-id="b297e-124">DataTables</span><span class="sxs-lookup"><span data-stu-id="b297e-124">DataTables</span></span>](datatables.md)
- [<span data-ttu-id="b297e-125">Behandeln von DataTable-Ereignissen</span><span class="sxs-lookup"><span data-stu-id="b297e-125">Handling DataTable Events</span></span>](handling-datatable-events.md)
- [<span data-ttu-id="b297e-126">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="b297e-126">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
