---
title: "\"DataSets\", \"DataTables\" und \"DataViews\""
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6d4c4b69-8919-4224-8a65-6cca1c61b48f
caps.latest.revision: 4
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: 5fe09601be7173fd1a9228dc090732ded7afdd90
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="datasets-datatables-and-dataviews"></a><span data-ttu-id="e62c5-102">"DataSets", "DataTables" und "DataViews"</span><span class="sxs-lookup"><span data-stu-id="e62c5-102">DataSets, DataTables, and DataViews</span></span>
<span data-ttu-id="e62c5-103">ADO.NET <xref:System.Data.DataSet> ist eine speicherresidente Darstellung von Daten, die – unabhängig von der darin enthaltenen Datenquelle – ein konsistentes relationales Programmiermodell bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="e62c5-103">The ADO.NET <xref:System.Data.DataSet> is a memory-resident representation of data that provides a consistent relational programming model regardless of the source of the data it contains.</span></span> <span data-ttu-id="e62c5-104">Ein <xref:System.Data.DataSet> stellt einen kompletten Satz aus Daten dar, einschließlich der Tabellen, die die Daten enthalten, ordnen und einschränken, sowie der Beziehungen zwischen den Tabellen.</span><span class="sxs-lookup"><span data-stu-id="e62c5-104">A <xref:System.Data.DataSet> represents a complete set of data including the tables that contain, order, and constrain the data, as well as the relationships between the tables.</span></span>  
  
 <span data-ttu-id="e62c5-105">Es gibt verschiedene Möglichkeiten, mit einem <xref:System.Data.DataSet> zu arbeiten, die unabhängig voneinander oder kombiniert angewendet werden können.</span><span class="sxs-lookup"><span data-stu-id="e62c5-105">There are several ways of working with a <xref:System.Data.DataSet>, which can be applied independently or in combination.</span></span> <span data-ttu-id="e62c5-106">Sie haben folgende Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="e62c5-106">You can:</span></span>  
  
-   <span data-ttu-id="e62c5-107">Sie können eine <xref:System.Data.DataTable>, eine <xref:System.Data.DataRelation> und eine <xref:System.Data.Constraint> innerhalb eines <xref:System.Data.DataSet> programmgesteuert erstellen und die Tabellen mit Daten füllen.</span><span class="sxs-lookup"><span data-stu-id="e62c5-107">Programmatically create a <xref:System.Data.DataTable>, <xref:System.Data.DataRelation>, and <xref:System.Data.Constraint> within a <xref:System.Data.DataSet> and populate the tables with data.</span></span>  
  
-   <span data-ttu-id="e62c5-108">Sie können das <xref:System.Data.DataSet> mithilfe eines `DataAdapter` mit Tabellen von Daten aus einer vorhandenen relationalen Datenquelle füllen.</span><span class="sxs-lookup"><span data-stu-id="e62c5-108">Populate the <xref:System.Data.DataSet> with tables of data from an existing relational data source using a `DataAdapter`.</span></span>  
  
