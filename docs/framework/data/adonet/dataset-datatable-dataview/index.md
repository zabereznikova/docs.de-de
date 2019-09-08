---
title: "\"DataSets\", \"DataTables\" und \"DataViews\""
ms.date: 03/30/2017
ms.assetid: 6d4c4b69-8919-4224-8a65-6cca1c61b48f
ms.openlocfilehash: 1744f6c6d8ea3c28a8dab30c0d201ae1dacc7ee3
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70786194"
---
# <a name="datasets-datatables-and-dataviews"></a><span data-ttu-id="adccd-102">"DataSets", "DataTables" und "DataViews"</span><span class="sxs-lookup"><span data-stu-id="adccd-102">DataSets, DataTables, and DataViews</span></span>
<span data-ttu-id="adccd-103">ADO.NET <xref:System.Data.DataSet> ist eine speicherresidente Darstellung von Daten, die – unabhängig von der darin enthaltenen Datenquelle – ein konsistentes relationales Programmiermodell bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="adccd-103">The ADO.NET <xref:System.Data.DataSet> is a memory-resident representation of data that provides a consistent relational programming model regardless of the source of the data it contains.</span></span> <span data-ttu-id="adccd-104">Ein <xref:System.Data.DataSet> stellt einen kompletten Satz aus Daten dar, einschließlich der Tabellen, die die Daten enthalten, anordnen und einschränken, sowie der Beziehungen zwischen den Tabellen.</span><span class="sxs-lookup"><span data-stu-id="adccd-104">A <xref:System.Data.DataSet> represents a complete set of data including the tables that contain, order, and constrain the data, as well as the relationships between the tables.</span></span>  
  
 <span data-ttu-id="adccd-105">Es gibt verschiedene Möglichkeiten, mit einem <xref:System.Data.DataSet> zu arbeiten, die unabhängig voneinander oder kombiniert angewendet werden können.</span><span class="sxs-lookup"><span data-stu-id="adccd-105">There are several ways of working with a <xref:System.Data.DataSet>, which can be applied independently or in combination.</span></span> <span data-ttu-id="adccd-106">Sie haben folgende Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="adccd-106">You can:</span></span>  
  
- <span data-ttu-id="adccd-107">Sie können eine <xref:System.Data.DataTable>, eine <xref:System.Data.DataRelation> und eine <xref:System.Data.Constraint> innerhalb eines <xref:System.Data.DataSet> programmgesteuert erstellen und die Tabellen mit Daten füllen.</span><span class="sxs-lookup"><span data-stu-id="adccd-107">Programmatically create a <xref:System.Data.DataTable>, <xref:System.Data.DataRelation>, and <xref:System.Data.Constraint> within a <xref:System.Data.DataSet> and populate the tables with data.</span></span>  
  
- <span data-ttu-id="adccd-108">Sie können das <xref:System.Data.DataSet> mithilfe eines `DataAdapter` mit Tabellen von Daten aus einer vorhandenen relationalen Datenquelle füllen.</span><span class="sxs-lookup"><span data-stu-id="adccd-108">Populate the <xref:System.Data.DataSet> with tables of data from an existing relational data source using a `DataAdapter`.</span></span>  
  
