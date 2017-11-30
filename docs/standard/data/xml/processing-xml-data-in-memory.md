---
title: Verarbeiten von XML-Daten im Arbeitsspeicher
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1bbb4d05-ead7-4bda-8ece-f86d35c57ad4
caps.latest.revision: "2"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ec4ccbff095071b279e07cee6a1aab3ca830423f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="processing-xml-data-in-memory"></a><span data-ttu-id="239bb-102">Verarbeiten von XML-Daten im Arbeitsspeicher</span><span class="sxs-lookup"><span data-stu-id="239bb-102">Processing XML Data In-Memory</span></span>
<span data-ttu-id="239bb-103">Microsoft .NET Framework enthält drei Modelle für die Verarbeitung von XML-Daten: die <xref:System.Xml.XmlDocument> -Klasse, die <xref:System.Xml.XPath.XPathDocument> -Klasse, und [LINQ to XML](http://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13).</span><span class="sxs-lookup"><span data-stu-id="239bb-103">The Microsoft .NET Framework includes three models for processing XML data: the <xref:System.Xml.XmlDocument> class, the <xref:System.Xml.XPath.XPathDocument> class, and [LINQ to XML](http://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13).</span></span>  
  
 <span data-ttu-id="239bb-104">Die <xref:System.Xml.XmlDocument>-Klasse implementiert die W3C-Empfehlungen "Document Object Model Level 1" und "Document Object Model (DOM) Level 2 Core Specification".</span><span class="sxs-lookup"><span data-stu-id="239bb-104">The <xref:System.Xml.XmlDocument> class implements the W3C document object model (DOM) level 1 core and the core DOM level 2 recommendations.</span></span> <span data-ttu-id="239bb-105">DOM ist eine Strukturdarstellung eines XML-Dokuments im Arbeitsspeicher (Cache).</span><span class="sxs-lookup"><span data-stu-id="239bb-105">The DOM is an in-memory (cache) tree representation of an XML document.</span></span> <span data-ttu-id="239bb-106">Mit dem <xref:System.Xml.XmlDocument> und seinen verwandten Klassen können Sie XML-Dokumente erstellen, Daten laden und auf diese zugreifen, Daten ändern und Änderungen speichern.</span><span class="sxs-lookup"><span data-stu-id="239bb-106">With the <xref:System.Xml.XmlDocument> and its related classes, you can construct XML documents, load and access data, modify data, and save changes.</span></span>  
  
 <span data-ttu-id="239bb-107">Die <xref:System.Xml.XPath.XPathDocument>-Klasse ist ein schreibgeschützter Datenspeicher im Arbeitsspeicher, der auf dem XPath-Datenmodell basiert.</span><span class="sxs-lookup"><span data-stu-id="239bb-107">The <xref:System.Xml.XPath.XPathDocument> class is a read-only, in-memory data store that is based on the XPath data model.</span></span> <span data-ttu-id="239bb-108">Die <xref:System.Xml.XPath.XPathNavigator>-Klasse bietet Optionen zur Bearbeitung und zum Navigieren mit einem Cursormodell in XML-Dokumenten, die in der schreibgeschützten <xref:System.Xml.XPath.XPathDocument>-Klasse oder in der <xref:System.Xml.XmlDocument>-Klasse enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="239bb-108">The <xref:System.Xml.XPath.XPathNavigator> class offers several editing options and navigation capabilities using a cursor model over XML documents contained in the read-only <xref:System.Xml.XPath.XPathDocument> class as well as the <xref:System.Xml.XmlDocument> class.</span></span>  
  
 <span data-ttu-id="239bb-109">[LINQ to XML](http://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13) ist das neue Modell in .NET Framework 3.5 zum Verarbeiten von XML-Daten.</span><span class="sxs-lookup"><span data-stu-id="239bb-109">[LINQ to XML](http://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13) is the new model in the .NET Framework version 3.5 for processing XML data.</span></span> <span data-ttu-id="239bb-110">Es ist ein in-Memory-Modell, die nutzt [LINQ (Language-Integrated Query)](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d).</span><span class="sxs-lookup"><span data-stu-id="239bb-110">It is an in-memory model that leverages [LINQ (Language-Integrated Query)](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d).</span></span> <span data-ttu-id="239bb-111">LINQ erweitert die Sprachsyntax von C# und Visual Basic um neue Abfragefunktionen.</span><span class="sxs-lookup"><span data-stu-id="239bb-111">LINQ extends the language syntax of C# and Visual Basic to provide new query capabilities.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="239bb-112">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="239bb-112">In This Section</span></span>  
 [<span data-ttu-id="239bb-113">Verarbeiten von XML-Daten mithilfe des DOM</span><span class="sxs-lookup"><span data-stu-id="239bb-113">Process XML Data Using the DOM Model</span></span>](../../../../docs/standard/data/xml/process-xml-data-using-the-dom-model.md)  
 <span data-ttu-id="239bb-114">Erläutert die Verwendung des <xref:System.Xml.XmlDocument> und seiner verwandten Klassen zur Verarbeitung von XML-Daten.</span><span class="sxs-lookup"><span data-stu-id="239bb-114">Discusses using the <xref:System.Xml.XmlDocument>, and its related classes to process XML data.</span></span>  
  
 [<span data-ttu-id="239bb-115">Verarbeiten von XML-Daten mithilfe des XPath-Datenmodells</span><span class="sxs-lookup"><span data-stu-id="239bb-115">Process XML Data Using the XPath Data Model</span></span>](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)  
 <span data-ttu-id="239bb-116">Erläutert die Verwendung der Klassen <xref:System.Xml.XPath.XPathDocument>, <xref:System.Xml.XmlDocument> und <xref:System.Xml.XPath.XPathNavigator> zur Verarbeitung von XML-Daten.</span><span class="sxs-lookup"><span data-stu-id="239bb-116">Discusses using the <xref:System.Xml.XPath.XPathDocument>, <xref:System.Xml.XmlDocument>, and <xref:System.Xml.XPath.XPathNavigator> classes to process XML data.</span></span>  
  
 [<span data-ttu-id="239bb-117">Verarbeiten von XML-Daten mithilfe von LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="239bb-117">Process XML Data Using LINQ to XML</span></span>](../../../../docs/standard/data/xml/process-xml-data-using-linq-to-xml.md)  
 <span data-ttu-id="239bb-118">Enthält eine kurze Übersicht über LINQ to XML sowie Links zur LINQ to XML-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="239bb-118">Provides a brief overview of LINQ to XML and provides links to the LINQ to XML documentation.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="239bb-119">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="239bb-119">Related Sections</span></span>  
 [<span data-ttu-id="239bb-120">XML-Dokumente und -Daten</span><span class="sxs-lookup"><span data-stu-id="239bb-120">XML Documents and Data</span></span>](../../../../docs/standard/data/xml/index.md)
