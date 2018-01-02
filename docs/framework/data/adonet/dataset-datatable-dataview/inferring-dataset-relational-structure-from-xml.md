---
title: Ableiten einer relationalen DataSet-Struktur aus einem XML-Schema
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cd2f41c6-6785-420e-aa43-3ceb0bdccdce
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 3c58dbd35c2c203450960118b58da49518098ed7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="inferring-dataset-relational-structure-from-xml"></a><span data-ttu-id="72501-102">Ableiten einer relationalen DataSet-Struktur aus einem XML-Schema</span><span class="sxs-lookup"><span data-stu-id="72501-102">Inferring DataSet Relational Structure from XML</span></span>
<span data-ttu-id="72501-103">Die relationale Struktur bzw. das Schema eines <xref:System.Data.DataSet> besteht aus Tabellen, Spalten, Einschränkungen und Beziehungen.</span><span class="sxs-lookup"><span data-stu-id="72501-103">The relational structure, or schema, of a <xref:System.Data.DataSet> is made up of tables, columns, constraints, and relations.</span></span> <span data-ttu-id="72501-104">Beim Laden eines <xref:System.Data.DataSet> aus XML kann das Schema vordefiniert sein oder explizit bzw. durch Rückschluss aus dem geladenen XML erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="72501-104">When loading a <xref:System.Data.DataSet> from XML, the schema can be predefined, or it can be created, either explicitly or through inference, from the XML being loaded.</span></span> <span data-ttu-id="72501-105">Weitere Informationen zum Laden des Schemas und der Inhalt einer <xref:System.Data.DataSet> aus XML finden Sie unter [beim Laden eines Datasets aus XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md) und [Laden von DataSet-Schemainformationen aus XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md).</span><span class="sxs-lookup"><span data-stu-id="72501-105">For more information about loading the schema and contents of a <xref:System.Data.DataSet> from XML, see [Loading a DataSet from XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md) and [Loading DataSet Schema Information from XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md).</span></span>  
  
 <span data-ttu-id="72501-106">Wenn das Schema einer <xref:System.Data.DataSet> erstellt wird aus XML ist die bevorzugte Methode explizit das Schema mithilfe von entweder der XML-Schemadefinitionssprache (XSD) angeben (wie in beschrieben [ableiten relationalen DataSet-Struktur von XML-Schema (XSD) ](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)) oder die XML-Data Reduced (XDR).</span><span class="sxs-lookup"><span data-stu-id="72501-106">If the schema of a <xref:System.Data.DataSet> is being created from XML, the preferred method is to explicitly specify the schema using either the XML Schema definition language (XSD) (as described in [Deriving DataSet Relational Structure from XML Schema (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)) or the XML-Data Reduced (XDR).</span></span> <span data-ttu-id="72501-107">Falls in XML kein XML-Schema oder XDR-Schema verfügbar ist, kann das Schema des <xref:System.Data.DataSet> aus der Struktur der XML-Elemente und -Attribute hergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="72501-107">If no XML Schema or XDR schema is available in the XML, the schema of the <xref:System.Data.DataSet> can be inferred from the structure of the XML elements and attributes.</span></span>  
  
 <span data-ttu-id="72501-108">In diesem Abschnitt werden anhand von XML-Elementen und -Attributen, ihrer Struktur und dem daraus hergeleiteten <xref:System.Data.DataSet>-Schema die Herleitungsregeln für <xref:System.Data.DataSet>-Schemata erläutert.</span><span class="sxs-lookup"><span data-stu-id="72501-108">This section describes the rules for <xref:System.Data.DataSet> schema inference by showing XML elements and attributes and their structure, and the resulting inferred <xref:System.Data.DataSet> schema.</span></span>  
  
 <span data-ttu-id="72501-109">Nicht alle in einem XML-Dokument vorhandenen Attribute sollten in den Rückschlussprozess einbezogen werden.</span><span class="sxs-lookup"><span data-stu-id="72501-109">Not all attributes present in an XML document should be included in the inference process.</span></span> <span data-ttu-id="72501-110">Namespace-qualifizierte Attribute enthalten häufig Metadaten, die zwar für das XML-Dokument wichtig sind, nicht jedoch für das <xref:System.Data.DataSet>-Schema.</span><span class="sxs-lookup"><span data-stu-id="72501-110">Namespace-qualified attributes can include metadata that is important for the XML document but not for the <xref:System.Data.DataSet> schema.</span></span> <span data-ttu-id="72501-111">Mithilfe von <xref:System.Data.DataSet.InferXmlSchema%2A> legen Sie fest, dass bestimmte Namespaces beim Rückschlussprozess ignoriert werden.</span><span class="sxs-lookup"><span data-stu-id="72501-111">Using <xref:System.Data.DataSet.InferXmlSchema%2A>, you can specify namespaces to be ignored during the inference process.</span></span> <span data-ttu-id="72501-112">Weitere Informationen finden Sie unter [Laden von DataSet-Schemainformationen aus XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md).</span><span class="sxs-lookup"><span data-stu-id="72501-112">For more information, see [Loading DataSet Schema Information from XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="72501-113">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="72501-113">In This Section</span></span>  
 [<span data-ttu-id="72501-114">Zusammenfassung des Rückschlussprozesses von DataSet-Schemas</span><span class="sxs-lookup"><span data-stu-id="72501-114">Summary of the DataSet Schema Inference Process</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/summary-of-the-dataset-schema-inference-process.md)  
 <span data-ttu-id="72501-115">Enthält eine Zusammenfassung der Regeln zur Herleitung des Schemas eines <xref:System.Data.DataSet> aus XML.</span><span class="sxs-lookup"><span data-stu-id="72501-115">Provides a high-level summary of the rules for inferring the schema of a <xref:System.Data.DataSet> from XML.</span></span>  
  
 [<span data-ttu-id="72501-116">Ableiten von Tabellen</span><span class="sxs-lookup"><span data-stu-id="72501-116">Inferring Tables</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-tables.md)  
 <span data-ttu-id="72501-117">Beschreibt die XML-Elemente, die als Tabellen in einem <xref:System.Data.DataSet> hergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="72501-117">Describes the XML elements that are inferred as tables in a <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="72501-118">Ableiten von Spalten</span><span class="sxs-lookup"><span data-stu-id="72501-118">Inferring Columns</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-columns.md)  
 <span data-ttu-id="72501-119">Beschreibt die XML-Elemente und -Attribute, die als Tabellenspalten hergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="72501-119">Describes the XML elements and attributes that are inferred as table columns.</span></span>  
  
 [<span data-ttu-id="72501-120">Ableiten von Beziehungen</span><span class="sxs-lookup"><span data-stu-id="72501-120">Inferring Relationships</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-relationships.md)  
 <span data-ttu-id="72501-121">Beschreibt das <xref:System.Data.DataRelation>-Objekt und das <xref:System.Data.ForeignKeyConstraint>-Objekt, die beide für geschachtelte, hergeleitete Tabellen erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="72501-121">Describes the <xref:System.Data.DataRelation> and <xref:System.Data.ForeignKeyConstraint> objects created for nested, inferred tables.</span></span>  
  
 [<span data-ttu-id="72501-122">Ableiten von Elementtext</span><span class="sxs-lookup"><span data-stu-id="72501-122">Inferring Element Text</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-element-text.md)  
 <span data-ttu-id="72501-123">Beschreibt die für den Text in XML-Elementen erstellten Spalten und erläutert, wann der Text in XML-Elementen ignoriert wird.</span><span class="sxs-lookup"><span data-stu-id="72501-123">Describes the columns that are created for text in XML elements, and explains when text in XML elements is ignored.</span></span>  
  
 [<span data-ttu-id="72501-124">Rückschlusseinschränkungen</span><span class="sxs-lookup"><span data-stu-id="72501-124">Inference Limitations</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inference-limitations.md)  
 <span data-ttu-id="72501-125">Behandelt die Einschränkungen der Schemaherleitung.</span><span class="sxs-lookup"><span data-stu-id="72501-125">Discusses the limitations of schema inference.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="72501-126">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="72501-126">Related Sections</span></span>  
 [<span data-ttu-id="72501-127">Using XML in a DataSet (Verwenden von XML in einem DataSet)</span><span class="sxs-lookup"><span data-stu-id="72501-127">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 <span data-ttu-id="72501-128">Beschreibt die Interaktion zwischen dem <xref:System.Data.DataSet>-Objekt und XML-Daten.</span><span class="sxs-lookup"><span data-stu-id="72501-128">Describes how the <xref:System.Data.DataSet> object interacts with XML data.</span></span>  
  
 [<span data-ttu-id="72501-129">Ableiten einer relationalen DataSet-Struktur aus einem XML-Schema (XSD)</span><span class="sxs-lookup"><span data-stu-id="72501-129">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 <span data-ttu-id="72501-130">Beschreibt die relationale Struktur bzw. das Schema eines <xref:System.Data.DataSet>, das aus einem XSD-Schema (XML Schema Definition Language) erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="72501-130">Describes the relational structure, or schema, of a <xref:System.Data.DataSet> that is created from XML Schema definition language (XSD) schema.</span></span>  
  
 [<span data-ttu-id="72501-131">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="72501-131">ADO.NET Overview</span></span>](../../../../../docs/framework/data/adonet/ado-net-overview.md)  
 <span data-ttu-id="72501-132">Beschreibt die ADO.NET-Architektur und -Komponenten und wie diese verwendet werden, um auf vorhandene Datenquellen zuzugreifen und Anwendungsdaten zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="72501-132">Describes the ADO.NET architecture and components and how to use them to access existing data sources and manage application data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72501-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="72501-133">See Also</span></span>  
 [<span data-ttu-id="72501-134">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="72501-134">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
