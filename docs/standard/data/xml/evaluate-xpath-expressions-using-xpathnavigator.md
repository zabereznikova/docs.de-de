---
title: Auswerten von XPath-Ausdrücken mit XPathNavigator
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 2913ccf3-f932-4363-8028-9e2d22ce6093
ms.openlocfilehash: 1a17aea66be7f9d35336434408c49bae8046b7e7
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710907"
---
# <a name="evaluate-xpath-expressions-using-xpathnavigator"></a><span data-ttu-id="7b0ea-102">Auswerten von XPath-Ausdrücken mit XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="7b0ea-102">Evaluate XPath Expressions using XPathNavigator</span></span>
<span data-ttu-id="7b0ea-103">Die <xref:System.Xml.XPath.XPathNavigator>-Klasse stellt die <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A>-Methode bereit, mit der ein XPath-Ausdruck ausgewertet werden kann.</span><span class="sxs-lookup"><span data-stu-id="7b0ea-103">The <xref:System.Xml.XPath.XPathNavigator> class provides the <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A> method to evaluate an XPath expression.</span></span> <span data-ttu-id="7b0ea-104">Die <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A>-Methode verwendet einen XPath-Ausdruck, wertet ihn aus und gibt je nach Ergebnis des XPath-Ausdrucks einen der W3C-XPath-Typen Boolean, Number, String oder Node Set zurück.</span><span class="sxs-lookup"><span data-stu-id="7b0ea-104">The <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A> method takes an XPath expression, evaluates it and returns a W3C XPath type of Boolean, Number, String, or Node Set based on the result of the XPath expression.</span></span>  
  
## <a name="the-evaluate-method"></a><span data-ttu-id="7b0ea-105">Die Evaluate-Methode</span><span class="sxs-lookup"><span data-stu-id="7b0ea-105">The Evaluate Method</span></span>  
 <span data-ttu-id="7b0ea-106">Die <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A>-Methode akzeptiert einen XPath-Ausdruck, wertet ihn aus und gibt ein typisiertes Ergebnis vom Typ Boolean (<xref:System.Boolean>), Number (<xref:System.Double>), String (<xref:System.String>) oder Node Set (<xref:System.Xml.XPath.XPathNodeIterator>) zurück.</span><span class="sxs-lookup"><span data-stu-id="7b0ea-106">The <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A> method takes an XPath expression, evaluates it, and returns a typed result of Boolean (<xref:System.Boolean>), Number (<xref:System.Double>), String (<xref:System.String>), or Node Set (<xref:System.Xml.XPath.XPathNodeIterator>).</span></span> <span data-ttu-id="7b0ea-107">Die <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A>-Methode kann z. B. in einer mathematischen Methode verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7b0ea-107">For example, the <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A> method could be used in a mathematical method.</span></span> <span data-ttu-id="7b0ea-108">Im folgenden Beispielcode wird der Gesamtpreis aller Bücher in der Datei `books.xml` berechnet.</span><span class="sxs-lookup"><span data-stu-id="7b0ea-108">The following example code calculates the total price of all the books in the `books.xml` file.</span></span>  
  
```vb  
Dim document As XPathDocument = New XPathDocument("books.xml")  
Dim navigator As XPathNavigator = document.CreateNavigator()  
  
Dim query As XPathExpression = navigator.Compile("sum(//price/text())")  
Dim total As Double = CType(navigator.Evaluate(query), Double)  
Console.WriteLine(total)  
```  
  
