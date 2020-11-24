---
title: Auswählen, Auswerten und Zuordnen von XML-Daten mithilfe von XPathNavigator
ms.date: 03/30/2017
ms.assetid: 46e059f8-4dc8-4185-9236-784be95228ed
ms.openlocfilehash: 249b99a627f3bbcc1723f104a80cb61552404877
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94822463"
---
# <a name="selecting-evaluating-and-matching-xml-data-using-xpathnavigator"></a><span data-ttu-id="91e77-102">Auswählen, Auswerten und Zuordnen von XML-Daten mithilfe von XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="91e77-102">Selecting, Evaluating and Matching XML Data using XPathNavigator</span></span>
<span data-ttu-id="91e77-103">Die <xref:System.Xml.XPath.XPathNavigator>-Klasse stellt Methoden bereit, die dazu dienen, Knoten in einem <xref:System.Xml.XPath.XPathDocument>- oder einem <xref:System.Xml.XmlDocument>-Objekt mithilfe einer XPath-Abfrage auszuwählen, die Ergebnisse eines XPath-Ausdrucks auszuwerten und zu überprüfen sowie dazu zu bestimmen, ob ein Knoten in einem <xref:System.Xml.XPath.XPathDocument>- oder einem <xref:System.Xml.XmlDocument>-Objekt mit einem angegebenen XPath-Ausdruck übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="91e77-103">The <xref:System.Xml.XPath.XPathNavigator> class provides methods to select nodes in an <xref:System.Xml.XPath.XPathDocument> or <xref:System.Xml.XmlDocument> object using an XPath query, evaluate and examine the results of an XPath expression, and determine if a node in an <xref:System.Xml.XPath.XPathDocument> or <xref:System.Xml.XmlDocument> object matches a given XPath expression.</span></span> <span data-ttu-id="91e77-104">Diese und andere Konzepte, die mit dem Auswählen, Auswerten und Zuordnen von Knoten in einem <xref:System.Xml.XPath.XPathDocument>-Objekt oder einem <xref:System.Xml.XmlDocument>-Objekt verbunden sind, werden in den folgenden Themen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="91e77-104">These and other concepts that relate to selecting, evaluating and matching nodes in an <xref:System.Xml.XPath.XPathDocument> or <xref:System.Xml.XmlDocument> object are described in the following topics.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="91e77-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="91e77-105">In This Section</span></span>  
 [<span data-ttu-id="91e77-106">Auswählen von XML-Daten mit XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="91e77-106">Select XML Data Using XPathNavigator</span></span>](select-xml-data-using-xpathnavigator.md)  
 <span data-ttu-id="91e77-107">Beschreibt eine Gruppe von Methoden der <xref:System.Xml.XPath.XPathNavigator>-Klasse, mit denen eine Gruppe von Knoten in einem <xref:System.Xml.XPath.XPathDocument>-Objekt oder einem <xref:System.Xml.XmlDocument>-Objekt mithilfe eines XPath-Ausdrucks ausgewählt werden kann.</span><span class="sxs-lookup"><span data-stu-id="91e77-107">Describes the set of <xref:System.Xml.XPath.XPathNavigator> class methods used to select a set of nodes in an <xref:System.Xml.XPath.XPathDocument> or <xref:System.Xml.XmlDocument> object using an XPath expression.</span></span>  
  
 [<span data-ttu-id="91e77-108">Auswerten von XPath-Ausdrücken mit XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="91e77-108">Evaluate XPath Expressions using XPathNavigator</span></span>](evaluate-xpath-expressions-using-xpathnavigator.md)  
 <span data-ttu-id="91e77-109">Beschreibt die <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A>-Methode der <xref:System.Xml.XPath.XPathNavigator>-Klasse, die zum Auswerten eines XPath-Ausdrucks verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="91e77-109">Describes the <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A> method of the <xref:System.Xml.XPath.XPathNavigator> class used to evaluate an XPath expression.</span></span>  
  
 [<span data-ttu-id="91e77-110">Vergleich von Knoten mit XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="91e77-110">Matching Nodes using XPathNavigator</span></span>](matching-nodes-using-xpathnavigator.md)  
 <span data-ttu-id="91e77-111">Beschreibt die <xref:System.Xml.XPath.XPathNavigator.Matches%2A>-Methode der <xref:System.Xml.XPath.XPathNavigator>-Klasse, mit der bestimmt wird, ob ein Knoten mit einem XPath-Ausdruck übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="91e77-111">Describes the <xref:System.Xml.XPath.XPathNavigator.Matches%2A> method of the <xref:System.Xml.XPath.XPathNavigator> class used to determine if a node matches an XPath expression.</span></span>  
  
 [<span data-ttu-id="91e77-112">In XPath-Abfragen erkannte Knotentypen</span><span class="sxs-lookup"><span data-stu-id="91e77-112">Node Types Recognized with XPath Queries</span></span>](node-types-recognized-with-xpath-queries.md)  
 <span data-ttu-id="91e77-113">Beschreibt die Knotentypen, die bei einer XPath-Abfrage erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="91e77-113">Describes the types of nodes recognized in an XPath query.</span></span>  
  
 [<span data-ttu-id="91e77-114">XPath-Abfragen und Namespaces</span><span class="sxs-lookup"><span data-stu-id="91e77-114">XPath Queries and Namespaces</span></span>](xpath-queries-and-namespaces.md)  
 <span data-ttu-id="91e77-115">Beschreibt die Verwendung von Namespaces in einer XPath-Abfrage.</span><span class="sxs-lookup"><span data-stu-id="91e77-115">Describes the use of namespaces in an XPath query.</span></span>  
  
 [<span data-ttu-id="91e77-116">Kompilierte XPath-Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="91e77-116">Compiled XPath Expressions</span></span>](compiled-xpath-expressions.md)  
 <span data-ttu-id="91e77-117">Beschreibt die <xref:System.Xml.XPath.XPathExpression>-Klasse, die eine kompilierte XPath-Abfrage darstellt.</span><span class="sxs-lookup"><span data-stu-id="91e77-117">Describes the <xref:System.Xml.XPath.XPathExpression> class that represents a compiled XPath query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91e77-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="91e77-118">See also</span></span>

