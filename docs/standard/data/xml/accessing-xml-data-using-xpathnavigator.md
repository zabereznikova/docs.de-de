---
title: Zugreifen auf XML-Daten mit XPathNavigator
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c57b46e6-5c77-408f-bc4e-67a5dcc9cc05
caps.latest.revision: "2"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 27f5bccc2ab5f229e8b726b3bff18ea7a590f5c0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="accessing-xml-data-using-xpathnavigator"></a><span data-ttu-id="b5aa2-102">Zugreifen auf XML-Daten mit XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="b5aa2-102">Accessing XML Data using XPathNavigator</span></span>
<span data-ttu-id="b5aa2-103">Die <xref:System.Xml.XPath.XPathNavigator>-Klasse stellt Methoden für das Durchsuchen von Knoten, das Extrahieren von XML-Daten und das Zugreifen auf stark typisierte XML-Daten in einem <xref:System.Xml.XPath.XPathDocument>-Objekt oder einem <xref:System.Xml.XmlDocument>-Objekt bereit.</span><span class="sxs-lookup"><span data-stu-id="b5aa2-103">The <xref:System.Xml.XPath.XPathNavigator> class provides methods to navigate nodes, extract XML data and access strongly typed XML data in an <xref:System.Xml.XPath.XPathDocument> or <xref:System.Xml.XmlDocument> object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b5aa2-104">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="b5aa2-104">In This Section</span></span>  
 [<span data-ttu-id="b5aa2-105">In Knotengruppen mit "XPathNavigator"</span><span class="sxs-lookup"><span data-stu-id="b5aa2-105">Node Set Navigation Using XPathNavigator</span></span>](../../../../docs/standard/data/xml/node-set-navigation-using-xpathnavigator.md)  
 <span data-ttu-id="b5aa2-106">Beschreibt die Knotensatz-Navigationsmethoden der <xref:System.Xml.XPath.XPathNavigator>-Klasse, mit denen Knoten in einem <xref:System.Xml.XPath.XPathDocument>-Objekt oder einem <xref:System.Xml.XmlDocument>-Objekt durchsucht werden.</span><span class="sxs-lookup"><span data-stu-id="b5aa2-106">Describes the node set navigation methods of the <xref:System.Xml.XPath.XPathNavigator> class used to navigate nodes in an <xref:System.Xml.XPath.XPathDocument> or <xref:System.Xml.XmlDocument> object.</span></span>  
  
 [<span data-ttu-id="b5aa2-107">Attribut und Namespace-Knoten Navigation mit "XPathNavigator"</span><span class="sxs-lookup"><span data-stu-id="b5aa2-107">Attribute and Namespace Node Navigation Using XPathNavigator</span></span>](../../../../docs/standard/data/xml/attribute-and-namespace-node-navigation-using-xpathnavigator.md)  
 <span data-ttu-id="b5aa2-108">Beschreibt die Navigationsmethoden für Attribut- und Namespaceknoten der <xref:System.Xml.XPath.XPathNavigator>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="b5aa2-108">Describes the attribute and namespace node navigation methods of the <xref:System.Xml.XPath.XPathNavigator> class.</span></span>  
  
 [<span data-ttu-id="b5aa2-109">Extrahieren von XML-Daten mit "XPathNavigator"</span><span class="sxs-lookup"><span data-stu-id="b5aa2-109">Extract XML Data Using XPathNavigator</span></span>](../../../../docs/standard/data/xml/extract-xml-data-using-xpathnavigator.md)  
 <span data-ttu-id="b5aa2-110">Beschreibt die verschiedenen Methoden zum Extrahieren von XML-Daten aus einem <xref:System.Xml.XPath.XPathDocument>-Objekt oder einem <xref:System.Xml.XmlDocument>-Objekt.</span><span class="sxs-lookup"><span data-stu-id="b5aa2-110">Describes the various methods of extracting XML data from an <xref:System.Xml.XPath.XPathDocument> or <xref:System.Xml.XmlDocument> object.</span></span>  
  
 [<span data-ttu-id="b5aa2-111">Zugreifen auf streng typisierte XML-Daten mit "XPathNavigator"</span><span class="sxs-lookup"><span data-stu-id="b5aa2-111">Accessing Strongly Typed XML Data Using XPathNavigator</span></span>](../../../../docs/standard/data/xml/accessing-strongly-typed-xml-data-using-xpathnavigator.md)  
 <span data-ttu-id="b5aa2-112">Beschreibt das Zugreifen auf stark typisierte XML-Daten in einem <xref:System.Xml.XPath.XPathDocument>-Objekt oder einem <xref:System.Xml.XmlDocument>-Objekt mithilfe der <xref:System.Xml.XPath.XPathNavigator>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="b5aa2-112">Describes accessing strongly-typed XML data in an <xref:System.Xml.XPath.XPathDocument> or <xref:System.Xml.XmlDocument> object using the <xref:System.Xml.XPath.XPathNavigator> class.</span></span>  
  
 [<span data-ttu-id="b5aa2-113">Benutzerdefinierte Funktionen und Variablen</span><span class="sxs-lookup"><span data-stu-id="b5aa2-113">User Defined Functions and Variables</span></span>](../../../../docs/standard/data/xml/user-defined-functions-and-variables.md)  
 <span data-ttu-id="b5aa2-114">Beschreibt das Implementieren einer benutzerdefinierten <xref:System.Xml.Xsl.XsltContext>-Klasse mit den Schnittstellen <xref:System.Xml.Xsl.IXsltContextFunction> und <xref:System.Xml.Xsl.IXsltContextVariable>, die Erweiterungsfunktionen und -variablen unterstützen.</span><span class="sxs-lookup"><span data-stu-id="b5aa2-114">Describes implementing a custom <xref:System.Xml.Xsl.XsltContext> class along with the interfaces <xref:System.Xml.Xsl.IXsltContextFunction> and <xref:System.Xml.Xsl.IXsltContextVariable> that support extension functions and variables.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5aa2-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b5aa2-115">See Also</span></span>  
 <xref:System.Xml.XmlDocument>  
 <xref:System.Xml.XPath.XPathDocument>  
 <xref:System.Xml.XPath.XPathNavigator>  
 [<span data-ttu-id="b5aa2-116">Verarbeiten von XML-Daten mithilfe des XPath-Datenmodells</span><span class="sxs-lookup"><span data-stu-id="b5aa2-116">Process XML Data Using the XPath Data Model</span></span>](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)  
 [<span data-ttu-id="b5aa2-117">Lesen von XML-Daten mithilfe von XPathDocument und XmlDocument</span><span class="sxs-lookup"><span data-stu-id="b5aa2-117">Reading XML Data using XPathDocument and XmlDocument</span></span>](../../../../docs/standard/data/xml/reading-xml-data-using-xpathdocument-and-xmldocument.md)  
 [<span data-ttu-id="b5aa2-118">Auswählen, auswerten und Zuordnen von XML-Daten mit "XPathNavigator"</span><span class="sxs-lookup"><span data-stu-id="b5aa2-118">Selecting, Evaluating and Matching XML Data using XPathNavigator</span></span>](../../../../docs/standard/data/xml/selecting-evaluating-and-matching-xml-data-using-xpathnavigator.md)  
 [<span data-ttu-id="b5aa2-119">Bearbeiten von XML-Daten mit "XPathNavigator"</span><span class="sxs-lookup"><span data-stu-id="b5aa2-119">Editing XML Data using XPathNavigator</span></span>](../../../../docs/standard/data/xml/editing-xml-data-using-xpathnavigator.md)  
 [<span data-ttu-id="b5aa2-120">Schema-Validierung mit "XPathNavigator"</span><span class="sxs-lookup"><span data-stu-id="b5aa2-120">Schema Validation using XPathNavigator</span></span>](../../../../docs/standard/data/xml/schema-validation-using-xpathnavigator.md)