```csharp  
XPathDocument document = new XPathDocument("books.xml");  
XPathNavigator navigator = document.CreateNavigator();  
  
XPathExpression query = navigator.Compile("sum(//price/text())");  
Double total = (Double)navigator.Evaluate(query);  
Console.WriteLine(total);  
```  
  
 <span data-ttu-id="7b0ea-109">In diesem Beispiel wird die Datei `books.xml` als Eingabe verwendet.</span><span class="sxs-lookup"><span data-stu-id="7b0ea-109">The example takes the `books.xml` file as input.</span></span>  
  
 [!code-xml[XPathXMLExamples#1](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/books.xml#1)]  
  
### <a name="position-and-last-functions"></a><span data-ttu-id="7b0ea-110">position-Funktion und last-Funktion</span><span class="sxs-lookup"><span data-stu-id="7b0ea-110">position and last Functions</span></span>  
 <span data-ttu-id="7b0ea-111">Die <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A>-Methode ist überladen.</span><span class="sxs-lookup"><span data-stu-id="7b0ea-111">The <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A> method is overloaded.</span></span> <span data-ttu-id="7b0ea-112">Eine der <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A>-Methoden akzeptiert ein <xref:System.Xml.XPath.XPathNodeIterator>-Objekt als Parameter.</span><span class="sxs-lookup"><span data-stu-id="7b0ea-112">One of the <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A> methods takes an <xref:System.Xml.XPath.XPathNodeIterator> object as a parameter.</span></span> <span data-ttu-id="7b0ea-113">Diese bestimmte <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A>-Methode ist identisch mit der <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A>-Methode, die nur ein <xref:System.Xml.XPath.XPathExpression>-Objekt als Parameter verwendet, außer dass sie ein node-set-Argument zulässt, um den aktuellen Kontext anzugeben, in dem die Auswertung ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="7b0ea-113">This particular <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A> method is identical to the <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A> method that takes only an <xref:System.Xml.XPath.XPathExpression> object as a parameter, except that it allows a node set argument to specify the current context to perform the evaluation on.</span></span> <span data-ttu-id="7b0ea-114">Dieser Kontext ist für die XPath-Funktionen `position()` und `last()` erforderlich, da diese relativ zum aktuellen Kontextknoten sind.</span><span class="sxs-lookup"><span data-stu-id="7b0ea-114">This context is required for the XPath `position()` and `last()` functions as they are relative to the current context node.</span></span> <span data-ttu-id="7b0ea-115">Für die `position()`-Funktion und die `last()`-Funktion ist für die Auswertung ein Verweis auf eine Knotengruppe erforderlich, sofern sie nicht als Prädikat in einem Location-Step verwendet werden, da die `position`-Funktion und die `last`-Funktion andernfalls `0` zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="7b0ea-115">Unless used as a predicate in a location step, the `position()` and `last()` functions require a reference to a node set in order to be evaluated otherwise, the `position` and `last` functions return `0`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b0ea-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7b0ea-116">See also</span></span>

- <xref:System.Xml.XmlDocument>
- <xref:System.Xml.XPath.XPathDocument>
- <xref:System.Xml.XPath.XPathNavigator>
- [<span data-ttu-id="7b0ea-117">Verarbeiten von XML-Daten mithilfe des XPath-Datenmodells</span><span class="sxs-lookup"><span data-stu-id="7b0ea-117">Process XML Data Using the XPath Data Model</span></span>](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)
- [<span data-ttu-id="7b0ea-118">Auswählen von XML-Daten mit XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="7b0ea-118">Select XML Data Using XPathNavigator</span></span>](../../../../docs/standard/data/xml/select-xml-data-using-xpathnavigator.md)
- [<span data-ttu-id="7b0ea-119">Vergleich von Knoten mit XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="7b0ea-119">Matching Nodes using XPathNavigator</span></span>](../../../../docs/standard/data/xml/matching-nodes-using-xpathnavigator.md)
- [<span data-ttu-id="7b0ea-120">In XPath-Abfragen erkannte Knotentypen</span><span class="sxs-lookup"><span data-stu-id="7b0ea-120">Node Types Recognized with XPath Queries</span></span>](../../../../docs/standard/data/xml/node-types-recognized-with-xpath-queries.md)
- [<span data-ttu-id="7b0ea-121">XPath-Abfragen und Namespaces</span><span class="sxs-lookup"><span data-stu-id="7b0ea-121">XPath Queries and Namespaces</span></span>](../../../../docs/standard/data/xml/xpath-queries-and-namespaces.md)
- [<span data-ttu-id="7b0ea-122">Kompilierte XPath-Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="7b0ea-122">Compiled XPath Expressions</span></span>](../../../../docs/standard/data/xml/compiled-xpath-expressions.md)