- <xref:System.Xml.XmlDocument>
- <xref:System.Xml.XPath.XPathDocument>
- <xref:System.Xml.XPath.XPathNavigator>
- [<span data-ttu-id="91e77-119">Verarbeiten von XML-Daten mithilfe des XPath-Datenmodells</span><span class="sxs-lookup"><span data-stu-id="91e77-119">Process XML Data Using the XPath Data Model</span></span>](process-xml-data-using-the-xpath-data-model.md)
- [<span data-ttu-id="91e77-120">Lesen von XML-Daten mithilfe von XPathDocument und XmlDocument</span><span class="sxs-lookup"><span data-stu-id="91e77-120">Reading XML Data using XPathDocument and XmlDocument</span></span>](reading-xml-data-using-xpathdocument-and-xmldocument.md)
- [<span data-ttu-id="91e77-121">Zugreifen auf XML-Daten mit XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="91e77-121">Accessing XML Data using XPathNavigator</span></span>](accessing-xml-data-using-xpathnavigator.md)
- [<span data-ttu-id="91e77-122">Bearbeiten von XML-Daten mit XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="91e77-122">Editing XML Data using XPathNavigator</span></span>](editing-xml-data-using-xpathnavigator.md)
- [<span data-ttu-id="91e77-123">Schemavalidierung mithilfe von „XPathNavigator“</span><span class="sxs-lookup"><span data-stu-id="91e77-123">Schema Validation using XPathNavigator</span></span>](schema-validation-using-xpathnavigator.md)
