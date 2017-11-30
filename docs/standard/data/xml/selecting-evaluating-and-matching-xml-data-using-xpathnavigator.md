---
title: "Auswählen, Auswerten und Zuordnen von XML-Daten mithilfe von XPathNavigator"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 46e059f8-4dc8-4185-9236-784be95228ed
caps.latest.revision: "2"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 7a86fb36d367342ea0c5bc4968bdd5744bd0524e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="selecting-evaluating-and-matching-xml-data-using-xpathnavigator"></a><span data-ttu-id="60661-102">Auswählen, Auswerten und Zuordnen von XML-Daten mithilfe von XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="60661-102">Selecting, Evaluating and Matching XML Data using XPathNavigator</span></span>
<span data-ttu-id="60661-103">Die <xref:System.Xml.XPath.XPathNavigator>-Klasse stellt Methoden zum Auswählen von Knoten in einem <xref:System.Xml.XPath.XPathDocument>-Objekt oder einem <xref:System.Xml.XmlDocument>-Objekt mithilfe einer XPath-Abfrage, zum Auswerten und Überprüfen der Ergebnisse eines XPath-Ausdrucks sowie zum Bestimmen, ob ein Knoten in einem <xref:System.Xml.XPath.XPathDocument>-Objekt oder einem <xref:System.Xml.XmlDocument>-Objekt mit einem angegebenen XPath-Ausdruck übereinstimmt, bereit.</span><span class="sxs-lookup"><span data-stu-id="60661-103">The <xref:System.Xml.XPath.XPathNavigator> class provides methods to select nodes in an <xref:System.Xml.XPath.XPathDocument> or <xref:System.Xml.XmlDocument> object using an XPath query, evaluate and examine the results of an XPath expression, and determine if a node in an <xref:System.Xml.XPath.XPathDocument> or <xref:System.Xml.XmlDocument> object matches a given XPath expression.</span></span> <span data-ttu-id="60661-104">Diese und andere Konzepte, die mit dem Auswählen, Auswerten und Zuordnen von Knoten in einem <xref:System.Xml.XPath.XPathDocument>-Objekt oder einem <xref:System.Xml.XmlDocument>-Objekt verbunden sind, werden in den folgenden Themen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="60661-104">These and other concepts that relate to selecting, evaluating and matching nodes in an <xref:System.Xml.XPath.XPathDocument> or <xref:System.Xml.XmlDocument> object are described in the following topics.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="60661-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="60661-105">In This Section</span></span>  
 [<span data-ttu-id="60661-106">Wählen Sie die XML-Daten mit "XPathNavigator"</span><span class="sxs-lookup"><span data-stu-id="60661-106">Select XML Data Using XPathNavigator</span></span>](../../../../docs/standard/data/xml/select-xml-data-using-xpathnavigator.md)  
 <span data-ttu-id="60661-107">Beschreibt eine Gruppe von Methoden der <xref:System.Xml.XPath.XPathNavigator>-Klasse, mit denen eine Gruppe von Knoten in einem <xref:System.Xml.XPath.XPathDocument>-Objekt oder einem <xref:System.Xml.XmlDocument>-Objekt mithilfe eines XPath-Ausdrucks ausgewählt werden kann.</span><span class="sxs-lookup"><span data-stu-id="60661-107">Describes the set of <xref:System.Xml.XPath.XPathNavigator> class methods used to select a set of nodes in an <xref:System.Xml.XPath.XPathDocument> or <xref:System.Xml.XmlDocument> object using an XPath expression.</span></span>  
  
 [<span data-ttu-id="60661-108">Auswerten von XPath-Ausdrücken mit "XPathNavigator"</span><span class="sxs-lookup"><span data-stu-id="60661-108">Evaluate XPath Expressions using XPathNavigator</span></span>](../../../../docs/standard/data/xml/evaluate-xpath-expressions-using-xpathnavigator.md)  
 <span data-ttu-id="60661-109">Beschreibt die <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A>-Methode der <xref:System.Xml.XPath.XPathNavigator>-Klasse, die zum Auswerten eines XPath-Ausdrucks verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="60661-109">Describes the <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A> method of the <xref:System.Xml.XPath.XPathNavigator> class used to evaluate an XPath expression.</span></span>  
  
 [<span data-ttu-id="60661-110">Vergleich von Knoten mit "XPathNavigator"</span><span class="sxs-lookup"><span data-stu-id="60661-110">Matching Nodes using XPathNavigator</span></span>](../../../../docs/standard/data/xml/matching-nodes-using-xpathnavigator.md)  
 <span data-ttu-id="60661-111">Beschreibt die <xref:System.Xml.XPath.XPathNavigator.Matches%2A>-Methode der <xref:System.Xml.XPath.XPathNavigator>-Klasse, mit der bestimmt wird, ob ein Knoten mit einem XPath-Ausdruck übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="60661-111">Describes the <xref:System.Xml.XPath.XPathNavigator.Matches%2A> method of the <xref:System.Xml.XPath.XPathNavigator> class used to determine if a node matches an XPath expression.</span></span>  
  
 [<span data-ttu-id="60661-112">In XPath-Abfragen erkannte Knotentypen</span><span class="sxs-lookup"><span data-stu-id="60661-112">Node Types Recognized with XPath Queries</span></span>](../../../../docs/standard/data/xml/node-types-recognized-with-xpath-queries.md)  
 <span data-ttu-id="60661-113">Beschreibt die Knotentypen, die bei einer XPath-Abfrage erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="60661-113">Describes the types of nodes recognized in an XPath query.</span></span>  
  
 [<span data-ttu-id="60661-114">XPath-Abfragen und Namespaces</span><span class="sxs-lookup"><span data-stu-id="60661-114">XPath Queries and Namespaces</span></span>](../../../../docs/standard/data/xml/xpath-queries-and-namespaces.md)  
 <span data-ttu-id="60661-115">Beschreibt die Verwendung von Namespaces in einer XPath-Abfrage.</span><span class="sxs-lookup"><span data-stu-id="60661-115">Describes the use of namespaces in an XPath query.</span></span>  
  
 [<span data-ttu-id="60661-116">Kompilierte XPath-Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="60661-116">Compiled XPath Expressions</span></span>](../../../../docs/standard/data/xml/compiled-xpath-expressions.md)  
 <span data-ttu-id="60661-117">Beschreibt die <xref:System.Xml.XPath.XPathExpression>-Klasse, die eine kompilierte XPath-Abfrage darstellt.</span><span class="sxs-lookup"><span data-stu-id="60661-117">Describes the <xref:System.Xml.XPath.XPathExpression> class that represents a compiled XPath query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60661-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="60661-118">See Also</span></span>  
 <xref:System.Xml.XmlDocument>  
 <xref:System.Xml.XPath.XPathDocument>  
 <xref:System.Xml.XPath.XPathNavigator>  
 [<span data-ttu-id="60661-119">Verarbeiten von XML-Daten mithilfe des XPath-Datenmodells</span><span class="sxs-lookup"><span data-stu-id="60661-119">Process XML Data Using the XPath Data Model</span></span>](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)  
 [<span data-ttu-id="60661-120">Lesen von XML-Daten mithilfe von XPathDocument und XmlDocument</span><span class="sxs-lookup"><span data-stu-id="60661-120">Reading XML Data using XPathDocument and XmlDocument</span></span>](../../../../docs/standard/data/xml/reading-xml-data-using-xpathdocument-and-xmldocument.md)  
 [<span data-ttu-id="60661-121">Zugreifen auf XML-Daten mit "XPathNavigator"</span><span class="sxs-lookup"><span data-stu-id="60661-121">Accessing XML Data using XPathNavigator</span></span>](../../../../docs/standard/data/xml/accessing-xml-data-using-xpathnavigator.md)  
 [<span data-ttu-id="60661-122">Bearbeiten von XML-Daten mit "XPathNavigator"</span><span class="sxs-lookup"><span data-stu-id="60661-122">Editing XML Data using XPathNavigator</span></span>](../../../../docs/standard/data/xml/editing-xml-data-using-xpathnavigator.md)  
 [<span data-ttu-id="60661-123">Schema-Validierung mit "XPathNavigator"</span><span class="sxs-lookup"><span data-stu-id="60661-123">Schema Validation using XPathNavigator</span></span>](../../../../docs/standard/data/xml/schema-validation-using-xpathnavigator.md)
