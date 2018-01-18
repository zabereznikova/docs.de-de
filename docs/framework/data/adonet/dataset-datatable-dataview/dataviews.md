---
title: "\"DataViews\""
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0fe5dfa2-c1cd-435f-90b6-b4dd2e3ef34b
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: ad24de9fd003637d1c6e31841da209346a872143
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="dataviews"></a><span data-ttu-id="d4e3e-102">"DataViews"</span><span class="sxs-lookup"><span data-stu-id="d4e3e-102">DataViews</span></span>
<span data-ttu-id="d4e3e-103">Mit einer <xref:System.Data.DataView> können Sie verschiedene Ansichten der in einer <xref:System.Data.DataTable> gespeicherten Daten erstellen. Diese Funktion wird oft in Datenbindungsanwendungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="d4e3e-103">A <xref:System.Data.DataView> enables you to create different views of the data stored in a <xref:System.Data.DataTable>, a capability that is often used in data-binding applications.</span></span> <span data-ttu-id="d4e3e-104">Mit einem **"DataView"**, können Sie die Daten in einer Tabelle mit verschiedenen Sortierreihenfolgen verfügbar machen, und Sie können die Daten nach Zeilenstatus oder basierend auf einem Filterausdruck filtern.</span><span class="sxs-lookup"><span data-stu-id="d4e3e-104">Using a **DataView**, you can expose the data in a table with different sort orders, and you can filter the data by row state or based on a filter expression.</span></span>  
  
 <span data-ttu-id="d4e3e-105">Ein **"DataView"** enthält eine dynamische Ansicht der Daten in der zugrunde liegenden **DataTable**: Inhalt, Reihenfolge und Mitgliedschaft Änderungen wider, sobald sie auftreten.</span><span class="sxs-lookup"><span data-stu-id="d4e3e-105">A **DataView** provides a dynamic view of data in the underlying **DataTable**: the content, ordering, and membership reflect changes as they occur.</span></span> <span data-ttu-id="d4e3e-106">Dieses Verhalten unterscheidet sich von der **wählen** Methode der **DataTable**, welche gibt eine <xref:System.Data.DataRow> Arrays aus einer Tabelle auf der Basis von einer bestimmten Filters und/oder einer Sortierreihenfolge Reihenfolge: Thiscontent berücksichtigt Änderungen in der zugrunde liegende Tabelle, aber seine Mitgliedschaft und Reihenfolge bleiben statisch.</span><span class="sxs-lookup"><span data-stu-id="d4e3e-106">This behavior differs from the **Select** method of the **DataTable**, which returns a <xref:System.Data.DataRow> array from a table based on a particular filter and/or sort order: thiscontent reflects changes to the underlying table, but its membership and ordering remain static.</span></span> <span data-ttu-id="d4e3e-107">Die dynamischen Funktionen von der **DataView** ideal für datenbindungsanwendungen.</span><span class="sxs-lookup"><span data-stu-id="d4e3e-107">The dynamic capabilities of the **DataView** make it ideal for data-binding applications.</span></span>  
  
 <span data-ttu-id="d4e3e-108">Ein **DataView** bietet Ihnen eine dynamische Ansicht einer einzelnen Satz von Daten, ähnlich wie eine Datenbanksicht, zu dem Sie verschiedene Sortier- und Filterkriterien anwenden können.</span><span class="sxs-lookup"><span data-stu-id="d4e3e-108">A **DataView** provides you with a dynamic view of a single set of data, much like a database view, to which you can apply different sorting and filtering criteria.</span></span> <span data-ttu-id="d4e3e-109">Im Gegensatz zu einer Datenbanksicht jedoch eine **"DataView"** nicht als Tabelle behandelt werden und eine Ansicht der verknüpften Tabellen können nicht bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="d4e3e-109">Unlike a database view, however, a **DataView** cannot be treated as a table and cannot provide a view of joined tables.</span></span> <span data-ttu-id="d4e3e-110">Außerdem können Sie keine Spalten ausschließen, die in der Quelltabelle vorhanden sind, und auch keine Spalten (z. B. berechnete Spalten) anhängen, die nicht in der Quelltabelle vorliegen.</span><span class="sxs-lookup"><span data-stu-id="d4e3e-110">You also cannot exclude columns that exist in the source table, nor can you append columns, such as computational columns, that do not exist in the source table.</span></span>  
  
 <span data-ttu-id="d4e3e-111">Können Sie eine <xref:System.Data.DataView.DataViewManager%2A> zum Verwalten von ansichtseinstellungen für alle Tabellen in einem **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="d4e3e-111">You can use a <xref:System.Data.DataView.DataViewManager%2A> to manage view settings for all the tables in a **DataSet**.</span></span> <span data-ttu-id="d4e3e-112">Die **DataViewManager** bietet Ihnen eine bequeme Möglichkeit zum Verwalten von standardansichtseinstellungen für jede Tabelle.</span><span class="sxs-lookup"><span data-stu-id="d4e3e-112">The **DataViewManager** provides you with a convenient way to manage default view settings for each table.</span></span> <span data-ttu-id="d4e3e-113">Beim Binden ein Steuerelement an mehr als eine Tabelle mit einer **DataSet**, binden an einen **DataViewManager** die optimale Möglichkeit dar.</span><span class="sxs-lookup"><span data-stu-id="d4e3e-113">When binding a control to more than one table of a **DataSet**, binding to a **DataViewManager** is the ideal choice.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d4e3e-114">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="d4e3e-114">In This Section</span></span>  
 [<span data-ttu-id="d4e3e-115">Erstellen einer DataView</span><span class="sxs-lookup"><span data-stu-id="d4e3e-115">Creating a DataView</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-a-dataview.md)  
 <span data-ttu-id="d4e3e-116">Enthält Informationen zum Erstellen einer **"DataView"** für eine **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="d4e3e-116">Describes how to create a **DataView** for a **DataTable**.</span></span>  
  
 [<span data-ttu-id="d4e3e-117">Sortieren und Filtern von Daten</span><span class="sxs-lookup"><span data-stu-id="d4e3e-117">Sorting and Filtering Data</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/sorting-and-filtering-data.md)  
 <span data-ttu-id="d4e3e-118">Beschreibt, wie zum Festlegen der Eigenschaften von einer **"DataView"** zum Zurückgeben von Teilmengen von Datenzeilen bestimmte Filterkriterien erfüllen, oder um Daten in einer bestimmten Sortierreihenfolge zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="d4e3e-118">Describes how to set the properties of a **DataView** to return subsets of data rows meeting specific filter criteria, or to return data in a particular sort order.</span></span>  
  
 [<span data-ttu-id="d4e3e-119">DataRows und DataRowViews</span><span class="sxs-lookup"><span data-stu-id="d4e3e-119">DataRows and DataRowViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datarows-and-datarowviews.md)  
 <span data-ttu-id="d4e3e-120">Beschreibt, wie für den Datenzugriff verfügbar gemacht werden, indem Sie die **"DataView"**.</span><span class="sxs-lookup"><span data-stu-id="d4e3e-120">Describes how to access the data exposed by the **DataView**.</span></span>  
  
 [<span data-ttu-id="d4e3e-121">Suchen nach Zeilen</span><span class="sxs-lookup"><span data-stu-id="d4e3e-121">Finding Rows</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/finding-rows.md)  
 <span data-ttu-id="d4e3e-122">Beschreibt das Suchen einer bestimmten Zeile in einer **"DataView"**.</span><span class="sxs-lookup"><span data-stu-id="d4e3e-122">Describes how to find a particular row in a **DataView**.</span></span>  
  
 [<span data-ttu-id="d4e3e-123">ChildViews und Beziehungen</span><span class="sxs-lookup"><span data-stu-id="d4e3e-123">ChildViews and Relations</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/childviews-and-relations.md)  
 <span data-ttu-id="d4e3e-124">Enthält Informationen zum Erstellen von Ansichten von Daten aus einer hierarchischen Beziehung mit einer **"DataView"**.</span><span class="sxs-lookup"><span data-stu-id="d4e3e-124">Describes how to create views of data from a parent-child relationship using a **DataView**.</span></span>  
  
 [<span data-ttu-id="d4e3e-125">Ändern von DataViews</span><span class="sxs-lookup"><span data-stu-id="d4e3e-125">Modifying DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/modifying-dataviews.md)  
 <span data-ttu-id="d4e3e-126">Beschreibt, wie die Daten in der zugrunde liegenden ändern **DataTable** über die **"DataView"**, einschließlich aktivieren oder Deaktivieren von Updates.</span><span class="sxs-lookup"><span data-stu-id="d4e3e-126">Describes how to modify the data in the underlying **DataTable** via the **DataView**, including enabling or disabling updates.</span></span>  
  
 [<span data-ttu-id="d4e3e-127">Behandeln von DataView-Ereignissen</span><span class="sxs-lookup"><span data-stu-id="d4e3e-127">Handling DataView Events</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/handling-dataview-events.md)  
 <span data-ttu-id="d4e3e-128">Beschreibt, wie die **ListChanged** Ereignis benachrichtigt werden soll bei den Inhalt oder die Sortierung einer **"DataView"** wird aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="d4e3e-128">Describes how to use the **ListChanged** event to receive notification when the contents or order of a **DataView** is being updated.</span></span>  
  
 [<span data-ttu-id="d4e3e-129">Verwalten von DataViews</span><span class="sxs-lookup"><span data-stu-id="d4e3e-129">Managing DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/managing-dataviews.md)  
 <span data-ttu-id="d4e3e-130">Beschreibt, wie eine **DataViewManager** verwalten **"DataView"** Einstellungen für jede Tabelle in einer **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="d4e3e-130">Describes how to use a **DataViewManager** to manage **DataView** settings for each table in a **DataSet**.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="d4e3e-131">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="d4e3e-131">Related Sections</span></span>  
 [<span data-ttu-id="d4e3e-132">ASP.NET-Webanwendungen</span><span class="sxs-lookup"><span data-stu-id="d4e3e-132">ASP.NET Web Applications</span></span>](http://msdn.microsoft.com/en-us/a812d7b7-049e-4234-a4c2-6acf690301f6)  
 <span data-ttu-id="d4e3e-133">Stellt Übersichten und ausführliche schrittweise Anleitungen zum Erstellen von ASP.NET-Anwendungen, Web Forms und Web Services bereit.</span><span class="sxs-lookup"><span data-stu-id="d4e3e-133">Provides overviews and detailed, step-by-step procedures for creating ASP.NET applications, Web Forms, and Web Services.</span></span>  
  
 [<span data-ttu-id="d4e3e-134">Windows-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="d4e3e-134">Windows Applications</span></span>](http://msdn.microsoft.com/en-us/a6bb2180-09b1-4738-b9fd-7fb05fc92f23)  
 <span data-ttu-id="d4e3e-135">Stellt ausführliche Informationen zum Arbeiten mit Windows Forms und Konsolenanwendungen bereit.</span><span class="sxs-lookup"><span data-stu-id="d4e3e-135">Provides detailed information about working with Windows Forms and console applications.</span></span>  
  
 [<span data-ttu-id="d4e3e-136">DataSets, DataTables und DataViews</span><span class="sxs-lookup"><span data-stu-id="d4e3e-136">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 <span data-ttu-id="d4e3e-137">Beschreibt die **DataSet** Objekt und wie Sie es zum Verwalten von Anwendungsdaten verwenden können.</span><span class="sxs-lookup"><span data-stu-id="d4e3e-137">Describes the **DataSet** object and how you can use it to manage application data.</span></span>  
  
 [<span data-ttu-id="d4e3e-138">DataTables</span><span class="sxs-lookup"><span data-stu-id="d4e3e-138">DataTables</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 <span data-ttu-id="d4e3e-139">Beschreibt die **DataTable** -Objekt und wie Sie zum Verwalten von Anwendungsdaten allein oder als Teil der Verwendung einer **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="d4e3e-139">Describes the **DataTable** object and how you can use it to manage application data by itself or as part of a **DataSet**.</span></span>  
  
 [<span data-ttu-id="d4e3e-140">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="d4e3e-140">ADO.NET</span></span>](../../../../../docs/framework/data/adonet/index.md)  
 <span data-ttu-id="d4e3e-141">Beschreibt die ADO.NET-Architektur und -Komponenten und die Verwendung von ADO.NET zum Zugriff auf vorhandene Datenquellen und zum Verwalten von Anwendungsdaten.</span><span class="sxs-lookup"><span data-stu-id="d4e3e-141">Describes the ADO.NET architecture and components, and how to use ADO.NET to access existing data sources and manage application data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4e3e-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d4e3e-142">See Also</span></span>  
 [<span data-ttu-id="d4e3e-143">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="d4e3e-143">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