- <span data-ttu-id="adccd-109">Sie können den Inhalt des <xref:System.Data.DataSet> mithilfe von XML laden und beibehalten.</span><span class="sxs-lookup"><span data-stu-id="adccd-109">Load and persist the <xref:System.Data.DataSet> contents using XML.</span></span> <span data-ttu-id="adccd-110">Weitere Informationen finden Sie unter [Using XML in a DataSet (Verwenden von XML in einem DataSet)](using-xml-in-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="adccd-110">For more information, see [Using XML in a DataSet](using-xml-in-a-dataset.md).</span></span>  
  
 <span data-ttu-id="adccd-111">Bei einem <xref:System.Data.DataSet> mit strikter Typbindung besteht auch die Möglichkeit, es mit einem XML-Webdienst zu übertragen.</span><span class="sxs-lookup"><span data-stu-id="adccd-111">A strongly typed <xref:System.Data.DataSet> can also be transported using an XML Web service.</span></span> <span data-ttu-id="adccd-112">Durch seinen Aufbau ist das <xref:System.Data.DataSet> ideal für die Übertragung von Daten mithilfe von XML-Webdiensten geeignet.</span><span class="sxs-lookup"><span data-stu-id="adccd-112">The design of the <xref:System.Data.DataSet> makes it ideal for transporting data using XML Web services.</span></span> <span data-ttu-id="adccd-113">Eine Übersicht über die XML-Webdienste finden Sie unter [XML Web Services Overview (Übersicht über XML-Webdienste)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/w9fdtx28(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="adccd-113">For an overview of XML Web services, see [XML Web Services Overview](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/w9fdtx28(v=vs.100)).</span></span> <span data-ttu-id="adccd-114">Ein Beispiel für die Nutzung von <xref:System.Data.DataSet> von einem XML-Webdienst aus finden Sie unter [Consuming a DataSet from an XML Web Service (Verwenden eines DataSets von einem XML-Webdienst aus)](consuming-a-dataset-from-an-xml-web-service.md).</span><span class="sxs-lookup"><span data-stu-id="adccd-114">For an example of consuming a <xref:System.Data.DataSet> from an XML Web service, see [Consuming a DataSet from an XML Web Service](consuming-a-dataset-from-an-xml-web-service.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="adccd-115">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="adccd-115">In This Section</span></span>  
 [<span data-ttu-id="adccd-116">Creating a DataSet (Erstellen eines DataSets)</span><span class="sxs-lookup"><span data-stu-id="adccd-116">Creating a DataSet</span></span>](creating-a-dataset.md)  
 <span data-ttu-id="adccd-117">Beschreibt die Syntax zum Erstellen einer Instanz eines <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="adccd-117">Describes the syntax for creating an instance of a <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="adccd-118">Adding a DataTable to a DataSet (Hinzufügen einer DataTable zu einem DataSet)</span><span class="sxs-lookup"><span data-stu-id="adccd-118">Adding a DataTable to a DataSet</span></span>](adding-a-datatable-to-a-dataset.md)  
 <span data-ttu-id="adccd-119">Beschreibt das Erstellen sowie das Hinzufügen von Tabellen und Spalten zu einem <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="adccd-119">Describes how to create and add tables and columns to a <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="adccd-120">Adding DataRelations (Hinzufügen von DataRelations)</span><span class="sxs-lookup"><span data-stu-id="adccd-120">Adding DataRelations</span></span>](adding-datarelations.md)  
 <span data-ttu-id="adccd-121">Beschreibt das Erstellen von Beziehungen zwischen Tabellen in einem <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="adccd-121">Describes how to create relations between tables in a <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="adccd-122">Navigating DataRelations (Navigieren in DataRelations)</span><span class="sxs-lookup"><span data-stu-id="adccd-122">Navigating DataRelations</span></span>](navigating-datarelations.md)  
 <span data-ttu-id="adccd-123">Beschreibt, wie die Beziehungen zwischen Tabellen in einem <xref:System.Data.DataSet> dazu verwendet werden, untergeordnete oder übergeordnete Zeilen einer Beziehung zwischen über- und untergeordneten Tabellen zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="adccd-123">Describes how to use the relations between tables in a <xref:System.Data.DataSet> to return the child or parent rows of a parent-child relationship.</span></span>  
  
 [<span data-ttu-id="adccd-124">Merging DataSet Contents (Zusammenführen von DataSet-Inhalten)</span><span class="sxs-lookup"><span data-stu-id="adccd-124">Merging DataSet Contents</span></span>](merging-dataset-contents.md)  
 <span data-ttu-id="adccd-125">Beschreibt, wie der Inhalt eines <xref:System.Data.DataSet>-Arrays, <xref:System.Data.DataTable>-Arrays oder <xref:System.Data.DataRow>-Arrays mit einem anderen <xref:System.Data.DataSet> zusammengeführt wird.</span><span class="sxs-lookup"><span data-stu-id="adccd-125">Describes how to merge the contents of one <xref:System.Data.DataSet>, <xref:System.Data.DataTable>, or <xref:System.Data.DataRow> array into another <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="adccd-126">Copying DataSet Contents (Kopieren von DataSet-Inhalten)</span><span class="sxs-lookup"><span data-stu-id="adccd-126">Copying DataSet Contents</span></span>](copying-dataset-contents.md)  
 <span data-ttu-id="adccd-127">Beschreibt das Erstellen einer Kopie eines <xref:System.Data.DataSet>, die ein Schema sowie angegebene Daten enthalten kann.</span><span class="sxs-lookup"><span data-stu-id="adccd-127">Describes how to create a copy of a <xref:System.Data.DataSet> that can contain schema as well as specified data.</span></span>  
  
 [<span data-ttu-id="adccd-128">Handling DataSet Events (Behandeln von DataSet-Ereignissen)</span><span class="sxs-lookup"><span data-stu-id="adccd-128">Handling DataSet Events</span></span>](handling-dataset-events.md)  
 <span data-ttu-id="adccd-129">Beschreibt die Ereignisse eines <xref:System.Data.DataSet> und wie diese verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="adccd-129">Describes the events of a <xref:System.Data.DataSet> and how to use them.</span></span>  
  
 [<span data-ttu-id="adccd-130">Typed DataSets (Typisierte DataSets)</span><span class="sxs-lookup"><span data-stu-id="adccd-130">Typed DataSets</span></span>](typed-datasets.md)  
 <span data-ttu-id="adccd-131">Erläutert, was ein typisiertes <xref:System.Data.DataSet> ist, und wie es erstellt und verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="adccd-131">Discusses what a typed <xref:System.Data.DataSet> is and how to create and use it.</span></span>  
  
 [<span data-ttu-id="adccd-132">DataTables</span><span class="sxs-lookup"><span data-stu-id="adccd-132">DataTables</span></span>](datatables.md)  
 <span data-ttu-id="adccd-133">Beschreibt das Erstellen einer <xref:System.Data.DataTable>, das Definieren des zugehörigen Schemas und das Bearbeiten von Daten.</span><span class="sxs-lookup"><span data-stu-id="adccd-133">Describes how to create a <xref:System.Data.DataTable>, define the schema, and manipulate data.</span></span>  
  
 [<span data-ttu-id="adccd-134">DataTableReaders</span><span class="sxs-lookup"><span data-stu-id="adccd-134">DataTableReaders</span></span>](datatablereaders.md)  
 <span data-ttu-id="adccd-135">Beschreibt das Erstellen und Verwenden eines <xref:System.Data.DataTableReader>.</span><span class="sxs-lookup"><span data-stu-id="adccd-135">Describes how to create and use a <xref:System.Data.DataTableReader>.</span></span>  
  
 [<span data-ttu-id="adccd-136">DataViews</span><span class="sxs-lookup"><span data-stu-id="adccd-136">DataViews</span></span>](dataviews.md)  
 <span data-ttu-id="adccd-137">Beschreibt das Erstellen von und Arbeiten mit `DataViews` sowie das Arbeiten mit <xref:System.Data.DataView>-Ereignissen.</span><span class="sxs-lookup"><span data-stu-id="adccd-137">Describes how to create and work with `DataViews` and work with <xref:System.Data.DataView> events.</span></span>  
  
 [<span data-ttu-id="adccd-138">Using XML in a DataSet (Verwenden von XML in einem DataSet)</span><span class="sxs-lookup"><span data-stu-id="adccd-138">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)  
 <span data-ttu-id="adccd-139">Beschreibt, wie das <xref:System.Data.DataSet> mit XML als Datenquelle interagiert, einschließlich des Ladens und Beibehaltens des Inhalts eines <xref:System.Data.DataSet> als XML-Daten.</span><span class="sxs-lookup"><span data-stu-id="adccd-139">Describes how the <xref:System.Data.DataSet> interacts with XML as a data source, including loading and persisting the contents of a <xref:System.Data.DataSet> as XML data.</span></span>  
  
 [<span data-ttu-id="adccd-140">Consuming a DataSet from an XML Web Service (Verwenden eines DataSets von einem XML-Webdienst aus)</span><span class="sxs-lookup"><span data-stu-id="adccd-140">Consuming a DataSet from an XML Web Service</span></span>](consuming-a-dataset-from-an-xml-web-service.md)  
 <span data-ttu-id="adccd-141">Beschreibt, wie ein XML-Webdienst erstellt wird, der für die Übertragung von Daten ein <xref:System.Data.DataSet> verwendet.</span><span class="sxs-lookup"><span data-stu-id="adccd-141">Describes how to create an XML Web service that uses a <xref:System.Data.DataSet> to transport data.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="adccd-142">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="adccd-142">Related Sections</span></span>  
 [<span data-ttu-id="adccd-143">Neues in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="adccd-143">What's New in ADO.NET</span></span>](../whats-new.md)  
 <span data-ttu-id="adccd-144">Enthält eine Einführung in neue Funktionen von ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="adccd-144">Introduces features that are new in ADO.NET.</span></span>  
  
 [<span data-ttu-id="adccd-145">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="adccd-145">ADO.NET Overview</span></span>](../ado-net-overview.md)  
 <span data-ttu-id="adccd-146">Bietet eine Einführung in das Design und die Komponenten von ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="adccd-146">Provides an introduction to the design and components of ADO.NET.</span></span>  
  
 [<span data-ttu-id="adccd-147">Populating a DataSet from a DataAdapter (Auffüllen eines DataSets durch einen DataAdapter)</span><span class="sxs-lookup"><span data-stu-id="adccd-147">Populating a DataSet from a DataAdapter</span></span>](../populating-a-dataset-from-a-dataadapter.md)  
 <span data-ttu-id="adccd-148">Beschreibt das Laden eines **DataSets** mit Daten aus einer Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="adccd-148">Describes how to load a **DataSet** with data from a data source.</span></span>  
  
 [<span data-ttu-id="adccd-149">Updating Data Sources with DataAdapters (Aktualisieren von Datenquellen mit DataAdapters)</span><span class="sxs-lookup"><span data-stu-id="adccd-149">Updating Data Sources with DataAdapters</span></span>](../updating-data-sources-with-dataadapters.md)  
 <span data-ttu-id="adccd-150">Beschreibt, wie Änderungen an Daten in einem **DataSet** auch in der Datenquelle vorgenommen werden können.</span><span class="sxs-lookup"><span data-stu-id="adccd-150">Describes how to resolve changes to the data in a **DataSet** back to the data source.</span></span>  
  
 [<span data-ttu-id="adccd-151">Adding Existing Constraints to a DataSet (Hinzufügen von vorhandenen Einschränkungen zu einem DataSet)</span><span class="sxs-lookup"><span data-stu-id="adccd-151">Adding Existing Constraints to a DataSet</span></span>](../adding-existing-constraints-to-a-dataset.md)  
 <span data-ttu-id="adccd-152">Beschreibt das Auffüllen eines **DataSets** mit Primärschlüsselinformationen aus einer Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="adccd-152">Describes how to populate a **DataSet** with primary key information from a data source.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="adccd-153">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="adccd-153">See also</span></span>

- [<span data-ttu-id="adccd-154">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="adccd-154">ADO.NET</span></span>](../index.md)
- [<span data-ttu-id="adccd-155">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="adccd-155">ADO.NET Overview</span></span>](../ado-net-overview.md)
