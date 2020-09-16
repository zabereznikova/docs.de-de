---
title: "\"DataSets\", \"DataTables\" und \"DataViews\""
description: Erfahren Sie, wie Sie mit einem ADO.NET-DataSet arbeiten, einer Speicher Residenten Darstellung von Daten, die ein konsistentes relationales Programmiermodell bereitstellt.
ms.date: 03/30/2017
ms.assetid: 6d4c4b69-8919-4224-8a65-6cca1c61b48f
ms.openlocfilehash: 4e1c0ea5f1de1715ad8e862e6a3ed7370b53c6ce
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90555863"
---
# <a name="datasets-datatables-and-dataviews"></a><span data-ttu-id="1c1a4-103">"DataSets", "DataTables" und "DataViews"</span><span class="sxs-lookup"><span data-stu-id="1c1a4-103">DataSets, DataTables, and DataViews</span></span>

<span data-ttu-id="1c1a4-104">ADO.NET <xref:System.Data.DataSet> ist eine speicherresidente Darstellung von Daten, die – unabhängig von der darin enthaltenen Datenquelle – ein konsistentes relationales Programmiermodell bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="1c1a4-104">The ADO.NET <xref:System.Data.DataSet> is a memory-resident representation of data that provides a consistent relational programming model regardless of the source of the data it contains.</span></span> <span data-ttu-id="1c1a4-105">Ein <xref:System.Data.DataSet> stellt einen kompletten Satz aus Daten dar, einschließlich der Tabellen, die die Daten enthalten, ordnen und einschränken, sowie der Beziehungen zwischen den Tabellen.</span><span class="sxs-lookup"><span data-stu-id="1c1a4-105">A <xref:System.Data.DataSet> represents a complete set of data including the tables that contain, order, and constrain the data, as well as the relationships between the tables.</span></span>  
  
<span data-ttu-id="1c1a4-106">Es gibt verschiedene Möglichkeiten, mit einem <xref:System.Data.DataSet> zu arbeiten, die unabhängig voneinander oder kombiniert angewendet werden können.</span><span class="sxs-lookup"><span data-stu-id="1c1a4-106">There are several ways of working with a <xref:System.Data.DataSet>, which can be applied independently or in combination.</span></span> <span data-ttu-id="1c1a4-107">Sie können:</span><span class="sxs-lookup"><span data-stu-id="1c1a4-107">You can:</span></span>  
  
- <span data-ttu-id="1c1a4-108">Sie können eine <xref:System.Data.DataTable>, eine <xref:System.Data.DataRelation> und eine <xref:System.Data.Constraint> innerhalb eines <xref:System.Data.DataSet> programmgesteuert erstellen und die Tabellen mit Daten füllen.</span><span class="sxs-lookup"><span data-stu-id="1c1a4-108">Programmatically create a <xref:System.Data.DataTable>, <xref:System.Data.DataRelation>, and <xref:System.Data.Constraint> within a <xref:System.Data.DataSet> and populate the tables with data.</span></span>  
  
- <span data-ttu-id="1c1a4-109">Sie können das <xref:System.Data.DataSet> mithilfe eines `DataAdapter` mit Tabellen von Daten aus einer vorhandenen relationalen Datenquelle füllen.</span><span class="sxs-lookup"><span data-stu-id="1c1a4-109">Populate the <xref:System.Data.DataSet> with tables of data from an existing relational data source using a `DataAdapter`.</span></span>  
  
