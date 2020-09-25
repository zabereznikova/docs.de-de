---
title: Verwenden von XML in einem "DataSet"
ms.date: 03/30/2017
ms.assetid: 35138159-e199-49ec-baf7-1ec6777e171e
ms.openlocfilehash: e133da727887271af3bc5330a5779df4af58a37e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201186"
---
# <a name="using-xml-in-a-dataset"></a><span data-ttu-id="754cb-102">Verwenden von XML in einem "DataSet"</span><span class="sxs-lookup"><span data-stu-id="754cb-102">Using XML in a DataSet</span></span>

<span data-ttu-id="754cb-103">Mit ADO.NET können Sie ein <xref:System.Data.DataSet> über einen XML-Stream oder ein XML-Dokument füllen.</span><span class="sxs-lookup"><span data-stu-id="754cb-103">With ADO.NET you can fill a <xref:System.Data.DataSet> from an XML stream or document.</span></span> <span data-ttu-id="754cb-104">Die können den XML-Stream oder das XML-Dokument verwenden, um das <xref:System.Data.DataSet> mit Daten oder Schemainformationen oder mit beidem zu versorgen.</span><span class="sxs-lookup"><span data-stu-id="754cb-104">You can use the XML stream or document to supply to the <xref:System.Data.DataSet> either data, schema information, or both.</span></span> <span data-ttu-id="754cb-105">Die vom XML-Stream oder vom XML-Dokument bereitgestellten Daten können mit vorhandenen Daten oder Schemainformationen kombiniert werden, die bereits im <xref:System.Data.DataSet> enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="754cb-105">The information supplied from the XML stream or document can be combined with existing data or schema information already present in the <xref:System.Data.DataSet>.</span></span>  
  
 <span data-ttu-id="754cb-106">ADO.NET ermöglicht auch das Erstellen einer XML-Darstellung eines <xref:System.Data.DataSet> mit oder ohne zugehöriges Schema, damit das <xref:System.Data.DataSet> über HTTP übertragen und von anderen Anwendungen oder XML-fähigen Plattformen verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="754cb-106">ADO.NET also allows you to create an XML representation of a <xref:System.Data.DataSet>, with or without its schema, in order to transport the <xref:System.Data.DataSet> across HTTP for use by another application or XML-enabled platform.</span></span> <span data-ttu-id="754cb-107">Bei einer XML-Darstellung eines <xref:System.Data.DataSet> werden die Daten im XML-Format geschrieben, und das Schema wird, sofern es sich um ein Inlineschema handelt, mit XSD (XML Schema Definition Language) geschrieben.</span><span class="sxs-lookup"><span data-stu-id="754cb-107">In an XML representation of a <xref:System.Data.DataSet>, the data is written in XML and the schema, if it is included inline in the representation, is written using the XML Schema definition language (XSD).</span></span> <span data-ttu-id="754cb-108">XML und das XML-Schema stellen ein komfortables Format zum Übertragen des <xref:System.Data.DataSet>-Inhalts an und von Remoteclients bereit.</span><span class="sxs-lookup"><span data-stu-id="754cb-108">XML and XML Schema provide a convenient format for transferring the contents of a <xref:System.Data.DataSet> to and from remote clients.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="754cb-109">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="754cb-109">In This Section</span></span>  

 [<span data-ttu-id="754cb-110">DiffGrams</span><span class="sxs-lookup"><span data-stu-id="754cb-110">DiffGrams</span></span>](diffgrams.md)  
 <span data-ttu-id="754cb-111">Bietet Einzelheiten zum DiffGram, einem XML-Format, das zum Lesen und Schreiben des Inhalts eines <xref:System.Data.DataSet> verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="754cb-111">Provides details on the DiffGram, an XML format used to read and write the contents of a <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="754cb-112">Laden eines "DataSets" aus XML</span><span class="sxs-lookup"><span data-stu-id="754cb-112">Loading a DataSet from XML</span></span>](loading-a-dataset-from-xml.md)  
 <span data-ttu-id="754cb-113">Beschreibt verschiedene Möglichkeiten beim Füllen eines <xref:System.Data.DataSet> mit einem XML-Dokument.</span><span class="sxs-lookup"><span data-stu-id="754cb-113">Discusses different options to consider when loading the contents of a <xref:System.Data.DataSet> from an XML document.</span></span>  
  
 [<span data-ttu-id="754cb-114">Schreiben von DataSet-Inhalten als XML-Daten</span><span class="sxs-lookup"><span data-stu-id="754cb-114">Writing DataSet Contents as XML Data</span></span>](writing-dataset-contents-as-xml-data.md)  
 <span data-ttu-id="754cb-115">Erläutert, wie der Inhalt eines <xref:System.Data.DataSet> als XML-Daten generiert wird und welche XML-Formatoptionen verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="754cb-115">Discusses how to generate the contents of a <xref:System.Data.DataSet> as XML data, and the different XML format options you can use.</span></span>  
  
 [<span data-ttu-id="754cb-116">Laden von DataSet-Schemainformationen aus XML</span><span class="sxs-lookup"><span data-stu-id="754cb-116">Loading DataSet Schema Information from XML</span></span>](loading-dataset-schema-information-from-xml.md)  
 <span data-ttu-id="754cb-117">Erläutert die <xref:System.Data.DataSet>-Methoden, die zum Laden des Schemas eines <xref:System.Data.DataSet> aus einem XML-Dokument verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="754cb-117">Discusses the <xref:System.Data.DataSet> methods used to load the schema of a <xref:System.Data.DataSet> from XML.</span></span>  
  
 [<span data-ttu-id="754cb-118">Schreiben von DataSet-Schemainformationen als XSD</span><span class="sxs-lookup"><span data-stu-id="754cb-118">Writing DataSet Schema Information as XSD</span></span>](writing-dataset-schema-information-as-xsd.md)  
 <span data-ttu-id="754cb-119">Erläutert, wie ein XML-Schema verwendet und aus einem <xref:System.Data.DataSet> generiert wird.</span><span class="sxs-lookup"><span data-stu-id="754cb-119">Discusses the uses for an XML Schema and how to generate one from a <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="754cb-120">DataSet- und XmlDataDocument-Synchronisierung</span><span class="sxs-lookup"><span data-stu-id="754cb-120">DataSet and XmlDataDocument Synchronization</span></span>](dataset-and-xmldatadocument-synchronization.md)  
 <span data-ttu-id="754cb-121">Erläutert die Möglichkeiten, die in .NET Framework für den synchronen Zugriff auf relationale und hierarchische Darstellungen eines einzigen Datensatzes zur Verfügung stehen. Darüber hinaus wird gezeigt, wie eine synchrone Beziehung zwischen einem <xref:System.Data.DataSet> und einem <xref:System.Xml.XmlDataDocument> erstellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="754cb-121">Discusses the capability available in the .NET Framework of synchronous access to both relational and hierarchical views of a single set of data, and shows how to create a synchronous relationship between a <xref:System.Data.DataSet> and an <xref:System.Xml.XmlDataDocument>.</span></span>  
  
 [<span data-ttu-id="754cb-122">Verschachteln von "DataRelations"</span><span class="sxs-lookup"><span data-stu-id="754cb-122">Nesting DataRelations</span></span>](nesting-datarelations.md)  
 <span data-ttu-id="754cb-123">Erläutert die Bedeutung geschachtelter <xref:System.Data.DataRelation>-Objekte beim Darstellen des Inhalts eines <xref:System.Data.DataSet> als XML-Daten und beschreibt deren Erstellung.</span><span class="sxs-lookup"><span data-stu-id="754cb-123">Discusses the importance of nested <xref:System.Data.DataRelation> objects when representing the contents of a <xref:System.Data.DataSet> as XML data, and describes how to create them.</span></span>  
  
 [<span data-ttu-id="754cb-124">Ableiten einer relationalen DataSet-Struktur aus einem XML-Schema (XSD)</span><span class="sxs-lookup"><span data-stu-id="754cb-124">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>](deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 <span data-ttu-id="754cb-125">Beschreibt die relationale Struktur bzw. das Schema eines <xref:System.Data.DataSet>, das aus einem XML-Schema erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="754cb-125">Describes the relational structure, or schema, of a <xref:System.Data.DataSet> that is created from XML Schema.</span></span>  
  
 [<span data-ttu-id="754cb-126">Ableiten einer relationalen DataSet-Struktur aus einem XML-Schema</span><span class="sxs-lookup"><span data-stu-id="754cb-126">Inferring DataSet Relational Structure from XML</span></span>](inferring-dataset-relational-structure-from-xml.md)  
 <span data-ttu-id="754cb-127">Beschreibt die resultierende relationale Struktur bzw. das Schema eines <xref:System.Data.DataSet>, das beim Herleiten aus XML-Elementen erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="754cb-127">Describes the resulting relational structure, or schema, of a <xref:System.Data.DataSet> that is created when inferred from XML elements.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="754cb-128">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="754cb-128">Related Sections</span></span>  

 [<span data-ttu-id="754cb-129">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="754cb-129">ADO.NET Overview</span></span>](../ado-net-overview.md)  
 <span data-ttu-id="754cb-130">Beschreibt die ADO.NET-Architektur und -Komponenten und wie diese dazu verwendet werden, auf vorhandene Datenquellen zuzugreifen sowie Anwendungsdaten zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="754cb-130">Describes the ADO.NET architecture and components, and how to use them to access existing data sources as well as to manage application data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="754cb-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="754cb-131">See also</span></span>

- [<span data-ttu-id="754cb-132">"DataSets", "DataTables" und "DataViews"</span><span class="sxs-lookup"><span data-stu-id="754cb-132">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="754cb-133">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="754cb-133">ADO.NET Overview</span></span>](../ado-net-overview.md)
