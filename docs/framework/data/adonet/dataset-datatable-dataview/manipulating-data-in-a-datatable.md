---
title: Bearbeiten von Daten in einer "DataTable"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5cb86d48-a987-4af4-80e0-8cc2c8373d62
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: eb4ecf8996836fde443216f1d9225e8f113b0b7f
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="manipulating-data-in-a-datatable"></a><span data-ttu-id="b6ee3-102">Bearbeiten von Daten in einer "DataTable"</span><span class="sxs-lookup"><span data-stu-id="b6ee3-102">Manipulating Data in a DataTable</span></span>
<span data-ttu-id="b6ee3-103">Nach dem Erstellen einer <xref:System.Data.DataTable> in einem <xref:System.Data.DataSet> können Sie die gleichen Aktionen ausführen, die Sie auch bei der Verwendung einer Tabelle in einer Datenbank ausführen würden.</span><span class="sxs-lookup"><span data-stu-id="b6ee3-103">After creating a <xref:System.Data.DataTable> in a <xref:System.Data.DataSet>, you can perform the same activities that you would when using a table in a database.</span></span> <span data-ttu-id="b6ee3-104">Sie können Daten in der Tabelle hinzufügen, anzeigen, bearbeiten und löschen, Fehler und Ereignisse überwachen und die Abfragen über die Daten in der Tabelle ausführen.</span><span class="sxs-lookup"><span data-stu-id="b6ee3-104">You can add, view, edit, and delete data in the table; you can monitor errors and events; and you can query the data in the table.</span></span> <span data-ttu-id="b6ee3-105">Beim Ändern von Daten in einem **DataTable**, Sie können auch überprüfen, ob die Änderungen stimmen und bestimmen, ob programmgesteuert akzeptieren oder Ablehnen der Änderungen.</span><span class="sxs-lookup"><span data-stu-id="b6ee3-105">When modifying data in a **DataTable**, you can also verify whether the changes are accurate, and determine whether to programmatically accept or reject the changes.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b6ee3-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="b6ee3-106">In This Section</span></span>  
 [<span data-ttu-id="b6ee3-107">Hinzufügen von Daten zu einer DataTable</span><span class="sxs-lookup"><span data-stu-id="b6ee3-107">Adding Data to a DataTable</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/adding-data-to-a-datatable.md)  
 <span data-ttu-id="b6ee3-108">Erläutert das Erstellen von neuen Zeilen und das anschließende Hinzufügen zu einer Tabelle.</span><span class="sxs-lookup"><span data-stu-id="b6ee3-108">Explains how to create new rows and add them to a table.</span></span>  
  
 [<span data-ttu-id="b6ee3-109">Anzeigen von Daten in einer DataTable</span><span class="sxs-lookup"><span data-stu-id="b6ee3-109">Viewing Data in a DataTable</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/viewing-data-in-a-datatable.md)  
 <span data-ttu-id="b6ee3-110">Beschreibt, wie Sie auf die Daten in einer Zeile zugreifen (sowohl auf die ursprünglichen als auch die aktuellen Versionen der Daten).</span><span class="sxs-lookup"><span data-stu-id="b6ee3-110">Describes how to access the data in a row, including original and current versions of the data.</span></span>  
  
 [<span data-ttu-id="b6ee3-111">Load-Methode</span><span class="sxs-lookup"><span data-stu-id="b6ee3-111">The Load Method</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/the-load-method.md)  
 <span data-ttu-id="b6ee3-112">Beschreibt die Verwendung von der **laden** zu füllende Methode eine **DataTable** mit Zeilen.</span><span class="sxs-lookup"><span data-stu-id="b6ee3-112">Describes the use of the **Load** method to fill a **DataTable** with rows.</span></span>  
  
 [<span data-ttu-id="b6ee3-113">Bearbeitungen von DataTable</span><span class="sxs-lookup"><span data-stu-id="b6ee3-113">DataTable Edits</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-edits.md)  
 <span data-ttu-id="b6ee3-114">Erläutert, wie Sie die Daten in einer Zeile bearbeiten und die Änderungen in einer Zeile beispielsweise aussetzen können, bis die angeforderten Änderungen überprüft und übernommen wurden.</span><span class="sxs-lookup"><span data-stu-id="b6ee3-114">Explains how to modify the data in a row, including suspending the changes to a row until the proposed changes are verified and accepted.</span></span>  
  
 [<span data-ttu-id="b6ee3-115">Zeilenstatus und Zeilenversionen</span><span class="sxs-lookup"><span data-stu-id="b6ee3-115">Row States and Row Versions</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md)  
 <span data-ttu-id="b6ee3-116">Stellt Informationen zu den unterschiedlichen Statusangaben für eine Zeile bereit.</span><span class="sxs-lookup"><span data-stu-id="b6ee3-116">Provides information about the different states of a row.</span></span>  
  
 [<span data-ttu-id="b6ee3-117">DataRow-Löschung</span><span class="sxs-lookup"><span data-stu-id="b6ee3-117">DataRow Deletion</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datarow-deletion.md)  
 <span data-ttu-id="b6ee3-118">	Beschreibt, wie Sie eine Zeile aus einer Tabelle löschen.</span><span class="sxs-lookup"><span data-stu-id="b6ee3-118">Describes how to remove a row from a table.</span></span>  
  
 [<span data-ttu-id="b6ee3-119">Zeilenfehlerinformationen</span><span class="sxs-lookup"><span data-stu-id="b6ee3-119">Row Error Information</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-error-information.md)  
 <span data-ttu-id="b6ee3-120">Beschreibt, wie Sie Fehlerinformationen, die zur Behebung von Problemen mit den Daten in einer Anwendung verwendet werden können, zeilenweise einfügen.</span><span class="sxs-lookup"><span data-stu-id="b6ee3-120">Explains how to insert error information per row, to help resolve problems with the data within an application.</span></span>  
  
 [<span data-ttu-id="b6ee3-121">AcceptChanges und RejectChanges</span><span class="sxs-lookup"><span data-stu-id="b6ee3-121">AcceptChanges and RejectChanges</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/acceptchanges-and-rejectchanges.md)  
 <span data-ttu-id="b6ee3-122">Beschreibt, wie Änderungen in einer Zeile angenommen oder abgelehnt werden.</span><span class="sxs-lookup"><span data-stu-id="b6ee3-122">Explains how to accept or reject the changes made to a row.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6ee3-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b6ee3-123">See Also</span></span>  
 [<span data-ttu-id="b6ee3-124">DataTables</span><span class="sxs-lookup"><span data-stu-id="b6ee3-124">DataTables</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 [<span data-ttu-id="b6ee3-125">Behandeln von DataTable-Ereignissen</span><span class="sxs-lookup"><span data-stu-id="b6ee3-125">Handling DataTable Events</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/handling-datatable-events.md)  
 [<span data-ttu-id="b6ee3-126">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="b6ee3-126">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