- <span data-ttu-id="1c1a4-110">Sie können den Inhalt des <xref:System.Data.DataSet> mithilfe von XML laden und beibehalten.</span><span class="sxs-lookup"><span data-stu-id="1c1a4-110">Load and persist the <xref:System.Data.DataSet> contents using XML.</span></span> <span data-ttu-id="1c1a4-111">Weitere Informationen finden Sie unter [Using XML in a DataSet (Verwenden von XML in einem DataSet)](using-xml-in-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="1c1a4-111">For more information, see [Using XML in a DataSet](using-xml-in-a-dataset.md).</span></span>  
  
<span data-ttu-id="1c1a4-112">Bei einem <xref:System.Data.DataSet> mit strikter Typbindung besteht auch die Möglichkeit, es mit einem XML-Webdienst zu übertragen.</span><span class="sxs-lookup"><span data-stu-id="1c1a4-112">A strongly typed <xref:System.Data.DataSet> can also be transported using an XML Web service.</span></span> <span data-ttu-id="1c1a4-113">Durch seinen Aufbau ist das <xref:System.Data.DataSet> ideal für die Übertragung von Daten mithilfe von XML-Webdiensten geeignet.</span><span class="sxs-lookup"><span data-stu-id="1c1a4-113">The design of the <xref:System.Data.DataSet> makes it ideal for transporting data using XML Web services.</span></span> <span data-ttu-id="1c1a4-114">Eine Übersicht über die XML-Webdienste finden Sie unter [XML Web Services Overview (Übersicht über XML-Webdienste)](/previous-versions/dotnet/netframework-4.0/w9fdtx28(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="1c1a4-114">For an overview of XML Web services, see [XML Web Services Overview](/previous-versions/dotnet/netframework-4.0/w9fdtx28(v=vs.100)).</span></span> <span data-ttu-id="1c1a4-115">Ein Beispiel für die Nutzung von <xref:System.Data.DataSet> von einem XML-Webdienst aus finden Sie unter [Consuming a DataSet from an XML Web Service (Verwenden eines DataSets von einem XML-Webdienst aus)](consuming-a-dataset-from-an-xml-web-service.md).</span><span class="sxs-lookup"><span data-stu-id="1c1a4-115">For an example of consuming a <xref:System.Data.DataSet> from an XML Web service, see [Consuming a DataSet from an XML Web Service](consuming-a-dataset-from-an-xml-web-service.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1c1a4-116">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="1c1a4-116">In this section</span></span>

 [<span data-ttu-id="1c1a4-117">Sicherheitsleitfaden</span><span class="sxs-lookup"><span data-stu-id="1c1a4-117">Security guidance</span></span>](security-guidance.md)  
 <span data-ttu-id="1c1a4-118">Bietet Sicherheits Anleitungen für <xref:System.Data.DataSet> und <xref:System.Data.DataTable> .</span><span class="sxs-lookup"><span data-stu-id="1c1a4-118">Provides security guidance for <xref:System.Data.DataSet> and <xref:System.Data.DataTable>.</span></span>

 [<span data-ttu-id="1c1a4-119">Erstellen eines Datasets</span><span class="sxs-lookup"><span data-stu-id="1c1a4-119">Creating a DataSet</span></span>](creating-a-dataset.md)  
 <span data-ttu-id="1c1a4-120">Beschreibt die Syntax zum Erstellen einer Instanz eines <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="1c1a4-120">Describes the syntax for creating an instance of a <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="1c1a4-121">Hinzufügen einer "DataTable" zu einem "DataSet"</span><span class="sxs-lookup"><span data-stu-id="1c1a4-121">Adding a DataTable to a DataSet</span></span>](adding-a-datatable-to-a-dataset.md)  
 <span data-ttu-id="1c1a4-122">Beschreibt das Erstellen sowie das Hinzufügen von Tabellen und Spalten zu einem <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="1c1a4-122">Describes how to create and add tables and columns to a <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="1c1a4-123">Hinzufügen von "DataRelations"</span><span class="sxs-lookup"><span data-stu-id="1c1a4-123">Adding DataRelations</span></span>](adding-datarelations.md)  
 <span data-ttu-id="1c1a4-124">Beschreibt das Erstellen von Beziehungen zwischen Tabellen in einem <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="1c1a4-124">Describes how to create relations between tables in a <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="1c1a4-125">Navigieren in "DataRelations"</span><span class="sxs-lookup"><span data-stu-id="1c1a4-125">Navigating DataRelations</span></span>](navigating-datarelations.md)  
 <span data-ttu-id="1c1a4-126">Beschreibt, wie die Beziehungen zwischen Tabellen in einem <xref:System.Data.DataSet> dazu verwendet werden, untergeordnete oder übergeordnete Zeilen einer Beziehung zwischen über- und untergeordneten Tabellen zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="1c1a4-126">Describes how to use the relations between tables in a <xref:System.Data.DataSet> to return the child or parent rows of a parent-child relationship.</span></span>  
  
 [<span data-ttu-id="1c1a4-127">Zusammenführen von DataSet-Inhalten</span><span class="sxs-lookup"><span data-stu-id="1c1a4-127">Merging DataSet Contents</span></span>](merging-dataset-contents.md)  
 <span data-ttu-id="1c1a4-128">Beschreibt, wie der Inhalt eines <xref:System.Data.DataSet>-Arrays, <xref:System.Data.DataTable>-Arrays oder <xref:System.Data.DataRow>-Arrays mit einem anderen <xref:System.Data.DataSet> zusammengeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1c1a4-128">Describes how to merge the contents of one <xref:System.Data.DataSet>, <xref:System.Data.DataTable>, or <xref:System.Data.DataRow> array into another <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="1c1a4-129">Kopieren von DataSet-Inhalten</span><span class="sxs-lookup"><span data-stu-id="1c1a4-129">Copying DataSet Contents</span></span>](copying-dataset-contents.md)  
 <span data-ttu-id="1c1a4-130">Beschreibt das Erstellen einer Kopie eines <xref:System.Data.DataSet>, die ein Schema sowie angegebene Daten enthalten kann.</span><span class="sxs-lookup"><span data-stu-id="1c1a4-130">Describes how to create a copy of a <xref:System.Data.DataSet> that can contain schema as well as specified data.</span></span>  
  
 [<span data-ttu-id="1c1a4-131">Behandeln von DataSet-Ereignissen</span><span class="sxs-lookup"><span data-stu-id="1c1a4-131">Handling DataSet Events</span></span>](handling-dataset-events.md)  
 <span data-ttu-id="1c1a4-132">Beschreibt die Ereignisse eines <xref:System.Data.DataSet> und wie diese verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1c1a4-132">Describes the events of a <xref:System.Data.DataSet> and how to use them.</span></span>  
  
 [<span data-ttu-id="1c1a4-133">Typisierte "DataSets"</span><span class="sxs-lookup"><span data-stu-id="1c1a4-133">Typed DataSets</span></span>](typed-datasets.md)  
 <span data-ttu-id="1c1a4-134">Erläutert, was ein typisiertes <xref:System.Data.DataSet> ist, und wie es erstellt und verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="1c1a4-134">Discusses what a typed <xref:System.Data.DataSet> is and how to create and use it.</span></span>  
  
 [<span data-ttu-id="1c1a4-135">"DataTables"</span><span class="sxs-lookup"><span data-stu-id="1c1a4-135">DataTables</span></span>](datatables.md)  
 <span data-ttu-id="1c1a4-136">Beschreibt das Erstellen einer <xref:System.Data.DataTable>, das Definieren des zugehörigen Schemas und das Bearbeiten von Daten.</span><span class="sxs-lookup"><span data-stu-id="1c1a4-136">Describes how to create a <xref:System.Data.DataTable>, define the schema, and manipulate data.</span></span>  
  
 [<span data-ttu-id="1c1a4-137">"DataTableReaders"</span><span class="sxs-lookup"><span data-stu-id="1c1a4-137">DataTableReaders</span></span>](datatablereaders.md)  
 <span data-ttu-id="1c1a4-138">Beschreibt das Erstellen und Verwenden eines <xref:System.Data.DataTableReader>.</span><span class="sxs-lookup"><span data-stu-id="1c1a4-138">Describes how to create and use a <xref:System.Data.DataTableReader>.</span></span>  
  
 [<span data-ttu-id="1c1a4-139">"DataViews"</span><span class="sxs-lookup"><span data-stu-id="1c1a4-139">DataViews</span></span>](dataviews.md)  
 <span data-ttu-id="1c1a4-140">Beschreibt das Erstellen von und Arbeiten mit `DataViews` sowie das Arbeiten mit <xref:System.Data.DataView>-Ereignissen.</span><span class="sxs-lookup"><span data-stu-id="1c1a4-140">Describes how to create and work with `DataViews` and work with <xref:System.Data.DataView> events.</span></span>  
  
 [<span data-ttu-id="1c1a4-141">Using XML in a DataSet (Verwenden von XML in einem DataSet)</span><span class="sxs-lookup"><span data-stu-id="1c1a4-141">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)  
 <span data-ttu-id="1c1a4-142">Beschreibt, wie das <xref:System.Data.DataSet> mit XML als Datenquelle interagiert, einschließlich des Ladens und Beibehaltens des Inhalts eines <xref:System.Data.DataSet> als XML-Daten.</span><span class="sxs-lookup"><span data-stu-id="1c1a4-142">Describes how the <xref:System.Data.DataSet> interacts with XML as a data source, including loading and persisting the contents of a <xref:System.Data.DataSet> as XML data.</span></span>  
  
 [<span data-ttu-id="1c1a4-143">Verwenden eines "DataSet" von einem XML-Webdienst aus</span><span class="sxs-lookup"><span data-stu-id="1c1a4-143">Consuming a DataSet from an XML Web Service</span></span>](consuming-a-dataset-from-an-xml-web-service.md)  
 <span data-ttu-id="1c1a4-144">Beschreibt, wie ein XML-Webdienst erstellt wird, der für die Übertragung von Daten ein <xref:System.Data.DataSet> verwendet.</span><span class="sxs-lookup"><span data-stu-id="1c1a4-144">Describes how to create an XML Web service that uses a <xref:System.Data.DataSet> to transport data.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="1c1a4-145">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="1c1a4-145">Related sections</span></span>

 [<span data-ttu-id="1c1a4-146">Neues in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="1c1a4-146">What's New in ADO.NET</span></span>](../whats-new.md)  
 <span data-ttu-id="1c1a4-147">Enthält eine Einführung in neue Funktionen von ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="1c1a4-147">Introduces features that are new in ADO.NET.</span></span>  
  
 [<span data-ttu-id="1c1a4-148">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="1c1a4-148">ADO.NET Overview</span></span>](../ado-net-overview.md)  
 <span data-ttu-id="1c1a4-149">Bietet eine Einführung in das Design und die Komponenten von ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="1c1a4-149">Provides an introduction to the design and components of ADO.NET.</span></span>  
  
 [<span data-ttu-id="1c1a4-150">Auffüllen eines "DataSets" durch einen "DataAdapter"</span><span class="sxs-lookup"><span data-stu-id="1c1a4-150">Populating a DataSet from a DataAdapter</span></span>](../populating-a-dataset-from-a-dataadapter.md)  
 <span data-ttu-id="1c1a4-151">Beschreibt das Laden eines **DataSets** mit Daten aus einer Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="1c1a4-151">Describes how to load a **DataSet** with data from a data source.</span></span>  
  
 [<span data-ttu-id="1c1a4-152">Aktualisieren von Datenquellen mit "DataAdapters"</span><span class="sxs-lookup"><span data-stu-id="1c1a4-152">Updating Data Sources with DataAdapters</span></span>](../updating-data-sources-with-dataadapters.md)  
 <span data-ttu-id="1c1a4-153">Beschreibt, wie Änderungen an Daten in einem **DataSet** auch in der Datenquelle vorgenommen werden können.</span><span class="sxs-lookup"><span data-stu-id="1c1a4-153">Describes how to resolve changes to the data in a **DataSet** back to the data source.</span></span>  
  
 [<span data-ttu-id="1c1a4-154">Hinzufügen von vorhandenen Einschränkungen zu einem "DataSet"</span><span class="sxs-lookup"><span data-stu-id="1c1a4-154">Adding Existing Constraints to a DataSet</span></span>](../adding-existing-constraints-to-a-dataset.md)  
 <span data-ttu-id="1c1a4-155">Beschreibt das Auffüllen eines **DataSets** mit Primärschlüsselinformationen aus einer Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="1c1a4-155">Describes how to populate a **DataSet** with primary key information from a data source.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c1a4-156">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1c1a4-156">See also</span></span>

- [<span data-ttu-id="1c1a4-157">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="1c1a4-157">ADO.NET</span></span>](../index.md)
- [<span data-ttu-id="1c1a4-158">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="1c1a4-158">ADO.NET Overview</span></span>](../ado-net-overview.md)