-   <span data-ttu-id="e62c5-109">Sie können den Inhalt des <xref:System.Data.DataSet> mithilfe von XML laden und beibehalten.</span><span class="sxs-lookup"><span data-stu-id="e62c5-109">Load and persist the <xref:System.Data.DataSet> contents using XML.</span></span> <span data-ttu-id="e62c5-110">Weitere Informationen finden Sie unter [Using XML in a DataSet (Verwenden von XML in einem DataSet)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="e62c5-110">For more information, see [Using XML in a DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md).</span></span>  
  
 <span data-ttu-id="e62c5-111">Bei einem <xref:System.Data.DataSet> mit strikter Typbindung besteht auch die Möglichkeit, es mit einem XML-Webdienst zu übertragen.</span><span class="sxs-lookup"><span data-stu-id="e62c5-111">A strongly typed <xref:System.Data.DataSet> can also be transported using an XML Web service.</span></span> <span data-ttu-id="e62c5-112">Durch seinen Aufbau ist das <xref:System.Data.DataSet> ideal für die Übertragung von Daten mithilfe von XML-Webdiensten geeignet.</span><span class="sxs-lookup"><span data-stu-id="e62c5-112">The design of the <xref:System.Data.DataSet> makes it ideal for transporting data using XML Web services.</span></span> <span data-ttu-id="e62c5-113">Eine Übersicht über die XML-Webdienste finden Sie unter [XML Web Services Overview (Übersicht über XML-Webdienste)](http://msdn.microsoft.com/library/9db0c7b8-bca6-462b-9be5-f5f9a7f05a4d).</span><span class="sxs-lookup"><span data-stu-id="e62c5-113">For an overview of XML Web services, see [XML Web Services Overview](http://msdn.microsoft.com/library/9db0c7b8-bca6-462b-9be5-f5f9a7f05a4d).</span></span> <span data-ttu-id="e62c5-114">Ein Beispiel für die Nutzung von <xref:System.Data.DataSet> von einem XML-Webdienst aus finden Sie unter [Consuming a DataSet from an XML Web Service (Verwenden eines DataSets von einem XML-Webdienst aus)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/consuming-a-dataset-from-an-xml-web-service.md).</span><span class="sxs-lookup"><span data-stu-id="e62c5-114">For an example of consuming a <xref:System.Data.DataSet> from an XML Web service, see [Consuming a DataSet from an XML Web Service](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/consuming-a-dataset-from-an-xml-web-service.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e62c5-115">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="e62c5-115">In This Section</span></span>  
 [<span data-ttu-id="e62c5-116">Creating a DataSet (Erstellen eines DataSets)</span><span class="sxs-lookup"><span data-stu-id="e62c5-116">Creating a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-a-dataset.md)  
 <span data-ttu-id="e62c5-117">Beschreibt die Syntax zum Erstellen einer Instanz eines <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="e62c5-117">Describes the syntax for creating an instance of a <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="e62c5-118">Adding a DataTable to a DataSet (Hinzufügen einer DataTable zu einem DataSet)</span><span class="sxs-lookup"><span data-stu-id="e62c5-118">Adding a DataTable to a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/adding-a-datatable-to-a-dataset.md)  
 <span data-ttu-id="e62c5-119">Beschreibt das Erstellen sowie das Hinzufügen von Tabellen und Spalten zu einem <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="e62c5-119">Describes how to create and add tables and columns to a <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="e62c5-120">Adding DataRelations (Hinzufügen von DataRelations)</span><span class="sxs-lookup"><span data-stu-id="e62c5-120">Adding DataRelations</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/adding-datarelations.md)  
 <span data-ttu-id="e62c5-121">Beschreibt das Erstellen von Beziehungen zwischen Tabellen in einem <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="e62c5-121">Describes how to create relations between tables in a <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="e62c5-122">Navigating DataRelations (Navigieren in DataRelations)</span><span class="sxs-lookup"><span data-stu-id="e62c5-122">Navigating DataRelations</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/navigating-datarelations.md)  
 <span data-ttu-id="e62c5-123">Beschreibt, wie die Beziehungen zwischen Tabellen in einem <xref:System.Data.DataSet> dazu verwendet werden, untergeordnete oder übergeordnete Zeilen einer Beziehung zwischen über- und untergeordneten Tabellen zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="e62c5-123">Describes how to use the relations between tables in a <xref:System.Data.DataSet> to return the child or parent rows of a parent-child relationship.</span></span>  
  
 [<span data-ttu-id="e62c5-124">Merging DataSet Contents (Zusammenführen von DataSet-Inhalten)</span><span class="sxs-lookup"><span data-stu-id="e62c5-124">Merging DataSet Contents</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/merging-dataset-contents.md)  
 <span data-ttu-id="e62c5-125">Beschreibt, wie der Inhalt eines <xref:System.Data.DataSet>-Arrays, <xref:System.Data.DataTable>-Arrays oder <xref:System.Data.DataRow>-Arrays mit einem anderen <xref:System.Data.DataSet> zusammengeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e62c5-125">Describes how to merge the contents of one <xref:System.Data.DataSet>, <xref:System.Data.DataTable>, or <xref:System.Data.DataRow> array into another <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="e62c5-126">Copying DataSet Contents (Kopieren von DataSet-Inhalten)</span><span class="sxs-lookup"><span data-stu-id="e62c5-126">Copying DataSet Contents</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/copying-dataset-contents.md)  
 <span data-ttu-id="e62c5-127">Beschreibt das Erstellen einer Kopie eines <xref:System.Data.DataSet>, die ein Schema sowie angegebene Daten enthalten kann.</span><span class="sxs-lookup"><span data-stu-id="e62c5-127">Describes how to create a copy of a <xref:System.Data.DataSet> that can contain schema as well as specified data.</span></span>  
  
 [<span data-ttu-id="e62c5-128">Handling DataSet Events (Behandeln von DataSet-Ereignissen)</span><span class="sxs-lookup"><span data-stu-id="e62c5-128">Handling DataSet Events</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/handling-dataset-events.md)  
 <span data-ttu-id="e62c5-129">Beschreibt die Ereignisse eines <xref:System.Data.DataSet> und wie diese verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e62c5-129">Describes the events of a <xref:System.Data.DataSet> and how to use them.</span></span>  
  
 [<span data-ttu-id="e62c5-130">Typed DataSets (Typisierte DataSets)</span><span class="sxs-lookup"><span data-stu-id="e62c5-130">Typed DataSets</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md)  
 <span data-ttu-id="e62c5-131">Erläutert, was ein typisiertes <xref:System.Data.DataSet> ist, und wie es erstellt und verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e62c5-131">Discusses what a typed <xref:System.Data.DataSet> is and how to create and use it.</span></span>  
  
 [<span data-ttu-id="e62c5-132">DataTables</span><span class="sxs-lookup"><span data-stu-id="e62c5-132">DataTables</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 <span data-ttu-id="e62c5-133">Beschreibt das Erstellen einer <xref:System.Data.DataTable>, das Definieren des zugehörigen Schemas und das Bearbeiten von Daten.</span><span class="sxs-lookup"><span data-stu-id="e62c5-133">Describes how to create a <xref:System.Data.DataTable>, define the schema, and manipulate data.</span></span>  
  
 [<span data-ttu-id="e62c5-134">DataTableReaders</span><span class="sxs-lookup"><span data-stu-id="e62c5-134">DataTableReaders</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatablereaders.md)  
 <span data-ttu-id="e62c5-135">Beschreibt das Erstellen und Verwenden eines <xref:System.Data.DataTableReader>.</span><span class="sxs-lookup"><span data-stu-id="e62c5-135">Describes how to create and use a <xref:System.Data.DataTableReader>.</span></span>  
  
 [<span data-ttu-id="e62c5-136">DataViews</span><span class="sxs-lookup"><span data-stu-id="e62c5-136">DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)  
 <span data-ttu-id="e62c5-137">Beschreibt das Erstellen von und Arbeiten mit `DataViews` sowie das Arbeiten mit <xref:System.Data.DataView>-Ereignissen.</span><span class="sxs-lookup"><span data-stu-id="e62c5-137">Describes how to create and work with `DataViews` and work with <xref:System.Data.DataView> events.</span></span>  
  
 [<span data-ttu-id="e62c5-138">Using XML in a DataSet (Verwenden von XML in einem DataSet)</span><span class="sxs-lookup"><span data-stu-id="e62c5-138">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 <span data-ttu-id="e62c5-139">Beschreibt, wie das <xref:System.Data.DataSet> mit XML als Datenquelle interagiert, einschließlich des Ladens und Beibehaltens des Inhalts eines <xref:System.Data.DataSet> als XML-Daten.</span><span class="sxs-lookup"><span data-stu-id="e62c5-139">Describes how the <xref:System.Data.DataSet> interacts with XML as a data source, including loading and persisting the contents of a <xref:System.Data.DataSet> as XML data.</span></span>  
  
 [<span data-ttu-id="e62c5-140">Consuming a DataSet from an XML Web Service (Verwenden eines DataSets von einem XML-Webdienst aus)</span><span class="sxs-lookup"><span data-stu-id="e62c5-140">Consuming a DataSet from an XML Web Service</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/consuming-a-dataset-from-an-xml-web-service.md)  
 <span data-ttu-id="e62c5-141">Beschreibt, wie ein XML-Webdienst erstellt wird, der für die Übertragung von Daten ein <xref:System.Data.DataSet> verwendet.</span><span class="sxs-lookup"><span data-stu-id="e62c5-141">Describes how to create an XML Web service that uses a <xref:System.Data.DataSet> to transport data.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="e62c5-142">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="e62c5-142">Related Sections</span></span>  
 [<span data-ttu-id="e62c5-143">Neues in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="e62c5-143">What's New in ADO.NET</span></span>](../../../../../docs/framework/data/adonet/whats-new.md)  
 <span data-ttu-id="e62c5-144">Enthält eine Einführung in neue Funktionen von ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="e62c5-144">Introduces features that are new in ADO.NET.</span></span>  
  
 [<span data-ttu-id="e62c5-145">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="e62c5-145">ADO.NET Overview</span></span>](../../../../../docs/framework/data/adonet/ado-net-overview.md)  
 <span data-ttu-id="e62c5-146">Bietet eine Einführung in das Design und die Komponenten von ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="e62c5-146">Provides an introduction to the design and components of ADO.NET.</span></span>  
  
 [<span data-ttu-id="e62c5-147">Populating a DataSet from a DataAdapter (Auffüllen eines DataSets durch einen DataAdapter)</span><span class="sxs-lookup"><span data-stu-id="e62c5-147">Populating a DataSet from a DataAdapter</span></span>](../../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md)  
 <span data-ttu-id="e62c5-148">Beschreibt das Laden eines **DataSets** mit Daten aus einer Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="e62c5-148">Describes how to load a **DataSet** with data from a data source.</span></span>  
  
 [<span data-ttu-id="e62c5-149">Updating Data Sources with DataAdapters (Aktualisieren von Datenquellen mit DataAdapters)</span><span class="sxs-lookup"><span data-stu-id="e62c5-149">Updating Data Sources with DataAdapters</span></span>](../../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md)  
 <span data-ttu-id="e62c5-150">Beschreibt, wie Änderungen an Daten in einem **DataSet** auch in der Datenquelle vorgenommen werden können.</span><span class="sxs-lookup"><span data-stu-id="e62c5-150">Describes how to resolve changes to the data in a **DataSet** back to the data source.</span></span>  
  
 [<span data-ttu-id="e62c5-151">Adding Existing Constraints to a DataSet (Hinzufügen von vorhandenen Einschränkungen zu einem DataSet)</span><span class="sxs-lookup"><span data-stu-id="e62c5-151">Adding Existing Constraints to a DataSet</span></span>](../../../../../docs/framework/data/adonet/adding-existing-constraints-to-a-dataset.md)  
 <span data-ttu-id="e62c5-152">Beschreibt das Auffüllen eines **DataSets** mit Primärschlüsselinformationen aus einer Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="e62c5-152">Describes how to populate a **DataSet** with primary key information from a data source.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e62c5-153">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e62c5-153">See Also</span></span>  
 [<span data-ttu-id="e62c5-154">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="e62c5-154">ADO.NET</span></span>](../../../../../docs/framework/data/adonet/index.md)  
 [<span data-ttu-id="e62c5-155">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="e62c5-155">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
